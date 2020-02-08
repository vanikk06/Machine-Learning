# Content
- [Attributes](https://github.com/vanikk06/Machine-Learning/tree/master/Data#attributes)
- [Symmetric vs. Skewed Data](https://github.com/vanikk06/Machine-Learning/tree/master/Data#symmetric-vs-skewed-data)
- [Basic Statistical Descriptions](https://github.com/vanikk06/Machine-Learning/tree/master/Data#basic-statistical-descriptions)
- [Machine Learning Process](https://github.com/vanikk06/Machine-Learning/tree/master/Data#machine-learning-process)

# Attributes
  > 屬性
  >> or dimensions（維度）、features（特徵）、variables（變數）
  
 A data field, representing a characteristic or featurbe of a data object.
  > E.g. ID、name、address
  
  
#### § 種類 §

![](https://github.com/vanikk06/Machine-Learning/blob/master/Data/image/Snipaste_2020-02-06_23-13-16.png)

- Non-numeric：非數值型
  - Nominal：類別尺度，種類（categories）、狀態（states）或事物名稱（names of things）
    > E.g. red、blue
      - Binary：二進制，特徵僅有「兩個狀態」，0和1
        > 特殊的Nominal案例
  - Ordinal：順序尺度，值與值之間為有意義的順序（有優劣、先後區分），但連續值之間的大小關係未知
    > E.g. freshman、sophomore、junior、senior
  
- Numeric：數值型
  >  Quantity，以可否進行數學運算作區分
  >> 主要用於**迴歸分析**
  
  - Interval-scaled：區間尺度（等距）
    > 意義可加減、不可乘除
    >> E.g. 100 ℃\
    >> 溫度0 ℃時仍然有溫度，所以乘除是沒意義的
      1. 以**相同大小的單位**進行度量
      2. 值有排序
  - Ratio-scaled：比率尺度（等比）
    > 可除法，倍數有意義
    >> E.g. 100 m
      1. 具固有的零點
      2. 值之間可明確的進行數量級的比較
         > E.g. 10m是5m的兩倍

[🦢](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)

# Symmetric vs. Skewed Data
  > 正態分佈 與 偏態分佈
 

![](https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2017/04/30195702/Stats1.png)

- normal distribution：正態分佈，資料呈「對稱」分佈
  > mean、median、mode相同
- skewed distribution：偏態分佈
  > 左右以尾部判斷
  >> mean：落在約「底部面積一半」的位置
    - negatively skewed distribution：負偏態，又稱 left skewed distribution（左偏態），資料大多集中於右側
      > Mode > Median > Mean
    - positively skewed distribution：正偏態，又稱 right skewed distribution（右偏態），資料大多集中於左側
      > Mean > Median > Mode

#### Source
[Analytics Vidhya](https://www.analyticsvidhya.com/blog/2017/05/41-questions-on-statisitics-data-scientists-analysts/stats1/)

[正態分佈（normal distribution）與偏態分佈（skewed distribution）](https://www.itread01.com/content/1542005346.html)

[🕊](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)

# Basic Statistical Descriptions
  > 基本統計描述
  
- Histogram：直方圖，x軸為值（values），y軸為次數、頻率（frequencies）
  > 連續型資料
  >> 長條間黏在一起
- Boxplot：盒鬚圖，由五個數組成，又稱「五數綜合圖」
  > [✍🏼](https://github.com/vanikk06/Machine-Learning/tree/master/Data#-boxplot-)
    - 最大值（Max）
    - 最小值（min）
    - 四分位數：資料由小到大排序
        - Q1：25%
        - Q2：50%（中位數）
        - Q3：75%
- Scatter plot：散佈圖，每對值為一對座標，並在平面中繪製為點
- 常用距離公式
    - 歐幾里得（Euclidean）距離：平方＆根號
    - 曼哈頓（Manhattan）距離：絕對值
    - 名可夫斯基（Minkowski）距離：通式

#### § Boxplot §

- IQR（四分位距）：Q3 - Q1
- 離群值：範圍為「小於Q1 - 1.5IQR」的值與「大於Q3 + 1.5IQR」的值

```python
sum( )/4    #Q1

sum( )/2    #Q2

sum( )/4*3  #Q3
```

[🦅](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)


# Machine Learning Process
  > 機器學習步驟
  
- **Step 1. 準備資料（包含資料愈處理）**
  
  [Exercise](https://github.com/vanikk06/Machine-Learning/tree/master/Data#-%E6%BA%96%E5%82%99%E8%B3%87%E6%96%99-)

- **Step 2. 選擇演算法**

  [Exercise](https://github.com/vanikk06/Machine-Learning/tree/master/Data#-%E9%81%B8%E6%93%87%E6%BC%94%E7%AE%97%E6%B3%95-)

- **Step 3. 調整參數**

  [Exercise](https://github.com/vanikk06/Machine-Learning/tree/master/Data#-%E8%AA%BF%E6%95%B4%E5%8F%83%E6%95%B8--%E8%A9%95%E4%BC%B0%E7%B5%90%E6%9E%9C-)

- **Step 4. 評估結果**

  [Exercise](https://github.com/vanikk06/Machine-Learning/tree/master/Data#-%E8%AA%BF%E6%95%B4%E5%8F%83%E6%95%B8--%E8%A9%95%E4%BC%B0%E7%B5%90%E6%9E%9C-)

### § 準備資料 §
> 使用 Iris Data Set（鳶尾花卉數據集）
>> 為150個樣本，屬於鳶尾花下的三個亞屬
>> - 山鳶尾（setosa）
>> - 變色鳶尾（versicolor）
>> - 維吉尼亞鳶尾（virginica）
>>> 各自的四個特徵：花萼（Sepal）和花瓣（Petal）的長度與寬度

- Loading the Data
  ```python
  import pandas as pd

  df = pd.read_csv('iris.csv', header=None, names=names)
  ```
  - `pd.read_csv('檔案名', header, names)`
      - header：檔案是否有欄位名
        > header=None：沒有欄位名
      - names：指定欄位名稱
- Observing the data
  ```python
  df.head()
  
  df.info()
  
  df.describe()
  ```
  - `df.head()`：前五前五筆資料
  - `df.info()`：資料的基本資料（個數、資料類型...）
  - `df.describe()`：基本的統計計算（個數、平均數、標準差...）
  
- Plotting graph 
  > 藉由圖形來輔助我們判斷class及其他特徵關係
  
  - matplotlib.pyplot：python繪圖套件
  - seaborn：matplotlib的補強，以matplotlib建構的高階繪圖套件
  
  ```python
  import matplotlib.pyplot as plt
  import seaborn as sns
  
  plt.style.use('ggplot')
  sns.lmplot("sepal_length", "sepal_width", data=df, fit_reg=False, hue='class')
  ```
  - `plt.style.use()`：指定套用風格、主題
    >  可結合兩種不同的內建風格使用，也可自訂風格
    >> [Learning more](https://medium.com/%E8%B3%87%E6%96%99%E8%A6%96%E8%A6%BA%E5%8C%96/matplotlib-06-%E5%9C%96%E8%A1%A8%E9%A2%A8%E6%A0%BC-d58498069700#2a92)
    
    ```python
    plt.style.use([“bmh”, “dark_background”])
    ```
    - `plt.style.available`：可印出所有可用的內建風格
      
      ```python
      print(plt.style.available)
      ```
  - `sns.lmplot()`：迴歸圖，可直觀地總覽數據的內在關係
    > 必要參數：x、y、data
      - x、y：x軸、y軸要放置的欄位
        > 必須指定為**字符串**
        >> 此種數據格式稱為「長格式」或「整潔」數據
      - data：整個資料變數
      - fit_reg：是否要有迴關線
        > 預設為True
      - hue：分類，定義數據子集
  
 ### § 選擇演算法 §
 
 - Split into train and test
   > 區分training data、testing data，用於交叉驗證
   
   先匯入套件
   ```python
   import numpy as np
   from sklearn.model_selection import train_test_split
   ```
   再將數據從dataframe的資料格式轉換為array，並放入函式中將data set用隨機分配方式，分割為"training set"與"testing set"
   ```python
   x = df.iloc[:,:-1].values
   y = df.iloc[:,4].values
   
   x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.33, random_state=42)
   ```
   > x為特徵變數（class以外的）\
   > y為目標變數（class）
   
   - `df.iloc[row, column]`：選取欄位
      > 參數：index
   - `df.values`：將dataframe轉為array
   -  `train_test_split(x, y, test_size, random_state)`：將x、y按照相同的隨機分配進行切割
        - x：特徵變數
        - y：目標變數
        - test_size：測試集大小
        - random_state：隨機抽取的方式
          > PRG(Pseudo-random- Generator):偽隨機數生成器
   
- Algorithm：K-NN
 
  使用K-NN（k-nearest neighbor）演算法，簡單來說，它假設欲預測點是i，找出離i最近的k筆資料多數是哪一類，以此預測i的類型
  > Given a test instance i, find the k closest neighbors and their labels
Predict i’s label as the majority of the labels of the k nearest neighbors.

  K-NN為監督式學習的一種，適用於「數值型」和「標稱型」
    > 標稱型：目標變數的結果，只有在有限目標集中取值
    >> 主要用於**分類**
    
  Step 1. 確定 k 大小
  
  Step 2. 對於 testing set中的一個樣本，找到 training set 中和它最近的 k 個樣本
  
  Step 3. 將這 k 個樣本的投票結果作為測試樣本的類別（多數決）
  
  - 優點：
      - 精確度高
      - 對離群值不敏感
      - 無資料輸入假定
  - 缺點：
      - 時間與空間複雜度高
      - 訓練模型依賴訓練集，且不可丟棄
  
  ![](https://github.com/vanikk06/Machine-Learning/blob/master/Data/image/Snipaste_2020-02-08_03-14-14.png)
  
  匯入套件，k為用戶定義的參數，為新資料附近的k個鄰居
   > k 的設定很重要，好的 k 能夠讓 training 出來的 model 有足夠的彈性，避免掉 Overfitting 和 Underfitting
   >> - 若 k 為偶數，有可能碰到「無法直接決定類別」的時候，需再針對該狀況作exception handling
   >> - Overfitting：當 k=1 時，會導致過度符合training set的資料特性，使其無法預測較為普遍的資料
   >> - Underfitting：當 k=n （過大）時，預測結果一定是資料數量最多的那類，導致model失去預測能力
  
  ```python
  from sklearn.neighbors import KNeighborsClassifier
  
  knn = KNeighborsClassifier(n_neighbors=3)
  ```
  > 要告知 k 的大小
  
  擬合model並進行預測
  ```python
  knn.fit(x_train, y_train)
  
  pred = knn.predict(x_test)
  ```
  
  - `knn.fit(X, y)`：訓練model，拿training set去訓練model
     > X、y為training data
  - `knn.predict(X)`：預測，將testing set放入由training set訓練出的model中，看model的準確程度
     > X為testing data 
  
  計算模型準確度
  ```python
  from sklearn.metrics import accuracy_score
  
  accuracy_score(y_test, pred)
  ```
  
  - `accuracy_score(y_true, y_pred, normalize=True)`：計算**分類器**的準確率
    > [Learning more](https://blog.csdn.net/CherDW/article/details/55813071)
      - y_true：testing set中 y 的真實資料
      - y_pred：model預測出的 y
      - normalize：是否返回正確的分類比例
          - True：正確的分類比例
          - False：正確的分類樣本數
 
 ### § 調整參數 ＆ 評估結果 §
 
 - cross-validation：交叉驗證
    > 檢驗model方法
    >> 避免model依賴某一特定的training set與testing set產生**偏差**
 
    一般我們會將數據分為training set與testing set，交叉驗證是一種統計學上將樣本切割為多個小子集，以不同分區作為training與testing，並計算不同分區上的平均得分
    
    此次使用K-Fold交叉驗證的方式，使用不同的資料組合來驗證訓練的model
    > E.g. 將資料分為10等份，其中「第一等份」作為testing set，其餘九等份作為training set；\
    下一輪，繼續將「第二等份」作為testing set，剩下的九等份作為training set，重複此動作做10次\
    最後，藉由將10次的準確性（Accuracy）平均，得到的平均值可以做為我們判斷準確度是否偏差的指標
    
    ![](https://i.imgur.com/tLWEE80.png)

    ```python
    from sklearn.model_selection import cross_val_score
    
    scores = cross_val_score(knn, x_train, y_train, cv=10, scoring='accuracy')
    print(scores)
    print(scores.mean())
    #輸出
    [0.91666667 0.72727273 0.90909091 0.81818182 0.9        0.88888889
    1.         1.         0.77777778 0.77777778]
    0.8715656565656567
    ```
    - `cross_val_score(estimator, X, y=None, cv=None, scoring=None)`：對數據集進行指定次數的交叉驗證，並為每次驗證效果評測
       > [Learning more](https://www.itread01.com/content/1541250025.html)
       - estimator：分類器，估計方法對象
       - X：特徵變數（features）
       - y：目標變數（Labels）
       - cv：分幾組
       - scoring：分數計算方法
         - accuracy：顯示準確度高不高
           > 愈高愈好


    交叉檢驗為驗證model的方法，而此次model是依照K-NN演算法去訓練出的，用戶自行設定的 k 也會影響到 model 的好壞，帶入不同的 k 進行交叉檢驗，看哪個模型的分數較高，以此找出最適當的 k
    
    ```python
    neighbors = [x for x in range(1,50) if x%2 != 0]
    cv_scores = []
    
    for k in neighbors:
      knn = KNeighborsClassifier(n_neighbors=k)
      scores = cross_val_score(knn, x_train, y_train, cv=10, scoring='accuracy')
      cv_scores.append(scores.mean())
    ```
    > cv_scores為不同model（由不同 k 訓練）各自的準確度平均

    - changing to misclassification error：分類錯誤
      > MSE：均方誤差，預測值與真實值之間差異的均方值(大小)
      
      ```python
      MSE = [1-x for x in cv_scores]
      ```
      
    - determining best k：找出最佳的 k
      
      ```python
      optimal_k = neighbors[MSE.index(min(MSE))]
      
      print("The optimal number of neighbors is %d" % optimal_k)
      #輸出
      The optimal number of neighbors is 7
      ```
        - `index(x, start, end)`：list中第一個匹配的值
            - x：查找的對象
            - start, end：開始結束的範圍
        - 格式化操作
        
          ```python
          print("I'm %s. I'm %d years old." % ("kid", 18))
          print("Hi, %s. I'm %s" % ('mom', 'kid'))
          #輸出
          I'm kid. I'm 18 years old.
          Hi, mom. I'm kid
          ```
           - %s：字符串
           - %d：十進位制整數
           
     - plot misclassification error vs. k：畫出「分類誤差」與「k」之間的折線圖
     
       ```python
       plt.plot(neighbors, MSE)
       plt.xlabel('Number of neighbors k')
       plt.ylabel('Misclassification Error')
       ```
       > 由圖可看出，當 k 數字大到一定程度時，model分類的錯誤率也會愈來愈高

#### Source   
[10分钟python图表绘制 | seaborn入门（四）：回归模型lmplot](https://zhuanlan.zhihu.com/p/25909753)
 
[Seaborn(sns)官方文档学习笔记（第四章 线性关系的可视化）](https://zhuanlan.zhihu.com/p/27593869)
 
[[Matplotlib-06]圖表風格](https://medium.com/%E8%B3%87%E6%96%99%E8%A6%96%E8%A6%BA%E5%8C%96/matplotlib-06-%E5%9C%96%E8%A1%A8%E9%A2%A8%E6%A0%BC-d58498069700)
 
[train_test_split用法](https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/37690/)
 
[k近邻--一个懒惰学习算法](https://ljalphabeta.gitbooks.io/python-/content/knn.html)
  
[kNN分類演算法](https://medium.com/@NorthBei/machine-learning-knn%E5%88%86%E9%A1%9E%E6%BC%94%E7%AE%97%E6%B3%95-b3e9b5aea8df)
 
[機器學習：KNN分類演算法！](https://ithelp.ithome.com.tw/articles/10197110)
  
[sklearn.metrics中的评估方法介绍（accuracy_score, recall_score, roc_curve, roc_auc_score, confusion_matrix）](https://blog.csdn.net/CherDW/article/details/55813071)
 
[sklearn 中的交叉驗證](https://www.itread01.com/content/1541250025.html)

[sklearn中的cross_val_score()函数参数](https://blog.csdn.net/Asher117/article/details/87617702)

[交叉驗證(Cross-validation, CV)-K-fold CV](https://medium.com/@chih.sheng.huang821/%E4%BA%A4%E5%8F%89%E9%A9%97%E8%AD%89-cross-validation-cv-3b2c714b18db#681e)

[機器學習：交叉驗證！](https://ithelp.ithome.com.tw/articles/10197461)
 
[機器/深度學習: 基礎介紹-損失函數(loss function)](https://medium.com/@chih.sheng.huang821/%E6%A9%9F%E5%99%A8-%E6%B7%B1%E5%BA%A6%E5%AD%B8%E7%BF%92-%E5%9F%BA%E7%A4%8E%E4%BB%8B%E7%B4%B9-%E6%90%8D%E5%A4%B1%E5%87%BD%E6%95%B8-loss-function-2dcac5ebb6cb) 
 
[🦃](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)

# Data Pre-processing
  > 資料預處理
