# Content
  > 自學python的學習筆記
  >> [class](http://moocs.nccu.edu.tw/course/123/intro)\
  >> [github](https://github.com/yenlung/Python-3-Data-Analysis-Basics)
  
- [week 1](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#week-1)
    - [Magic Commend](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#magic-commend)
       - [numpy.random](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#numpyrandom)
  
  
  
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
   
   
#### Source
[numpy.random.randn()用法](https://blog.csdn.net/u012149181/article/details/78913167)

[👣👣](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)
