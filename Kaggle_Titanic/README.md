# Content
- [Lecture 6 Kaggle.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Kaggle_Titanic/Lecture%206%20Kaggle.pdf)
- [df.append()](https://github.com/vanikk06/Machine-Learning/tree/master/Kaggle_Titanic#dfappend)
- [df.set_index() ＆ df.reset_index()](https://github.com/vanikk06/Machine-Learning/tree/master/Kaggle_Titanic#dfset_index--dfreset_index)

# df.append()
  > 合併
  >> 僅可**縱向合併**，不可橫向合併

此種方法並不推薦，因效率較差，除此之外，也可使用`pd.concat()`函式合併

- `df.append(other, ignore_index=False, verify_integrity=False, sort=False)`
   - other：DataFrame、Series、dict、list這類的數據結構
   - ignore_index：是否忽略原本的index
     > 預設為False
   - verify_integrity：若為True，當創建相同的index時會拋出`ValueError`的錯誤
     > 預設為 False
   - sort：排序欄位，當兩個合併欄位無對齊時
     > 預設為 False

#### Source
[Pandas 合并concat - Numpy & Pandas | 莫烦Python](https://morvanzhou.github.io/tutorials/data-manipulation/np-pd/3-6-pd-concat/)

[pandas.DataFrame.append](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.append.html)

[pandas的DataFrame的append方法详细介绍](https://blog.csdn.net/sinat_29957455/article/details/84961936)

[🚝](https://github.com/vanikk06/Machine-Learning/tree/master/Kaggle_Titanic#content)


# df.set_index() ＆ df.reset_index()
  > 單索引、複合索引
  
- `df.set_index()`：設置單索引或複合索引
  - dataframe.set_index(keys, drop=True, append=False, inplace=False, verify_integrity=False)
    - keys：要設置為index的欄位變數
    - drop：是否丟棄表格中原本的欄位
      > 預設為True
    - append：是否以增加一欄的方式，設置新的index（即保留原始的index）
      > 預設為False
    - inplace：是否變更原始資料
      > 預設為False
      >> 若為True，無回傳值
- `df.reset_index()`：還原索引值，重新變為默認的整數型索引
   - dataframe.reset_index(drop=False, inplace=False)

#### Source
[pandas中关于set_index和reset_index的用法](https://blog.csdn.net/jingyi130705008/article/details/78162758)

[🚈](https://github.com/vanikk06/Machine-Learning/tree/master/Kaggle_Titanic#content)

# Seaborn
  > 資料視覺化
- `sns.countplot()`：長條圖，計算單一變數的次數
   > 類別型

#### Source
[[第 19 天] 資料視覺化（2）Seaborn](https://ithelp.ithome.com.tw/articles/10186624)

[Python 資料視覺化筆記(二) — 使用Seaborn繪圖](https://medium.com/@yanweiliu/python-%E8%B3%87%E6%96%99%E8%A6%96%E8%A6%BA%E5%8C%96%E7%AD%86%E8%A8%98-%E4%BA%8C-%E4%BD%BF%E7%94%A8seaborn%E7%B9%AA%E5%9C%96-3adb03407a9)

[Python學習筆記#6：Seaborn資料視覺化篇](http://psop-blog.logdown.com/posts/3056283-python-seaborn)

[10分钟python图表绘制 | seaborn入门（二）：barplot与countplot](https://zhuanlan.zhihu.com/p/24553277)

[🚅](https://github.com/vanikk06/Machine-Learning/tree/master/Kaggle_Titanic#content)
