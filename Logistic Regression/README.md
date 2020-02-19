# Content
- [Lecture 4 Logistic Regression 拷貝.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/Lecture%204%20Logistic%20Regression%20%E6%8B%B7%E8%B2%9D.pdf)
- [Logistic Regression](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#logistic-regression)


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
  > 轉換連續值的function
  
![](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/image/Snipaste_2020-02-20_03-04-40.png) 
![](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/image/Snipaste_2020-02-20_03-05-10.png)
> exp()：次方的部份
