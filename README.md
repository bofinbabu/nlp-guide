# A practical guide to Natural Language Processing tasks

Natural Language Processing is a field that studies the interactions between computers and human (natural) languages. Most of the NLP is put into practice using Deep Learning, classical Machine Learning as well as some other less-known AI techniques. Beyond the realm of Artificial Intelligence, the field also takes contributions from Linguistics. 

This guide covers some popular NLP tasks from a practical point of view.

## Content
1. [Stemming & lemmatization](#Stemming-&-lemmatization)
2. [Part-of-Speech Tagging](#part-of-speech-tagging)
3. [Named Enitity Linking](#named-enitity-linking)
4. [Named Entity Recognition](#named-entity-recognition)
5. [Semantic Role Labeling](#semantic-role-labeling)
6. [Coreference Resolution](#coreference-resolution)
7. [Automatic Text Summarization](#automatic-text-summarization)

## Stemming & lemmatization
Stemming is the process of deriving the inflected words to their word stem, base or root form. 
For example, `cats`, `catlike`, `catty` etc are based on the root form `cat`. 
Given below are some more examples of inflected words and their root form.

| Example |            Inflected words            | Root form (output of a stemmer) |
|:-------:|:-------------------------------------:|:-------------------------------:|
|    1    |        fishing, fished, fisher        |               fish              |
|    2    | argue, argued, argues, arguing, argus |               argu              |
|    3    |          argument, arguments          |             argument            |
|    4    |   stems, stemmer, stemming, stemmed   |               stem              |

From example 2 and 3, it’s clear that the stem itself is not a word or root.

While stemming is crude heuristic process that chops off the ends of words to derive the word stem, it includes the removal of derivational affixes most of the time. Lemmatization does this job in a proper way with vocabulary and morphological analysis of words aiming to remove inflectional endings and to return the dictionary form of a word, which is known as the lemma.

For example the stemming might return `s` for the token `saw` which not a dictionary word. Lemmatization on the other hand would return either `see` or `saw` depending on whether the token was used as a verb or a noun.

### Reading
1. Jurafsky, [Speech and Language Processing - Chapter 2](https://web.stanford.edu/~jurafsky/slp3/2.pdf), Section 3.4: Lemmatization and Stemming.
2. [The Porter Stemming Algorithm](snowball.tartarus.org/algorithms/porter/stemmer.html)
3. [Stemming and lemmatization](https://nlp.stanford.edu/IR-book/html/htmledition/stemming-and-lemmatization-1.html) - IR-Book, Stanford

## Part-of-Speech Tagging
Part-of-speech (POS) tagging is the process of classifying words in to their part of speech (lexical items). 

For example, here are the part of speeches for the sentence: 
`"And now for something completely different"`

|    Word    | Part-of-speech |
|:----------:|:--------------:|
|     And    |       CC       |
|     now    |       RB       |
|     for    |       IN       |
|  something |       NN       |
| completely |       RB       |
|  different |       JJ       |

Where CC (Coordinating conjunction), RB (Adverb), NN(Noun) etc are [POS tags](https://cs.nyu.edu/grishman/jet/guide/PennPOS.html).

### Reading
1. [Optional] Jurafsky, [Speech and Language Processing - Chapter 11](https://web.stanford.edu/~jurafsky/slp3/11.pdf) - Formal Grammars of English
2. Jurafsky, [Speech and Language Processing - Chapter 10](https://web.stanford.edu/~jurafsky/slp3/10.pdf) - Part-of-Speech Tagging
3. Natural Language Processing with Python, [Chapter 5](http://www.nltk.org/book/ch05.html)

### Datasets
1. [CoNLL-2000 chunking dataset](https://www.clips.uantwerpen.be/conll2000/chunking/)
2. [EmpiriST 2015 dataset](https://sites.google.com/site/empirist2015/home/shared-task-data)

## Named Enitity Linking
Named Entity Linking, also known as Named Entity Disambiguation is the task of detetermining the identies mentioend in text. For example in the sentence `"Michael Jordan and his Machine Learning research team wants to put smarter A.I. in your home"`, the idea is to determine "Michael Jordan" refers to the Artificial Intelligence reseacher Michael I. Jordan, not to the basketball player Michael Jordan or any other entity that could be referred with same title.

### Reading
1. [Using encyclopedic knowledge for named entity disambiguation](http://www.aclweb.org/anthology/E06-1002)
2. [Discovering Types for Entity Disambiguation
](https://blog.openai.com/discovering-types-for-entity-disambiguation) - OpenAI

### Datasets
1. Dataset from the [OKE Challenge](https://github.com/anuzzolese/oke-challenge-2016)
2. [WES2015 dataset](https://github.com/dbpedia-spotlight/evaluation-datasets)
3. [Micropost datasets](http://ikt.ui.sav.sk/microposts/)

## Named Entity Recognition
Named Entity Recognition (NER) is the process of labelling named-entities in a text. 
Named entities are real world objects such as persons, locations, organisations etc, that can be denoted with a proper name.

For example here is the [Stanford-NER](https://nlp.stanford.edu/software/CRF-NER.html) result for the sentence: `“Khan Academy is a Mountain View based non-profit educational organization created by educator Salman Khan.”`

> ORGANIZATION: Khan Academy,
> LOCATION: Mountain View,
> PERSON: Salman Khan

### Reading
1.  [Neural architectures for named entity recognition](https://arxiv.org/pdf/1603.01360.pdf).

### Datasets
1. [Annotated Corpus for Named Entity Recognition: Corpus (CoNLL 2002)](https://www.kaggle.com/abhinavwalia95/entity-annotated-corpus)
2. [N3 - A collection of datasets for NER](https://github.com/dice-group/n3-collection)
3. [Annotated Corpus for Named Entity Recognition](https://www.kaggle.com/velavok/nercorpus) by Anton Dmitriev
4. [The Groningen Meaning Bank (GMB)](http://gmb.let.rug.nl/)
5. Dataset from the [OKE Challenge 2016](https://github.com/anuzzolese/oke-challenge-2016)


## Semantic Role Labeling

Semantic Role Labelling (SRL) is the process of assigning labels to words or phrases in a sentence that shows their semantic role in that sentence. `agent`, `goal`,  `result` etc are examples of some semantic roles.

For example, in the sentence `"Mary sold the book to John”`, the task `to sell` represents the predicate, `Mary` represents 
the seller (agent), `the book` represents the goods (theme), and `John` represents the recipient.

### Reading
1. [Optional] Jurafsky, [Speech and Language Processing - Chapter 11](https://web.stanford.edu/~jurafsky/slp3/11.pdf) - Formal Grammars of English
2. Jurafsky, [Speech and Language Processing - Chapter 22](https://web.stanford.edu/~jurafsky/slp3/22.pdf) - Semantic Role Labeling
3. [CoNLL-2005 Shared Task: Semantic Role Labeling - Description & Goal](www.lsi.upc.es/~srlconll/spec.html)

### Datasets
1. [FrameNet](https://framenet.icsi.berkeley.edu/fndrupal/)
2. [The Proposition Bank](https://propbank.github.io/)

## Coreference Resolution

Coreference, as the name suggests is a case where a same person or a thing get refers multiple times in a text. 
Coreference Resolution is the task of finding all such expressions that refer to the same entity in a text.

For example in the sentence `“Bill said he would come”`, the proper noun `Bill` and the noun `he` refers to the 
same person, namely to Bill.

### Reading
1. [Introduction to Coreference Resolution](http://www-labs.iro.umontreal.ca/~felipe/IFT6010-Hiver2015/Presentations/Abbas-Coreference.pdf)
2. [Coreference Resolution with World Knowledge](http://www.aclweb.org/anthology/P11-1082)

## Automatic Text Summarization
Automatic text summarization is the process of automatically condensing a text document into a shorter 
version. It is usually achieved by one of the below two approaches,
1. Extractive summarization: The summary is created by selecting a subset of passages from the text and arranging them in a meaningful order.
2. Abstractive summarization: The summary is generated using natural language generation techniques, applied on the given text.

### Reading
1. [Text Summarization in Python: Extractive vs. Abstractive techniques revisited](https://rare-technologies.com/text-summarization-in-python-extractive-vs-abstractive-techniques-revisited/)
2. [Text Summarization Techniques: A Brief Survey](https://arxiv.org/pdf/1707.02268.pdf)
3. [Taming Recurrent Neural Networks for Better Summarization](www.abigailsee.com/2017/04/16/taming-rnns-for-better-summarization.html)

### Datasets
1. [The CNN / Daily Mail dataset](https://github.com/abisee/cnn-dailymail)

---

## TODO (draft)
- ~~Include lemmatization with stemming ~~
- ~~ Add Named Entity Disambiguation ~~
- Add Text Similarity
- Add Sentiment Analysis
- Add a header image
- Better intro
- Add a license
- Add references
- Add Software/Tools section

