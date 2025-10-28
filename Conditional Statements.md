## ⚖️ Conditional Statements  
（条件付き実行／條件式執行）

---

### 1️⃣ Conditional Execution（条件付き実行／條件式執行）
Conditional execution means the program can **decide whether or not to run** certain parts of the code.  
Sequential execution just runs line by line, but with conditions, the program becomes smarter — *that’s where `if` comes in.*

条件付き実行とは、**条件に応じてコードの一部を実行するかどうかを選べる**ことです。  
順次実行は単に上から下に処理を進めますが、`if` によってプログラムはより「賢く」動作します。

所謂條件式執行，就是讓程式能**依條件決定是否執行某段代碼**。  
一般情況下程式會一行一行執行，但加上 `if`，它就變得更「聰明」。

---

### 2️⃣ Indentation インデント／縮排）

Indentation shows which lines belong to which block.  
Python uses **indentation instead of braces `{}`**, usually 4 spaces.  
Mixing tabs and spaces = chaos (and errors).

インデントは「どのコードがどの条件に属するか」を示します。  
Python は `{}` の代わりに **インデント（4 スペース）** を使います。  
タブとスペースを混ぜるとエラーの原因になります。

縮排用來表示**哪一段代碼屬於哪個條件或區塊**。  
Python 不用 `{}`，而是靠縮排（通常 4 個空格）。  
不要混用 tab 與空白，否則會報錯。

---

### 3️⃣ Comparison Operators  
（比較演算子／比較運算子）

| Symbol | English | 日本語 | 中文 |
|:--:|:--|:--|:--|
| `<` | less than | より小さい | 小於 |
| `<=` | less than or equal to | 以下 | 小於或等於 |
| `==` | equal to | 等しい | 等於 |
| `>` | greater than | より大きい | 大於 |
| `>=` | greater than or equal to | 以上 | 大於或等於 |
| `!=` | not equal to | 等しくない | 不等於 |

💡 `=` is **assignment** (put value into variable).  
`==` is **comparison** (ask if they’re the same).

---

### 4️⃣ `if ... else`  
（もし〜なら／如果...否則）

#### 🇬🇧 EN
The `else` clause runs when the `if` condition is `False`.

#### 🇯🇵 日本語
`if` の条件が `False` のときに `else` ブロックが実行されます。

#### 🇨🇳 中文
當 `if` 條件為 `False` 時，會執行 `else` 區塊。

```python
x = 5
if x > 10:
    print("Big")
else:
    print("Small")
