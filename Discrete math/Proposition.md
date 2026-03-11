# Proposition 1
### 1. Proposition


1. A Proposition has to be a declarative sentence. It has to be either ***True*** or ***False***. 
2. A proposition is not necessarily true 

---

Sample 1
- "Toronto is the capital of Canada."
  *this is a false proposition, but it is still a proposition.

---

Sample 2
- 1 + 1 = 2 
  A true proposition.

---

Sample 3
- What time is it
  Non-Proposition

- x + 1 = 2
  Until the value of x is known, its truth or falsity cannot be determined.Non-Proposition)

---
### 2.Variables & Truth Values

- Truth Value
1.If a proposition is true, it is denoted as T. 
  If a proposition is false, it is denoted as F.
  
- Propositional Variables
1.Propositions are usually denoted by lowercase italic letters, like $p, q, r, s$.

---

### 3.Atomic Proposition

A statement that cannot be decomposed into simpler ones.  
Example: $p$: "It is raining."

---

### 4.Compound Propositions

A statement formed by combining two or more atomic propositions using logical connectives (e.g., AND, OR, NOT). 
Example: $p \land q$: "It is raining and I am wet."

### 5.Operators

#### 1.Negation 


$\neg$
"Not $p$"



### 1. What those symbols mean

| Symbol    | Name               | Read as      | Meaning              | True when...                      |
| --------- | ------------------ | ------------ | -------------------- | --------------------------------- |
| **¬p**    | Negation           | not p        | opposite of p        | p is false                        |
| **p ∧ q** | Conjunction        | p and q      | both happen          | both p and q are true             |
| **p ∨ q** | Disjunction        | p or q       | at least one happens | at least one is true              |
| **p ⊕ q** | Exclusive Or (XOR) | p xor q      | one, but not both    | exactly one is true               |
| **p → q** | Implication        | if p, then q | p leads to q         | false only when p = T and q = F   |
| **p ↔ q** | Biconditional      | p iff q      | p if and only if q   | p and q have the same truth value |

#### 1-1. 
`¬p` (Negation)

- Let **p** = "Today is raining." 今天下雨
- **¬p** = "Today is **not** raining." 今天沒下雨

| p | ¬p |
|---|---|
| T | F |
| F | T |
---

`p ∧ q` (AND)

- Let **p** = "I finished my homework." 今天我寫完作業
- Let **q** = "I submitted it." 今天我交了
- **p ∧ q** = "I finished my homework **and** I submitted it." 我寫完作業而且我交了

| p | q | p ∧ q |
|---|---|---|
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | F |

---

`p ∨ q` (OR, inclusive)

- Let **p** = "I drink coffee." 我喝了咖啡
- Let **q** = "I drink tea." 我喝了茶
- **p ∨ q** = "I drink coffee **or** I drink tea." 我喝了咖啡又喝了茶

- This can mean **one or both**.

---

`p ⊕ q` (XOR, exactly one)

- Let **p** = "I take the MRT."
- Let **q** = "I take the bus."
- **p ⊕ q** = "I take the MRT **or** I take the bus,
-
- this can mean **one but not both**."

---

`p → q` (Implication)

- Let **p** = "I study."
- Let **q** = "I pass the quiz."
- **p → q** = "**If** I study, **then** I pass the quiz."

---

 `p ↔ q` (Biconditional / iff)

- Let **p** = "You can enter."
- Let **q** = "You have a student ID."
- **p ↔ q** = "You can enter **if and only if** you have a student ID."

### 1.恆真句 Tautology 

Exp: p v ¬p (意思是p or ¬p) meaning: p or not p  
如果有一個真 就是真的 If either one is true, then the whole statement is true  

命題：p =「今天下雨」Proposition: p = "It is raining today."  
式子：p ∨ ¬p =「今天下雨 或 今天沒下雨」Expression: p ∨ ¬p = "It is raining today, or it is not raining today."  
結論：一定真（因為只能二選一）Conclusion: Always true (because there are only two possibilities).  

命題：p =「我有帶學生證」  Proposition: p = "I brought my student ID."
p ∨ ¬p =「我有帶學生證 或 我沒帶學生證」  Expression: p ∨ ¬p = "I brought my student ID, or I did not bring my student ID."
結論：一定真  Conclusion: Always true.


| p | ¬p | p ∨ ¬p |
| - | -- | ------ |
| T | F  | T      |
| F | T  | T      |

