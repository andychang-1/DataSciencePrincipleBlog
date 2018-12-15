---
mathjax: true
---


# Data Science Principles Project: Quora Insincere questions classification


### Introduction

This is a final project done for EE 461P: Data Science Principles at the University of Texas at Austin. This project was completed by Andy Chang, Clive Unger, Nick Edelman, Nic Key, and Avishka Suduwa Dewage.

We chose to do this problem from Kaggle: 
kaggle.com/c/quora-insincere-questions-classification

Quora.com is a platform where people can ask questions and connect with others who contribute unique insights and quality answers.

A key challenge is to weed out insincere questions, founded upon false premises, or intending to make a statement rather than look for helpful answers.

In this competition, Kagglers will develop models that identify and flag insincere questions.



### The Data
The **training data** is 1.31m rows of data, it looks like this.

| qid | question_text | target |
| -| -| -|
| 00002165364db923c7e6 | How did Quebec nationalists see their province as a nation in the 1960s? | 0 |
| … | … | … |
| cd7642554d107f946d8a | What is the full form of DML? | 0 |

The **test data** is 56.4k rows of data, it obviously does not have the target labels, it looks like this.

| qid | question_text |
| -| -|
| 00014894849d00ba98a9 | My voice range is A2-C5. My chest voice goes up to F4. Included sample in my higher chest range. What is my voice type?|
| … | … |
| fffed08be2626f74b139 | Why do all the stupid people I know tend to be left-wing?|

The rules by which the training data was scored is as follows:
* Has a non-neutral tone
* Is disparaging or inflammatory
* Isn’t grounded in reality
* Uses sexual content for shock value

Several sets of **word embeddings** were also provided:
* Google word2vec embeddings from Google News
* “GloVe” word embeddings from Wikipedia
* PPDB Paragram word Embeddings
* fastText trained word embeddings from Wikinews


### Evaluation

#### Submissions are scored on F1 Score

$$ E = m\cdot c^2 \label{eq:mc2}$$

<iframe width="100%" height="300" src="//jsfiddle.net/avishkas/f3wmypv9/embedded/result/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
