# Note1 - Bayes rule
### 1) What is Bayes rule
- In NLP, it’s super important because a lot of things are judged using probabilities. For example, it can help you tell whether a tweet is expressing a positive mood or a negative one.

$$
P(A \mid B)=\frac{P(B \mid A)\,P(A)}{P(B)}
$$

- **P(A|B)**: the probability that **A happens after you’ve seen B** *(this is the one you want)* 
- **P(B|A)**: the probability of **seeing B if A actually happened**
- **P(A)**: the **original probability of A** *(your first guess before seeing anything)*
- **P(B)**: the probability that **B shows up** *(overall chance of seeing “happy,” no matter positive or negative)*

### 2) explain the concept

- Imagine I have a huge tweet corpus, and every tweet can only be labeled as either **positive** or **negative**—not both. 
- In this dataset, the word **“happy”** sometimes shows up in tweets labeled **positive**, and sometimes it also shows up in tweets labeled **negative**.

- Probability = count / total
- Total tweets: **N = 20**

## Event A: Tweet is Positive
- Positive tweets: **13**

$$
P(A)=\frac{13}{20}=0.65
$$

- Negative is the complement:

$$
P(\text{negative}) = 1 - P(\text{positive}) = 1 - 0.65 = 0.35
$$

- (Also: negative count = $$　\(20-13=7\), so \(P(\text{negative})=\frac{7}{20}=0.35\))　$$

---

## Event B: Tweet contains “happy”
- Tweets containing **happy**: **4**

$$
P(B)=\frac{4}{20}=0.20
$$

---

## Intersection: Positive AND “happy”
- Tweets that are **positive + contain happy**: **3**

$$
P(A\cap B)=\frac{3}{20}=0.15
$$

---

## Summary Table
| Event | Meaning | Count | Probability |
|------|---------|------:|------------:|
| \(P(A)\) | positive | 13/20 | 0.65 |
| \(P(B)\) | contains “happy” | 4/20 | 0.20 |
| \(P(A\cap B)\) | positive and “happy” | 3/20 | 0.15 |

---

## Conditional Probabilities
### 1) Probability of Positive given “happy”
$$
P(A\mid B)=\frac{P(A\cap B)}{P(B)}
=\frac{3/20}{4/20}=\frac{3}{4}=0.75
$$

### 2) Probability of “happy” given Positive
$$
P(B\mid A)=\frac{P(A\cap B)}{P(A)}
=\frac{3/20}{13/20}=\frac{3}{13}\approx 0.23
$$

<img width="438" height="285" alt="image" src="https://github.com/user-attachments/assets/5789e54d-6135-476f-bb22-ef942dc1df4f" />

---
# Note2 - Bayes rule 2

Let:
- **A** = tweet is **positive**
- **B** = tweet contains **"happy"**

---

### Key conditional probability formulas
$$
P(A\mid B)=\frac{P(A\cap B)}{P(B)}
$$

$$
P(B\mid A)=\frac{P(A\cap B)}{P(A)}
$$

---

### Step 1: Solve for the intersection from each formula
From \(P(A\mid B)\):

$$
P(A\cap B)=P(A\mid B)\,P(B)
$$

From \(P(B\mid A)\):

$$
P(A\cap B)=P(B\mid A)\,P(A)
$$

---

### Step 2: Set them equal (same intersection)
$$
P(A\mid B)\,P(B)=P(B\mid A)\,P(A)
$$

---

### Step 3: Isolate \(P(A\mid B)\) → Bayes’ Rule
$$
P(A\mid B)=\frac{P(B\mid A)\,P(A)}{P(B)}
$$

---

## Quick numeric check (from the example)
Given:
 
 $$ \(P(A)=\frac{13}{20}\) $$ 
 
 $$ \(P(B)=\frac{4}{20}\) $$ 
 
 $$ \(P(B\mid A)=\frac{3}{13}\) $$ 

$$
P(A\mid B)=\frac{\left(\frac{3}{13}\right)\left(\frac{13}{20}\right)}{\frac{4}{20}}
=\frac{\frac{3}{20}}{\frac{4}{20}}
=\frac{3}{4}=0.75
$$

Result matches: **75%**


# Note3 - Bayes rule 3 (EXTREMLY EASY VERSION)

Assume:
- A = the tweet is positive  
- B = the tweet contains “happy”

### Two facts about conditional probability
- “Positive given happy” = (positive + happy) / (happy)
- “Happy given positive” = (positive + happy) / (positive)

### Rearranging the first one
- (positive + happy) = (positive given happy) × (happy)

### Rearranging the second one
- (positive + happy) = (happy given positive) × (positive)

### Since both equal the same “positive + happy”
- (positive given happy) × (happy) = (happy given positive) × (positive)

### So:
- **Positive given happy** = (happy given positive × positive) / happy

