# Content
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
