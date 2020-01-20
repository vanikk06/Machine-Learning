# Content
  > 自學python的學習筆記
  >> [class](http://moocs.nccu.edu.tw/course/123/intro)\
  >> [github](https://github.com/yenlung/Python-3-Data-Analysis-Basics)
  
- [week 1](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#week-1)
    - [Magic Commend](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#magic-commend)
  
  
  
# week 1

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
     plot([0,1,2,3,4])
     ```
     > list中為y值，x會自動補上0, 1, 2,...
     >> 會產生由(0,0), (1,1), (2,2), (3,3), (4,4)點，依照x值由小到大連成的線
    
    
    
    
#### Source
[Jupyter 的魔術指令](http://moocs.nccu.edu.tw/media/17831#tab-note-share)

[IPython 的 Notebook 界面](https://yenlungblog.wordpress.com/2013/11/21/python-ipython-%E7%9A%84-notebook-%E7%95%8C%E9%9D%A2/)
   
[👣](https://github.com/vanikk06/Machine-Learning/tree/master/Learning%20Python#content)
   
   
   
