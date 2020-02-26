# Content
- [What is decision tree](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#what-is-decision-tree)
- [Building decision tree](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#building-decision-tree)
  - [Information Gain](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#information-gain)
  - [Gain ratio](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#gain-ratio)
  - [Gini Index](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#gini-index)
  


# What is decision tree
  > 分類：決策樹
  
什麼是決策樹？
- 用來處理「分類問題」的**樹狀**結構
- 每個內部節點（node），表示一個**評估欄位**
- 每個分枝，代表一個可能的**欄位輸出結果**
- 每個樹葉節點，代表不同分類的**類別標記**

![](https://github.com/vanikk06/Machine-Learning/blob/master/Decision%20Tree/image/Snipaste_2020-02-22_03-57-55.png)

[🏝](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#content)


# Building decision tree
  > 建立決策樹

- 初始值：根節點（root）包含所有的 training data

重複將每個內部節點（node）依據**所選擇的特徵**去分割節點，直到達到停止條件

- 不同類型的節點分割
  - 二元屬性：資料只有兩個不同的值，分割後會產生兩個不同方向的分支
  - 名目屬性：資料沒有前後次序關係，可分割出不同值域的分支
    > 每個分支的表示，亦可以子集合的型態表示
  - 順序屬性：資料有前後次序關係，可產生二元或是多元分割
    > 順序屬性內的值可以被「群組」，但在群組中，不可違反屬性值的順序
    >> E.g. 可\[小、中], \[大]，不可\[小、大], \[中]    
  - 連續性屬性：可採用離散化的方式，將資料分割成許多區間，但仍須保持資料的順序性

- 分割歸納方式：希望同群的同質性愈高愈好，不同群的同質性愈低愈好，因此，需檢驗節點的不純度（Node Impurity）
  > 希望不純度愈低愈好
  
  - 測量純度方法
    > 根據測量方法不同，決策樹的演算法也會有所不同
    
    - 資訊獲利（Information Gain）：ID3
      > [✍🏽](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#information-gain)
    - 獲利比例（Gain ratio）：C4.5
      > [✍🏼](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#gain-ratio)
    - 吉尼係數（Gini Index）：CART
      > [✍🏿](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#gini-index)
  
[🏜](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#content)

## Information Gain
  > 資訊獲利
  >> ID3

- 熵：亂度，可當作資訊量的**凌亂程度**（不確定性）指標
  > 熵值愈大，表示資訊的凌亂程度愈高
  
  ![](http://i.stack.imgur.com/OUgcx.png)
  
  - 【範例】丟銅板
     
     - 若銅板是「公平」的，則丟出正面與反面的機率是一樣的（一半一半）
       > 最凌亂
     - 若銅板非公平的，則丟出正面與反面的機率不會是一樣的
       > 愈不凌亂
     
     收集一組丟銅板之後的資料集合 S，該資料組的計算公式為
     
     ![](https://github.com/vanikk06/Machine-Learning/blob/master/Decision%20Tree/image/Snipaste_2020-02-27_02-45-15.png)
     
     - Entropy(S) = -p<sub>+</sub>log<sub>2</sub>p<sub>+</sub> - p<sub>-</sub>log<sub>2</sub>p<sub>-</sub>
       > Why log皆為負號?\
       > 因p為機率，介於\[0,1]之間為分數，其取log後值為負號，因此在其前面加一個負號，希望最後的結果為正號
       
       假設丟了14次銅板，出現「9個正面」與「5個正面」，計為\[9<sub>+</sub>, 5<sub>-</sub>]\
       放入計算Entropy([9<sub>+</sub>, 5<sub>-</sub>]]) = -(9/14)log<sub>2</sub>(9/14) - (5/14)log<sub>2</sub>(5/14) = 0.94
       
       - 若銅板丟出正面與反面的數量一樣，則熵為1（最凌亂）
       - 若銅板僅丟出正面或反面，則熵為0（最不凌亂）
     
#### Source     
[資訊的度量- Information Entropy](https://blog.xuite.net/metafun/life/69851478-%E8%B3%87%E8%A8%8A%E7%9A%84%E5%BA%A6%E9%87%8F-+Information+Entropy)

[🏜🏜](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#content)

## Gain ratio
  > 獲利比例
  >> C4.5


[🏜🏜🏜](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#content)

## Gini Index
  > 吉尼係數
  >> CART
  

[🏜🏜🏜🏜](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#content)
