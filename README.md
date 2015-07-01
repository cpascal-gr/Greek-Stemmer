## GREEK STEMMER

In this thesis work, a stemming system for the Greek language is presented. This Greek Stemmer is developed during the master thesis with title "Corpus Based Methods for Learning Models of Metaphor in Modern Greek" and the phd thesis "Metaphor Detection in greek corpus" in the Institute of Informatics and Telecommunications at NCSR Demokritos. The system takes as input, a word (ignore case) and the Part Of Speech tagging(POS) of word and removes its inflexional suffix according to a set of rules based algorithm. The algorithm is developed according to the grammatical rules of the Modern Greek language "���������� ��� ��������� �������" David Holton, Peter Mackridge, ������ ���������-Warburton (2002). An extended documentation of the removal process, as well as a short evaluation of the system is showing the algorithm accuracy that works with better performance than other past stemming algorithms for the Greek language giving 99.4 percent correct results in a dataset of 5000 of words.

POS: The system uses the POS tagger of [Ellogon](https://www.ellogon.org/) with the following [categories](https://www.ellogon.org/index.php/download/all-categories/category/7-ellogon-documentation-manuals#) for the rules:

* Verbs: VB, VBD, VBF, MD, VBS, VBS, VBDS, VBFS

* Definite Article : DDT

* Indefinite Article: IDT

* Nouns: NNM, NNF, NNN, NNSM, NNSF, NNSN, NNPM, NNPF, NNPN, NNPSM, NNPSF, NNPSN

* Adjectives: JJM, JJF, JJN, CD, JJSM, JJSF, JJSN

* Pronouns: PRP, PP, REP, DP, IP, WP, QP, INP

* Participles: VBG, VBP, VBPD

* Adverb: RB

* Preposition: INP

Although there is a variety of stemmers, the unique morphological system of each language doesn't allow the creation of a global rule-based algorithm which would be able to find out the stem of each word. Especially, in some languages with a rich morphological system, like greek, is even more difficult to find the word stem by reducing the suffix from inflected or derived words. At this point, it would be useful to be mentioned that the greek morphological system may appear a wide variety of suffixes, some of them may appear in different parts of speech. For this reason it is necessary to point out the part of speech of the certain word before trying to find out the root of the concrete word. Let's exam some typical examples. For instance, the word "�����������" is the participle of the verb "���������". Altough, the typical suffix of the present participle is "-������", it may be confused with the basic suffix of adjectives  "-��". As a result can be erroneously be identified as the root of the word "�����������", the stem "���������", while in fact its stem is "�����". Moreover, there are numerals or adverbs which may appear typical verbal suffixes. So, the number "����" or the adverb "��������" seem to have the same suffix with the verbal forms of the first, singular person of the present tense of the active voice. For this reason, it is appropriate to know the part of speech of the word in order to find the stem as in the certain case the suffix of the verb is actually "-�", while the numerals and adverbs are non declinable parts of speech and as a consequence their stem is the word itself.


#### Examples

| WORD | CONFUSED WITH THE STEM OF ANOTHER POS | REAL STEM |
|------|---------------------------------------|-----------|
| ����������� (employee) | ��������� (confused with the stem of the adjectives) | ����� |
| ���� (eight) | ��� (confused with the stem of the verbs) | ���� |
| �������� (more) | ������� (confused with the stem of the verbs) | �������� |



#### Example usage

```python
$ python greek_stemmer.py word POS
```

Arguments:

1. word: the current word
2. POS: part of speech of word

