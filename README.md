# Social Network Analysis

## 簡介
* 最原始的社群網路是一種由節點 (node) 與邊 (edge) 所組成的圖形結構 (graph)，其中節點所代表的是人，邊所代表的是人與人之間的各種相互認識的
* 根據網路(Network theory)及圖論(Graph theory)對社會結構進行探索的分析方法
<br>

## 名詞
* 「動態社群網路」(Dynamic Social Network)：資料集所建構的社群網路並非全然靜態 (static)，隨著時間會有新的成員加入，節點數因而增加，同時新成員與舊成員彼此間會彼此認識，進而產生新的邊
* 「異質性社群網路」(Heterogeneous Social Network)：社群網路中的個體會有不同的身分類型(如學生、老師、演員與導演等)或屬性(如性別、興趣與專長等)，且個體間的連結關係也有非常多種可能類型，如朋友關係、家人關係、師生關係與合作關係等
* 計算節點之中心程度 (centrality)，即位居一個社群網路的中心位置，是最基礎的課題，中心節點普遍被認為在社群網路中扮演重要角色，其中最重要的三種中心度指標為
  * 「度中心性」(degree)：擁有愈多鄰居的節點為中心節點
  * 「親近中心性」(closeness)：與其他節點之平均距離越短的節點為中心
  * 「間接中心性」(betweenness)：頻繁地被其他節點間之最短路徑經過的節點為中心
* 角色分析 (Role Analysis)：目的在於識別社群網路中扮演相同角色之節點，如哪些節點是扮演父母親的角色、或哪些節點是公司主管的角色
* 結構平衡理論 (Structure Balance)：假定社群網路每個邊上有一個正或負的標籤，正代表彼此是朋友，負則代表彼此是敵人，並指出在以三個節點為基礎的三角形結構中，具有三個正邊或一個正邊兩個負邊之三角形才算是結構平衡，即三個人之中，彼此互為朋友，或者兩個朋友並有一共同敵人，個體間才不會有競爭關係
* 六度分離 (Six-degree of Separation)：透過信件傳遞的實驗發現，連結世界上任意兩個人平均而言只需在社群網路中走六步即可到達，即平均只需要五個中間人 就可以聯繫任兩個互不相識的人(社會心理學家 Stanley Milgram)
<br>

## 社群網路特性：
* 物理學家 Mark Newman 觀察與歸納出十幾種重要的社群網路特性，最重要的三個為:
  (1) 低平均路徑距離 (low average path length)：任兩節點之平均距離是短的，如上述的六度分離現象，代表資訊能在網路中能迅速傳播
  (2) 高群聚係數 (high clustering coefficient)：一個人的朋友們傾向也彼此成為朋友，形成三角形結構，網路中愈多三角形，則群聚係數愈高
  (3) 節點度冪次分布 (power-law degree distribution)：社群網路中朋友數很少的人相當多，朋友數非常多的人相當少，且呈現指數級遞減
 * 物理學家 Duncan Watts 與數學家 Steve Strogatz，1998 年提出「小世界模型」(small-world model) 認為只要隨機將格點圖 (ring lattice)(即點與邊如棋盤狀規則排列之圖形)中少數節點的邊，重新連接 (random rewiring) 到任意其他節點，即能生成兼具低平均路徑距離與高群聚係數的社群網路
 * 物理學家 Albert-László Barabási 與 Réka Albert，1999 年提出「無尺度網路模型」（scalefree model），該模型假設新成員是逐一被加入社群網路的，每當有新節點加入，它的連結生成方式遵從
「偏好依附原則」（preferential attachment）：有較高的機率連接到現有社群網路中朋友數較多的節點，以此方式即可生成出具有節點度冪次分布之社群網路
<br>

## 安裝 Rstudio
```
docker pull rocker/rstudio
docker run -d -p 8787:8787 -e ROOT=TRUE rocker/rstudio
```
<br>

## 安裝 ubuntu 套件
```
sudo apt-get update
sudo apt-get install libxml2-dev
```
<br>

## 安裝 R 套件
```
install.packages(c("xml2","XML","httr","stringr", "igraph", "dplyr"));
```
<br>

## 爬網
```
```
<br>

## 參考資料
* (巨量資料中的小世界––漫談社群網路)[https://ee.ntu.edu.tw/upload/hischool/doc/2014.05.pdf]
* ([R]PTT推文文化的社群網絡分析，帶你一窺社群網絡中的互動情況)[https://medium.com/bryanyang0528/r-ptt%E6%8E%A8%E6%96%87%E6%96%87%E5%8C%96%E7%9A%84%E7%A4%BE%E7%BE%A4%E7%B6%B2%E7%B5%A1%E5%88%86%E6%9E%90-social-network-analysis-%E5%B8%B6%E4%BD%A0%E4%B8%80%E7%AA%BA%E7%A4%BE%E7%BE%A4%E7%B6%B2%E7%B5%A1%E4%B8%AD%E7%9A%84%E4%BA%92%E5%8B%95%E6%83%85%E6%B3%81-5cab015bbac8]
* ([Python]淺談社會網路分析的度中心性、介數中心性及接近中心性)[https://medium.com/qiubingcheng/python-%E6%B7%BA%E8%AB%87%E7%A4%BE%E6%9C%83%E7%B6%B2%E8%B7%AF%E5%88%86%E6%9E%90-social-network-analysis-%E7%9A%84%E5%BA%A6%E4%B8%AD%E5%BF%83%E6%80%A7-degree-centrality-%E4%BB%8B%E6%95%B8%E4%B8%AD%E5%BF%83%E6%80%A7-betweenness-9b9f01c4d088]
