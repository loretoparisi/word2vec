# Word2vec
This fork of the Google Word2Vec repository available [here](https://code.google.com/archive/p/word2vec/) compiles on MacOS X Sierra

## How to build word2vec
To build `word2vec`, `word2phrase`, `word-analogy`, `compute-accuracy`, `distance` binaries

```
$ git clone https://github.com/loretoparisi/word2vec.git
$ cd word2vec
$ ./make
```

To run the word demo example, training the sample corpus `text8` from http://mattmahoney.net/dc/

```
./demo-word.sh
```

To run the phrases demo example, training the monolingual (en) `2012 news` corpus from http://www.statmt.org/wmt14/

```
./demo-phrases.sh
```

NOTE. You can modify this script to training a different language from http://www.statmt.org/wmt14/training-monolingual-news-crawl/

## About
We provide an implementation of the Continuous Bag-of-Words (CBOW) and the Skip-gram model (SG), as well as several demo scripts.

Given a text corpus, the word2vec tool learns a vector for every word in the vocabulary using the Continuous
Bag-of-Words or the Skip-Gram neural network architectures. The user should to specify the following:
 - desired vector dimensionality
 - the size of the context window for either the Skip-Gram or the Continuous Bag-of-Words model
 - training algorithm: hierarchical softmax and / or negative sampling
 - threshold for downsampling the frequent words 
 - number of threads to use
 - the format of the output word vector file (text or binary)




