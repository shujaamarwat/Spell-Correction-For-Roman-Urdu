# Spell Correction For Roman Urdu
 
Implementation of a spell correction program for Roman Urdu in Python using the Noisy Channel model based on Bayes Theorem.


## Data
This repository requires two files data.txt which will serve as the corpus and misspellings.txt for generating
error model tables. data.txt is a collection of Roman Urdu sentences and misspellings.txt contains a list of words and their misspellings.

## Implementation 
The spell corrector contains four main components:
1. Language Model: The language model gives the probability of each word occurring in the vocabulary V determined using the corpus given in data.txt. A simple unigram model should be trained using the provided file data.txt. Assuming that all words given in data.txt are correctly spelled.

2. Error Model: This model will be used to estimate the probability of typing x when w was intended. This error is to be modeled using character level insert, delete, transpose and substitute tables. Generating these tables using the provided list of common misspellings in Roman Urdu.

3. Candidate Words Generation: The candidate model will give you all the possible words w which could have been mistyped as x. We consider words that are one edit away from x and exist in our vocabulary V determined by data.txt. Note that there could be many possible words for example for "kitaab" deleting the b would give kitaa which does not exist in Roman Urdu. Thus, for each error word we will be generating a set of words from V.

4. Selection Model using argmax: The final selection using argmax will be responsible for choosing the candidate word w which has the highest probability.
