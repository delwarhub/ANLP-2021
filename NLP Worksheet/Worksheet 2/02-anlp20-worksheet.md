*ANLP 2020/21; Uni Potsdam; D. Schlangen, B. Aktas*

# Work Sheet for Week 02: Language Models

## Background

For this worksheet, you again need to work with text corpora. NLTK provides easy access to several standardly used (English) corpora, as described [in Chapter 2 of the nltk book](https://www.nltk.org/book/ch02.html).



## Questions / Exercises

**[E1] Write out the equation for trigram probability estimation (by modifying Eq. 3.11 in JM3, Chapter 3)**
P(wn|wn-2,wn-1) = Count(wn-2,wn-1,wn)/Count(wn-2,wn-1)
---

**[E2] Write a program to compute unsmoothed unigrams and bigrams from a given corpus.**

---

**[E3] Run your N-gram program on two different small corpora of your choice (you might use email text or newsgroups). Now compare the statistics of the two corpora. What are the differences in the most common unigrams between the two? How about interesting differences in bigrams?**

---

**[E4] Add an option to your program to generate random sentences.**


---

**[E5] Add an option to compute the probability (according to the model) of an arbitrary input sentence. Create an input sentence that causes a problem. (I.e., where the output is different from your intuition about what the output should be.)**


---

**[E6] Add Laplace smoothing, and UNK. Does that fix the problem from the previous exercise? What does this intervention do to the probability mass? Compare the smoothed and unsmoothed probability of P("the" | "end") and P("end" | "the").**

