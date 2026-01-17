# Note 1 downside of Naive Bayes  

### 1: Word Independence
Naive Bayes assumes each word in a sentence is **independent** of the others.  
In real language, words often come in **patterns/collocations** (e.g., *sunny* and *hot*).  
This can make the model **overestimate or underestimate** how important certain words are.

---

### 2: Training Data Matches Real-World Distribution
Naive Bayes assumes the **class proportions** in training data match real life.  
But many datasets are **artificially balanced** (e.g., 50% positive / 50% negative).  
If real data is imbalanced, predictions can become **too optimistic or too pessimistic**.

---

### 3: Error Analysis for Misclassified Tweets  

When a sentence is classified wrong, check these common causes:

### Original tweet
> "My beloved grandmother :("

### After preprocessing (bad)
- remove punctuation/emoticons → `"my beloved grandmother"`
- tokens → `["beloved", "grandmother"]`

### What the model “sees”
- words look **warm/positive** → predicts **Positive** ✅
- but the real meaning is **sad** → should be **Negative** ❌

Fix idea: **don’t blindly delete emoticons** (keep `:(`, `:)`, `😭`, etc.)

---

### 4: Even worse: removing **not** flips sentiment

### Original tweet
> "This is not good because your attitude is not even close to being nice."

### After preprocessing (very bad)
- remove stopwords/neutral words (wrong) → `"good attitude close nice"`
- tokens → `["good", "attitude", "close", "nice"]`

### What the model “sees”
- many **positive words** → predicts **Positive** ✅  
- but the real sentiment is **Negative** ❌

Fix idea: **never remove negations** like `not`, `never`, `no`

---

### 5: Word order matters 

### Tweet A (Positive)
> "I’m happy because I did not go."

Meaning: *I’m happy (reason: I didn’t go)* ✅

### Tweet B (Negative)
> "I’m not happy because I did not go."

Meaning: *I’m unhappy (reason: I didn’t go)* ❌

### Why Naive Bayes fails
Both contain similar keywords:
- `{happy, not, go, because}`  
But **“not” attaches to different parts**, changing meaning.

Fix idea: use **bigrams / n-grams** or models that learn word order

---
### 6: Sarcasm / irony 
### Original tweet (actually Positive)
> "This is a ridiculously powerful movie. The plot was gripping and I cried until the ending."

### What Naive Bayes might latch onto
- negative-looking words: `["ridiculously", "cried"]`
- ignores the “wow this is amazing” tone

So it may predict **Negative** ✅  
but real label is **Positive** ❌

Fix idea: sarcasm is hard — use better features (context, embeddings) + more data

---
