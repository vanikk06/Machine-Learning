
# introduction
  > 簡單介紹一下，什麼是機器學習
  >> 要先明白，機器學習並非100%精確的，大多數情況下只是一個很好的猜測，並且需要大量的調整疊代（時間和資源耗費在訓練模型上）
  
  
主流的定義機器學習
  > 由機器學習教父Tom Mitchell提出
  >> 透過從過往的資料和經驗中學習並找到其運行規則
  
  "A computer program is said to learn from **experience E** with respect to some class of **tasks T** and **performance measure P**, if its performance at tasks in T, as measured by P, improves with experience E. "
  
  簡單的說就是一個程式可以根據過去的經驗（Data）去做某些任務（Task），然後會有一些效能評估（performance measure）來評估這些Task做得好不好，如果這些效能評估可以透過「利用過往的資料來提升」的話，就叫作機器學習
  
  
#### Machine Learning v.s. Algorithms
  > 機器學習 v.s. 演算法

- Algorithms：訂立一個明確的規則，透過coding將這種規則具現化
  > 寫死的
  
- Machine Learning：透過樣本訓練機器辨識出運作模式，而不是用特定的規則來coding，換句話說，machine learning是從資料中得到複雜的函式（或樣本）來**學習**以創造algorithms（或一組規則），並利用它來做**預測**
  > 建立模型（model）
  >> 模型的好壞必須針對特定問題的種類
  
  ![](https://github.com/vanikk06/Machine-Learning/blob/master/Intro/image/Snipaste_2020-01-14_03-41-03.png)

machine learning的厲害之處在於它可以**自主學習**，同樣的ML系統仍然可以使用在未來的物件，並不需要重寫程式碼，這是相當方便起強大的 e.g.識別物件

#### Machine Learning v.s. Artificial Intelligence v.s. Deep Learning
  > 機器學習 v.s. 人工智慧
  
machine learning是人工智慧的一個分支，人工智慧是一個較廣泛的名詞

- Artificial Intelligence（AI）：

  “Intelligent Agents“ refers to the ability of the computer to **simulate/model human thinking** processes to **imitate human ability or behavior**"
  
  現在所執行的系統是一種「弱人工智慧」的形式，人工智慧系統可以做一件或是多件事情，而做的程度與人類相當，甚至超越人類
  
![](https://github.com/vanikk06/Machine-Learning/blob/master/Intro/image/Snipaste_2020-01-14_17-35-34.png)

- machine learning的種類，可以分為四種：\
  [learning more](https://ai4dt.wordpress.com/2018/05/25/%E4%B8%89%E5%A4%A7%E9%A1%9E%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92%EF%BC%9A%E7%9B%A3%E7%9D%A3%E5%BC%8F%E3%80%81%E5%BC%B7%E5%8C%96%E5%BC%8F%E3%80%81%E9%9D%9E%E7%9B%A3%E7%9D%A3%E5%BC%8F/)
    1. 監督式學習（supervised learning）
        > 一比一對照資料
    2. 非監督式學習（unsupervised learning）
        > 機器自行摸索出資料規則
    3. 增強式學習（reinforcement learning）
        > 在未知探索與遵從既有知識間取得平衡
          
- Deep Learning（DL）

#### Source
[〔資料分析&機器學習〕 第3.1講：Python 機器學習以及Scikit-learn介紹](https://medium.com/jameslearningnote/%E8%B3%87%E6%96%99%E5%88%86%E6%9E%90-%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92-%E7%AC%AC3-1%E8%AC%9B-python-%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92%E4%BB%A5%E5%8F%8Ascikit-learn%E4%BB%8B%E7%B4%B9-fdb052463911)

[人工智慧、機器學習、深度學習是什麼? – Machine Learning 教學系列 (一)](https://blog.gcp.expert/ml-1-ai-ml-deep-learning-intro/)

[機器學習跟統計學差在哪？哈佛博士：機器學習重視預測結果，統計學在乎因果推理](https://buzzorange.com/techorange/2019/05/02/difference-between-statistics-and-machine-learning/)

[史上最完整機器學習自學攻略！我不相信有人看完這份不會把它加進我的最愛](https://buzzorange.com/techorange/2017/08/21/the-best-ai-lesson/)

[三大類機器學習：監督式、強化式、非監督式](https://ai4dt.wordpress.com/2018/05/25/%E4%B8%89%E5%A4%A7%E9%A1%9E%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92%EF%BC%9A%E7%9B%A3%E7%9D%A3%E5%BC%8F%E3%80%81%E5%BC%B7%E5%8C%96%E5%BC%8F%E3%80%81%E9%9D%9E%E7%9B%A3%E7%9D%A3%E5%BC%8F/)

# Overview

#### Source
[8種常見機器學習演算法比較](https://www.itread01.com/content/1541334303.html)

[【機器學習懶人包】從數據分析到模型整合，各種好用的演算法全都整理給你啦！](https://buzzorange.com/techorange/2019/08/13/machine-learning-algorithm-collection/)
