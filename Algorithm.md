## 1.1 Time complexity

For the same input size, the actual running time may vary, and hardware/software also affect speed.
But those usually change only a ***constant factor***, not the ***growth rate***.
The growth function is called ***time complexity***


我們看的是：**輸入大小 (n) 變大時，演算法的執行時間怎麼成長**。
同樣大小的輸入，實際時間可能不同；硬體和軟體也會影響速度。
但那些通常只改變**常數倍**，不改變**成長速度**。
這個成長函數就叫 **time complexity**。

---

###  1.2 Growth rate/Constant factor

**constant factor** is the constant in front, Changing hardware or software usually only makes a program:
* 2 times faster(這個2就是constant factor,固定倍數就是前面的常數)
* 3 times slower
* 10 times faster
That only changes the **constant factor**, it would not change the **growth rate***  
* `2n`
* `10n`
* `100n^2`
The `2`, `10`, and `100` are **constant factors**.  

---

**Growth rate** describes the main pattern as ``n`` becomes large.    
描述輸入資料量 ``n`` 變非常大時，執行時間增加的主要趨勢。 

``n`` is linear growth,  線性成長(等比例增加)  
``n^2`` is quadratic growth 平方成長(暴增)  
``log n`` is logarithmic growth.**  對數成長（增加肥腸緩慢）  

---

Sample 1  
這些複雜度等級是嚴格區分的，一個本質上是 ``O(n)`` 的演算法，成長趨勢都不會變成 ``O(n^2)``，無論給它多少資料都不會變成如下列範例:  

``n`` won't become ``n^2``,    
``n^2`` won't become ``n``,   
and ``n log n`` won't become ``O(1)``.**  

---

Sample 2 

資料量 ``n`` 很小時（例如 ``n = 10``），  
`md
100 * 10 = 1000
`
此時   
`md
10^2 = 100``
`
看起來 ``100n`` 比較慢（耗時較多）。    
但是！當 ``n`` 變大時（例如 ``n = 1000``）  
`md
100 * 1000 = 100,000`
`
而 

`md
1000^2 = 1,000,000
`

``n^2`` 瞬間反超並且無情暴增。  
證明前面的常數（如 100）在資料量大時沒意義，  
不管 ``n`` 前面乘上多大的數字，``100n`` 依然歸類為**線性 (Linear)**，而 ``n^2`` 是**二次方 (Quadratic)**。  


---

### 1.3 **Big O**

<img width="1961" height="1242" alt="image" src="https://github.com/user-attachments/assets/e940e56c-8d72-4afe-aa9a-3a15fcaf3396" />

If after some point, `f(n)` never goes above `c · g(n)`,
then we say:
`f(n) = O(g(n))`

`f(n)` 
真正要分析的函數    
The actual function you want to analyze.   
usaully the running time of algorithms.   

---

`g(n)`
拿來當標準比較的函數。  
The comparison function.  
For example: `n, n^2, log n.`  

---

`c`
一個正常的正數常數。  
它只是把 g(n) 放大幾倍。  

A positive constant.  
It just scales g(n) up.  

---

`c·g(n)`

把 g(n) 放大 c 倍  
it means scaling g(n) by c

---

`n0`
起點(`f(n)` 永遠小於`c·g(n)`的起點    
a starting point  
What happens before that does not matter.    

---

`f(n) = O(g(n))` iff there exist positive constants c and n0
such that `f(n) ≤ c·g(n)` for all `n ≥ n0`

只要找得到某個常數 c 和某個起點 n0，
讓 n 只要大於等於 n0 時，
f(n) 都壓在 c·g(n) 的下面，
那就可以說 f(n)=O(g(n))。

---

### 1.7 Common complexity classes

* **(O(1))**：constant｜常數
* **(O(\log n))**：logarithmic｜對數
* **(O(n))**：linear｜線性
* **(O(n^2))**：quadratic｜二次
* **(O(n^3))**：cubic｜三次
* **(O(2^n))**：exponential｜指數 

---


## 一句話背起來 | One-line memory trick

* **O** = 上界 = upper bound
* **Ω** = 下界 = lower bound
* **Θ** = 同級 = same order
* **o** = 更小 = strictly smaller
* **ω** = 更大 = strictly larger




.

\\
