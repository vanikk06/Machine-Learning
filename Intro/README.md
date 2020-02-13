
# Content
- [intro.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Intro/intro.pdf)
- [Lecture 1.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Intro/Lecture%201.pdf)
- [Class_01.ipynb](https://github.com/vanikk06/Machine-Learning/blob/master/Intro/Class_01.ipynb)
    - [webpage](https://nbviewer.jupyter.org/github/vanikk06/Machine-Learning/blob/master/Intro/Class_01.ipynb)
- [作業一.ipynb](https://github.com/vanikk06/Machine-Learning/blob/master/Intro/%E4%BD%9C%E6%A5%AD%E4%B8%80.ipynb)
    - [webpage](https://nbviewer.jupyter.org/github/vanikk06/Machine-Learning/blob/master/Intro/%E4%BD%9C%E6%A5%AD%E4%B8%80.ipynb)
- [Introduction](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#introduction)
- [Python](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#python)
    - [Identifier](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#identifier)
    - [Math Operator](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#math-operator)
    - [String](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#string)
    - [List](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#list)
    - [Tuple](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#tuple)
    - [Dictionary](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#dictionary)
    - [Set](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#set)
    - [Flow Control](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#flow-control)
    - [List Comprehensions](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#list-comprehensions)
    - [Function](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#function)
    - [Numpy](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#numpy)
    - [Matplotlib](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#matplotlib)
- [zip()](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#zip)
- [map()](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#map)
- [enumerate()](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#enumerate)
- [Overview](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#overview)

# Introduction
  > 簡單介紹一下，什麼是機器學習
  >> 要先明白，機器學習並非100%精確的，大多數情況下只是一個很好的猜測，並且需要大量的調整疊代（時間和資源耗費在訓練模型上）
  
- [Machine Learning v.s. Algorithms](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#machine-learning-vs-algorithms)
- [Machine Learning v.s. Artificial Intelligence v.s. Deep Learning](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#machine-learning-vs-artificial-intelligence-vs-deep-learning)
  
  
主流的定義機器學習
  > 由機器學習教父Tom Mitchell提出
  >> 透過從過往的資料和經驗中學習並找到其運行規則
  
  "A computer program is said to learn from **experience E** with respect to some class of **tasks T** and **performance measure P**, if its performance at tasks in T, as measured by P, improves with experience E. "
  
  簡單的說就是一個程式可以根據過去的經驗（Data）去做某些任務（Task），然後會有一些效能評估（performance measure）來評估這些Task做得好不好，如果這些效能評估可以透過「利用過往的資料來提升」的話，就叫作機器學習
  
  
#### Machine Learning v.s. Algorithms
  > 機器學習 v.s. 演算法

- Algorithms：訂立一個明確的規則，透過coding將這種規則具現化
  > 寫死的
  
- Machine Learning：透過樣本訓練機器辨識出運作模式，而不是用特定的規則來coding，換句話說，machine learning是從資料中得到複雜的函式（或樣本）來**學習**以創造algorithms（或一組規則），並利用它來做**預測**
  > 建立模型（model）
  >> 模型的好壞必須針對特定問題的種類
  
  ![](https://github.com/vanikk06/Machine-Learning/blob/master/Intro/image/Snipaste_2020-01-14_03-41-03.png)

machine learning的厲害之處在於它可以**自主學習**，同樣的ML系統仍然可以使用在未來的物件，並不需要重寫程式碼，這是相當方便起強大的 e.g.識別物件

#### Machine Learning v.s. Artificial Intelligence v.s. Deep Learning
  > 機器學習 v.s. 人工智慧
  
machine learning是人工智慧的一個分支，人工智慧是一個較廣泛的名詞

- Artificial Intelligence（AI）：

  “Intelligent Agents“ refers to the ability of the computer to **simulate/model human thinking** processes to **imitate human ability or behavior**"
  
  現在所執行的人工智慧系統是一種「弱人工智慧」的形式，人工智慧系統可以做一件或是多件事情，而做的程度與人類相當，甚至超越人類
  
![](https://github.com/vanikk06/Machine-Learning/blob/master/Intro/image/Snipaste_2020-01-14_17-35-34.png)

- machine learning的種類，可以分為四種：\
  [[learning more]](https://ai4dt.wordpress.com/2018/05/25/%E4%B8%89%E5%A4%A7%E9%A1%9E%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92%EF%BC%9A%E7%9B%A3%E7%9D%A3%E5%BC%8F%E3%80%81%E5%BC%B7%E5%8C%96%E5%BC%8F%E3%80%81%E9%9D%9E%E7%9B%A3%E7%9D%A3%E5%BC%8F/)
    1. 監督式學習（supervised learning）
        > 一比一對照資料
    2. 非監督式學習（unsupervised learning）
        > 機器自行摸索出資料規則
    3. 增強式學習（reinforcement learning）
        > 在未知探索與遵從既有知識間取得平衡
          
- Deep Learning（DL）：

   "learning data representations with use a cascade of **multiple layers of nonlinear processing unit**"
   
   深度學習是機器學習的一個分支，可以被定義為「一種實現機器學習的技術」，此技術被稱為深度神經網路（deep neural networks – DNNs），被安排在模仿人類大腦的圖層，學習模式中的模式（learning patterns of patterns）

#### Source
[〔資料分析&機器學習〕 第3.1講：Python 機器學習以及Scikit-learn介紹](https://medium.com/jameslearningnote/%E8%B3%87%E6%96%99%E5%88%86%E6%9E%90-%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92-%E7%AC%AC3-1%E8%AC%9B-python-%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92%E4%BB%A5%E5%8F%8Ascikit-learn%E4%BB%8B%E7%B4%B9-fdb052463911)

[人工智慧、機器學習、深度學習是什麼? – Machine Learning 教學系列 (一)](https://blog.gcp.expert/ml-1-ai-ml-deep-learning-intro/)


[史上最完整機器學習自學攻略！我不相信有人看完這份不會把它加進我的最愛](https://buzzorange.com/techorange/2017/08/21/the-best-ai-lesson/)

[三大類機器學習：監督式、強化式、非監督式](https://ai4dt.wordpress.com/2018/05/25/%E4%B8%89%E5%A4%A7%E9%A1%9E%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92%EF%BC%9A%E7%9B%A3%E7%9D%A3%E5%BC%8F%E3%80%81%E5%BC%B7%E5%8C%96%E5%BC%8F%E3%80%81%E9%9D%9E%E7%9B%A3%E7%9D%A3%E5%BC%8F/)

#### Learning more
[機器學習跟統計學差在哪？哈佛博士：機器學習重視預測結果，統計學在乎因果推理](https://buzzorange.com/techorange/2019/05/02/difference-between-statistics-and-machine-learning/)

[👁‍🗨](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)


# Python
  > 基本語法介紹
  
- [Identifier](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#identifier)
- [Math Operator](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#math-operator)
- [String](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#string)
- [List](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#list)
- [Tuple](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#tuple)
- [Dictionary](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#dictionary)
- [Set](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#set)
- [Flow Control](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#flow-control)
- [List Comprehensions](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#list-comprehensions)
- [Function](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#function)
- [Numpy](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#numpy)
- [Matplotlib](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#matplotlib)


在此課堂上會使用的套件：
- Numpy：矩陣（n-dimensional array）運算
- Pandas：資料處理
- Matplotlib：繪圖
- Scikit-learn：包含機器學習常用的演算法

## Identifier
   > 識別字
   >> Python3 Unicode
   
寫程式時需要自行定義的名稱，可使用底線、英文字母、數字和中文，但不可與保留字相同
> 自行定義名稱：變數（variable）、函數（function）、類別（class）
    
- 保留字：具有語法功能

![](https://github.com/vanikk06/Machine-Learning/blob/master/Intro/image/Snipaste_2020-01-15_02-24-53.png)

[[learning more]](https://www.itread01.com/articles/1506142629.html)

#### Source
[【Python學習筆記之一】Python關鍵字及其總結](https://www.itread01.com/articles/1506142629.html)

[🕐](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

## Math Operator
   > 數學運算符
   
- `+`：加法
- `-`：減法
- `*`：乘法
- `/`：除法
- `%`：除法，取餘數
- `//`：除法，取商數
- `**`：次方

[🕑](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

## String
   > 字串
 
- `'xxx'` 或 `"xxx"`：以此包起的東西為字串
  > 引號必須兩兩成對出現
 
- `"""xxx"""`：連續使用三個雙引號可建立**多行**字串

[🕒](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

## List
   > 列表

最常用的資料結構，儲存**按順序排列**的東西
  > index從0開始
  >> 可儲存一種以上的資料格式

基本操作：
> x = [0, 1, 2, 3, 4]
  - `len(x)`：長度
  - `sum(x)`：所有元素的總合
     > 若元素為不能加總的，會出現`TypeError`
  - `x[-1]`：倒數第一位
     > 4
  - `x[1:3]`：取頭不取尾
     > [1, 2]
  - `x[:2]`：從頭開始
     > [0, 1]
  - `x[-2:]`：從倒數第二個到最後
     > [3, 4]
  - `.extend()`、`.append()`：在最後面增加
      - `.extend()`：拆包
         > x.extend([8, 7])
         >> [0, 1, 2, 3, 4, 8, 7]
      - `x.append()`：不拆包
         > x.append([8, 7])
         >> [0, 1, 2, 3, 4, [8, 7]]
      - `+`：也可使用此運算符，合併兩個list（小心，對list使用`+`運算符並非相加，而是使兩個list串接起來）
         > [1,3] + [0,2]
         >> [1, 3, 0, 2]
  - `*`：使用此運算符並非相乘，而是將list重複n次
    ```python
    L = [3, 87, -5, 9]
    L*2
    #輸出
    [3, 87, -5, 9, 3, 87, -5, 9]
    ```

[🕓](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

## Tuple
   > 序對
   
類似list，但tuple是一種**唯讀**且**不可變更**的資料結構
  > 不可取代tuple中的任意一個元素
  
- `()`：tuple
   > 改變tuple中的元素會出現`TypeError`
   
[🕔](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

## Dictionary
   > 字典
   
為**key：value**配對的資料結構，在dict內的元素是**無序的**
  > key不能是list，但可以是tuple
  >> 將key設為list會出現`TypeError`
  
[🕕](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)  

## Set
   > 集合
   
類似數學中的集合，包含一堆**各不相同**的元素

- 使用時機：
  1. 檢查某個元素是否存在
      > 速度比list快
  2. 想從一大堆資料中，找出不同的項目
      > set內儲存不重複的元素

- 基本操作：
   - `set()`：建立集合
   - `-`：差集
   - `|`：聯集
   - `&`：交集
   - `in`：檢查某元素是否存在

[🕖](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)
  
## Flow Control
   > 控制流程
   >> 使用**縮排**的方式，來切分程式碼
   
- 判斷式：`if-elif-else`
  > 可寫在同一行
  ```python
  "even" if X % 2 == 0 else "odd"
  ```

- 迴圈
  - `for`：指定執行次數
     ```python
     sum = 0
     for x in range(1, 10, 1):
        sum += x
     ```
     > `range(1, count+1, 1)`
     >> 產生1, 2, ..., count
     
  - `while`：指定條件
      
[🕗](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

## List Comprehensions
   > 解析式列表
   
將某個list轉換成另一個list
  > e.g.挑選其中某個元素、對某些元素進行轉換
  
```python
even_numbers = [x for x in range(0,5,1) if x%2 == 0]
square_dict = {x : x*x for x in range(0,5,1)}
square_set = {x*x for x in [2,-1]}

print('even_numbers:', even_numbers)
print('square_dict:', square_dict)
print('square_set:', square_set)    
```
輸出：
```python
even_numbers: [0, 2, 4]
square_dict: {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
square_set: {1, 4}
```

[🕘](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

## Function
   > 函式
   
input → function → output
> 使用`def`定義函式

- `lambda`：短版的function，不像`def`需要額外命名函數識別字
  ```python
  lambda x: x+4
  ```
  > x：input\
  x+4：output

[🕙](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

## Numpy
   > 矩陣套件
   >> 操作多維度陣列
   
```python
import numpy as np

a = np.array([1,2,3])
b = np.array([4,5,6]
```
- `*`：對應位置相乘
  > a*b
  >> array([ 4, 10, 18])
  
- `np.dot(x, y)`：x、y之內積
  > np.dot(a, b)
  >> 32 = 1x4+2x5+3x6
  
- `np.sum()`：總合
- `np.max()`：最大值
- `np.min()`：最小值
- `.size`：個數
  > a.size
  >> 3
- `np.array()`：建立array
- `np.append(x, y)`：在x最後面增加y
   > np.append(a, b)
   >> array([1, 2, 3, 4, 5, 6])
- `np.linspace(x, y, n)`：生成一個x到y，個數為n的等差級數
   
[🕚](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

## Matplotlib
   > 繪圖套件
   >> 顏色查詢：MatplotlibColormap
   
- `%matplotlib inline`：魔法函式，內嵌繪圖，可以省略`plt.show()`
  > 新版的不一定需要
  
- `plt.plot()`：折線圖
   > [[learning more]](https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.plot.html)
    - color
        - ' g '：green
        - ' r '：red
        - ' b '：blue
        - ' c '：cyan（青色）
        - ' m '：magenta（品紅色）
        - ' y '：yellow
        - ' k '：black
        - ' w '：white
    - line styles
        - ' - '：solid line（粗線）
        - ' -- '：dashed line（虛線）
        - ' -. '：dash-dot line（虛點線）
        - ' : '：dotted line（點線）
    - label：參數，標籤
- `plt.bar()`：長條圖
- `plt.hist()`：直方圖
    - bins：間隔、組界
    - edgecolor：邊界顏色
- `plt.scatter`：散佈圖
  > plt.scatter(x, y, s=大小(20), c=顏色(blue))
- `plt.title()`：標題
- `plt.xlabel()`：x軸標籤
- `plt.ylabel()`：y軸標籤
- `plt.xticks()`：x軸刻度
   > plt.xticks(刻度, 對應標籤)
- `plt.legend()`：圖例
   > plt.legend(loc=9)
   >> loc=9：位置，中間偏上
- `plt.annotate()`：註解
   > plt.annotate(s, xy, xytext, textcoords)
   >> [[learning more]](https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.annotate.html)
   - s：註解文字內容
   - xy：被註釋的座標點，二維元组形(x,y)
     > 把標籤放在對應的點上
   - xytext：註釋文字的座標點
   - textcoords：註釋文字的整個座標系屬性
     > offset points：相對於被註釋點xy的偏移量(單位：點)
- `plt.axis()`：數字座標軸
- `plt.figure()`：建立一個figure（空的顯示區）
    - figsize：顯示區大小
      > e.g. `plt.figure(figsize=(8,10))`
- `plt.subplot()`：畫多張圖
    > plt.subplot(nrows, ncols, plot_number)
    - nrows：幾個橫排
    - ncols：幾行
    - plot_number：第幾個圖
    ```python
    plt.subplot(2,2,1) #第一張
    ```
- `plt.tight_layout()`：圖表過度集中，可用此分開
- 三維等高線圖
    - `plt.coutour(x, y, f(x,y), cmap, alpha)`：輪廓線
    - `plt.contourf(x, y, f(x,y), cmap, alpha)`：填充輪廓
        - x、y：變數
          > 2D array，兩者shape要相同
        - f(x, y)：對應到顏色
        - cmap：繪圖主題
        - alpha：透明度
    
 
![](https://github.com/vanikk06/Machine-Learning/blob/master/Intro/image/Snipaste_2020-01-17_02-45-09.png)

-  Figure vs. Axes vs. Axis
   - Figure：含Axes(被畫出來的東西)和canvas(畫布)
   - Axes：是figure上面一個區塊呈現資料的地方(畫出來的東西)
   - Axis：數字座標軸，產生座標上面的ticks，也能決定tick的位置與格式
      
#### Source
[〔資料分析&機器學習〕 第2.5講：資料視覺化(Matplotlib, Seaborn, Plotly)](https://medium.com/jameslearningnote/%E8%B3%87%E6%96%99%E5%88%86%E6%9E%90-%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92-%E7%AC%AC2-5%E8%AC%9B-%E8%B3%87%E6%96%99%E8%A6%96%E8%A6%BA%E5%8C%96-matplotlib-seaborn-plotly-75cd353d6d3f)

[matplotlib.pyplot.plot](https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.plot.html)

[matplotlib.pyplot.annotate](https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.annotate.html)

[Python學習筆記#5：Matplotlib資料視覺化篇](http://psop-blog.logdown.com/posts/3020978-python-matplotlib)

[matplotlib.pyplot contourf()函式的使用](https://www.itread01.com/content/1542579970.html)

[🕛](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

# zip()
  > 壓縮
  >> 可同時操作多個list

將多個list中對應的元素打包成一個個tuple，返回這些tuples組成的list
> 若參數長度不等，取短的

   在python3中為了減少內存無法直接顯示zip()    
   ```python
   a = [1,2,3]
   b = [4,5,6]
   c = [7,8,9,10,11]
   
   zip(a, b)
   # 輸出
   <zip at 0x1b8d8fdde48>   
   ```
    
   可以放到迴圈中顯示
   ```python
   for i in zip(a,b):
       print(i)
    
   #輸出
   (1, 4)
   (2, 5)
   (3, 6)
   ```
  
   長度不等取短的
   ```python
   for i in zip(a,c):
       print(i)
        
   #輸出
   (1, 7)
   (2, 8)
   (3, 9)
   ```

- `zip(*list/tuple)`：表示將參數（list/tuple）分開，按照位置參數傳遞給對應函數
  > 會得到**行列互換**的效果
  
  ```python
  a = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
  
  for i in zip(*a):
    print(i)
  
  #輸出
  (1, 4, 7)
  (2, 5, 8)
  (3, 6, 9)
  ```
  可再通過`map()`將tuple轉換為list
  ```python
  for i in map(list,zip(*a)):
    print(i)
    
  #輸出
  [1, 4, 7]
  [2, 5, 8]
  [3, 6, 9]
  ```
  
其他應用
    
   ```python
   x = [1,2,3]
   for i in zip(*[x]*3):
       print(i)
   
   #輸出
   (1, 1, 1)
   (2, 2, 2)
   (3, 3, 3)
   ```

#### Source
[Python zip() 函數](https://www.runoob.com/python/python-func-zip.html)

[python zip()函數用法](https://www.itread01.com/content/1516473617.html)

[💬](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

# map()
  > 映射
  >> 對物件內每個元素做處理
  
- map(function, iterable,...)：對iterable內每個元素調用function，返回一個新list

   與`zip()`相同無法直接顯示
   ```python
   a = ['1', '2', '3']
   map(int, a)
   
   #輸出
   <map at 0x1b8db4f7400>
   ```
   放到迴圈中顯示
   ```python
   a = ['1', '2', '3']
   for i in map(int, a):
       print(i, type(i))
       
   #輸出
   1 <class 'int'>
   2 <class 'int'>
   3 <class 'int'>
   ```
   
   也可以自行定義函式
   ```python
   def square(x):
       return x**2
       
   for i in map(square, [1,2,3,4,5]):
       print(i)
       
   #輸出
   1
   4
   9
   16
   25
   ```
   或使用`lambda function`來定義簡易的函式
   ```python
   for i in map(lambda x: x**2, [1,2,3,4,5]):
       print(i)
       
   #輸出
   1
   4
   9
   16
   25
   ```
   或使用解析式列表的方式
   ```python
   b = [x**2 for x in [1,2,3,4,5]]
   b
   
   #輸出
   [1, 4, 9, 16, 25]
   ```

#### Source
[Python map() 函数](https://www.runoob.com/python/python-func-map.html)

[Python 基礎系列 map() 用法解說](https://e8859487.pixnet.net/blog/post/392947555-python-%E5%9F%BA%E7%A4%8E%E7%B3%BB%E5%88%97--map%28%29-%E7%94%A8%E6%B3%95%E8%A7%A3%E8%AA%AA)

[🗯](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

# enumerate()
  > 枚舉、列舉(字典上)
  >> 既遍歷索引又遍歷元素
  
- enumerate(sequence, start=0)：產生許多索引序列（key, value）的tuple
  > 組成一個索引序列，可以同時獲索引跟值
    - sequence：數列
    - start：index起始，預設從0開始

    無法直接顯示
    ```python
    seasons = ['Spring', 'Summer', 'Fall', 'Winter'] 
    enumerate(seasons)

    #輸出
    <enumerate at 0x1b8db7c8c60>
    ```
    可以使用`list()`協助
    ```python
    seasons = ['Spring', 'Summer', 'Fall', 'Winter'] 
    list(enumerate(seasons))
    
    #輸出
    [(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
    ```
    索引應用
    ```python
    list = [1,2,3,4,5,6]
    for index, value in enumerate(list,1):
        print("%s,%s" %(index, value))

    #輸出
    1,1
    2,2
    3,3
    4,4
    5,5
    6,6
    ```
    > `%s`：一個字串

#### 補充
若要統計文件行數，可以這樣寫：
```python
count = len(open(filepath, 'r').readlines())
```
這種方法簡單，但是會比較慢，當文件較大時甚至不能作業

此時可以利用`enumerate()`
```python
count = 0
for index, line in enumerate(open(filepath,'r'))： 
    count += 1
```
#### Source
[Python enumerate()函數](https://www.runoob.com/python/python-func-enumerate.html)

[python enumerate用法總結](https://blog.csdn.net/churximi/article/details/51648388)

[💭](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)

# Overview
  > 機器學習：電腦利用數據自主學習並優化性能

#### Source
[8種常見機器學習演算法比較](https://www.itread01.com/content/1541334303.html)

[【機器學習懶人包】從數據分析到模型整合，各種好用的演算法全都整理給你啦！](https://buzzorange.com/techorange/2019/08/13/machine-learning-algorithm-collection/)

[🗨](https://github.com/vanikk06/Machine-Learning/tree/master/Intro#content)


