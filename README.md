# clausiepy
Implementation of the ClausIE information extraction system for python+spacy

## Credits
While this is a re-implementation by me, original research work (and also the dictionaries) is attributed to Luciano Del Corro
and Rainer Gemulla. If you use it in your code please note that there are slight modifications in the code in order to make it work with the spacy dependency parser, and also cite:
```
Del Corro Luciano, and Rainer Gemulla. "Clausie: clause-based open information extraction." Proceedings of the 22nd international conference on World Wide Web. ACM, 2013.
```
## Requirements
`spacy>=2.0.0`

## Installation
```
$ git clone https://github.com/mmxgn/clausiepy.git
$ cd clausiepy
$ python3 setup.py build 
$ python3 setup.py install [--user]
```

## Usage

```
$ ipython3

In [1]: import clausiepy as clausie
In [2]: clauses = clausie.clausie('Albert Einstein died in Princeton in 1955.')
In [3]: clauses
Out[3]: 
[{'S': [Einstein],
  'V': [died],
  'O': [],
  'IO': [],
  'XCOMP': [],
  'C': [],
  'type': 'SV',
  'A?': [in, in]}]
In [4]: propositions = clausie.extract_propositions(clauses)
In [5]: clausie.print_propositions(propositions)
Out [5]:
([Einstein], [died], [], [], [], [])
([Einstein], [died], [], [], [], [in, Princeton])
([Einstein], [died], [], [], [], [in, 1921])
```
Note that `clausie`, and `extract_propositions` here return dictionaries and lists of `spacy` span objects which you
can subsequently use however you like.

## License

This code is licensed under the [Creative Commons Attribution-ShareAlike 3.0 Unported License](https://creativecommons.org/licenses/by-sa/3.0/).
