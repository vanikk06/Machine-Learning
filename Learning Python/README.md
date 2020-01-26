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
   
   [✍](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#nprandomrand)
    
- `np.random.randn()`：`randn`根據給定的維度，生成具**常態分配**的隨機數據，返回指定維度的array
    > 常態分配（standard normal distribution）：平均值為0，標準差為1，可記為N(0,1)
    >> [Learning more](https://blog.csdn.net/zenghaitao0128/article/details/78556535#1nprandomrandn%E5%87%BD%E6%95%B0)
   - 參數
     - np.random.randn(a)：一維array含a個元素
     - np.random.randn(a,b)：axb的二維array含axb個元素
     - np.random.randn(a,b,c)：a個bxc的二維array含ax(bxc)個元素
     
   [✍🏻](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#nprandomrandn)
   
- `np.random.randint(low, high=None, size=None, dtype='l')`：根據給定的維度，生成隨機**整數**
   > 範圍：\[low,high），包含low，不包含high
   - 參數
     - low：最小值
     - high：最大值
       > 無此參數時，預設生成隨機數範圍為[0，low)
       >> 包含0，不包含low
     - size：維度大小
     - dtype：數據類型，預設為np.int
    
   [✍🏼](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#nprandomrandint)
   
- `np.random.choice(a, size=None, replace=True, p=None)`：從**給定的一維數組中**產生隨機數
   - 參數
      - a：一組數組
        > 若a為整數，則數組為對應的np.arange(a)
      - size：維度大小
      - replace：是否有重複值
      - p：數組內元素的比重
        > 長度需與a相同\
        > 元素為機率：介於0-1之間，總和需為1
    
    [✍🏽](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#nprandomchoice)
    
- `np.random.seed()`：使得隨機數據可預測
     - 當設置相同的`seed()`時，每次生成的隨機數相同
     - 當不設置`seed()`時，每次生成不同的隨機數
      
     [✍🏾](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#nprandomseed)
#### np.random.rand()
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

#### np.random.randn()
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

#### np.random.randint()
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

#### np.random.choice()
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

#### np.random.seed()
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
     
     
# week 3
  > numpy、向量化...

## Git
  > [Learning more_video](https://www.youtube.com/watch?v=4eOOZeL2WJ4&list=PLRxMjOjh7Y5d_eRLWr-DaujfI2YHgCqIf&index=1)
  
  > [Learning more_book](https://gitbook.tw/)
  
Git是一種**分散式版本的版本控制系統**，是為了更好管理Linux內核而開發的
> 將檔案狀態作為更新歷史紀錄保存

- 版本控制系統（Version Control System）
    - 版本：在一個目錄下，不管是新增、刪除檔案，或是修改檔案內容，只要是對目錄下的檔案做出更動，都稱為一個版本
    - 版本控制系統：是指會記錄這些所有的狀態變化，並且可以隨時切換到過去某個「版本」時候的狀態


Git優點：
  1. 免費、開源：
     Git是由Linux核心的作者Linus Torvalds在2005年為了管理Linux核心程式碼，僅花了10天所開發出來的，除了可免費使用外，整個Git的原始程式碼也可在網路上取得。
  2. 速度快、檔案體積小：
     Git特別之處在於它並不是記錄版本的差異（大部分版本控制系統為此），而是記錄檔案內容的「快照」（snapshot），它讓Git可以非常快速的切換版本。
  3. 分散式系統：
  

#### Git vs. GitHub

兩者並不相同，很多新手容易誤解，以為Git就是GitHub（或是以為GitHub就是Git）
- Git：一種工具，一款版本控制軟體
- GitHub：一個商業網站，其本體是一個Git伺服器，在GitHub上的應用程式可以透過Web介面來操作一些原本需要複雜的Git指令才能做到的事
  
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

#### Source

[📢](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)


## numpy package
- numpy套件：應用於科學計算、數據分析
  > 主要型態：array
  
  - **array oriented**：陣列導向的程式設計方式（數據分析中的重要概念）
     > 少用迴圈，多用array

[🎮](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)

 
