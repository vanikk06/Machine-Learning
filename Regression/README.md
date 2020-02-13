# Content
  
  - [Correlation coefficient](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#correlation-coefficient)
  - [Linear Regression](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#linear-regression)


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

尋找數據背後隱藏的函式，也就是數據背後統一一致的規則

線性模型：點與線之間距離最短
 > 線性函數：y = ax + b
 >> ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-13_04-14-05.png)
 
- Machine learning：利用 data 計算假設 g，讓其近似目標 f
  - Step 1. 收集訓練資料
  - Step 2. 設計數學模型
  - Step 3. 找出具最佳參數之模型

[🧪](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)

# Least square method ＆ Gradient descent
  > 「最小平方法」與「梯度下降法」

利用「最小平方法」與「梯度下降法」找出最佳的回歸線
- Least square method：目的是為了尋找**最小**的cost function
  > P.S. 距離的計算「平方」會優於「絕對值」
  >> 因為在尋找「最佳化」函數時，會使用微積分的方式，絕對值微分的話，在0會突然變化劇烈
  （sharp），不利於判斷
  
  
  
  
  
#### Source

[🧫](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)
