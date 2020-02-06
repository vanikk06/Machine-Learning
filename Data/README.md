# Content
- [Attributes](https://github.com/vanikk06/Machine-Learning/tree/master/Data#attributes)
- [Symmetric vs. Skewed Data](https://github.com/vanikk06/Machine-Learning/tree/master/Data#symmetric-vs-skewed-data)
- [Basic Statistical Descriptions](https://github.com/vanikk06/Machine-Learning/tree/master/Data#basic-statistical-descriptions)

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
