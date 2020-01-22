# Content
  > 自學python的學習筆記
  >> [class](http://moocs.nccu.edu.tw/course/123/intro)\
  >> [github](https://github.com/yenlung/Python-3-Data-Analysis-Basics)
  
- [week 1](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#week-1)
    - [Magic Commend](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#magic-commend)
       - [numpy.random](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#numpyrandom)
    - [Markdown](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#markdown)
  
  
  
# week 1
  > tips：Shift + Tab可以查看函式的說明文件


在終端機的Unix指令
  - pwd：顯示當前路徑
  - dir：列出當前目錄所有的檔案


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

####

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
