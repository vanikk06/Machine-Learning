# Content
- [Attributes](https://github.com/vanikk06/Machine-Learning/tree/master/Data#attributes)
- [Symmetric vs. Skewed Data](https://github.com/vanikk06/Machine-Learning/tree/master/Data#symmetric-vs-skewed-data)
- [Basic Statistical Descriptions](https://github.com/vanikk06/Machine-Learning/tree/master/Data#basic-statistical-descriptions)
- [Machine Learning Process](https://github.com/vanikk06/Machine-Learning/tree/master/Data#machine-learning-process)
- [Data Pre-processing](https://github.com/vanikk06/Machine-Learning/tree/master/Data#data-pre-processing)
    - [Data description](https://github.com/vanikk06/Machine-Learning/tree/master/Data#data-description)
    - [Data cleaning](https://github.com/vanikk06/Machine-Learning/tree/master/Data#data-cleaning)
    - [Data integration](https://github.com/vanikk06/Machine-Learning/tree/master/Data#data-integration)
    - [Data transformation](https://github.com/vanikk06/Machine-Learning/tree/master/Data#data-transformation)
    - [Data reduction](https://github.com/vanikk06/Machine-Learning/tree/master/Data#data-reduction)
- [fit and transform](https://github.com/vanikk06/Machine-Learning/tree/master/Data#fit-and-transform)
- [Pandas map()、apply() and applymap()](https://github.com/vanikk06/Machine-Learning/tree/master/Data#pandas-mapapply-and-applymap)

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
   > 驗證model
   >> 區分training data、testing data，用於交叉驗證
   
   進行model驗證的一個重要目的，是要選出一個適合的model，對監督式學習而言，我們希望model**對於未知數據的泛化能力強**
   
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
  > K-NN：物以類聚
 
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
  - `knn.predict(X)`：預測，將testing set放入由training set訓練出的model中，看model的準確程度（預測表現能力）
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
    > 檢驗model方法，協助調節參數
    >> 避免model依賴某一特定的training set與testing set產生**偏差**
 
    一般我們會將數據分為training set與testing set，交叉驗證是一種統計學上將樣本切割為多個小子集，以不同分區作為training與testing，並計算不同分區上的平均得分
    
    此次使用K-Fold交叉驗證的方式，使用不同的資料組合來驗證訓練的model
    > E.g. 將資料分為10等份，其中「第一等份」作為testing set，其餘九等份作為training set；\
    下一輪，繼續將「第二等份」作為testing set，剩下的九等份作為training set，重複此動作做10次\
    最後，藉由將10次的準確性（Accuracy）平均，得到的平均值可以做為我們判斷準確度是否偏差的指標
    
    ![](https://i.imgur.com/tLWEE80.png)

    ```python
    from sklearn.model_selection import cross_val_score
    
    scores = cross_val_score(knn, x, y, cv=10, scoring='accuracy')
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
       - X：特徵變數（features），需放入完整資料
       - y：目標變數（Labels），需放入完整資料
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
      scores = cross_val_score(knn, x, y, cv=10, scoring='accuracy')
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

[cross_val_score交叉验证及其用于参数选择、模型选择、特征选择](https://blog.csdn.net/weixin_38536057/article/details/78702564)
 
[機器/深度學習: 基礎介紹-損失函數(loss function)](https://medium.com/@chih.sheng.huang821/%E6%A9%9F%E5%99%A8-%E6%B7%B1%E5%BA%A6%E5%AD%B8%E7%BF%92-%E5%9F%BA%E7%A4%8E%E4%BB%8B%E7%B4%B9-%E6%90%8D%E5%A4%B1%E5%87%BD%E6%95%B8-loss-function-2dcac5ebb6cb) 
 
[🦃](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)

# Data Pre-processing
  > 資料預處理

在真實世界中的資料是**不乾淨的（Dirty）**，再進行分析之前，必須先對資料做些處理，否則會分析出的結果
> garbage in, garbage out（GIGO）
>> 沒有高品質的資料，就沒有高品質的探勘結果

- 不乾淨的資料可能出現的問題
    1. 不完整（Incomplete）：缺少「屬性值」或「某些有價值的屬性」，也可能「僅包含聚集資料」
       > E.g. 職業=' ', 公司人數=20（公司人數為聚集資料，而無公司人員資料）
    2. 有雜訊（Noise）：包含「錯誤」或「離異值/離群值」
    3. 不一致（Inconsistent）：資料本身或命名上不一致


- 在資料預處理中，主要包含四項工作
    - 資料清理(Data Cleaning)：
      > [✍🏻](https://github.com/vanikk06/Machine-Learning/tree/master/Data#data-cleaning)
        - 填入**遺失值**
        - 找出且移除**離異值（雜訊）**
        - 解決**不一致**
    - 資料整合(Data Integration)：整合**不同來源**的資料庫或檔案
      > [✍🏼](https://github.com/vanikk06/Machine-Learning/tree/master/Data#data-integration)
    - 資料轉換(Data Transformation)：**標準化**與**聚合**
      > [✍🏾](https://github.com/vanikk06/Machine-Learning/tree/master/Data#data-transformation)
    - 資料縮減(Data Reduction)：降低資料量的大小，並預期能獲得相同或近似的分析結果
      > [✍🏿](https://github.com/vanikk06/Machine-Learning/tree/master/Data#data-reduction)

[🐓](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)

## Data description 
   > 資料描述
   
若要資料預處理成功，對資料有**全盤的概念**是很重要的

- Descriptive Data Summarization：敘述資料彙總，用於說明資料整體特性，並指出哪些資料值為雜訊或離異值

    主要想知道的資料整體特性：
    > 統計資訊
    
    - 主要傾向
        - Mean：平均數
        - Mediam：中位數
        - Mode：眾數            
    - 資料散佈
        - Quartiles：四分位數
        - Variance：變異數

[🐓🐓](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)


## Data cleaning
   > 資料清理
   
- 填補**遺失值**
  > [✍🏼](https://github.com/vanikk06/Machine-Learning/tree/master/Data#-missing-value-)
- 找出**Outliers**並淡化（平滑）雜訊
  > [✍🏻](https://github.com/vanikk06/Machine-Learning/tree/master/Data#-noisy-data-)
- 修正資料的**不一致**
- 解決資料整合所造成的**重複**


#### § Missing value §

通常在進行分類時，值組的類別資料有可能是遺失的狀況，當對分析結果有重大影響的資料屬性存在遺失值時，分析效果會很差

- Method 1：忽略
    > 不是很有效，除非許多值組的屬性包含遺失值
- Method 2：**人工方式**填入遺失值
    > 費時且不實際
- Method 3：自動填入
    - 利用**全域常數（Global Constant）**
      > E.g. "未知", "±∞"
    - 使用**平均值、中位數或眾數**
        - 數值型：平均數
          > 確保無極端值
        - 順序型：中位數
        - 類別型：眾數
    - 使用**相同類別值組的屬性平均值**
      > 資料類型為數值型
    - 使用**最有可能的值**：可透過迴歸、貝氏理論等推論式工具，或決策樹推論來決定
    
   機器學習的model是利用**空間中的距離**來做迴歸或是分類，若資料中有缺值，就無法在空間中表現位置，需要處理

    ```python
    import pandas as pd

    df = pd.read_csv('data.csv')
    ```

   查看是否有遺失值
    ```python
    df.isnull()

    df.isnull().sum() #總合
    ```
     - `df.isnull()`：是否為空值/遺失值
        > 回傳布林值的dataframe
        
   刪除遺失值
     ```python
     df.dropna(axis=0) #row
     
     df.dropna(axis=1) #column
     
     df.dropna(how='all') #指定
     
     df.dropna(subset=['C'])  #刪掉C內有missing value的row
     ```
     - `df.dropna(axis, how, subset, inplace)`：移除遺失值
        - axis：按何方向
            - axis=0：預設，按**row方向**刪除
              > 含有遺失值的row會被刪除
              >> 一般處理遺失值，不太會將整筆資料刪除
            - axis=1：按**column方向**刪除
              > 含有遺失值的column會被刪除
        - how：指定刪除條件
            - any：預設，只要含有遺失值，即刪除那row或column
            - all：當全部資料為遺失值時，即刪除那row或column
        - subset：指定特定特徵
        - inplace：是否改變原始資料
          > 預設為False
          
   填補遺失值
     ```python
     df.fillna(0) #補上固定值
     ```
     - `df.fillna()`：補上遺失值
   
   使用`sklearn.preprocessing`套件內的 Imputer 來訓練 model 以填補遺失值
     ```python
     from sklearn.preprocessing import Imputer
      
     imr = Imputer(missing_values='NaN', strategy = 'mean', axis=0) 
     imr = imr.fit(df.values)
     imputed_data = imr.transform(df.values)
     imputed_data
     #輸出
     array([[ 1. ,  2. ,  3. ,  4. ],
            [ 5. ,  6. ,  7.5,  8. ],
            [ 0. , 11. , 12. ,  6. ]])
     ```
     - `Imputer(missing_values='NaN', strategy='mean', axis=0)`：使用數據的**統計訊息**（平均值、中位數...等）來填補遺失值
         - missing_values：遺失值表示符，可為整數或NaN
            > 預設值為'NaN'
            >> NaN：為numpy.nan用字符串
         - strategy：替換策略，字符串
              - 'mean'：預設，用axis的平均值填補
              - 'median'：用axis的中位數填補
              - 'most_frequent'：用axis的眾數填補
         - axis：指定軸向
              - axis=0：預設，計算columns（按欄位）
              - axis=1：計算rows（按單筆資料）
     - `imr.fit(X)`：計算 training set 的統計值，儲存統計值
         - X：訓練model變數，資料型態為array              
     - `imr.transform(X)`：將統計值應用於 testing set
         - X：計算missing values於X中
         
   另一個例子，也可使用**加權平均式**的方式，如之前提到的K-NN演算法，物以類聚，透過計算不同維度之間的關係來找出最有可能的答案，也就是以不同維度之間的關係（距離）作為權重的大小，距離愈近的要愈相似
   
   - 權重：距離的倒數，另其加總為1才可使用
     > 一種演算基礎標準化的方式
     >> E.g. 假設總共有4筆資料（G1-G4），每筆資料各有5個屬性（E1-E5）\
             G3在E1的位置為遺失值\
             可以利用計算G3其E2-E5屬性與其他筆資料的E2-E5屬性之間的距離，轉換為權重，透過其他3筆資料的E1值搭配權重計算，以此推測G3的E1為何
   
   查詢說明文件
     ```python
     help('imputer')
     ```
     
     - `help()`：查詢說明文件
        > 資料型態：字串
    
#### § Noisy data §
  > 有可能為「離群值」、「離散值」，導致資料呈現曲折

處裡這類資料，可分為四種方法：
1. 箱狀法（Binning）
2. 迴歸（Regression）
3. 聚類（Clustering）
4. 整合電腦與人檢驗：利用人檢驗有問題的值
   > E.g.處裡可能離異值
 
- 箱狀法（Binning）：先將資料進行排序，再利用其鄰居的值進行**平滑化**
  > 為考量箱內資料之「鄰居」（Neighborhood）的值，因此屬於**區域平滑法（Local Smoothing）**方法
    - Step 1. 排序：將資料分成數個頻率相同的的箱子（Buckets、Bins）
      > 頻率相同：箱內資料筆數相同
      >> E.g. 將九筆資料分為4,8,15,21,21,24,25,28,34
        - 等寬：**距離**分割，切割成n個等寬範圍的箱子
          > E.g.\
            資料：\[4,8], [15], [21,21,24,25,28], [34]\
            箱子：[-, 10), [10, 20), [20, 30), [30, +)
          
            - 易受離異值主導
            - 對偏斜資料處理較差
         
        - 等深：**頻率**分割，切割成有「大約相同」樣本數的箱子(較常使用)
          > E.g.\
          資料：\[4,8,15], [21,21,24], [25,28,34]\
          箱子：\[-, 20), \[20, 25) \[25, 35)
            - 資料量度性
    
    - Step 2. 平滑化：每個箱子獨立，對各個箱子內的資料進行平滑化
      > 箱子寬度愈大，愈平滑
        - 平均值、中間值：以平均值/中間值替代箱內所有的值，以進行平滑化
          > E.g. \[9,9,9], [22,22,22], [29,29,29]
        - 邊界值（Bin Boundaries）：以箱子內資料的 Max 與 min 作基準，將其他資料以最接近的邊界值取代
          > E.g. \[4,4,15], [21,21,24], [25,25,34] 

- 迴歸（Regression）：透過將資料分佈情況對應至函數，來進行平滑化
  > 將離群值用「迴歸線上對應的點」取代
  
- 聚類（Clustering）：偵測聚類，並移除離異值

#### Source
[sklearn.preprocessing中的Imputer用法解析](https://www.chzzz.club/post/212.html)

[sklearn.preprocessing.Imputer](https://blog.csdn.net/kancy110/article/details/75041923)

[Python 機器學習 Scikit-learn 完全入門指南](https://kknews.cc/zh-tw/code/g5qoogm.html)


[🐓🐓🐓](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)


## Data integration
   > 資料整合
   
- 多源：將許多來源的資料，整合成一個**具連貫性**的資料
  > E.g. 量化單位不同
  
- 多餘：
    - 一個屬性可由其他**單一屬性**或**一組屬性**導出
    - 屬性不一致或屬性命名不一致
    
- 發掘並解決資料值衝突問題：真實世界的個體，屬性值有可能來自不同來源
    > E.g. 不同表示、不同量化
       
   
[🐓🐓🐓🐓](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)  


## Data transformation
   > 資料轉換
   
- Normalization：正則化，讓資料在原始的樣態下，**等比縮放**落在\[0, 1]區間中
  > 將資料原本的 min-Max 轉換為 new_min-new_Max，且不改變原本分佈
 
- Standardization：標準化，將原始資料轉換成符合標準常態分佈的樣態
  > 優點：
  >  1. 提升model的收斂速度
  >  2. 提升model的精準度：可讓每個特徵值對結果做出相近程度的貢獻
    
    - 標準常態分配（Standard Normal Distribution）：平均值為0，標準化為1
        - 一個標準差：68%
        - 兩個標準差：95%
        - 三個標準差：99.7%
        
- Z-score：代表原始資料和母體平均值之間的距離，以標準差為單位計算
  > 經此轉換後，資料將符合標準常態分佈

    ![](https://raw.githubusercontent.com/chenkenanalytic/img/master/tm-01/f01.png)
    
- 十進位標準化：可讓資料介於\[0, 1]之間


#### § Exercise §
    
   練習處理不同類型的資料，必須將非數值型資料轉換數值型，才可丟入model訓練
   > 大部分model是基於數學運算

- 非數值型
    - **順序型**特徵：定義**對應字典（mapping dictionary）**
      
      ```python
      df = pd.DataFrame([['green', 'M', 10.1, 'class1'],
                         ['red', 'L', 13.5, 'class2'],
                         ['blue', 'XL', 15.3, 'class1']])
                         
      df.columns = ['color', 'size', 'price', 'classlabel']
      ```
      - `pd.DataFrame()`：生成一個dataframe
      - `.columns`：dataframe欄位名稱
      
      利用字典將「順序型」資料，轉換為「數值型」
       ```python
       size_mapping = {'XL':3, 'L':2, 'M':1}
       
       df['size'] = df['size'].map(size_mapping)
       ```
       - `.map()`：用於Series物件或DataFrame對象的一欄，接收函數或字典作為參數，返回經函數或字典處理後的值
         > 對物件內每個元素做處理
         
           若要反轉字典映射後的結果，也就是要返回value:key的結果，可以利用字典中的`.item()`
           ```python
           inv_size_mapping = {v:k for k, v in size_mapping.items()}
           df['size'] = df['size'].map(inv_size_mapping)
           ```
    - **類別型**特徵：將類別標籤轉換為整數值
       
         - Method 1：對應字典
           > 適用對單欄資料
           
           先挑出唯一值，再放入字典中做映射
           
           ```python
           import numpy as np
           
           class_mapping = {label:idx for idx, label in enumerate(np.unique(df['classlabel']))}
           class_mapping
           #輸出
           {'class1': 0, 'class2': 1}
           
           df['classlabel'] = df['classlabel'].map(class_mapping)
           ```
           
           - `np.unique(array, return_index=False)`：除去重複值，返回唯一值
              > 返回 array ，若input為非 1-D array會壓平為 1-D\
              >  - 「數值型」與「字串型」不可同時放在一起，會出現錯誤
              >  - 若返回array內為數值型，會由小到大排列
              >> 不影響原始資料

                - array：input
                - return_index：預設為False，是否回傳唯一值在原始資料中的位置
                  > 回傳值為 array，會另存在唯一值以外的array中

               ```python
               a = [1,6,43,7,7,7,1,2,4,6]
               A = np.unique(a)
               A
               #輸出
               array([ 1,  2,  4,  6,  7, 43])
               ```
               返回唯一值原始的位置
               ```python
               A, i = np.unique(a, return_index=True)

               A
               #輸出           
               array([ 1,  2,  4,  6,  7, 43])

               i
               #輸出
               array([0, 7, 8, 1, 3, 2], dtype=int64)
               ```
           
           - `enumerate()`：枚舉，計算元素位置
              > 會將list的index與list的元素（item），包成一個tuple，再將每個tuple包成按index排序的list

              ```python
              list(enumerate(np.unique(df['classlabel'])))
              #輸出
              [(0, 'class1'), (1, 'class2')]        
              ```

              在字典中，是要將原本「類別型」資料轉換為「數值型」，因此要改變idx與label位置

              ```python
              for idx, label in enumerate(np.unique(df['classlabel'])):
                     print('{}:{}'.format(label, idx))

              #輸出
              class1:0
              class2:1
              ```
         - Method 2：使用LabelEncoder
           > 會將每個類別 mapping 到某個**整數**，不會增加新欄位
           >> 適用於「有序」離散值，因整數有大小之分
           
           
           放入 LabelEncoder的模型，去轉換類別型資料，不須特別去定義轉換對象
           ```python
           from sklearn.preprocessing import LabelEncoder
           
           class_le = LabelEncoder()
           df['classlabel'] = class_le.fit_transform(df['classlabel'].values)    
           ```
           
            - `.fit_transform()`：訓練model並取代之 
              > input：array
            - `.inverse_transform`：將數值型轉換為原本的類別型            
            
                ```python            
                df['classlabel'] = class_le.inverse_transform(df['classlabel'])
                ```
           換個方式對另一個欄位做處理
           ```python
           X = df[['color', 'size', 'price']].values
           
           color_le = LabelEncoder()
           X[:,0] = color_le.fit_transform(X[:,0])
           X
           #輸出
           array([[1, 1, 10.1],
           [2, 2, 13.5],
           [0, 3, 15.3]], dtype=object)
           ```
           > blue=0, green=1, red=2
           >> 0,1,2有大小之分，但名目特徵本身無
           
   
           
         
         
        
        





#### Source
[資料的正規化(Normalization)及標準化(Standardization)](https://aifreeblog.herokuapp.com/posts/54/data_science_203/)

[標準分數](https://zh.wikipedia.org/wiki/%E6%A8%99%E6%BA%96%E5%88%86%E6%95%B8#%E6%A6%82%E5%BF%B5)

[資料預處理——標準化、歸一化、正則化](https://www.itread01.com/content/1541512225.html)

[pandas map()用法](https://blog.csdn.net/y12345678904/article/details/72385656)

[🐓🐓🐓🐓🐓](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)  

## Data reduction
   > 資料壓縮
   
   
   
[🐓🐓🐓🐓🐓🐓](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)     


# fit and transform

- fit()：一個訓練 model 的過程，可求得 training set 的固有屬性（平均值、標準差、最大、最小...等等）

- transform()：在fit()的基礎上，進行標準化、降維、歸一化...等操作
  > 因建立在fit()基礎之上，若直接執行會出錯
  
- fit_transform()：結合fit()與transform()


[🦜](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)

# Pandas map()、apply() and applymap()
  > 皆不改變原始資料

Pandas中「映射」與「應用」兩中方法的整理應用

- Series
  > Series物件 或 dataframe 中的任一欄
  >> [✍🏾](https://github.com/vanikk06/Machine-Learning/tree/master/Data#-series-)
    - `map()`：可對Series物件中的每個元素，執行給定的function、dictionary、Series映射處理（只要元素可以一一對應即可）
    - `apply(function, agrs)`：能對物件執行給定的function，還能設定指定參數（args）
      > 適用於Series與dataframe
          - function：要執行的函式
          - agrs：tuple，指定function內參數
            > 前提，function須為兩個以上參數
      
- DataFrame
  > 無map()
  >> [✍🏽](https://github.com/vanikk06/Machine-Learning/tree/master/Data#-dataframe-)
    - `apply(function, agrs)`：針對column的aggregates（合集）操作
       > 若給定的函數是ufunc，也會有element-wise效果
         - Aggregate functions：合計函數，SQL中一種基本的函數類型，指**操作面向為一系列的值，並返回一個單一值**
           > E.g. count、max、min、sum、avg(平均)...等等
           >> 回傳Series
         - universal function：縮寫為ufunc，這類函數能夠作用於narray對象中的**每一個元素上**，而分針對narray對象操作
           > [Learning more](https://blog.csdn.net/unixtch/article/details/78531585)
              
    - `applymap()`：針對element-wise操作
       > element-wise：按元素
    


#### § Series §

可使用`map()`與`apply()`兩種函式，兩者功能差不多，都是對**Series物件中的每一個元素值**做處理，差別在於`apply()`僅能進行functiont處理，而`map()`可以進行function、dictionary、Series處理

- `pd.Series(data, index=None)`：建立一個Series物件
    - data：資料內容
    - index：指標，預設為數字
    
    ```python
    import pnadas as pd
    
    ser = pd.Series([1,2,3,4,5])
    ser
    #輸出
    0    1
    1    2
    2    3
    3    4
    4    5
    dtype: int64
    ```
    若指定index
    ```python
    ser = pd.Series([1,2,3,4,5], index=['one', 'two', 'three', 'four', 'five'])
    ser
    #輸出
    one      1
    two      2
    three    3
    four     4
    five     5
    dtype: int64
    ```

- 進行function處理：對Series中的每個元素，`apply()`與`map()`皆可使用
  > 兩者結果相同
   
   
   ```python
   ser.map(lambda x:x**2)
   #輸出
   0     1
   1     4
   2     9
   3    16
   4    25
   dtype: int64
    
    
   ser.apply(lambda x:x**2)
   #輸出
   0     1
   1     4
   2     9
   3    16
   4    25
   dtype: int64
   ```
    - `lambda x:y`：簡易的定義函式方法
         - x：input
         - y：output
   
   除此之外，`apply()`還可以指定function中要帶入的參數
   > function須為**兩個以上參數**
   ```python
   def f(x, m):
       return x**m
    
   ser.apply(f, args=(3,))
   #輸出
   0      0
   1      8
   2    512
   3     64
   4    125
   dtype: int64
   ```
   > f為兩個參數的函式：
   >  - 第一個參數：Series中的各個元素
   >  - 第二個參數：args中指定
   
   function也可以兩個參數以上
   ```python
   def f(x, m, a):
       return (x**m)+a

   ser.apply(f, args=(3,1))
   #輸出
   0      1
   1      9
   2    513
   3     65
   4    126
   dtype: int64
   ```   
      
   執行function雖然兩者結果相同，但處理過程不同
    - `apply()`：對Series中的元素做出function的應用
    - `map()`：**將原本的值映射（mapping）到另一個值**
       > 因此`map()`不只可以接收function，還可以接收dictionary、Series
       
- 進行dictionary處理：將Serice中的元素作為dict中的keys，以此對應values
  > 僅適用`map()`
  
  會將Series中的元素作為key對應到dict中，映射出相對應的value
  ```python
  dic = {1:11, 2:21, 3:31, 5:51, 6:61}
  ser.map(dic)
  #輸出
  0    11.0
  1    21.0
  2    31.0
  3     NaN
  4    51.0
  dtype: float64
  ```
  > 將Series中的元素，由key轉為value
  >> 因為dict中不存在「4」這個key，因此自動填補「NaN」
  
  
- 進行Series處理：將Series_A中的元素作為index，對應到Series_B中的元素
  > 僅適用`map()`
  
    - Series_A.map(Series_B)
      > 若Series_A與Series_B中元素不相等，不足的會自動補上「NaN」
  
  ```python
  ser_map = pd.Series(['A', 'B', 'C', 'D', 'E', 'F', 'G'])
  ser.map(ser_map)
  #輸出
  0    B
  1    C
  2    D
  3    E
  4    F
  dtype: object  
  ```
  > Series_B 元素較 Series_A 多，但因Series_A中的元素對應值已滿足，因此不影響
  
  
  ```python
  ser = pd.Series([0,2,8,4,5])
  ser.map(ser_map)
  #輸出
  0      A
  1      C
  2    NaN
  3      E
  4      F
  dtype: object
  ```
  > 無法對應元素，自動補上「NaN」 


#### § DataFrame §

可以使用`apply()`與`applymap()`
- `apply()`：以column為單位做計算
- `applymap()`以element-wise計算

   ```python
   df = pd.DataFrame([[1,2,3], [4,5,6], [7,8,9]])
   
   df.apply(sum)
   #輸出
   0    12
   1    15
   2    18
   dtype: int64
   ```
   > 計算每col的總合
   >> 與`df.sum()`相同
   
   也可設定args
   ```python
   def ff(xs, n):
       return xs.sum() *n
   
   df.apply(ff, args=(2,))
   #輸出
   0    24
   1    30
   2    36
   dtype: int64
   ```
   > 因 function 為 Aggregate functions，所以回傳為Series
    
   若 function 為 ufunc ，也可有 element-wise 效果
   ```python
   df.apply(lambda x:x-5)
   ```
   > 回傳為dataframe
   
   ```python
   import numpy as np
   
   df.apply(np.sqrt)   
   ```
     - `np.sqrt`：取各個元素的平方根
   
#### Source
[pandas的map、apply、applymap](https://home.gamer.com.tw/creationDetail.php?sn=4219422)

[SQL 函数](https://www.w3school.com.cn/sql/sql_functions.asp)

[[Day10]Pandas Groupby使用！](https://ithelp.ithome.com.tw/articles/10194027)

[python科学计算之numpy——ufunc函数](https://blog.csdn.net/unixtch/article/details/78531585)

[【python】numpy库ndarray多维数组的的运算：np.abs(x)、np.sqrt(x)、np.modf(x)等](https://blog.csdn.net/brucewong0516/article/details/79186176)

[🦚](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)
