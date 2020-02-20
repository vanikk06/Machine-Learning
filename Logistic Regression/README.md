# Content
- [Lecture 4 Logistic Regression 拷貝.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/Lecture%204%20Logistic%20Regression%20%E6%8B%B7%E8%B2%9D.pdf)
- [Logistic Regression](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#logistic-regression)
- [Sigmoid function](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#sigmoid-function)
- [Decision Boundary](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#decision-boundary)
- [Logistic regression's cost function](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#logistic-regressions-cost-function)
- [Praticing logistic regression](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#praticing-logistic-regression)


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

因預測結果為機率，希望各筆資料的結果同時成立時，須將所有相乘，希望最終的目標愈大愈好

![](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/image/Snipaste_2020-02-21_03-17-30.png)
> 機率相乘一般化的式子

- 若 y<sup>(i)</sup> = 1，僅留下前項，後項因0次方而變為1
- 若 y<sup>(i)</sup> = 0，僅留下後項，前項因0次方而變為0

但因機率介於\[0, 1]之間，全部相乘會愈乘愈小，慢慢趨近於0，導致過小無法造成影響，因此將最終目標取log，使值放大

![](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/image/Snipaste_2020-02-21_03-18-16.png)

最後在配合regression 一般cost function目標值為愈小愈好，加上「負號」

![](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/image/Snipaste_2020-02-21_03-19-28.png)
> 因此，最終為希望目標函數「愈小愈好」

除此之外，還希望model愈簡單愈好

![](https://github.com/vanikk06/Machine-Learning/blob/master/Logistic%20Regression/image/Snipaste_2020-02-21_03-20-05.png)
> 紅色部分為控制model複雜度
>> λ：正規化參數（regularization parameter），控制「cost function」與「複雜度」的比重

[🍻](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#content)
  
# Praticing logistic regression  
  > 使用 鳶尾花數據集

logistic regression 本為處理二元分類，然而從二元分類變形，仍可處理多元分類的的問題

- 變形方法

  假設目標函數有三個值：紅色、藍色與綠色
  
  首先訓練紅色資料的決策邊界：區分「紅色」與「非紅色」的部分，重複此方式，訓練藍色與綠色的決策邊界
  
  在新的資料進入時，會一個個比較，判斷屬於何顏色
  
  - 若new_data介於兩決策區域之間：比較機率強度/力度（距離），與決策邊界的距離愈遠，表示分隊的信心強度愈高
    > 搶著要
  - 若new_data被排除在決策區域之間：比較機率強度/力度（距離），與決策邊界的距離愈近，表示判給其的機率愈高
    > 大家都不要


先匯入資料集與相關套件
```python
import pandas as pd
import numpy as np
from sklearn.datasets import load_iris

iris = load_iris()
iris.keys()
#輸出
dict_keys(['data', 'target', 'target_names', 'DESCR', 'feature_names', 'filename'])
```
將資料轉為dataframe形式，並區分「2」與「非2」的部分（僅取兩個類別）
```python
feature = pd.DataFrame(iris['data'], columns = iris['feature_names'])
target = pd.DataFrame(iris['target'], columns = ['class'])

data = pd.concat([feature, target], axis=1)

df = data[data['class'] != 2]
```
畫出散佈圖，查看資料型態，是否可用一條線區分
```python
import matplotlib.pyplot as plt
import seaborn as sns

plt.style.use('ggplot')
g = sns.FacetGrid(df, hue='class', size=5)
g.map(plt.scatter, "sepal length (cm)", "sepal width (cm)")
g.add_legend()
```
- `plt.style.use()`：優化視覺化
- `sns.FacetGrid(data, row, col, hue, size)`：初始化網格，設置畫板和軸，但無繪製畫板上任何東西
    - data：資料型態為 DataFrame
    - row、col：可放入指定欄位，與「軸」有明顯對應關係
    - hue：根據此指定欄位進行分群，使用不同顏色
    - size：大小
- `.map(method, x, y)`：在網格上繪製數據
    - method：繪製方法
        - plt.scatter：散佈圖
        - plt.hist：直方圖
        - sns.regplot：散佈圖之一
        - sns.barplot：長條圖
        - sns.boxplot：盒鬚圖
    - x：x軸標籤名稱
    - y：y軸標籤名稱
- `.add_legend()`：增加圖例

先將資料標準化，以增加收斂速度，避免偏向某個變數訓練
```python
from sklearn.preprocessing import StandardScaler
X = df.iloc[:, :2].values 
y = df.iloc[:, 4].values

sc = StandardScaler()
sc.fit(X)
X_std = sc.transform(X)
```
> X：僅取前兩個特徵變數

訓練 logistic regression model
> 使用`sklearn.linear_model`套件的`LogisticRegression`
```python
from sklearn.linear_model import LogisticRegression

lr = LogisticRegression(C=100.0, random_state=1)
lr.fit(X_std, y)

print(lr.coef_)
print(lr.intercept_)
#輸出
[[ 9.87113623 -6.67376595]]
[1.7401565]
```
> 輸出決策邊界（線）

- `LogisticRegression(C, random_state)`：logistic regression model
    - C：1/λ，正則強度的倒數，值愈小正則強度就愈強
      > 浮點數

定義決策區域（decision region）
```python
from matplotlib.colors import ListedColormap

def plot_decision_regions(X, y, classifier, test_idx=None, resolution=0.02):

    #setup marker generator and color map設置標記生成器 & 顏色圖
    markers = ('s', 'x', 'o', '^', 'v')
    colors = ('red', 'blue', 'lightgreen', 'gray', 'cyan')
    cmap = ListedColormap(colors[:len(np.unique(y))])
    
    #plot the decision surface繪製決策面
    x1_min, x1_max = X[:, 0].min()-1, X[:, 0].max()+1
    x2_min, x2_max = X[:, 1].min()-1, X[:, 1].max()+1
    xx1, xx2 = np.meshgrid(np.arange(x1_min, x1_max, resolution), np.arange(x2_min, x2_max, resolution))
    Z = classifier.predict(np.array([xx1.ravel(), xx2.ravel()]).T)
    Z = Z.reshape(xx1.shape)
    plt.contourf(xx1, xx2, Z, alpha=0.3, cmap=cmap)    
    plt.xlim(xx1.min(), xx1.max())
    plt.ylim(xx2.min(), xx2.max())
    
    #畫出資料點(y：實際點)
    for idx, cl in enumerate(np.unique(y)):
      plt.scatter(x=X[y == cl, 0], y=X[y == cl, 1], alpha=0.8, c=colors[idx], marker=markers[idx], label=cl, edgecolor='black')
      
    #highlight test samples
    if test_idx:
        #plot all samples
        X_test, y_test = X[test_idx, :], y[test_idx]
        
        plt.scatter(X_test[:, 0], X_test[:, 1], c='', edgecolor='black', alpha=1.0, linewidth=1, marker='o', s=100, label='test set')
```
- `ListedColormap`：創造或是操作顏色映射
- classifier：迴歸模型
- resolution：解析度(間隔)
- `ListedColormap(colors[:len(np.unique(y))])`：找出y(目標變數)種類，用color內顏色區分(最多5類)
   - `np.unique(input, return_index=True, return_inverse=True)`：去除重複的元素，並按元素順序由小到大排列，返回一個新的無重tuple or list
     - return_index=True：返回new_list元素在old_list中的位置，並以list形式另外儲存
       > 要多給一個空間，長度等於new_list
     - return_inverse=True：返回old_list元素在new_list中的位置，並以list形式另外儲存
       > 要多給一個空間，長度等於old_list
   - `colors[:x]`：從index=0到index=x-1(總共會出現x個元素)

- x1_min、x1_max：找出第一欄的範圍(min-1, Max+1)
- x2_min、x2_max：找出第二欄的範圍(min-1, Max+1)
- xx1、xx2：用X變數找出x軸、y軸
   - `np.arange(start, end, step)`：建立一個range內的list
   - `np.meshgrid(x, y)`：用兩個座標軸上的點在平面上畫網格
- Z：使用給定的套件模型去預測(決策邊線)
   - `.ravel()`：降為1維
   - `np.array`：建立一個array，合併xx1、xx2資料
   - `.T`：轉置
- `plt.contourf(data_x, data_y, z, alpha, camp)`：繪製輪廓線且填充輪廓
  - data_x：X軸數據
  - data_y：Y軸數據
  - z：指定X、Y座標對應點的高度數據
  - alpha：透明度
  - cmap：指定等高線的顏色映射(自動用不同的顏色來區分不同的高度區域)

畫出目前model的決策邊界
```python
plot_decision_regions(X_std, y, classifier=lr)
plt.xlabel('sepal length [standardized]')
plt.ylabel('sepal width [standardized]')
plt.legend(loc='upper left')
plt.tight_layout()
```

#### Source
[Seaborn学习（一）------- 构建结构化多绘图网格（FacetGrid(）、map()）详解](https://blog.csdn.net/weixin_42398658/article/details/82960379)

[18-12-11-視覺化庫Seaborn學習筆記（六：FacetGrid）](https://www.itread01.com/content/1545030424.html)

[machine learning 下的 Logistic Regression 實作(使用python)](https://medium.com/@jacky308082/machine-learning-%E4%B8%8B%E7%9A%84-logistic-regression-%E5%AF%A6%E4%BD%9C-%E4%BD%BF%E7%94%A8python-d19b971ff9dc)

[Python中numpy庫unique函數解析](https://blog.csdn.net/yangyuwen_yang/article/details/79193770)

[Numpy中Meshgrid函數介紹及2種應用場景](https://www.cnblogs.com/lemonbit/p/7593898.html#4184208)

[Python Matplotlib contour和contourf：繪製等高線](http://c.biancheng.net/view/2719.html)

[matplotlib.pyplot contourf()函式的使用](https://www.itread01.com/content/1542579970.html)

[🍺](https://github.com/vanikk06/Machine-Learning/tree/master/Logistic%20Regression#content)
