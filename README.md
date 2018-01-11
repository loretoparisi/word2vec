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

## The questions words
A file of categorized questions that answer the rule

```
Term `X` is to term `Y` as Term `W` is to term `Z`
Example: king – man + women = queen
```

in the following categories

```
: capital-common-countries
: capital-world
: currency
: city-in-state
: family
: gram1-adjective-to-adverb
: gram2-opposite
: gram3-comparative
: gram4-superlative
: gram5-present-participle
: gram6-nationality-adjective
: gram7-past-tense
: gram8-plural
: gram9-plural-verbs
```

that can be obtained with

```
$ cat questions-words.txt | grep -E ":"
```

like the following tuples in

`capital-common-countries`

```
$ cat questions-words.txt | grep -E -A 5 ": capital-common-countries"
: capital-common-countries
Athens Greece Baghdad Iraq
Athens Greece Bangkok Thailand
Athens Greece Beijing China
Athens Greece Berlin Germany
Athens Greece Bern Switzerland
```

`capital-world`

```
$ cat questions-words.txt | grep -E -A 5 ": capital-world"
: capital-world
Abuja Nigeria Accra Ghana
Abuja Nigeria Algiers Algeria
Abuja Nigeria Amman Jordan
Abuja Nigeria Ankara Turkey
Abuja Nigeria Antananarivo Madagascar
```

`currency`

```
$ cat questions-words.txt | grep -E -A 5 ": currency"
: currency
Algeria dinar Angola kwanza
Algeria dinar Argentina peso
Algeria dinar Armenia dram
Algeria dinar Brazil real
Algeria dinar Bulgaria lev
```

`city-in-state`

```
$ cat questions-words.txt | grep -E -A 5 ": city-in-state"
: city-in-state
Chicago Illinois Houston Texas
Chicago Illinois Philadelphia Pennsylvania
Chicago Illinois Phoenix Arizona
Chicago Illinois Dallas Texas
Chicago Illinois Jacksonville Florida
```

`family`

```
$ cat questions-words.txt | grep -E -A 5 ": family"
: family
boy girl brother sister
boy girl brothers sisters
boy girl dad mom
boy girl father mother
boy girl grandfather grandmother
```

`gram1-adjective-to-adverb`

```
$ cat questions-words.txt | grep -E -A 5 ": gram1-adjective-to-adverb"
: gram1-adjective-to-adverb
amazing amazingly apparent apparently
amazing amazingly calm calmly
amazing amazingly cheerful cheerfully
amazing amazingly complete completely
amazing amazingly efficient efficiently
```

`gram2-opposite`

```
$ cat questions-words.txt | grep -E -A 5 ": gram2-opposite"
: gram2-opposite
acceptable unacceptable aware unaware
acceptable unacceptable certain uncertain
acceptable unacceptable clear unclear
acceptable unacceptable comfortable uncomfortable
acceptable unacceptable competitive uncompetitive
```

`gram3-comparative`

```
$ cat questions-words.txt | grep -E -A 5 ": gram3-comparative"
: gram3-comparative
bad worse big bigger
bad worse bright brighter
bad worse cheap cheaper
bad worse cold colder
bad worse cool cooler
```

`gram4-superlative`

```
$ cat questions-words.txt | grep -E -A 5 ": gram4-superlative"
: gram4-superlative
bad worst big biggest
bad worst bright brightest
bad worst cold coldest
bad worst cool coolest
bad worst dark darkest
```

`gram5-present-participle`

```
$ cat questions-words.txt | grep -E -A 5 ": gram5-present-participle"
: gram5-present-participle
code coding dance dancing
code coding debug debugging
code coding decrease decreasing
code coding describe describing
code coding discover discovering
```

`gram6-nationality-adjective`

```
$ cat questions-words.txt | grep -E -A 5 ": gram6-nationality-adjective"
: gram6-nationality-adjective
Albania Albanian Argentina Argentinean
Albania Albanian Australia Australian
Albania Albanian Austria Austrian
Albania Albanian Belarus Belorussian
Albania Albanian Brazil Brazilian
```

`gram7-past-tense`

```
$ cat questions-words.txt | grep -E -A 5 ": gram7-past-tense"
: gram7-past-tense
dancing danced decreasing decreased
dancing danced describing described
dancing danced enhancing enhanced
dancing danced falling fell
dancing danced feeding fed
```

`gram8-plural`

```
$ cat questions-words.txt | grep -E -A 5 ": gram8-plural"
: gram8-plural
banana bananas bird birds
banana bananas bottle bottles
banana bananas building buildings
banana bananas car cars
banana bananas cat cats
```

`gram9-plural-verbs`

```
$ cat questions-words.txt | grep -E -A 5 ": gram9-plural-verbs"
: gram9-plural-verbs
decrease decreases describe describes
decrease decreases eat eats
decrease decreases enhance enhances
decrease decreases estimate estimates
decrease decreases find finds
```



