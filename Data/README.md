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
 
 ### § 調整參數 ＆ 評估結果 §
 
  
 #### Source
 [10分钟python图表绘制 | seaborn入门（四）：回归模型lmplot](https://zhuanlan.zhihu.com/p/25909753)
 
 [Seaborn(sns)官方文档学习笔记（第四章 线性关系的可视化）](https://zhuanlan.zhihu.com/p/27593869)
 
 [[Matplotlib-06]圖表風格](https://medium.com/%E8%B3%87%E6%96%99%E8%A6%96%E8%A6%BA%E5%8C%96/matplotlib-06-%E5%9C%96%E8%A1%A8%E9%A2%A8%E6%A0%BC-d58498069700)
  
[🦃](https://github.com/vanikk06/Machine-Learning/tree/master/Data#content)
