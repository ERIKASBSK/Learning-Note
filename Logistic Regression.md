
## Supervised Learning Training Loop

X → model(θ) → Ŷ → compare with Y → cost → update θ → repeat
Turn text into numbers → guess → compare → fix mistakes → finally classify sentiment. 

1.Build a vocabulary of all unique words  
2.Convert each tweet into a sparse 0/1 vector showing which words appear   
3.but a large vocabulary makes vectors long and slows training and prediction  


## HOW IT WORKS 
<img width="2146" height="790" alt="image" src="https://github.com/user-attachments/assets/2a4320bc-4ce0-41dd-aec1-5a960e4c71e5" />

1.Represent a tweet as a **|V|-dimensional 0/1 vector**, marking **1** for words that appear and **0** otherwise.  
2.As **|V| grows**, vectors become **more sparse** (mostly zeros) and the model needs **more parameters**.   
3.More parameters → **longer training time** and **slower prediction**.

## Note1 — Frequency Counts for Sentiment 
Goal: Count how many times each word appears in positive tweets vs negative tweets, then use these counts as features for Logistic Regression.
Steps
  1. Build a vocabulary (V)  *V = all unique words in the corpus (all tweets)
  2. Split tweets into 2 classes Positive (y=1) Negative (y=0)
  3. Count word frequencies per class  
     pos_count(word) = times the word appears in positive tweets  
     neg_count(word) = times the word appears in negative tweets  

| Word     | Positive count (y=1) | Negative count (y=0) |
|----------|---------------------:|---------------------:|
| happy    |                    2 |                    0 |
| am       |                    0 |                    3 |
| learning |                    1 |                    0 |
| bad      |                    0 |                    2 |

## Note2 — Frequency dictionary

Before: a tweet was a big vector with size V (very slow).  
Now: a tweet becomes a small vector with size 3 (much faster).  

*A frequency dictionary: It tells you how many times each word appears in positive tweets and negative tweets 

### 1) Build a frequency dictionary `freqs`
Store how often each word appears in each class:

- `PosFreq(1)` = count in **positive tweets**
- `NegFreq(0)` = count in **negative tweets**

Key format:
- `(word, 1) → PosFreq`
- `(word, 0) → NegFreq`

### 2) Example frequency table
| Vocabulary | PosFreq(1) | NegFreq(0) |
|-----------|-----------:|-----------:|
| I         |          3 |          3 |
| am        |          3 |          3 |
| happy     |          2 |          0 |
| because   |          1 |          0 |
| learning  |          1 |          1 |
| NLP       |          1 |          1 |
| sad       |          0 |          2 |
| not       |          0 |          1 |

*A tweet can be represented as **[bias, positive-frequency-sum, negative-frequency-sum]**, enabling Logistic Regression with only **3 features**.
✅ **Key point:** The model can classify a tweet using only **three numbers**, instead of a **huge vector with thousands of dimensions**.

## Note3 — Clean tweets before feeding them into the model

### 1) Stop Words 
very common words (e.g., *the, is, and*) that usually carry little meaning for NLP tasks.  
They are often removed to reduce noise and speed up processing, especially in **bag-of-words / TF-IDF** models.  
However removing them can hurt tasks like **sentiment** (e.g., *not good*), so it depends on the goal.
Typical handling: use a stop-word list + keep important exceptions like **negations** (*not, never*).  

- **Bag-of-Words (BoW)**: represents text as a vector of word counts (order is ignored).  
- **TF-IDF**: reweights BoW by down-weighting common words and up-weighting informative ones.  

### 2) Stemming 
reduces words to a rough root form (e.g., *playing → play*, *studies → studi*).  
shrink the vocabulary for **BoW/TF-IDF** models.  
Downsides: stems can look “wrong” and may hurt meaning (not real words).  
Common stemmers: **Porter Stemmer**, **Snowball Stemmer**.  

- **Porter Stemmer**: a classic rule-based English stemmer that aggressively strips suffixes (fast but stems may look unnatural).  
- **Snowball Stemmer**: an improved, more consistent version of Porter, with better rules and support for multiple languages.  


