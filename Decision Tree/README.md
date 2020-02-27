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
     > 有c個不同的類別
     
     - Entropy(S) = -p<sub>+</sub>log<sub>2</sub>p<sub>+</sub> - p<sub>-</sub>log<sub>2</sub>p<sub>-</sub>
       > Why log皆為負號?\
       > 因p為機率，介於\[0,1]之間為分數，其取log後值為負號，因此在其前面加一個負號，希望最後的結果為正號
       
       假設丟了14次銅板，出現「9個正面」與「5個正面」，計為\[9<sub>+</sub>, 5<sub>-</sub>]\
       放入計算Entropy([9<sub>+</sub>, 5<sub>-</sub>]]) = -(9/14)log<sub>2</sub>(9/14) - (5/14)log<sub>2</sub>(5/14) = 0.94
       
       - 若銅板丟出正面與反面的數量一樣，則熵為1（最凌亂）
       - 若銅板僅丟出正面或反面，則熵為0（最不凌亂）
     

ID3 演算法是利用資訊獲利來衡量**分類資料的能力**，看母群體的不純度在經過分割之後子群體的不純度的總和是否會減少

屬性A在資料集合 S 的資訊獲利Gain(S, A)被定義為
> Gain(S, A)：減少多少 Entropy

![](https://github.com/vanikk06/Machine-Learning/blob/master/Decision%20Tree/image/Snipaste_2020-02-27_03-17-09.png)

- 決定分割點：Gain愈大愈好
  > ★ Gain為「母體Entropy - 子群體Entropy」的結果，值愈大表示Entropy減少愈多
  
  再分出一個分割點後，若想繼續往下分，則以此分割為母體重複計算，直到Entropy為0為止
  
在 ID3演算法中，因為計算Entropy有個特質，當分的種類愈多 Gain 的值就愈大，判斷分割點好壞的方法又剛好是擇 Gain 大者為優，因此此演算法的判斷，會傾向分愈多愈好（採分支最多的方式）\
此分法，在某些情況會顯得無意義（E.g. 產品編號）

- ID3演算法：使用「資訊獲利」會傾向選擇**擁有許多不同數值**的屬性
  > 類別多的屬性，會佔分類優勢

#### 【範例】天氣評估

假設有一套天氣評估系統，有一些評估屬性（E.g. 風力、濕度...），用來評估該天氣是否適合打網球

| Day | Outlook | Temp. | Humidity | Wind | Play Tennis |
| --- | --- | --- | --- | --- | --- |
| D1 | Sunny | Hot | High | Weak | No |
| D2 | Sunny | Hot | High | Strong | No |
| D3 | Overcast | Hot | High | Weak | Yes |
| D4 | Rain | Mild | High | Weak | Yes |
| D5 | Rain | Cool | Normal | Weak | Yes |
| D6 | Rain | Cool | Normal | Strong | No |
| D7 | Overcast | Cool | Normal | Weak | Yes |
| D8 | Sunny | Mild | High | Weak | No |
| D9 | Sunny | Cool | Normal | Weak | Yes |
| D10 | Rain | Mild | Normal | Strong | Yes |
| D11 | Sunny | Mild | Normal | Strong | Yes |
| D12 | Overcast | Mild | High | Strong | Yes |
| D13 | Overcast | Hot | Normal | Weak | Yes |
| D14 | Rain | Mild | High | Strong | No |

以 Wind （風力）屬性為例，在所有訓練資料中所會出現的值有 weak、strong

在目前資料集合S中有14筆資料，其中目標屬性（Play Tennis）有9個正例5個反例，記為\[9<sub>+</sub>,5<sub>-</sub>]\
在這14筆資料中，關於 Wind的資料為
- Wind = weak：8筆資料（S<sub>weak</sub>），其中有6個正例和2個反例，記為\[6<sub>+</sub>,2<sub>-</sub>]
- Wind = strong：6筆資料（S<sub>strong</sub>），其中有個3正例和3個反例，記為\[3<sub>+</sub>,3<sub>-</sub>]

透過上例資訊，可得知 Wind 這個屬性的資訊獲利為多少

![](https://github.com/vanikk06/Machine-Learning/blob/master/Decision%20Tree/image/Snipaste_2020-02-27_21-01-40.png)
> 目標：分割，希望分割之後，Entropy能夠減少

- 紅色：母群體的Entropy，\[9<sub>+</sub>,5<sub>-</sub>]為0.94
- 藍色：以 Wind 屬性為分割點後，在 weak 的 Entropy\[6<sub>+</sub>,2<sub>-</sub>]為0.811
- 綠色：以 Wind 屬性為分割點後，在 strong 的Entropy\[3<sub>+</sub>,3<sub>-</sub>]為1.0
- 黑色：以 Wind 為分割點後的 Gain值
  > 因 weak 與 strong 的個數不同，不能直接平均，要以**加權平均**的方式計算（權重：個數、大小）

透過計算各屬性作為分割點的Gain值後，取Gain值最大者作為分割點（即選具**最大資訊獲利**之屬性為分割點）

#### Source     
[資訊的度量- Information Entropy](https://blog.xuite.net/metafun/life/69851478-%E8%B3%87%E8%A8%8A%E7%9A%84%E5%BA%A6%E9%87%8F-+Information+Entropy)

[🏜🏜](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#content)

## Gain ratio
  > 獲利比例
  >> C4.5

利用獲利比率的方式，克服ID3的問題（將資訊獲利正規化）\
在計算屬性A的獲利比例時，需要計算「資訊獲利」與「分割資訊值」（Split Information）

- 補償方法
  > 算子節點之加權平均值的權重的Entropy
  >> 擁有最大獲利比例的屬性，被設為分割屬性
  
  GainRatio(A) = Gain(S, A) / SplitInfo<sub>A</sub>(S)
  > 獲利比率 = 資訊獲利 / 分割資訊值
  
  - 分割資訊值
  
    ![](https://github.com/vanikk06/Machine-Learning/blob/master/Decision%20Tree/image/Snipaste_2020-02-27_03-46-26.png)

[🏜🏜🏜](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#content)

## Gini Index
  > 吉尼係數
  >> CART
  

[🏜🏜🏜🏜](https://github.com/vanikk06/Machine-Learning/tree/master/Decision%20Tree#content)
