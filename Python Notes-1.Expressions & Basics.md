# 🐍 Python Notes – Expressions & Basics  
> My personal study notes on Python fundamentals (EN / JP / 中文對照)

---

## 1️⃣ Constant（常數 / 定数）

Fixed value written directly in code, such as `1`, `2`, `3`.

固定値は、Pythonでは `type()` 関数を使ってその型を確認することができます。  
在 Python 中，可以用 `type()` 來檢查常數的型態。

123      # int
98.3     # float
"yeepee" # string

## 2️⃣ Reserved Words（予約語 / 保留字）
Words like if, for, while, class, return are reserved.   
変数名や関数名として使用できない、あらかじめ決められた特別な単語。  
Python 內建關鍵字無法作為變數名稱使用。

``` python
import keyword
print(keyword.kwlist)
```

## 3️⃣ Variables & Assignment（変数と代入）

Variables are named boxes in memory that store data.  
変数はメモリ上の「ラベル付きの箱」です。  = は数学の「等しい」ではなく「右の値を左の変数に入れる」という矢印のような意味になります。
在 Python 裡，「=」不是數學的等號，而是「把右邊的值放入左邊變數」。
``` python
x = 12.2
y = 14
x = 100  # overwrites old value
```
## 4️⃣ Variable Naming Rules（変数名のルール／變數命名規則）

変数名は数字で始めてはいけません。  
英字・数字・アンダースコア（_）が使えます。  
特殊記号（$, -, @など）は使用できません。  
大文字と小文字は区別されます。

變數名稱**不能以數字開頭**。  
可以包含**英文字母、數字、底線（_）**。  
**不能使用特殊符號**（如 $, -, @ 等）。  
**大小寫有區別**，`Hours`、`hours`、`HOURS` 是三個不同的變數。

### ✅ Basic Rules

- Variable names **cannot start with a number**  
  ➤ ❌ `23spam`  
  ➤ ✅ `spam23`

- Variable names **can include letters, numbers, and underscores**  
  ➤ ✅ `spam`, `eggs`, `_name`

- Variable names **cannot include special symbols** like `$`, `-`, `@`, etc.  
  ➤ ❌ `$rate`, `pay-rate`

- Variable names are **case-sensitive**  
  ➤ `Hours`, `hours`, `HOURS` are treated as **different variables**.

## 5️⃣ Expressions & Operators（式と演算子／運算式與運算子）

The right-hand side (RHS) of the assignment is evaluated first.
The result is then stored in the variable on the left-hand side (LHS).
x = x + 1 means “increase x by 1,” which is called an increment

代入文では、右辺（right side） が先に計算されます。
その結果が 左辺（left side） の変数に代入されます。
x = x + 1 は「x を 1 増やす」という意味で、インクリメント（increment） と呼ばれます。

在賦值運算中，會先計算右邊（right side） 的表達式，
然後將結果存入左邊（left side） 的變數中。
x = x + 1 表示「讓 x 增加 1」，這個動作稱為 遞增（increment）。

### 🧩 Example

```python
x = 2
x = x + 2
print(x)   # 4
```
## 6️⃣ Functions & `print()`（関数と `print()`／函式與 `print()`）

### 
- A **function** performs a task and may take **arguments** inside parentheses.
- `print(value)` outputs a human-readable representation.

Python は変数名の意味を理解しませんが、人間には意味のある名前が読みやすさに直結します。
用途が分かる名詞を使いましょう（hours, rate, pay など）。

Python 不懂語義，但對一般人來說清楚的名字能大幅提升可讀性(不要寫一堆爛代碼)   
以用途命名（如 hours、rate、pay），日後維護更容易。

```python
print(4)
print("Hello, world")
print("Sum =", 2 + 3)
```

## 7️⃣ Operators & Symbols（演算子と記号／運算子與符號）

> In Python, arithmetic operators work left-to-right, and `/` always performs **true (float) division**.

| Symbol | English Term      | 日本語（意味） | 中文（說明） | Example | Result |
|:-------:|:------------------|:---------------|:--------------|:--------|:-------:|
| `+` | Addition | 加算 | 加法 | `5 + 2` | `7` |
| `-` | Subtraction | 減算 | 減法 | `5 - 2` | `3` |
| `*` | Multiplication | 乗算 | 乘法 | `5 * 2` | `10` |
| `/` | Division (float) | 除算（常に浮動小数点） | 除法（回傳小數） | `5 / 2` | `2.5` |
| `//` | Floor Division | 切り捨て除算 | 地板除（整數商） | `5 // 2` | `2` |
| `**` | Exponent / Power | べき乗 | 次方 | `5 ** 3` | `125` |
| `%` | Modulo (Remainder) | 剰余 | 取餘 | `23 % 5` | `3` |

---

### 💡 Notes

- `/` always returns a **float** in Python 3.  
- Use `//` when you want an **integer quotient**.  
- **Operator precedence (優先順位／運算優先序):**  
  `**` → `* / // %` → `+ -`  
  ➤ Use parentheses `()` for clarity.



