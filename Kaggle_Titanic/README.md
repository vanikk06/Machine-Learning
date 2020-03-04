# Content
- [Lecture 6 Kaggle.pdf](https://github.com/vanikk06/Machine-Learning/blob/master/Kaggle_Titanic/Lecture%206%20Kaggle.pdf)
- [df.append()](https://github.com/vanikk06/Machine-Learning/tree/master/Kaggle_Titanic#dfappend)

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