### 3) Punctuation removal
deletes symbols like `.,!?` to clean text before vectorization.  
*punctuation can sometimes carry meaning in sentiment (e.g., “Great!!!”, “Really?”).  

### 4) Remove handles & URLs
Handles and URLs usually don’t help sentiment → remove them  

### 5) Lowercasing
Treat GREAT / Great / great as the same word  

### 6) Tokenizing (tokenization)  
splits text into smaller units called **tokens** (words, subwords, or symbols).  
- Example: `"I love NLP!" → ["I", "love", "NLP", "!"]`  

<img width="1930" height="740" alt="image" src="https://github.com/user-attachments/assets/e3429ef4-d275-4e1f-8d89-ba33a2ee3a3d" />

## Note4 — NLTK  
A popular Python library for **NLP learning and prototyping**, 
provides tools for **tokenization, stemming, stopwords, POS tagging, parsing**, and more.  
It also includes **built-in corpora/datasets** (e.g., labeled tweets) for quick experiments.  
Commonly used in courses and baseline pipelines before moving to larger frameworks.  

```python
import nltk                                # Python library for NLP
from nltk.corpus import twitter_samples    # sample Twitter dataset from NLTK
import matplotlib.pyplot as plt            # library for visualization
import random                              # pseudo-random number generator
```
## Note5 — Create a feature matrix X for all training tweets
### 1) What is BIAS

Bias is the model’s baseline score, which makes it easier to adjust predictions and separate positive vs. negative cases
In Logistic Regression, it’s the intercept (represented by adding a feature `x₀ = 1`).  
It helps the decision boundary move instead of being forced through the origin.  
- `score = (bias×w0) + (pos_sum×w1) + (neg_sum×w2)`

### 2) The whole process
1. Raw tweet
   `I am Happy Because i am learning NLP @deeplearning`  
2. Preprocessing(remove stopwords / handles / punctuation + stemming + lowercase)
   `[happy, learn, nlp]`
3. Feature Extraction
   `[bias, sum_pos, sum_neg]`

<img width="993" height="1108" alt="image" src="https://github.com/user-attachments/assets/e967a30e-a175-4cc6-9080-aba7a5a19d2c" />

## Note6 — Sigmoid
Sigmoid squashes any number into 0 to 1  

$$
h(x^{(i)},\theta)=\frac{1}{1+e^{-\theta^T x^{(i)}}}
$$

it basically convert any real-valued score into a probability (0 to 1)

### Symbols
| Symbol | English | Meaning | 中文 | 意義 |
|---|---|---|---|---|
| $h(x^{(i)},\theta)$ | hypothesis / prediction | predicted probability (0 to 1) | 預測機率 | 模型對第 $i$ 筆資料「是正面」的機率 |
| $x^{(i)}$ | feature vector | input numbers describing the example | 特徵向量 | 第 $i$ 則 tweet 的特徵 |
| $\theta$ | parameters / weights | learned importance of each feature | 參數 / 權重 | 模型學到的權重（每個特徵多重要） |
| $\theta^T$ | transpose of $\theta$ | used to compute the dot product | 轉置 | 方便跟 $x^{(i)}$ 做內積 |
| $\theta^T x^{(i)}$ | dot product / score | weighted sum before sigmoid | 內積 / 分數 | 加權總分（可正可負），丟進 sigmoid 變機率 |
| $e$ | Euler’s number | base of natural exponential | 自然常數 | 約 2.718，用在指數運算 |
| $e^{-\theta^T x^{(i)}}$ | exponential term | part of the sigmoid calculation | 指數項 | sigmoid 裡用來「彎曲」機率的部分 |
| $i$ | index | which training example | 索引 | 第幾筆資料 / 第幾則 tweet |

### Quick intuition
- If $\theta^T x^{(i)}$ is big (positive) → $h \approx 1$
- If $\theta^T x^{(i)}$ is very negative → $h \approx 0$
- If $\theta^T x^{(i)} = 0$ → $h = 0.5$

