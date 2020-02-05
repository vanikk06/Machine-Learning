# Content
  > 自學python的學習筆記
  >> [class](http://moocs.nccu.edu.tw/course/123/intro)\
  >> [github](https://github.com/yenlung/Python-3-Data-Analysis-Basics)
  
- [week 1](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#week-1)
  - [Magic Commend](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#magic-commend)
     - [numpy.random](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#numpyrandom)
  - [Markdown](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#markdown)
  - [Interactive](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#interactive)

- [week 2](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#week-2)
  - [Format](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#format)
  - [Function](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#function)
  - [Cutting String](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#cutting-string)
  - [list()](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#list)
  
- [week 3](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#week-3)
  - [Git](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#git)
  - [Linux](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#linux)
  - [MySQL vs. NoSQL](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#mysql-vs-nosql)
  - [numpy package](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#numpy-package)
  - [Import](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#import)
     - [print()](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#print)
  - [Data Analysis](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#data-analysis)
  - [Array](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#array)
  
- [week 4](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#week-4)
  - [Interact](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#interact)
  - [GUI](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#gui)

- [week 5](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#week-5)
  - [Swift](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#swift)
  - [Pandas](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#pandas)
  - [Practice Pandas](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#practice-pandas)
  - [Moving Average](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#moving-average)
  
- [week 6](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#week-6)
  - [Linear Regression](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#linear-regression)
  - [data split](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#data-split)
  - [DataSet](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#dataset)
  - [enumerate()](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#enumerate)
  
- [week 7](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#week-7)
  - [SVM](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#svm)


 ---
 
# week 1
 
 [👉🏻HERE👈🏻](https://github.com/vanikk06/Machine-Learning/blob/master/Learning%20Python/week_1.ipynb)

在終端機的Unix指令
  - pwd：顯示當前路徑
  - dir：列出當前目錄所有的檔案

python函式說明文件
   - shift + tab：簡短提示
   - ?：完整提示
   
## Magic Commend
   > 魔術指令
   >> 一開始皆為"%"
   
- `%pylab inline`：簡化版的魔術指令，除了可以使用`Matplotlib`、`NumPy`套件畫圖，還可以進行數學運算
   > 讀入很多套件，並且使用很多混合的方式讀入matplotlib與numpy
    - pylab：python的實驗室
    - inline：畫圖時，直接於瀏覽器顯示
    
    數學運算，可以使用`pi`、`sin()`...
    ```python
    pi
    #輸出
    3.141592653589793
    
    sin(pi/2)
    #輸出
    1.0
    ```
   
    可以使用`plot()`畫圖
     ```python
     plot([0,1,2,3,4])  #list中為y值，x會自動補上0, 1, 2,...
     ```
     > 當`plot()`僅有一個變數參數時，為`plot(y)`
     >> 產生由(0,0), (1,1), (2,2), (3,3), (4,4)點，依照x值由小到大連成的線
    
     ```python
     plot([-2, 1, 2.7, 3.3], [3, -5, 6, 0])
     ```
     > 當變數參數有兩個時，為`plot(y)`
     >> 產生產生由(-2,3), (1,-5), (2.7,6), (3.3,0)點，依照x值由小到大連成的線
    
    
     透過numpy套件內的`randa()`可以從常態分佈中產生亂數
     > 常態分佈：平均值為0，標準差為1
     ```python
     randn(10)
     #輸出
     array([-0.34781453,  0.66509422, -3.05840771,  0.13878172,  0.82760157,
        0.35053549,  0.95661882,  0.76511042,  0.08030247, -1.19390008])
     ```
    
#### Source
[Jupyter 的魔術指令](http://moocs.nccu.edu.tw/media/17831#tab-note-share)

[IPython 的 Notebook 界面](https://yenlungblog.wordpress.com/2013/11/21/python-ipython-%E7%9A%84-notebook-%E7%95%8C%E9%9D%A2/)
   
[👣](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)
   
   
### numpy.random
 > numpy的隨機函數
 
隨機函式的（random）功能較多，下面個別整理介紹

- `np.random.rand()`：`rand`根據給定的維度，生成\[0, 1)之間的隨機數據
   > 包含0，不包含1
   >> 返回指定維度array
   - 參數
     - np.random.rand(a)：一維array含a個元素
     - np.random.rand(a,b)：axb的二維array含axb個元素
     - np.random.rand(a,b,c)：a個bxc的二維array含ax(bxc)個元素
   
   [✍](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#-nprandomrand-)
    
- `np.random.randn()`：`randn`根據給定的維度，生成具**常態分配**的隨機數據，返回指定維度的array
    > 常態分配（standard normal distribution）：平均值為0，標準差為1，可記為N(0,1)
    >> [Learning more](https://blog.csdn.net/zenghaitao0128/article/details/78556535#1nprandomrandn%E5%87%BD%E6%95%B0)
   - 參數
     - np.random.randn(a)：一維array含a個元素
     - np.random.randn(a,b)：axb的二維array含axb個元素
     - np.random.randn(a,b,c)：a個bxc的二維array含ax(bxc)個元素
     
   [✍🏻](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#-nprandomrandn-)
   
- `np.random.randint(low, high=None, size=None, dtype='l')`：根據給定的維度，生成隨機**整數**
   > 範圍：\[low,high），包含low，不包含high
   - 參數
     - low：最小值
     - high：最大值
       > 無此參數時，預設生成隨機數範圍為[0，low)
       >> 包含0，不包含low
     - size：維度大小
     - dtype：數據類型，預設為np.int
    
   [✍🏼](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#-nprandomrandint-)
   
- `np.random.choice(a, size=None, replace=True, p=None)`：從**給定的一維數組中**產生隨機數
   - 參數
      - a：一組數組
        > 若a為整數，則數組為對應的np.arange(a)
      - size：維度大小
      - replace：是否有重複值
      - p：數組內元素的比重
        > 長度需與a相同\
        > 元素為機率：介於0-1之間，總和需為1
    
    [✍🏽](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#-nprandomchoice-)
    
- `np.random.seed()`：使得隨機數據可預測
     - 當設置相同的`seed()`時，每次生成的隨機數相同
     - 當不設置`seed()`時，每次生成不同的隨機數
      
     [✍🏾](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#-nprandomseed-)
     
#### § np.random.rand() §
生成\[0, 1)之間的隨機數據，包含0，不包含1

```python
import numpy as np

np.random.rand()   #返回float
#輸出
0.34556072704304774
```
沒有參數時，會返回一個介於0到1之間的float

```python
np.random.rand(2)
#輸出
array([0.53881673, 0.41919451])
```
一個參數（a）時，會返回一維的array含a個元素

```python
np.random.rand(2, 3)
#輸出
array([[0.6852195 , 0.20445225, 0.87811744],
       [0.02738759, 0.67046751, 0.4173048 ]])
```
兩個參數（a,b）時，會返回axb的二維array含axb個元素

```python
np.random.rand(2, 3, 4)
#輸出
array([[[0.6313557 , 0.89408194, 0.15488604, 0.06782768],
        [0.68288275, 0.60946259, 0.38781632, 0.73861597],
        [0.32914389, 0.28997312, 0.18071177, 0.20949215]],

       [[0.4477313 , 0.78821262, 0.11426555, 0.81428998],
        [0.66737157, 0.99489922, 0.56893378, 0.31914287],
        [0.75160793, 0.35091326, 0.52836748, 0.29405289]]])
```
三個參數（a,b,c）時，會返回a個bxc的二維array含ax(bxc)個元素

#### § np.random.randn() §
生成具**常態分配**的隨機數據，用法與`rand()`相似

```python
import numpy as np

np.random.randn() #返回float
#輸出
0.3912826547253317
```
沒有參數時，會返回一個float

```python
np.random.randn(5)
#輸出
array([-1.24274572,  1.59948307,  2.47441941, -0.33232485,  0.77714652])
```
一個參數（a）時，會返回一維的array含a個元素

```python
np.random.randn(5, 2)
#輸出
array([[ 0.09035118, -0.18659747],
       [ 0.74325857, -0.41917807],
       [ 0.00496046, -0.83355727],
       [-0.37935889, -0.54362249],
       [ 1.08361763,  0.12180609]])
```
兩個參數（a,b）時，會返回axb的二維array含axb個元素

```python
np.random.randn(2, 3, 4)
#輸出
array([[[ 0.65364026, -0.08915495,  0.90087165,  1.40248666],
        [ 0.21768255, -0.08359946, -1.83797562, -0.20606241],
        [ 0.04215544, -1.40456061,  1.97969053, -0.59401942]],

       [[ 0.98821644,  0.18310407,  0.92399299,  0.53317198],
        [-0.58513304, -0.56053692,  0.14077318,  1.76760095],
        [-0.78777374, -0.06172207,  0.23842679,  0.07477245]]])
```
三個參數（a,b,c）時，會返回a個bxc的二維array含ax(bxc)個元素

#### § np.random.randint() §
生成隨機**整數**

```python
import numpy as np

np.random.randint()
#輸出
TypeError: randint() takes at least 1 positional argument (0 given)
```
不可無參數，至少要有一個參數low

```python
np.random.randint(3) #int
#輸出
2
```
產生一個\[0, 3)之間的隨機整數

```python
np.random.randint(1, 5)
#輸出
3
```
產生一個\[1,5)之間的隨機整數

```python
np.random.randint(2, size=5)
#輸出
array([1, 0, 1, 1, 0])
```
產生一維array含5個元素，元素為\[0,2)之間的隨機整數

```python
np.random.randint(1, 5, size=(2,2))
#輸出
array([[3, 2],
       [2, 4]])
```
產生二為array含2x2個元素，元素為\[1,5)之間的隨機整數

#### § np.random.choice() §
從**給定的一維數組**中生成隨機數

```python
import numpy as np

np.random.choice()
#輸出
TypeError: choice() takes at least 1 positional argument (0 given)
```
至少要有一個參數

```python
np.random.choice(5)
#輸出
4

np.arange(5)
#輸出
array([0, 1, 2, 3, 4])
```
當一個整數參數（a）時，會產生一個0到a-1之間的隨機數

```python
np.random.choice(5,3)
#輸出
array([0, 3, 3])
```
產生一維array3個0到5-1之間的隨機數

```python
np.random.choice(5,3,replace=False) #不生成重複值
#輸出
array([1, 3, 0])
```
產生一維array含3個0到5-1之間互不相同的隨機數

```python
np.random.choice(5, size=(2,2))
#輸出
array([[4, 1],
       [2, 1]])
```
產生二維array含2x2個0到5-1之間的隨機數

```python
demo_list = ['lenovo', 'sansumg','moto','xiaomi', 'iphone']
np.random.choice(demo_list,size=(3,3))
#輸出
array([['xiaomi', 'moto'],
       ['iphone', 'moto']], dtype='<U7')
```
產生二為array含2x2個demo_list中隨機挑選的元素

```python
demo_list = ['lenovo', 'sansumg','moto','xiaomi', 'iphone']
np.random.choice(demo_list,size=(2,2), p=[0.1,0.6,0.1,0.1,0.1])
#輸出
array([['moto', 'sansumg'],
       ['sansumg', 'sansumg']], dtype='<U7')
```

#### § np.random.seed() §
使得隨機數據可預測

```python
np.random.seed(0)
np.random.rand(5)
#輸出
array([0.5488135 , 0.71518937, 0.60276338, 0.54488318, 0.4236548 ])
```
> 有設置`seed()`，重複執行隨機數仍相同

```python
np.random.rand(5)
#輸出
array([0.79172504, 0.52889492, 0.56804456, 0.92559664, 0.07103606])
```
> 無設置`seed()`，每次執行隨機數皆不同

#### Source
[numpy.random.randn()用法](https://blog.csdn.net/u012149181/article/details/78913167)

[👣👣](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## Markdown
  > 筆記
  
- 數學函式：LaTex語法
  > [Learning more](http://mohu.org/info/symbols/symbols.htm)
   - 隨文模式：在前後各加上一個"$"
   - 置中強調：在前後各加上兩個"$$"
   
   
  也可使用`SymPy`符號型計算套件，讓數學式子變漂亮
  ```python
  from sympy import *

  x = symbols('x')
  init_printing()
  (sin(x)*(1+x)**2)/(2*x**2+3)
  ```
   
#### Source
[常用数学符号的 LaTeX 表示方法](http://mohu.org/info/symbols/symbols.htm)

[使用Markdown輸出LaTex數學公式](https://www.jishuwen.com/d/2BU6/zh-tw)

[IPython 的 Notebook 界面](https://yenlungblog.wordpress.com/2013/11/21/python-ipython-%E7%9A%84-notebook-%E7%95%8C%E9%9D%A2/)

[🧠](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## Interactive
   > 與python互動

- `input()`：可在()內打入預期使用者輸入的提示
  > 輸入內容會被認為是**字串**
  
  
[👄](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

---
# week 2

[👉🏼HERE👈🏼](https://github.com/vanikk06/Machine-Learning/blob/master/Learning%20Python/week_2.ipynb)

python基本操作

## Format
   > 字串格式
   
在字串的串接中可以使用`+`運算符，也可使用`format`函式

- `format()`：字串格式
    1. 將變數放入字串中
    2. 資料型態轉換
    

在變數放入字串中，將字串中要放入變數的位置先放置"{}"，在字串後面增加`.format()`，函式內依照{}順序放入變數
> {}內可指定格式
```python
name = 'ET'
word = 'How are you?'

message = "Hello " + name + '. ' + word
message
#輸出
'Hello ET. How are you?'

message = "Hello {}. {}".format(name, word)
message
#輸出
'Hello ET. How are you?'
```
資料型態轉換
```python
m = 270
print(str(m) + '合台幣' + str(m*30.5) + '元')
#輸出
270合台幣8235.0元

print('{}合台幣{}元'.format(m, m*30.5))
#輸出
270合台幣8235.0元

print('{m}合台幣{n}元'.format(m=m, n=m*30.5))
#輸出
270合台幣8235.0元
```

[👥](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

## Function
   > 函式
   >> 函式名不可有空格
   
- `return`：函式內，設定回傳值
- `print()`：打印，無回傳值

[👤](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

## Cutting String
   > 與list相同
   
切割方式與list相同（中文字串也可處理）
- index從零開始
- 使用`:`時，取頭不取尾

[🗣](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

## list()
   > 快速稱成list
   
- `list()`：產生一個list

    可搭配`range()`函式，產生一組有順序的數列
    > range()無法直接顯示
     ```python
     range(10)
     #輸出
     range(0, 10)
     ```
     
     ```python
     list(range(10))
     #輸出
     [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
     
     list(range(3,15)) #取頭不取尾
     #輸出
     [3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]
     ```
     
     也可放入字串
     ```python
     list('ABCDEF')
     #輸出
     ['A', 'B', 'C', 'D', 'E', 'F']
     ```
     
[🧞‍♂️](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)
     
---
     
# week 3
  > numpy、向量化...
  
[👉🏼HERE👈🏼](https://github.com/vanikk06/Machine-Learning/blob/master/Learning%20Python/week_3.ipynb)
  
- 一個tab = 4個空格

## Git
  > [Learning more_video](https://www.youtube.com/watch?v=4eOOZeL2WJ4&list=PLRxMjOjh7Y5d_eRLWr-DaujfI2YHgCqIf&index=1)
  
  > [Learning more_book](https://gitbook.tw/)
  
Git是一種**分散式版本的版本控制系統**，是為了更好管理Linux內核而開發的
> 將檔案狀態作為更新歷史紀錄保存

> 只關心檔案的「內容」，所以只要是檔案，都可以使用Git來管理

- 版本控制系統（Version Control System）
    - 版本：在一個目錄下，不管是新增、刪除檔案或修改檔案內容，只要是對目錄下的檔案做出更動，都稱為一個版本
    - 版本控制系統：是指會記錄這些所有的狀態變化，並且可以隨時切換到過去某個「版本」時候的狀態


Git優點：
  1. 免費、開源：
  
     Git是由Linux核心的作者Linus Torvalds在2005年為了管理Linux核心程式碼，僅花了10天所開發出來的，除了可免費使用外，整個Git的原始程式碼也可在網路上取得。
  2. 速度快、檔案體積小：
  
     Git特別之處在於它並不是記錄版本的差異（大部分版本控制系統為此），而是記錄檔案內容的「快照」（snapshot），它讓Git可以非常快速的切換版本。
  3. 分散式系統：
     
     以往其他的版本控制系統，是屬於集中式的板控系統（Centralize Version Control），需要一台專用的伺服器，所有的更新都需要跟這台伺服器溝通，萬一這台伺服器壞了，或是沒有網路連線的環境，版本控制功能就沒辦法使用
     
     而Git是一款**分散式的版控系統（Distributed Version Control）**，雖然通常也會有共同的伺服器，但即使在沒有伺服器或沒有網路的環境，依舊可以使用Git來進行版控，等到伺服器恢復正常運作或是在有網路的環境後再進行同步，不會影響。（實際上，在使用Git的過程，大部分的Git操作也都是在自己電腦本機就可以完成的）
  
  

#### Git vs. GitHub

兩者並不相同，很多新手容易誤解，以為Git就是GitHub（或是以為GitHub就是Git）
- Git：一種工具，一款版本控制軟體
- GitHub：一個商業網站，其本體是一個Git伺服器
  > 在GitHub上的應用程式可以透過Web介面來操作一些原本需要複雜的Git指令才能做到的事
  
#### Source
[你知道 Git 是怎麼一回事嗎](https://www.youtube.com/watch?v=LgTf7m5B0xA)

[Git和Github小白入门教程1，什么是Git，Github？](https://www.youtube.com/watch?v=4eOOZeL2WJ4&list=PLRxMjOjh7Y5d_eRLWr-DaujfI2YHgCqIf&index=1)

[為你自己學 Git](https://gitbook.tw/)

[什麼是 Git？為什麼要學習它？](https://gitbook.tw/chapters/introduction/what-is-git.html)

[連猴子都能懂的Git入門指南](https://backlog.com/git-tutorial/tw/intro/intro1_1.html)

[🎰](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## Linux
  > [Learning more](http://linux.vbird.org/linux_basic/0110whatislinux.php)

Linux是一個大眾可以免費使用，並自由參與、集體協作的作業系統（基於POSIX和UNIX），繼承了Unix以**網絡**為核心的設計思想，是一個性能穩定的多用戶網絡作業系統，能運行主要的UNIX工具軟體、應用程式和網路協議，支持32位和64位硬體，


- OS（作業系統）：主要功能在於管理、協調電腦硬體資源，使其可以正確無誤的完成使用者所下達的各種指令，同時確保整個電腦可以在一個穩定的狀況下提供服務。
  > [Learning more](https://sls.weco.net/node/21321)
  
Linux特色：
  1. 自由、開放：基於GPL（General Public License）架構下的自由軟體
     > 開放性架構：任何人都可以自由的使用或是修改其中的原始碼意思
  2. 配備需求低廉：可支援個人電腦的x86架構
  3. 功能強大且穩定：Linux是基於Unix概念發展出的，具有與Unix系統相似的程式介面和操作方式，以及其穩定有效率的特點
  4. 獨立作業
  5. 洞的修補快速：因為自由軟體，開發支援者眾多，可以隨時獲得最新的安全資訊，並給予即時的更新
  6. 多工、多使用者：與Windows系統不同，Linux主機上允許同時多人上線來工作， 並且資源的分配較為公平

#### Source
[第一章、Linux是什麼與如何學習](http://linux.vbird.org/linux_basic/0110whatislinux.php)

[Linux是什麼？從網站開發到物聯網無所不在的OS作業系統介紹](https://progressbar.tw/posts/113)

[Linux系統介紹](http://neuron.csie.ntust.edu.tw/homework/94/os/homework/homework1/A9415061_2/linux.htm)

[UNIX and Linux overview](http://nmc.nchu.edu.tw/tanet/unix&linux.htm)

[6大主流PC作業系統，你在用的是哪一款？](https://kknews.cc/tech/o24xjrq.html)

[01. 作業系統原理簡介](https://sls.weco.net/node/21321)

[🕹](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## MySQL vs. NoSQL

資料庫（Database）是專門給資料儲存使用的，使用了很多優化功能，讓速度更快

- [MySQL](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#-mysql-)
- [NoSQL](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#-nosql-)



#### § MySQL §
  > RDBMS（關聯式資料庫管理系統）
  >> 可使用SQL
  
MySQL為關聯式資料庫（RDBMS，Relational Database Management System）的一種，具有較久的歷史（自1970年代），按照一套規則（Schema欄位架構）將資料庫管理系統視為關聯式的結構，並引入資料庫正規化的概念，以減少資料冗餘同時增進資料完整性的方式建構關聯式資料庫的程序

- SQL（Structured Query Language）：**關聯式資料庫的標準查詢語言**，並非資料庫系統（MySQL才是一個資料庫系統）

- Schema欄位架構：以此確立資料表之間的關聯，通常是**事先**設計好的架構，上線之後要進行欄位變更非常麻煩

RDBMS優點：
1. 標準符合性（ACID）：透過精確的交易（Transaction）設計，讓資料存取或異動過程中不會受到干擾
      - 單元性（Atomicity）：確保交易作為最小運作單位
      - 一致性（Consistency）：異動過程確保整體資料庫的一致
      - 獨立性（Isolation）：執行多筆交易時，各筆交易獨立不受其他較易影響
      - 持久性（Durability）：交易過程不會變動到原始資料
2. 以標準化為前提，數據更新的開銷很小
    > 資料以結構化方式組織
3. 可進行較SQL較複雜的指令查詢
4. 發展較久，較為成熟

遇到困難：

隨著網路的不斷發展，在現在雲計算的時代，對技術提出了更多的需求
1. 低延遲的讀寫速度
    > RDBMS讀寫慢，此情況主要發生在數據龐大到一定程度，由於RDBMS的邏輯複雜，使得其非常容易發生死鎖...等等的問題，導致讀寫速度下滑嚴重
    
2. 支持海量的數據和流量：「搜尋」需要利用PB級別的數據和應對百萬級的流量
    > RDBMS因ACID架構擴展困難、且為有限的支撐容量
    
3. 大規模集群的管理：系統管理員希望「分佈式應用」能更簡單的部屬和管理
    
4. 龐大營運成本的考量：於硬體、軟體和人力成本上能大幅度的降低
    > RDBMS隨著系統的規模，成本會不斷的上升且價格驚人

#### § NoSQL §
  > Not Only SQL、non-relational\
  > 具備彈性資料模型的高效能非關聯式資料庫
  >> [快速認識4類主流NoSQL資料庫](https://www.ithome.com.tw/news/92507)\
  >> [什麼是 NoSQL？](https://aws.amazon.com/tw/nosql/)


NoSQL是一群資料庫的統稱，此詞最早出現於1998年開發的一個輕量、開源且不提供SQL功能的關聯式資料庫，無法嚴格定義其屬性，頂多是無綱要（不去定義每個欄位存放某種特定的資料）及不實作ACID

![](https://1fly2sky.files.wordpress.com/2015/10/oos.jpg?w=383&h=226&zoom=2)

與RDBMS最大的差別，在於沒有一套固定的規則，較為彈性（但相對查詢資料的速度較慢）

NoSQL觀念：
  1. NoSQL大多為**開源的分散式資料庫系統**
     > 所以無法使用SQL，查詢速度較慢
  2. 具**水平擴充能力**：只要增加新的伺服器節點，就可不斷擴充資料庫系統的容量（且成本低廉）
  3. 打破Schema欄位架構的限制：改用key-value資料結構來解決龐大資料的異動困難
      > key-value是將一筆資料的結構，簡化到只有一個key值對應到一個value值，因此每筆資料之間沒有關聯性
  4. 資料遲早會一致：為了保持**分散式的擴充架構**，無採用ACID交易設計，而是採用另一種CAP的資料庫理論
      - Consistent：一致性，與RDBMS不同，採Eventually Consistency作法
          > 容許不同節點之間的同步過程會有時間落差，只要保證最終資料會達到一致
          >> 導入NoSQL資料庫時，開發者得先評估資料的性質，是否能承擔資料遺失的風險
      - Availabilit：可用性
      - Partition Tolerance：中斷容忍性
      > 理論上，無法同時兼顧此三種特性，通NoSQL會選擇其中兩種特性設計（通常為CP、AP）
      
  5. 成熟度不足，版本升級風險高：為近幾年因應資料暴漲問題而出現的資料庫，本身的功能還不完整；另一方面，NoSQL大多透過API來存取資料，新的版本若增加了新功能，也會改變API的參數或呼叫方式

#### Source
[在 NoSQL 和傳統關聯式資料庫之間做出決定](https://navicat.com/cht/company/aboutus/blog/1002-deciding-between-nosql-and-traditional-relational-databases.html)

[快速認識4類主流NoSQL資料庫](https://www.ithome.com.tw/news/92507)

[了解NoSQL不可不知的5項觀念](https://www.ithome.com.tw/news/92506)

[什麼是 NoSQL？](https://aws.amazon.com/tw/nosql/)

[大數據怎麼存-MySQL?NoSQL?](https://1fly2sky.wordpress.com/2015/10/30/%E5%A4%A7%E6%95%B8%E6%93%9A%E6%80%8E%E9%BA%BC%E5%AD%98-mysqlnosql/)

[閃開！讓專業的來：SQL 與 NoSQL](https://ithelp.ithome.com.tw/articles/10187443)

[關於NoSQL與SQL的區別](https://read01.com/GPnEx.html#.XjB8jGgzbb0)


[📢](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## numpy package
- numpy套件：應用於科學計算、數據分析
  > 主要型態：array
  
  - **array oriented**：陣列導向的程式設計方式（數據分析中的重要概念）
     > 少用迴圈，多用array

[🎮](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

 
## Import
   > 正規匯入套件方法
   
- `from` 套件名 `import` 函式：讀入套件內的函式
    - `*`：代表全部
      > 不建議如此使用（或是用%pylab inline）
      >> 若在不同套件中，出現相同命名的函式，則可能會導致混亂或衝突
      ```python
      from numpy import *  #會將numpy內的所有函式全部讀入
      ```
      
- `import`：讀入整個套件
  > 與`from xxx import *`等價
  
  - `import` 套件名 `as` 套件綽號：讀入整個套件，並給套件一個綽號
    ```python
    import numpy as np #np為numpy的標準綽號
    ```
      
 
P.S.小心"random"與"numpy.random"隨機數選取的範圍不同
  - random：`randint(a,b)`
    - 範圍：\[a, b]
      > 包含a與b
    - 參數：兩個，僅選取範圍的上限與下限（若要選取多個隨機數，可使用for迴圈）
  
    ```python
    randint(1, 10)
    #輸出
    10
    
    randint(1,10, 50)
    #輸出
    TypeError: randint() takes 3 positional arguments but 4 were given
    ```
 - numpy.random：`randint(low, high=None, size=None, dtype='l')`
    - 範圍：\[low, high)
      > 包含low，不包含high
    - 參數：最多可四個，可指定要重複的次數
    
    ```python
    randint(1, 10)
    #輸出
    9
    
    randint(1,10, 50)
    #輸出
    array([4, 5, 1, 7, 1, 1, 9, 9, 3, 6, 4, 8, 7, 7, 7, 2, 3, 3, 9, 5, 8, 4,
       7, 1, 7, 4, 2, 8, 1, 7, 9, 3, 9, 7, 8, 9, 9, 2, 7, 6, 6, 4, 7, 7,
       7, 6, 9, 5, 7, 5])
    ```

[🎲](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

### print()
  > 打印函式
  
`print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)`
- end：文末符
- sep：分隔符
  

預設在打印字串後，文末會加上「換行符號」，若想要更改換行的預設，可使用`end`參數
```python
print('a')
print('b',  end='.')
print('c', end='/')
#輸出
a
b.c/
```
在打印多個字串時，預設會使用「空格」將多個字串串成一行，可使用`sep`參數改變分隔符
```python
print('a', 'b', 'c', sep='/')
#輸出
a/b/c
```
  

#### Source
[Python初學重點 (04) – 聊聊print()](https://extenshu.com/2017/09/24/python%E5%88%9D%E5%AD%B8%E9%87%8D%E9%BB%9E-04-%E8%81%8A%E8%81%8Aprint/)

[Python3 print 函數用法總結](https://www.runoob.com/w3cnote/python3-print-func-b.html)

[🎲🎲](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## Data Analysis

★ 基本概念：能不用迴圈，就盡量不要用
   > Why？效率問題（計算速度上不同）
   >> 盡量使用**array導向（向量導向）**

常用套件：
  - `%matplotlib inline`：魔術指令，讓matplotlib畫出的圖直接呈現在網頁上，不另外開視窗
     > 新型的python不一定需要，有時使用甚至會造成錯誤，導致matplotlib無法使用
  - `numpy`：array，可做類似**向量**的運算
  - `matplotlib.pyplot`：畫圖
  ```python
  import numpy as np
  import matplotlib.pyplot as plt
  ```
  
[🔮](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

## Array
  > numpy套件
  
- `np.array()`：將list轉換為numpy array
- `np.zeros()`：生成一個元素皆為0的array
  > 參數：array形狀
- `np.ones()`：生成一個元素皆為1的array
  > 參數：array形狀
- `np.eye()`：生成一個對角矩陣的array
  > 參數：整數
  >> 對角矩陣形狀必為nxn
- `np.linspace()`：產生一連串的值
  > np.linspace(起始值, 結束值, 值的個數)
- `np.dot()`：內積，按照個別位置相乘，在取全部總和
  > np.dot(array1, array2)：將array1與array2做內積
  >> [✍🏻](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#-npdot-)
- `array.shape`：查看array形狀，也可改變array形狀
  > 變更原始資料
  >> [✍🏽](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#-arrayshape--arrayreshape-)
- `array.reshape()`：改變array形狀
  > 不變更原始資料，產生一個新array
  >> [✍🏽](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#-arrayshape--arrayreshape-)
- `np.sinc(x)`：返回元素經過sinc函數計算的array
  > x：要計算`sinc()`的值（可為多維）
- `np.meshgrid(x格線, y格線)`：找出各個格點座標
  > x-座標放一起；y-座標放一起\
  > 回傳 2D array
  >> [✍🏾](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#-npmeshgrid-)
  
#### § np.dot §
  > 內積

等價於：先進行array相乘，在使用`array.sum()`取總和 
   ```python
   import numpy as np

   grades = np.array([85, 70, 82])
   weights = np.array([0.3, 0.4, 0.3])

   g = grades*weights
   g.sum()
   #輸出
   78.1
   ```
   > array與array相乘，會按照各別的對應位置相乘（若元素個數不相等，會出現錯誤）

   ```python
   np.dot(grades, weights)
   #輸出
   78.1
   ```

array除了一維以外，還可以處理多維的資料
   ```python
   gradess = np.array([[85, 70, 82],
           [75, 92, 85],
           [66, 67, 64],
           [87, 94, 60]])
   weights = np.array([0.3, 0.4, 0.3])        

   print('gradess', np.shape(gradess))
   print('weights', np.shape(weights))
   #輸出
   gradess (4, 3)
   weights (3,)
   ```

   ```python
   np.dot(gradess, weights)
   #輸出
   array([78.1, 84.8, 65.8, 81.7])
   ```
   > 原理：將weights視為一個元素，以此元素對gradess內的每個元素做出相同的運算

使用內積的兩個array，放置位置（順序）必須符合內積對矩陣的形狀要求
   ```python
   np.dot(weights, gradess)
   #輸出
   ValueError: shapes (3,) and (4,3) not aligned: 3 (dim 0) != 4 (dim 0)
   ```
   > 參數位置（順序）放置不當，會出現錯誤


#### § array.shape ＆ array.reshape() §
  > 形狀
  
兩者差異在於，**是否會更動到原始資料**

查看array形狀
```python
A = np.random.randn(50)
A.shape
#輸出
(50,)
```
> 有50個元素


使用`array.shape`改變array形狀
> 要確保形式符合元素個數
```python
A.shape = (5, 10)
A
#輸出
array([[65.82782968, 36.20062413, 49.34737677, 65.27853253, 36.7678792 ,
        57.02734881, 50.14276113, 52.53827083, 55.34587881, 52.92872278],
       [63.09522261, 34.48059518, 32.36444097, 49.93984736, 42.71135319,
        40.55373232, 35.68639178, 55.5831795 , 41.9780338 , 74.98648563],
       [36.77538722, 59.62814077, 66.93109253, 63.60607722, 39.15664516,
        46.93492248, 33.5624362 , 49.47248012, 62.07935996, 50.56844756],
       [45.03894149, 41.65042371, 37.65927025, 61.13620592, 50.089949  ,
        36.59087623, 40.04238486, 41.11346863, 45.39145064, 50.52155565],
       [34.4753731 , 43.62682739, 39.71701874, 52.270227  , 72.6607359 ,
        58.17894429, 47.71655182, 39.91744768, 48.40310346, 50.50243736]])
```
> array內有5個元素，每個元素皆為一個有10筆資料的array

使用`array.reshape`改變array形狀
> array.reshape為函式，直接輸入參數
```python
A.reshape(2, 25)
#輸出
array([[65.82782968, 36.20062413, 49.34737677, 65.27853253, 36.7678792 ,
        57.02734881, 50.14276113, 52.53827083, 55.34587881, 52.92872278,
        63.09522261, 34.48059518, 32.36444097, 49.93984736, 42.71135319,
        40.55373232, 35.68639178, 55.5831795 , 41.9780338 , 74.98648563,
        36.77538722, 59.62814077, 66.93109253, 63.60607722, 39.15664516],
       [46.93492248, 33.5624362 , 49.47248012, 62.07935996, 50.56844756,
        45.03894149, 41.65042371, 37.65927025, 61.13620592, 50.089949  ,
        36.59087623, 40.04238486, 41.11346863, 45.39145064, 50.52155565,
        34.4753731 , 43.62682739, 39.71701874, 52.270227  , 72.6607359 ,
        58.17894429, 47.71655182, 39.91744768, 48.40310346, 50.50243736]])
```
> array內有2個元素，每個元素皆為一個有25筆資料的array
>> 產生新的array，不影響原始資料
```python
A
#輸出
array([[65.82782968, 36.20062413, 49.34737677, 65.27853253, 36.7678792 ,
        57.02734881, 50.14276113, 52.53827083, 55.34587881, 52.92872278],
       [63.09522261, 34.48059518, 32.36444097, 49.93984736, 42.71135319,
        40.55373232, 35.68639178, 55.5831795 , 41.9780338 , 74.98648563],
       [36.77538722, 59.62814077, 66.93109253, 63.60607722, 39.15664516,
        46.93492248, 33.5624362 , 49.47248012, 62.07935996, 50.56844756],
       [45.03894149, 41.65042371, 37.65927025, 61.13620592, 50.089949  ,
        36.59087623, 40.04238486, 41.11346863, 45.39145064, 50.52155565],
       [34.4753731 , 43.62682739, 39.71701874, 52.270227  , 72.6607359 ,
        58.17894429, 47.71655182, 39.91744768, 48.40310346, 50.50243736]])
```
#### § np.meshgrid() §
  > 格點
  
將x格點值的list與y格點值的list放入`np.meshgrid()`函式中  
```python
xx = [1,2,3,4]
yy = [5,6,7,8]

X, Y = np.meshgrid(xx, yy)
```
> 回傳會將x-座標值放一起，y-座標值放一起，因此使用兩個變數
  
```python
X
#輸出
array([[1, 2, 3, 4],
       [1, 2, 3, 4],
       [1, 2, 3, 4],
       [1, 2, 3, 4]])
```
> 從x座標來看，對應y軸的第一列、第二列...
```python
Y
#輸出
array([[5, 5, 5, 5],
       [6, 6, 6, 6],
       [7, 7, 7, 7],
       [8, 8, 8, 8]])
```
> y座標的第一列、第二列...

#### Source
[numpy.sinc](http://doc.codingdict.com/NumPy_v111/reference/generated/numpy.sinc.html)

[🎙](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

---

# week 4
[👉🏽HERE👈🏽](https://github.com/vanikk06/Machine-Learning/blob/master/Learning%20Python/week_4.ipynb)

- Learning step
  > 程式目標：Resolve problems
  - Make it work：讓程式會動
  - Make it right：讓程式與目標一致
  - Make it fast：加快程式的速度、效率

## Interact
   > 與jupyter互動，可做出GUI（圖形使用者介面）
   >> 使用ipywidgets套件
   
- `interact()`：產生互動工具
  > interact(函數, 參數=輸入值)
  >> 每種資料型態，都有與其相對應的互動功能
  
- `interact_manual()`：與`interact()`相似，差別在於要**手動按按鈕**才會產生東西
  
  - 數字：拉桿
  - 字串：輸入視窗
  - List：下拉選單
  - 字典：key的下拉選單
    > 出現值為其對應的value
  - bool：勾選的checkbox
  
  ```python
  from ipywidgets import interact
  
  def f(x):
    print(x)
    
  interact(f, x=3) #產生拉桿
  interact(f, x=3.) #也可將範圍為符點數
  
  interact(f, x=(1,10)) #設定範圍
  interact(f, x=(1.,10.))
  
  
  interact(f, x='hi') #產生輸入框
  
  
  interact(f, x=['台北', '台中', '台南', '高雄']) #下拉式選單
  
  
  interact(f, x={'台北':1, '台中':2, '台南':3, '高雄':4}) #對應value的下拉式選單
  
  
  interact(f, x=True) #勾選的checkbox
  ```
  
[☃](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## GUI
 > Graphical User Interface（圖形化介面、圖形使用者介面、圖形化輔助使用者操作介面）
 
GUI可以說是讓電子裝置普遍化的一個超重要變革，它是指**採用圖形式顯示的計算機操作環境使用者介面**。\
在早期計算機的使用方式，必須要靠DOS指令（也就是所謂的CLI，Command-Line Interface）才能操作電腦與電腦互動，但有了GUI不需要再死記硬背大量的命令，極大地方便了非專業使用者對計算機的操作，他們只要透過**視窗、圖示、選單、按鍵...等**方式就可以輕鬆的進行操作。

目前知名的GUI作業系統為Windows與MAC OS X，當然現在使用的消費型電子產品也具有GUI概念，全部都會預載GUI

- （嵌入式）GUI基本特點要求
  - 輕型、占用資源少
  - 高效能
  - 高可靠性
  - 方便移植
  - 可配置

#### Source
[GUI是什麼](https://www.itread01.com/content/1541936192.html)

[讓使用電腦不再黑白的人生 - GUI 圖形使用者界面](https://chinese.engadget.com/2011/04/13/gui/?guccounter=1&guce_referrer=aHR0cHM6Ly93d3cuZ29vZ2xlLmNvbS8&guce_referrer_sig=AQAAAIfNBHHhCvF_z75stlRxvsOkfH75vjdqiZhENs2Qpl3Jk_NwCLYbTQBrhKj6WfaUPZcl1jB_r375x32gcliakOlQAzMKcnjYQCSMF2GGyWqkzsOdcUveZnwgbsvkA-_OHZiFETh4FxakgnRpWdG81kvcEDYwTDYFzaw_cta6DEox)

[⛄](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

---

# week 5
[👉🏻HERE👈🏻](https://github.com/vanikk06/Machine-Learning/blob/master/Learning%20Python/week_5.ipynb)

## Swift
   > 建造 App 的開放程式語言
   >> [Learning more_Stanford](https://www.youtube.com/playlist?list=PLPA-ayBrweUzGFmkT_W65z64MoGnKRZMq)\
   >> [Learning more_王巍](https://swifter.tips/)
   
   
Swift 是強大且直覺的程式語言，由Apple創造，專門用來撰寫iOS、Mac、Apple TV 與 Apple Watch 的軟體，自由度高且為開放原始碼，是一套快速且有效率的語言，能夠提供即時回應，更可整合現有的 Objective-C 程式碼

優點：
  - 可以開發 iPhone/iPad/Mac 的 App，且為開源，未來將有更多平台使用Swift
    > 已開發 App：Airbnb、LinkedIn
    >> 手機 App 的應用廣泛，與生活結合，很有實用性
  - 開發環境整合，易於上手又強大
    > 整合 Objective-C
  - Swift 語言完整性夠
   
#### Others Language
- 程式語言
  - C：強大，可用於內嵌式系統，也可開發服務器級的應用
  - Python：易於上手，且應用廣泛
  - Swift：Apple推出，取代 Objective-C
  - Java：跨平台的程式語言

- Markup Language（標記語言）
  > e.g. 網頁的HTML/CSS


#### Swift 相關社群
- Swift Taipei
  > [more](https://www.meetup.com/Swift-Taipei-User-Group/)
- Swift Girls
  > [more](https://www.appcoda.com.tw/swift-girls-interview/)

- CocoaHeads Taipei
  > [more](https://cocoaheads.tw/)


#### Source
[Swift，強大的開放程式語言，讓人人創造傑出的 App](https://www.apple.com/tw/swift/)

[TOLL-FREE BRIDGING 和 UNMANAGED](https://swifter.tips/)

[Stanford CS193P iOS 11 Swift 4](https://www.youtube.com/playlist?list=PLPA-ayBrweUzGFmkT_W65z64MoGnKRZMq)

[想學程式語言，但完全不懂？從 Swift 開始吧！](https://coder01.com/blog/%E6%83%B3%E5%AD%B8%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80%EF%BC%9F%E5%BE%9E-swift-%E9%96%8B%E5%A7%8B%E5%90%A7%EF%BC%81/)

[🍕](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## Pandas
   > Python的Excel
   >> 用於「整理資料」：數據分析有80%的時間在做資料清理\
   >> 再利用Numpy、SKLearn套件，進行「計算分析」

奠定python奠定數據分析龍頭地位的重要套件

- 核心概念：
  - 資料型態有兩種
    - Series：類似list、array，每個欄位皆有名稱
    - DataFrame：類似Excel的試算表

[🍔](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## Practice Pandas
  > [Learning more](https://github.com/justmarkham/pandas-videos)

一般先用 Pandas 進行資本處理，找出想要的資料後，再使用 Numpy 做進一步的分析

- csv：資料格式，每欄用逗點隔開
- `%ls`：魔術指令，可查看此目錄下有什麼檔案


#### § Pandas §
  > Pandas傾向不變更原始資料，一般指令無設定參數會產生新的datafrme（有回傳值）
  >> pandas_datareader.data套件：有財務、股票相關的實際資料
   ```python
   import pandas_datareader.data as web
   ```
  
- `pd.read_csv('檔名')`：讀入csv檔
   > 也可讀取網路上的csv檔
- `dataframe名稱.head()`：查看前五行資料
- `dataframe名稱.項目名稱.mean()`：平均值
- `dataframe名稱.項目名稱.std()`：標準差
- `dataframe名稱.項目名稱.sum()`：總和
    - .sum(0)：按列方向相加
    - .sum(1)：按行方向相加
- `dataframe名稱.describe()`：基本的統計計算
- `dataframe名稱.DataFrame(array, columns=項目list)`：建立一個dataframe
    - array：放入的資料
    - columns：欄位名稱
- `dataframe名稱.concat()`：合併dataframe
  > 空格會自動補遺失值
    - axis：控制合併方向
      > 矩陣：先row後column
      - 0：按列方向合併，上下
      - 1：按行方向合併，左右
- `dataframe名稱.index`：更改index
- `dataframe名稱.groupby('項目')`：依項目集合值
- `dataframe名稱.count()`：計算次數
- 相關係數
  - `dataframe名稱.corr()`：所有的相關係數
  - `dataframe名稱.項目A.corr(dataframe名稱.項目B)`：各別的相關係數
     > A與B之間的相關係數
- 取單項資料
  > 索引使用"\[ ]"
  >> 取出的一欄串數據稱為Series\
  >> 每個Series都有各自的欄位名稱(columns)
  - `datafame名稱[項目名稱]`
  - `dataframe名稱.項目名稱`
- `dataframe名稱['新增項目'] = 要新增的內容`：新增一個欄位
- `dataframe名稱.loc[]`：尋找索引對象（適用於要更改索引對象時）
  > 參數：欄位名
- `dataframe名稱.sort_values()`：排序
    - by：基於何者進行排序
      > 若為list，則按順序作為基準
    - ascending：是否遞進排列
      - True：由小到大
      - False：由大到小
    - inplace：是否變更原始資料
      - True：變更原始資料
        > 無回傳值
      - False：預設，不變更原始資料
        > 有回傳值
- 將單項資料轉換成array
  - `dataframe名稱[項目名稱].values`
  - `dataframe名稱.項目名稱.values`
- 畫圖
  > 支援直接畫圖
  - `dataframe名稱.項目名稱.plot()`：單項資料折線圖
     - kind：種類
       > e.g.bar（長條圖）
  - `dataframe名稱.項目名稱.hist(bins=區分區間)`：單項資料直方圖
  
  
- `web.DataReader(股票代號, 資料源, 開始時間, 結束時間)`：讀入股票資料
- `dataframe名稱.diff()`：可計算此期與前一期的差異
  > 可進一步應用來計算「報酬率」
  >> 報酬率：(今日報酬率-昨日報酬率)/昨日報酬率
- `dataframe名稱.rolling()`：移動平均
  > 其一應用：#移動平均：讓漲幅變平滑，好看出走向
  - window：取多少範圍的平均


#### § Numpy §

- `array.mean()`：平均值
- `array.std()`：標準差

#### Source
[Python pandas Q&A video series](https://github.com/justmarkham/pandas-videos)

[🍟](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

## Moving Average
  > 移動平均線
  >> 股市分析中的常見指標
  
「移動平均線」是利用統計分析的方法，將一定期間內的價格（收盤價）加以平均，並將不同期間的平均值連接起來

- 功能：觀察價格**波動趨勢**的技術指標之一 
  > 快速工具：不必對股票有太多了解，就可從圖表中得出股票於年、季、月、週等表現
    - 方向：表示價格的走勢
      > 價格上升，移動平均線上揚
    - 橫行：表示價格的波動
 
- 常見種類：
   > 期間長短搭配不同的投資（愈短期的投資，會使用愈短的期間）
   >> 可分為「短期」、「中期」、「長期」
   - 短期：愈快反應價格走勢的變化
      - 5日（周線）
      - 10日
   - 中期
      - 20日（月線）
      - 50日
      - 60日（季線）
   - 長期：愈能反映長期的整體價格趨勢
      - 100日
      - 200日
      - 250日（年線、牛熊分界線）

- 應用：
  - 單線：股票價格"高於平均線"或"低於平均線"時，作為買入賣出的時機
    > 愈長期投資，均線數字愈大
  
  - 雙線：兩條期間不同的平均線
      - 黃金交叉（Golden Cross）：短期平均線升穿長期平均線
        > 買入時機
      - 死亡交叉（Death Cross）：短期平均線低穿長期平均線
        > 賣出時機
        >> 常見搭配：\
        >> 10 vs. 50\
        >> 20 vs. 50\
        >> 50 vs. 250
        
統計指出，移動平均線的普遍用法成效不大（以其作為入市時機），不適合作為買賣的策略，有時發出買入訊號後，股票價格反而跌，可搭配配合不同的指數，商品、外匯或不同的分析共具使用

#### Source
[一文看懂移動平均線(Moving Average)及其運用策略](https://www.dailyfxasia.com/cn/feaarticle/20190222-6337.html)

[投資初哥的殺手！移動平均線：你一直都用錯！均線真正用法](https://www.youtube.com/watch?v=BnkI0wejW-c)

[🌭](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

---

# week 6
  > 數據分析：預測
  >> Scikit-Learn
  
[👉🏿HERE👈🏿](https://github.com/vanikk06/Machine-Learning/blob/master/Learning%20Python/week_6.ipynb)

數據分析、人工智慧、機器學習，皆在學習現實世界中的「函數」
> input與output必須是「一堆數字」，否則電腦無法計算

- 函數：定義域 → f(x) → 值域
  > 問對問題重要
  >> y要一定程度的被x涵蓋
    - f(x) = y：x、y通常是一個或一組數字
       - x：features（特徵）
       - y：預測值
    - 定義域：所有可能的問題
      > 想預知的東西
    - 值域：所有可能的答案

- 步驟：
    1. 數學建模，將想要解決的問題化為函數
    2. 以「歷史資料」找出此函數
       >  e.g.回歸、機器學習、神經網路
    3. 評估是否符合需求
    
- noise：雜訊，相信數據背後含有一個涵式，在數據中不符合此函式的資料就稱為noise

## Linear Regression
   > 線性迴歸
   >> 可解決直線函式、多變數函式，甚至是非線性函式
 
利用線性迴歸來學習函數
> 觀察資料其函數為**直線方程式**
>> f(x) = ax + b

其中a、b為線性迴歸要學習的參數，也就是要找的目標（可利用統計或線性代數的最小平方法）

#### § Practice §
使用`sklearn`套件裡面的`LinearRegression`函式
```python
from sklearn.linear_model import LinearRegression
```
★ 注意！在此函數要的資料類型並非一個array，而是要將每筆訓練資料\[ ]起來，當作一列

利用`array.reshape()`將 1x50 的array轉換為 50x1 的array

先將`LinearRegression`函式實例化，再利用`.fit()`擬合資料，最後利用`.predict()`預測
- `.fit(X, y)`：讓模型學習
  - X：真實資料中的特徵變數（訓練集）
  - y：真實資料中的目標變數（訓練集）
- `.predict(X)`：預測
  - X：真實資料中的特徵變數（測試集）
  
[👑](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

## data split
  > 資料集切割
  >> 分成「訓練資料」與「測試資料」
  
一般想要看算出的逼近函式在預測上是否是可靠的，會把一些資料留給「測試」，也就是在電腦計算時，不會計算到這些資料。\
等函式學成之後，再拿這些保留資料看函式是否準確

- training data：訓練集，訓練模型
- testing data：測試集，測試模型的準確度如何

使用`sklearn.model_selection`套件內的`train_test_split`來**亂數選一定百分比**的資料
```python
from sklearn.model_selection import train_test_split

x_train, x_test, y_train, y_test = train_test_split(x, y,
                                                    test_size = 0.2,
                                                    random_state=87)
```
- `train_test_split(x, y, test_size, random_state)`：亂數分割「訓練集」與「測試集」
    - x：真實資料的特徵變數
    - y：真實資料的目標變數
    - test_size：測試集的大小
      > 百分比
    - random_state：隨機種子
      > 指定隨機的種子，可以知道這次抽取亂數的方式為何
      >> 1. 下次可以使用相同分配的亂數
      >> 2. 有時分析結果好，是因為亂數分配的方式好，記錄下來方便應用
      
#### Overfitting
  > 過度擬合
  
train data的準確度高於test data的準確度

[💍](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## DataSet
  > 數據集
  
在scikit-learn內有一些真實世界的數據，稱為「Toy Datasets」，可從`sklearn.datasets`匯入想要的數據
> import 後面放要匯入的資料
```python
from sklearn.datasets import load_boston

boston = load_boston()
```
> 匯入套件後，要記得實例化才可使用

- `.feature_names`：查看數據中所有的features
- `.data`：所有特徵變數
- `.target`：所有目標變數
- `.DESCR`：查看完整的解釋數據內容
  ```python
  print(boston.DESCR)
  ```

[💎](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## enumerate()
  > 枚舉
  >> 回傳枚舉物件

`enumerate(iterable, start=0)`：計算元素為第幾個
  > 會將list的index與list的元素（item），包成一個tuple，再將每個tuple包成按index排序的list
  - iterable：list

```python
L = ['a', 'b', 'c']

list(enumerate(L))
#輸出
[(0, 'a'), (1, 'b'), (2, 'c')]
```

#### § 使用時機 §
原本方法
```python
for i in range(3):
    print(i+1, L[i])
#輸出
1 a
2 b
3 c
```
使用`enumerate()`
```python
for i, j in enumerate(L):
    print(i+1, j)
#輸出
1 a
2 b
3 c
```

[💋](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

---

# week 7
  > 機器學習

機器學習：讓機器學一個函數
  > e.g. 分類：透過新資料的特徵、特性，預測它的分類

- 機器學習的兩大類：
    - 監督式學習（Supervised Learning）：用「歷史資料」讓機器學習，希望從中找到慣性，以預測新東西
      > 用已知答案的歷史資料學習
      >> e.g. SVM（Support Vector Machine，支持向量機）：透過一堆已知分類的數據，自動尋找曲線分開
    - 非監督式學習（Unsupervised Learning）：無「歷史資料」，完全由電腦分類
      > 完全不知道答案
      >> e.g. K-Means
    - 深度學習


## SVM
  > 支持向量機（Support Vector Machine）
  >> `sklearn.svm`套件
  
 是一種用**曲線**把資料分隔的方法，在高維度時為**曲面（超曲面）**分隔資料
 
 ```python
 from sklearn.svm import SVC
 
 clf = SVC() #分類機
 ```
 
 先使用`clf.fit()`擬合模型，再使用`clf.predict()`預測
 
 - `clf.fit(x, y)`：拿資料去訓練模型
      - x：特徵變數（輸入資料）
      - y：目標變數（正確答案）
      
 - `clf.predict()`：預測
      - input：**2D**的list或array
      - output：回傳array，分類的結果


[🍰](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)
