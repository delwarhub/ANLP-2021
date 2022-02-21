*ANLP 2020/21; Uni Potsdam; D. Schlangen, B. Aktas*

# Work Sheet for Week 04: Word Vectors

#### Notes

Please remember that these exercises are only meant to guide your active learning, and handing them in is only for us to see where additional feedback might be needed.

So, a) make use of your peers as much as possible, for example in learning groups, & by asking questions on piazza; b) use these exercises to have something to do during the practical on Thursdays; c) prioritise the assignments over the worksheets, and only work on the worksheets (outside of the practical) once you are sufficiently happy with your progress on the assignment.

Also, it is highly unlikely that you will have enough time to work on all of these! (Unless you are already somewhat familiar with the material.) This is just to give you a selection of exercises to work on. Or maybe you will want to come back to some of them in the teaching break.


#### Exercises

##### [E1] From Frequency to Meaning
<<<<<<< HEAD
Consider the following word-context matrix with the three words “orange”, “banana” and “car” and the three context words “juice”, “the” and “drive”.
=======
Consider the following word-context matrix with the three words "orange", "banana" and "car" and the three context words "juice", "the" and "drive".
>>>>>>> 50ca00f14e42a9c1ca9e9eacaa5ebc81090357dc

|   |         |            |   |
|:--| ------------- |:-------------:| -----:|
|   |       juice  | the           | drive  |
|orange| 10 | 20 | 0 |
|banana| 8| 20 | 0 |
|car| 1 | 20 | 10|

<<<<<<< HEAD
1. Compute the cosine similarity values for “orange” and “banana” and for “orange” and “car”. How you interpret the results of this computation?
2. Compute the MLEs using frequencies for the probabilities P(w), P(c) and P(w, c) for each word w and each context word c.
3. Based on these, compute the PPMI values for the cells in the matrix.
4. Now compute the cosine similarity values of the PPMI vectors for “orange” and “banana” and for “orange” and “car”. Are there any differences with the frequency based vectors computed in item (1)?
=======
1. Compute the cosine similarity values for "orange" and "banana" and for "orange" and "car". How you interpret the results of this computation?
2. Compute the MLEs using frequencies for the probabilities P(w), P(c) and P(w, c) for each word w and each context word c.
3. Based on the values found in (2), compute the PPMI values for the cells in the matrix.
4. Now compute the cosine similarity values of the PPMI vectors for "orange" and "banana" and for "orange" and "car". Are there any differences with the frequency based vectors computed in item (1)?

---
>>>>>>> 50ca00f14e42a9c1ca9e9eacaa5ebc81090357dc

##### [E2] Word Meaning Representations

Can you come up with a manually constructed vector representation for concepts / word meanings? For example, let's assume that the concept "woman" is represented by `human: yes, gender: female`, how could that be understood as a vector? How would you represent "man" in this system? How would you add more concepts (such as "fish", or "refridgerator", or "linguistics") to this system?
Is it the case that in your representation system, cosine similarity tracks semantic closeness? What would the advantage of such a system be compared to learned word vectors? What are the disadvantages?

<<<<<<< HEAD
##### [E3] Word Embeddings

Please load the word embeddings trained on the Google News corpora using the [gensim](https://radimrehurek.com/gensim/index.html) package. First, make sure that you have the gensim package installed on your computer. You can find the model [here](https://drive.google.com/uc?id=0B7XkCwpI5KDYNlNUTTlSS21pQmM). The model has a size of 1.5GB, so make sure you have some free memory before you load it. It is also possible to use one of the pre-trained glove models [here](https://nlp.stanford.edu/projects/glove/).
=======
---

##### [E3] Lots of Banks

Suppose you are given a sentence: 'The man was accused of robbing a bank.' and 'The man went fishing by the bank of the river.' . Do you think the word embedding for the word 'bank' will be similar? Does this pose a problem?

---

##### [E4] Word Embeddings

This exercise aims to let you evaluate word similarities using word embeddings. Compute the similarity between some of the words existing in **wordsim_similarity_goldstandard.txt** dataset which includes human judgements for the word similarities and check whether the human judgements correlate with the distances from the word vectors you computed.

You can use the word embeddings trained on the Google News corpora using the [gensim](https://radimrehurek.com/gensim/index.html) package. First, make sure that you have the gensim package installed on your computer. You can find the model [here](https://drive.google.com/uc?id=0B7XkCwpI5KDYNlNUTTlSS21pQmM). The model has a size of 1.5GB, so make sure you have some free memory before you load it. It is also possible to use one of the pre-trained glove models [here](https://nlp.stanford.edu/projects/glove/).
>>>>>>> 50ca00f14e42a9c1ca9e9eacaa5ebc81090357dc
If you don't have enough resources on your computer, you can also use the online interface [here](http://bionlp-www.utu.fi/wv_demo/).

```python
import gensim
model = gensim.models.KeyedVectors.load_word2vec_format('GoogleNews-vectors-negative300.bin', binary=True)
```
<<<<<<< HEAD

The gensim package has many easy to use [functions](https://radimrehurek.com/gensim/models/keyedvectors.html). Experiment with those functions to find interesting relations in the word embeddings (`most_similar`, `doesnt_match`, `similarity`). 

You can make use of the data set wordsim_similarity_goldstandard.txt which includes human judgments about similarities of some words. Compute the similarity between the words existing in this dataset and check whether the human judgments correlate with
the distances from the word vectors you computed.

---

##### [E4] Paraphraser
=======
The gensim package has many easy to use [functions](https://radimrehurek.com/gensim/models/keyedvectors.html). You can experiment with those functions to find interesting relations in the word embeddings (`most_similar`, `doesnt_match`, `similarity`) and to further explore the package.

---

##### [E5] Paraphraser
>>>>>>> 50ca00f14e42a9c1ca9e9eacaa5ebc81090357dc
Sometimes it might be useful to paraphrase a sentence. With similar words, it is possible to use them for a simple paraphraser system. How can you use word embeddings to implement such a system?

If you have time and resources, implement such a paraphraser (hint: you can use the `most_similar()` function in gensim.models.Word2Vec package). Does the paraphraser perform well? Are there cases where it maybe does not perform as well as expected?


<<<<<<< HEAD
##### [E5] Evaluate Word Embedding
=======
##### [E6] Evaluate Word Embedding
>>>>>>> 50ca00f14e42a9c1ca9e9eacaa5ebc81090357dc
With the model, Google also released syntactic and semantic test examples, following the \"A is to B as C is to D\" style. The evaluation file can be found [here](https://raw.githubusercontent.com/RaRe-Technologies/gensim/develop/gensim/test/test_data/questions-words.txt). Please use these examples to evaluate the model. What is the accuracy of the model on these evaluation examples?

Try to find some interesting examples of relations the model did not predict correctly. Do you think this evaluation is helpful? Please comment briefly!

---

<<<<<<< HEAD


##### [E6] Limitations
=======
##### [E7] Limitations
>>>>>>> 50ca00f14e42a9c1ca9e9eacaa5ebc81090357dc

Using word embeddings, words or phrases can be mapped to a continuous vector space (e.g. Word2Vec, GloVe). In your opinion, is there a limitation to this approach? Please make a brief comment.

---
<<<<<<< HEAD


##### [E7] Lots of Banks

Suppose you are given a sentence: 'The man was accused of robbing a bank.' and 'The man went fishing by the bank of the river.' . Do you think the word embedding for the word 'bank' will be similar? Does this pose a problem?

---

=======
>>>>>>> 50ca00f14e42a9c1ca9e9eacaa5ebc81090357dc
