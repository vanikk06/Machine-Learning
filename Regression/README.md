# Content
  - [Lecture 3 Regression 拷貝_完整.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/Lecture%203%20Regression%20%E6%8B%B7%E8%B2%9D_%E5%AE%8C%E6%95%B4.pdf)
  - [作業2.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/%E4%BD%9C%E6%A5%AD2.pdf)
  - [Class_03.ipynb](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/Class_03.ipynb)
    - [webpage](https://nbviewer.jupyter.org/github/vanikk06/Machine-Learning/blob/master/Regression/Class_03.ipynb)
  - [作業2_answer.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/%E4%BD%9C%E6%A5%AD2_answer.pdf)  
  - [Correlation coefficient](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#correlation-coefficient)
  - [Linear Regression](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#linear-regression)
  - [Least square method ＆ Gradient descent](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#least-square-method--gradient-descent)
  - [Pratices Linear Regression](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#pratices-linear-regression)


# Correlation coefficient
  > 相關係數


- Relationship：任兩列資料欄（屬性）之間的關係
  > 相關關係
  
- Correlation coefficient：相關係數，用以反映變數之間相關關係密切程度的統計指標
  > 介於\[-1, 1] 之間
  
  ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-13_03-54-34.png)
  
  是透過計算「xy的標準差」除以「x標準差乘以y標準差而來的」
  > ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-13_04-03-36.png)
  
  數字愈接近 1 代表相關性愈大
    - 正相關：正號
    - 負相關：負號
    - 相關係數=0：僅代表不存在線性相關，**不代表不存在相關性**

#### Source
[相關係數](https://wiki.mbalib.com/zh-tw/%E7%9B%B8%E5%85%B3%E7%B3%BB%E6%95%B0)

[⚗](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)


# Linear Regression
  > 線性回歸

線性迴歸，是尋找數據背後隱藏的函式，也就是符合數據規律的函式，
  > 為在資料點中找出規律、畫出一條直線的專業說法
  
是統計上在找「多個自變數和依變數之間的關係」建造出的模型
  - 簡單線性回歸（Simple linear regression）：一個自變數與一個依變數
  - 多元回歸（multiple regression）：大於一個自變數與一個依變數
      - 自變數（independent variable）：獨立，理論上此變數是不被其他變數影響的，只會影響別的變數，因此被認為是「因」（Cause）
      
      - 依變數（dependent variable）：相依，此變數基本上是被其他變數影響，引此被認為是「果」（effect）
  
  
  
線性模型：點與線之間距離最短
 > 線性函數：y = ax + b
 >> ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-13_04-14-05.png)
 
- Machine learning：利用 data 計算假設 g，讓其近似目標 f
  - Step 1. 收集訓練資料
  - Step 2. 設計數學模型
  - Step 3. 找出具最佳參數之模型


#### Source
[線性迴歸的運作原理](https://brohrer.mcknote.com/zh-Hant/how_machine_learning_works/how_linear_regression_works.html)

[線性回歸(Linear Regression)](https://medium.com/@chih.sheng.huang821/%E7%B7%9A%E6%80%A7%E5%9B%9E%E6%AD%B8-linear-regression-3a271a7453e)

[🧪](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)

# Least square method ＆ Gradient descent
  > 「最小平方法」與「梯度下降法」

利用「最小平方法」與「梯度下降法」找出最佳的回歸線
- Least square method：目的是為了尋找**最小**的cost function，希望誤差的平方愈小愈好，因誤插有正有負，取平方後皆為正值

  > P.S. 距離的計算「平方」會優於「絕對值」
  >> 因為在尋找「最佳化」函數時，會使用微積分的方式，絕對值微分的話，在0會突然變化劇烈
  （sharp），不利於判斷
  
  - Cost function / Loss function：損失函數，在最佳化理論裡稱為目標函數（objection function），希望目標函數愈小愈好
    > 找 minimize
    
    ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-14_00-02-57.png)
    > 微分時，函式會成倍數成長，因此「乘上1/2」可使函式更為簡潔，且不影響最小值
   
  
- Gradient descent：透過不斷**更新參數**慢慢靠近目標，最終找到一個極近似目標的函式
  > 微積分
   
   梯度下降法，是最佳化理論裡的一個一階找最佳解的一種方法，利用此方法找到函式中局部最小值
   > 找一組θ<sub>0</sub>, θ<sub>1</sub> 使E(θ<sub>0</sub>, θ<sub>1</sub>)最小
   >> θ<sub>1</sub>：斜率，與相關係數同號\
   >> θ<sub>0</sub>：截距（高度）
   >>> 從\[0,0]開始慢慢找，用每點與回歸線的距離總合為判斷，找最小值
   
   - 梯度
     > 微分：函式在某點上變化的方向
        - 一維度的純量x的梯度：計算f(x)對x的微分
        - 多維度的向量x的梯度：計算f(x)對x所有元素的偏微分，即對每個元素做偏微分所組成的向量空間
        
      可以將梯度想像成一個指向最低點的指南針，在梯度下降法中我們是往梯度的反方向走
      
    在函式中尋找極小值，可以想像是在一個拋物線中尋找最低點，搭配低度下降法
     - 當 f'(x) < 0，表示目前所在為負斜率的線，因此要往右移動，才會接近最低點
     - 當 f'(x) > 0，表示目前所在為正斜率的線，因此要往左移動，才會接近最低點
    
    透過上述移動θ，讓其往與導函數（f'(x)）相反的方向移動，就會往最小值的位置移動
    
    1. f'(x)決定方向
    2. η：learning rate，每次移動的大小
       > model要設定的參數
       >> 設定不好會無法收斂到最小
       
       ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-14_02-26-43.png)
       ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-14_02-36-50.png)
       ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-14_02-38-07.png)
       

#### § Pratices §
[👉🏻HERE👈🏻](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/Class_03.ipynb)

![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-14_03-02-20.png)

- h<sub>θ</sub>( x ) = θ<sub>0</sub> + θ<sub>1</sub>x
- θ<sub>0</sub>調整：h<sub>θ</sub>( x ) - y
- θ<sub>1</sub>調整：( h<sub>θ</sub>( x ) - y )*x

梯度下降法是不斷往下找誤差（cost）的最小值，但在找到之前，我們不知道要給model疊代多少次才會找到，因此可以在model上「給予誤差臨界值的限制」，讓model在誤差的變化小到一定程度時，就知道要停止，以減少多餘的時間、記憶體浪費
   
      
P.S. 要小心，找到的 min 是 local 還是 global
      
#### Source
[[深度學習講中文] 簡單解釋梯度下降法 (Gradient Descent)](https://medium.com/@arlen.mg.lu/%E6%B7%B1%E5%BA%A6%E5%AD%B8%E7%BF%92%E8%AC%9B%E4%B8%AD%E6%96%87-gradient-descent-b2a658815c72)

[機器/深度學習-基礎數學(二):梯度下降法(gradient descent)](https://medium.com/@chih.sheng.huang821/%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92-%E5%9F%BA%E7%A4%8E%E6%95%B8%E5%AD%B8-%E4%BA%8C-%E6%A2%AF%E5%BA%A6%E4%B8%8B%E9%99%8D%E6%B3%95-gradient-descent-406e1fd001f)

[[Day4] 梯度下降法（Gradient Descent）](https://ithelp.ithome.com.tw/articles/10193297?sc=iThelpR)

[線性回歸(Linear Regression)](https://medium.com/@chih.sheng.huang821/%E7%B7%9A%E6%80%A7%E5%9B%9E%E6%AD%B8-linear-regression-3a271a7453e)

[🧫](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)

# Pratices Linear Regression
  > 用套件來實踐 Linear Regression

讓機器透過學習觀察特徵來分類

先匯入相關套件與資料，並將資料由dataframe轉為array

```python
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np

data = pd.read_csv('regression1.csv')
x = data.iloc[:,0].values
y = data.iloc[:,-1].values
```

先將資料進行



[🧬](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)
