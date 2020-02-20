# Content
- [Lecture 4 Logistic Regression 拷貝.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/Lecture%204%20Logistic%20Regression%20%E6%8B%B7%E8%B2%9D.pdf)
- [Logistic Regression](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#logistic-regression)
- [Sigmoid function](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#sigmoid-function)


# Logistic Regression
  > 邏輯式迴歸

監督式學習，處理「分類問題」，大多為二元分類

- output：僅有兩種選擇
  - 1：True
  - 0：False
  
根據特徵變數來預測結果的**機率**，即從data中的不同變數判斷output
> 知道一種機率即可，因僅有兩種結果

- model：從變數X中，可得知y是否是等於1的機率
  > y：條件機率，必界於\[0, 1]
  >> E.g. X：濕度、y：是否會下雨
  
在 Linear regression中處理的是「連續型」的資料，然而在Logistic regression中是要處理「類別型」的分類問題\
在Logistic regression裡，可先透過Linear regression model將特徵變數與output之間的關係表現出來（算出值），再透過「function轉換」的方式，將Linear regression model所得出的連續型結果轉換為機率
  - Linear regression model：計算變數X與output之間關係
  - function轉換：將model結果轉為機率
    > E.g. Sigmoid function

[🥃](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#content)

# Sigmoid function
  > 轉換連續值為機率的function
  
![](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/image/Snipaste_2020-02-20_03-04-40.png) 
![](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/image/Snipaste_2020-02-20_03-05-10.png)
> exp()：次方的部份
  - 當 z 很大時，e<sup>-z</sup>會很小 → 極度靠近1
    > 必為正數，且不可能超過1
  - 當 z 很小時，e<sup>-z</sup>會很大 → 趨近於0
  - 當 z = 0 時，e<sup>-z</sup> = 1 → 1/2（即0.5）

#### Pratices
先匯入相關套件
```python
import matplotlib.pyplot as plt
import numpy as np
import math
```
帶入函式畫圖
```python
y = [1 / (1+math.exp(-x)) for x in np.linspace(-6, 6, 100)]

plt.plot(y)
```
- `math.exp()`：數學函式指數項

[🥤](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#content)


# Decision Boundary
  > 決策邊界
  
算出機率值後，要進行分類的判斷
> 為「條件機率」：在x發生的條件下，發生output的機率

![](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/image/Snipaste_2020-02-20_03-32-01.png)

決策邊界，一條在空間中的線，可作為邊界，告訴我們變數落在各邊界應得的結果為何\
為了處理線性不可分離的data，決策邊界也可以是一條多項式的線，以此處理非線性的決策邊界


[🥂](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#content)

# Logistic regression's cost function
  > Logistic regression的目標函式
  
若資料為 y=1 ，希望在x的情況下，預測結果為 y=1 的機率愈高愈好\
若資料為 y=0 ，希望在x的情況下，預測結果為 y=0 的機率愈高愈好

因預測結果為機率，希望各筆資料的結果同時成立時，須將所有相乘，希望最終的目標愈大愈好，但因機率介於\[0, 1]之間，全部相乘會愈乘愈小，慢慢趨近於0，導致過小無法造成影響，因此將最終目標取log，使值放大，
最後在配合regression 一般cost function目標值為愈小愈好，加上負號

因此，最終為希望目標函數「愈小愈好」

除此之外，還希望model愈簡單愈好

[🍻](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#content)
  
# Praticing logistic regression  



[🍺](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#content)
