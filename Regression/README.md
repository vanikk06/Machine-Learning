# Content
  - [Lecture 3 Regression 拷貝_完整.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/Lecture%203%20Regression%20%E6%8B%B7%E8%B2%9D_%E5%AE%8C%E6%95%B4.pdf)
  - [Class_03.ipynb](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/Class_03.ipynb)
    - [webpage](https://nbviewer.jupyter.org/github/vanikk06/Machine-Learning/blob/master/Regression/Class_03.ipynb)
  - [作業2.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/%E4%BD%9C%E6%A5%AD2.pdf)
    - [作業2_answer.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/%E4%BD%9C%E6%A5%AD2_answer.pdf)  
  - [Class_04.ipynb](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/Class_04.ipynb)
    - [webpage](https://nbviewer.jupyter.org/github/vanikk06/Machine-Learning/blob/master/Regression/Class_04.ipynb)
  - [作業3.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/%E4%BD%9C%E6%A5%AD3.pdf)
    - [作業三.ipynb](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/%E4%BD%9C%E6%A5%AD%E4%B8%89.ipynb)
      - [webpage](https://nbviewer.jupyter.org/github/vanikk06/Machine-Learning/blob/master/Regression/%E4%BD%9C%E6%A5%AD%E4%B8%89.ipynb)
    - [作業3_answer.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/%E4%BD%9C%E6%A5%AD3_answer.pdf)
  - [Correlation coefficient](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#correlation-coefficient)
  - [Linear Regression](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#linear-regression)
  - [Least square method ＆ Gradient descent](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#least-square-method--gradient-descent)
  - [Coefficient of Determination](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#coefficient-of-determination)
  - [Pratices Linear Regression](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#pratices-linear-regression)
  - [Overfitting v.s. Underfitting](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#overfitting-vs-underfitting)
  - [Pratices Polynomial Regression](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#pratices-polynomial-regression)
  - [Normal equation](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#normal-equation)
  - [Pratices Multiple Regression](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#pratices-multiple-regression)


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
  >> 目標變數必為**「連續值」**，不可是類別型、離散型

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

- 直線

  ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-14_03-02-20.png)

  - h<sub>θ</sub>( x ) = θ<sub>0</sub> + θ<sub>1</sub>x
  - θ<sub>0</sub>調整：h<sub>θ</sub>( x ) - y
  - θ<sub>1</sub>調整：( h<sub>θ</sub>( x ) - y )*x
  
- 二項式

  ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-15_02-27-46.png)
  
  - h<sub>θ</sub>( x ) = θ<sub>0</sub> + θ<sub>1</sub>x + θ<sub>2</sub>x<sup>2</sup>
  - θ<sub>0</sub>調整：h<sub>θ</sub>( x ) - y
  - θ<sub>1</sub>調整：( h<sub>θ</sub>( x ) - y )x
  - θ<sub>2</sub>調整：( h<sub>θ</sub>( x ) - y )x<sup>2</sup>
  

梯度下降法是不斷往下找誤差（cost）的最小值，但在找到之前，我們不知道要給model疊代多少次才會找到，因此可以在model上「給予誤差臨界值的限制」，讓model在誤差的變化小到一定程度時，就知道要停止，以減少多餘的時間、記憶體浪費
   
      
P.S. 要小心，找到的 min 是 local 還是 global
      
#### Source
[[深度學習講中文] 簡單解釋梯度下降法 (Gradient Descent)](https://medium.com/@arlen.mg.lu/%E6%B7%B1%E5%BA%A6%E5%AD%B8%E7%BF%92%E8%AC%9B%E4%B8%AD%E6%96%87-gradient-descent-b2a658815c72)

[機器/深度學習-基礎數學(二):梯度下降法(gradient descent)](https://medium.com/@chih.sheng.huang821/%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92-%E5%9F%BA%E7%A4%8E%E6%95%B8%E5%AD%B8-%E4%BA%8C-%E6%A2%AF%E5%BA%A6%E4%B8%8B%E9%99%8D%E6%B3%95-gradient-descent-406e1fd001f)

[[Day4] 梯度下降法（Gradient Descent）](https://ithelp.ithome.com.tw/articles/10193297?sc=iThelpR)

[線性回歸(Linear Regression)](https://medium.com/@chih.sheng.huang821/%E7%B7%9A%E6%80%A7%E5%9B%9E%E6%AD%B8-linear-regression-3a271a7453e)

[🧫](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)

# Coefficient of Determination
  > 決定係數
  
當model訓練好後，要評估model的效能如何

在此 linear regression model主要是要尋找「誤差極小值」，因此可以用 MSE 作評估
- MSE（Mean Squared Error）：均方誤差，可將其視為Cost function
  > 迴歸model的核心，扮演尋找係數的依據
  >> 單獨解讀無法判斷好壞，需透過比較才有意義
 
  
  ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-15_02-58-23.png)
  > MSE愈小，代表預測值與實際值差距愈小
  
  在線性迴歸中
  
  ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-15_03-03-51.png)
  
  ![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-15_03-08-05.png)
  
  - SST：總誤差，為 真實值_y 到 平均值_y 的距離，可分為 SSE 與 SSR
  - SSR：迴歸model可解釋的部分，為 預測值_y 到 平均值_y 的距離  
  - SSE：隨機誤差，為 真實值_y 到 預測值_y 的距離
  
  SST = SSR + SSE\
  透過上述式子，可將 SSR 於 SST 中的佔比，理解為一個「標準化後的MSE」，則為R<sup>2</sup>
  > 因其縮至\[0, 1]
  
  R<sup>2</sup>愈高，表示 model 的解釋能力愈好
  - R<sup>2</sup> = 1：表示 model 完全解釋數據
  - R<sup>2</sup> = 0.7 ~ 0.8：表示 model 部分解釋數據
  - R<sup>2</sup> = 0 ：表示 model 完全無法解釋數據
  
#### Source 
[機器學習-線性回歸分析(linear regression)](http://www.taroballz.com/2018/07/16/ML_LinearRegression/)

[如何預測資料：迴歸模型的評估](https://medium.com/datainpoint/evaluating-reg-e993ce27b61)

[💉](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)


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

先將資料特徵進行 normalization 處理，讓特徵資料（X）不改變原始分佈的按比例縮放，讓資料落在某一特定區間
> 使用`sklearn.preprocessing`套間中的`StandardScaler`函式
```python
from sklearn.preprocessing import StandardScaler

sc_x = StandardScaler()
x1 = x.reshape(-1,1)

X_std = sc_x.fit_transform(x1)
```
> 小心，fit_transform()的input格式為2-D array

- `StandardScaler()`：標準化，能夠計算訓練數據的平均值和標準差，從而在訓練數據集上再次使用
  > 平均值為 0；單位為標準差
  
  - 標準化：在此為「減掉平均值，再除以標準差」，有就是去除均值，再按標準差比例縮放

- `np.reshape(newshape)`：改變array形狀，不改變內部元素
  - newshape：新形狀
    - int：1-D array
    - int of ints：(row, col)
      > 新形狀的元素個數，要等於原array的元素個數
      >> -1：自動計算

- `sc_x.fit_transform()`：執行訓練並轉化
  > input：2-D array

接著再建立線性迴歸model
> 使用`sklearn.linear_model`套件中的`LinearRegression`函式
```python
from sklearn.linear_model import LinearRegression

lr = LinearRegression()
lr.fit(X_std, y)
y_pred = lr.predict(X_std)
```
- `LinearRegression()`：實例化
- `lr.fit(X_std, y)`：訓練/擬合model
    - X_std：特徵變數
    - y：目標變數
- lr.predict(X_std)：將資料放入model中進行預測


查看訓練出的迴歸線係數
```python
print('Slope: %.3f' % lr.coef_[0])
print('Intercept: %.3f' % lr.intercept_)
#輸出
Slope: 95.564
Intercept: 428.600
```
- `lr.coef_[0]`：斜率（θ<sub>1</sub>）
- `lr.intercept_`：截距（θ<sub>0</sub>）
    - `%.3f`：字串化格式
      - %：操作符，可將資料格式化
        > 基本語法`'' % ('')`
        >> [Learning more](https://www.footmark.info/programming-language/python/python-string-format/)
      - f：浮點數
      - .3：小數點後三位

畫出資料的散佈圖與迴歸線來看彼此的關係
```python
plt.scatter(X_std, y)
plt.plot(X_std, y_pred, 'c')
```
用 MSE 與 R<sup>2</sup> 來評估model
> 使用`sklearn.metrics`套件
```python
import sklearn.metrics as sm

print('MSE: %.3f' % sm.mean_squared_error(y, y_pred))
print('R^2: %.3f' % sm.r2_score(y, y_pred))
#輸出
MSE: 978.262
R^2: 0.903
```
> model 只能解釋90.3%的銷售收入變因

- `sm.mean_squared_error(y, y_pred)`：均方誤差迴歸損失，拿 model預測值 與 真實值 比較
    - y：真實數據的目標變數
    - y_pred：model的預測值
- `sm.r2_score(y, y_pred)`：測量 x 對 y 的解釋程度，也就是預測值 y 的變異中，有多少百分比可以由 x 解釋
  > 最佳為 1\
  > 有可能為負

#### Source
[sklearn中的数据预处理](http://d0evi1.com/sklearn/preprocessing/)

[Day13-Scikit-learn介紹(5)_ Linear-Regression](https://ithelp.ithome.com.tw/articles/10206114)

[Python 字串格式化](https://www.footmark.info/programming-language/python/python-string-format/)

[🧬](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)


# Overfitting v.s. Underfitting

model主要利用training set訓練，以期待可以使用歷史數據，進行預測

- Overfitting：model 過度擬合訓練集的特徵，導致 model 失去泛化能力

- Underfitting：model 擬合不足，model 沒有學好訓練集的特徵，導致 model 無法進行預測

#### 如何判斷Overfitting??
可將 data set 分割為 training set 與 testing set
1. training set：建立model
2. testing set：預測，以評估model

- Overfitting 發生情形
  - train MSE < test MSE
    > MSE愈小愈好
  - train R<sup>2</sup> > test R<sup>2</sup>
    > R<sup>2</sup>愈接近 1 愈好


[💊](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)

#  Pratices Polynomial Regression
   > 二項式線性回歸
   >> 通過增加 x 的高次項，對數據進行逼近

- Polynomial Regression：數據分佈為曲線，而非直線

要進行多項式函數的線性迴歸前，要先對特徵變數做些處理，讓其增加二次項

使用`sklearn.preprocessing`套件的`PolynomialFeatures`函式
```python
from sklearn.preprocessing import PolynomialFeatures

quadratic = PolynomialFeatures(degree=2)
x_quad = quadratic.fit_transform(X_std)
```
- `PolynomialFeatures(degree=2, interaction_only=False)`：實例化，專門生成「多項式特徵」，並且多項式包含的是相互影響的特徵集
   > 要指定「函式維度」
   >> [Learning more](https://www.itread01.com/content/1541737027.html)
   - degree：多項式階數，預設為2
   - interaction_only：是否只找互動作用的多項式
     > 預設False
     >> 互動作用：與他者互動\
     - interaction_only = True：\[1, a, b, a<sup>2</sup>, ab, b<sup>2</sup>] 會變成僅有 \[1, a, b, ab]
       > 無自己與自己互動的情形
- `quadratic.fit_transform(X_std)`：將數據放入model轉換
  > 可轉換為 x 內積 θ
  >> 在此為 h<sub>θ</sub>( x ) = θ<sub>0</sub> + θ<sub>1</sub>x + θ<sub>2</sub>x<sup>2</sup> 為 三維向量
  - input：2-D array
  
  產生一個二項式的係數
  ```python
  x = np.arange(4)
  x = x.reshape(-1,1)
  x
  #輸出
  array([[0],
         [1],
         [2],
         [3]])
  ```
  將資料格式每row為 \[a] 的 x 放入
  ```python
  poly = PolynomialFeatures(2)
  poly.fit_transform(x)
  #輸出
  array([[1., 0., 0.],
         [1., 1., 1.],
         [1., 2., 4.],
         [1., 3., 9.]])
  ```
  > 會生成 \[1, a, a<sup>2</sup>]的資料
  
  改成生成三項式的係數
  ```python
  poly = PolynomialFeatures(3)
  poly.fit_transform(x) 
  #輸出
  array([[ 1.,  0.,  0.,  0.],
         [ 1.,  1.,  1.,  1.],
         [ 1.,  2.,  4.,  8.],
         [ 1.,  3.,  9., 27.]])
  ```
  > 生成 \[1, a, a<sup>2</sup>, a<sup>3</sup>]
  
  將每row的資料格式更改 \[a, b]
  ```python
  y = np.arange(4).reshape(2,2)
  y
  #輸出
  array([[0, 1],
         [2, 3]])
  ```
  ```python
  poly = PolynomialFeatures(2)
  poly.fit_transform(y)
  #輸出
  array([[1., 0., 1., 0., 0., 1.],
         [1., 2., 3., 4., 6., 9.]])
  ```
  > 生成 \[1, a, b, a<sup>2</sup>, ab, b<sup>2</sup>]
  
  更改參數，僅有他者互動作用的參數
  ```python
  poly = PolynomialFeatures(2, interaction_only=True)
  poly.fit_transform(y)
  #輸出
  array([[1., 0., 1., 0.],
         [1., 2., 3., 6.]])
  ```
  > 生成 \[1, a, b, ab]
  >> 不存在自己與自己互動的情形\
  >> E.g. a<sup>2</sup>、b<sup>2</sup>
  
  
放入線性迴歸模型做訓練
```python
pr = LinearRegression()
pr.fit(x_quad, y)
y_quad_pred = pr.predict(x_quad)

print('theta1: %.3f' % pr.coef_[1])
print('theta2: %.3f' % pr.coef_[2])
print('Intercept: %.3f' % pr.intercept_)
#輸出
theta1: 97.133
theta2: 22.623
Intercept: 405.977
```
- `pr.coef_[1]`：x係數
- `pr.coef_[2]`：x<sup>2</sup>係數
  > pr.coef_\[0]：預設為1，因其可還原為 x 內積 θ
- `pr.intercept_`：截距


評估模型
```python
print('MSE: %.3f' % sm.mean_squared_error(y, y_quad_pred))
print('R^2: %.3f' % sm.r2_score(y, y_quad_pred))
#輸出
MSE: 377.582
R^2: 0.963
```

#### Source
[Day13-Scikit-learn介紹(5)_ Linear-Regression](https://ithelp.ithome.com.tw/articles/10206114)

[Sklearn-preprocessing.PolynomialFeatures](https://www.itread01.com/content/1541737027.html)

[🔬](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)


# Normal equation
  > 正規方程式
  >> cost function轉為矩陣，對矩陣微分，推倒最小值
  
在機器學習中，如果想要求得線性迴歸的參數，可以使用梯度下降法（Gradient Descent）或正規方程式（Normal Equation），來尋找讓 Cost Function 達到最小值的最佳參數

多元線性迴歸可用下列式子用兩變數之間的關係表示，可視為兩項量內積
![](https://github.com/vanikk06/Machine-Learning/blob/master/Regression/image/Snipaste_2020-02-17_03-08-32.png)  
 
Normal equation是將 cost function 轉成矩陣的形式，透過對其做一階偏微分，找cost function矩陣最小值時的迴歸係數

#### Gradient descent v.s. Normal equation
  
- 是否設定 learning rate（學習率）
  - Gradient descent：需設定學習率，學習率選擇的過程通常需要跑數次資料來決定（需要多次的疊代）
    > 學習率的大小會影響到下降的收斂速度，若選擇失當，有可能造成發散
  - Normal equation：不須設定學習率，也不須疊代運算
  
- Normal equation 需要計算「反矩陣」，當自變數的數目非常多時，矩陣的維度會變大，導致時間複雜度增加，這時使用 Gradient descent 會相對快速
  > 當自變數不多時，使用 Normal equation 是相對經濟的選擇
 
#### Source
[Normal Equation（正規方程式）](https://medium.com/@gatorsquare/ml-normal-equation-%E6%AD%A3%E8%A6%8F%E6%96%B9%E7%A8%8B%E5%BC%8F-9f1c09de4217)

[⚖](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)

# Pratices Multiple Regression
  > 多元迴歸、複迴歸

特徵變數為一個以上

載入糖尿病數據集
```python
from sklearn.datasets import load_diabetes

data = load_diabetes()
data.keys()
#輸出
dict_keys(['data', 'target', 'DESCR', 'feature_names', 'data_filename', 'target_filename'])
```
- `load_diabetes()`：實力化資料集
   - 十個特徵變數（已標準化）
     - Age
     - Sex
     - Body mass index（BMI）
     - Average blood pressure：平均血壓
     - S1 ~ S6：6種生理數據
   - 目標變數：一年後病情發展狀況
- `data.keys()`：顯示所有的key值

將資料取出放入dataframe
```python
import pandas as pd

feature = pd.DataFrame(data['data'], columns = data['feature_names'])
target = pd.DataFrame(data['target'], columns = ['target'])
df = pd.concat([feature, target], axis = 1)
```
- `pd.DataFrame(data, columns)`：建立dataframe
    - data：放入dataframe的資料
    - columns：欄位名稱（行）
      > 可使用list多欄給予，也可自行指定
        - 自行指定：list格式
          ```python
          columns = ['target']
          ```

- `pd.concat(objs, axis, join, join_axes, ignore_index)`：合併dataframe
    - objs：合併對象
      > list格式
    - axis：合併方向
      - axis=0：按row方向合併，直向合併（上下）
      - axis=1：按column方向合併，橫向合併（左右）
    - join：連接方式，有兩種模式
      - outer：預設，直接將空的資料，用NaN填補
      - inner：直接將空的資料刪除
    - join_axes：橫向合併時，指定index
      > E.g. join_axes = \[df1.index]
    - ignore_index：合併時，可忽略舊的index欄位，改用自動產生的新index
      > 預設True

多變量圖，觀察變數之間彼此的分佈關係
> 散佈圖 + 直方圖
```python
import matplotlib.pyplot as plt
import seaborn as sns

cols = ['age', 'bmi','s1', 's5', 'target']
sns.pairplot(df[cols])
plt.tight_layout()

plt.savefig('scatterplot.png', dpi=300)
```
- `seaborn`：多維繪圖的套件
- `sns.pairplot(變數, hue, palette)`：多變量圖，繪製成對關係
   > 對角線：直方圖
    - hue：分群，進一步區分不同變數
    - palette：顏色主題
- `plt.tight_layout()`：避免圖重疊，將其分開
- `plt.savefig(圖片名稱, 解析度)`：儲存圖檔

熱度圖（Heat map），畫出相關係數矩陣（correlation matrix）
```python
import numpy as np

cm = np.corrcoef(df[cols].values.T) 
sns.set(font_scale=1.5)
hm = sns.heatmap(cm, cbar=True, annot=True, square=True, fmt='.2f', annot_kws={'size':15}, yticklabels=cols, xticklabels=cols)

plt.tight_layout()
plt.savefig('correlation.png', dpi=300)
```
> 相關性愈低，顏色愈深

- `dataframe.values`：將dataframe轉為array
- `array.T`：轉置，column變為row，row變為column
  > \[row, column]
  >> E.g. 將原始資料由 441x5 轉為 5x441
- `np.corrcoef()`：相關係數，返回變數之間相關關係密切程度的指標
  > input：2-D array
  >> 以 row 為變量/欄位，column 為每個觀測值/每筆資料（所以需要**轉置**）
- `sns.set(font_scale)`：設置美學參數
  - font_scale：獨立縮放字體元素大小
- `sns.heatmap(data, cbar, annot, square, fmt, annot_kws, yticklabels, xticklabels)`：熱度圖，畫出相關係數矩陣
  - data：可為 array 或 dataframe
    > 若為dataframe，其 row（index）/ column 會分別對應到 heatmap 的 column / row
  - cbar：是否在 heatmap 測邊繪製顏色刻度圖
    > 預設為 True
  - annot：是否在每個方格內寫入資料
    > 預設為 False
    >> 若data為array（矩陣），會填入對應位置的資料
  - square：設定方格為方形
    > 預設為 False，原為長方形
  - fmt：字串格式
    > .2f：浮點數，到小數點後兩位
  - annot_kws：方格上數字的大小、顏色、字型
    > input為{ }
  - xticklabels：x軸標籤名輸出
  - yticklabels：y軸標籤名輸出
  
將 data set 分割為 training set 與 testing set 
```python
from sklearn.datasets import load_diabetes
from sklearn.model_selection import train_test_split

X, y = load_diabetes().data, load_diabetes().target
X_train, X_test, y_train, y_test = train_test_split(X, y, random_state=8)
```
- `load_diabetes().data`：糖尿病資料集的特徵資料集
- `load_diabetes().target`：糖尿病資料集的目標資料集
- `train_test_split(data, target, random_state)`：從樣本中隨機的按比例選取 train data 與 test data
    - data：要分割的樣本特徵集（feature dataset）
    - target：要分割的目標函數集（target dataset）
    - random_state：隨機數的種子

訓練迴歸模型，並計算 MSE 跟 R<sup>2</sup>
> 線性迴歸，目標變數必為連續值
```python
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
from sklearn.metrics import r2_score

slr = LinearRegression()

slr.fit(X_train, y_train)
y_train_pred = slr.predict(X_train)
y_test_pred = slr.predict(X_test)

print('MSE_train: %.3f, MSE_test: %.3f' % (mean_squared_error(y_train, y_train_pred), mean_squared_error(y_test, y_test_pred)))
print('R^2_train: %.3f, R^2_test: %.3f' % (r2_score(y_train, y_train_pred), r2_score(y_test, y_test_pred)))
#輸出
MSE_train: 2812.369, MSE_test: 3108.041
R2_train: 0.530, R2_test: 0.459
```
> 由 MSE 與 R<sup>2</sup>可以看出，此模型發生了 overfitting\
> 因 training data 的 MSE 低於 testing data\
>  因 training data 的 R<sup>2</sup> 高於 testing data

- y_train_pred：模型預測training data的結果
- y_test_pred：模型預測testing data的結果


在多變數的線性迴歸中，線性迴歸模型要求解釋能力，也就是預測因子（特徵變數
）對結果（目標變數）之間的影響，在處理時有以下幾點要注意
> 模型解釋能力：改善哪個因子時，對結果是有比較大的幫助的

- Note 1：X要先標準化
  > 去除單位的影響
- Note 2：迴歸係數數值愈大，表示對y的影響力愈大
  > 迴歸係數：權重，當其他預測因子存在的情況下，該預測因子的強度
  >> 前提，要小心預測因子之間是否會互相影響（確保因子是相互獨立的），否則會產生「共線性問題」
- Note 3：迴歸係數為負，表示負相關

關於「共線性問題」，其發生的原因為迴歸係數中的變數彼此之間有相關關係，因而導致迴歸係數被扭曲
 > E.g. "正相關"變為"負相關"

- 處理方式
  - 資料預處理：解決因子之間的相互關係
      - 資料轉換
        > E.g. 取兩變數的平均值 → 產生另一個變數
      - 只留下獨立（不相關）變數
  - 脊迴歸（ridge regression）
  - 主成分分析（principal component analysis）：PCA，留下主要成份（降維、維度縮減）

[🔭](https://github.com/vanikk06/Machine-Learning/tree/master/Regression#content)  
