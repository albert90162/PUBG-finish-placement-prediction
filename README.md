# PUBG 最終排名_視覺化
### PUBG-finish-placement_Visualization

<div align="center"><img src="https://i.loli.net/2020/04/01/ql1ZT7btSXzOvUN.jpg" width='690' height='330'></div>

#### 分析目的：以視覺化為主，分析遊戲中各項特徵與高順位排名之間的關係。
#### 分析流程：描述性統計分析 --> 特徵分布狀況 --> (例外狀況) --> 特徵與最終排名關係
#### 使用工具：matplotlib & seaborn
#### 資料大小：4446966 rows * 29 columns (628MB)
#### 資料來源：https://www.kaggle.com/c/pubg-finish-placement-prediction
#### 程式碼：

#### 目錄：
1. [殺敵數分析 The Killers](#the-killers)
2. [行走距離分析 The Runners](#the-runners)
3. [駕駛距離分析 The Drivers](#the-drivers)
4. [游泳距離分析 The Swimmers](#the-swimmers)
5. [補給藥品分析 The Healers](#the-healers)
6. [遊戲模式分析 Solos, Duos and Squads](#solos,-duos-and-squads)
7. [最終排名與各項特徵的關係](#最終排名與各項特徵的關係)
8. [結論](#結論)
<br>

## The Killers:<br>
在將近450萬筆的玩家中，平均殺敵數約為 0.925 人，其中 99% 的人有不超過 7 名殺敵數。而記錄中最高的殺敵數為 72 人。

將殺敵數作圖，看看殺敵數的分布狀況：
<div align="center"><img src="https://i.loli.net/2020/04/01/96zMEZG1vwqcpUQ.png" width='700' height='400'></div>
從圖中可以看出，250萬筆資料為 0 殺敵數，即 56% 的玩家沒有造成其他玩家死亡。那麼這些 0 殺的玩家，至少能對其他玩家造成傷害嗎？
<div align="center"><img src="https://i.loli.net/2020/04/01/5YqcIUr8HwMFBQ3.png" width='700' height='400'></div>
好吧，看來他們不能。從圖中可看出，0 傷害的玩家佔 0 殺的玩家大多數。
<br><br>

接下來，來看看例外狀況：
有 16666 名玩家 (佔所有玩家中約0.37%) 在沒有任何殺敵數的情況下贏得遊戲，更有 4770 名玩家 (佔所有玩家中約 0.11% )在沒造成任何傷害的情況下贏得遊戲！
<br><br>

對排名與殺敵數做圖：
<div align="center"><img src="https://i.loli.net/2020/04/01/mLlNiAqaUKF9dsy.png" width='700' height='400'></div>
顯然最終排名與殺敵數之間是有正相關的
<br><br>

最後將殺敵數分成 0, 1-2, 3-5, 6-10, 11以上，看看不同的殺敵數在最終排名的分布狀況：
<div align="center"><img src="https://i.loli.net/2020/04/01/ZrHJ4dLaG3jwRfx.png" width='700' height='400'></div>
<br>




## The Runners:<br>
在將近450萬筆的玩家中，平均行走距離（不含交通工具）為 1154.2m ，其中 99% 的人行走了不超過 4396m，而記錄中最遠的距離為 25780m。
<br>
<br>

對行走距離作圖，看看450萬名玩家的行走距離是如何分布的：
<div align="center"><img src="https://i.loli.net/2020/04/01/Zda9cAKkCYnOLpX.png" width='700' height='400'></div>
從圖中可看出只行走 0-100m 的玩家占最多比例，進一步深入觀察可發現：
有 99603 名玩家（占所有玩家約 2.24% ）行走了 0m ，這代表他們還來不及移動就被擊敗了，或者是斷線了（比較有可能）
<br><br>

一樣來看看最終排名與行走距離的關係：
<div align="center"><img src="https://i.loli.net/2020/04/01/xNidorcRF5h4bsE.png" width='700' height='400'></div>
很明顯，行走距離和最終排名之間也存在著正相關
<br><br>






## The Drivers:<br>
在將近450萬筆的玩家中，平均駕駛距離為 606.1m ，其中 99% 的人駕駛不超過 6966m 的距離，而記錄中最遠的駕駛紀錄為 40710m<br>
<br>

對駕駛距離作圖，看看450萬名玩家的駕駛距離怎麼分布：
<div align="center"><img src="https://i.loli.net/2020/04/01/6oYNd9WIEJapbVc.png" width='700' height='400'></div>
有趣的是，從圖中可以看到絕大部分的玩家沒有駕駛或不超過 100m，再深入觀察可以發現：約有 331 萬的玩家 （占所有玩家約 74.42%）駕駛了 0m。
超過7成的玩家沒有駕駛，卻有 606.1m 的平均駕駛距離，說明了玩家的駕駛情形：要嘛不駕駛，若駕駛則會行駛長遠的距離，且相較於行走會更長遠。<br>
<br>

看看最終排名與駕駛距離的關係：
<div align="center"><img src="https://i.loli.net/2020/04/01/cCnwLlito58vJgG.png" width='700' height='400'></div>
與行走距離的情形一樣，駕駛距離和最終排名也存在著正相關
<br>
<br>

另外，根據經驗，摧毀車輛通常能一併獲得殺敵數，並讓最終排名更上層樓，來看看摧毀車輛與最終排名間的關係：
<div align="center"><img src="https://i.loli.net/2020/04/01/3gWFPpl9CV5fkry.png" width='700' height='400'></div>
同樣地，摧毀車輛與最終排名也存在著正相關


<br>
<br>

## The Swimmers:<br>
在將近450萬筆的玩家中，平均游泳距離為 4.5m ，其中 99% 的人游泳不超過 123m，而記錄中最遠的游泳紀錄為 3823m。
<br>
<br>
看看游泳距離的分布狀態：
<div align="center"><img src="https://i.loli.net/2020/04/01/xPpJqUdN5cK9nC7.png" width='700' height='400'></div>
從圖中發現，幾乎沒有人游泳。<br>
將游泳距離分成 0m, 1~5m, 6~20m, 20m以上，看各組與最終排名的關係：
<div align="center"><img src="https://i.loli.net/2020/04/01/fBlLzbZJHpSuvd9.png" width='700' height='400'></div>
可以發現，游泳距離為 0 的玩家，最終排名也相對較低。
<br>
<br>



## The Healers:<br>

在將近450萬筆的玩家中，每位玩家一場遊戲平均會使用 1.4 個 heals item，其中 99% 的人使用不超過 12 個，而一場比賽中使用掉最多 heals item 是 80 個。
至於 boost item，每位玩家一場遊戲平均會使用 1.1 個，其中 99% 的人不使用超過 7 個，一場比賽最多次使用 boost item 的紀錄是 33 個<br>
<br>

比較 heals 和 boosts 與最終排名的關係：
<div align="center"><img src="https://i.loli.net/2020/04/01/LrXZjVO9ktlTiWu.png" width='700' height='400'></div>
從圖中可以發現，在使用超過 2 個時， boosts 的最終排名就會超越 heals 的最終排名，且 boosts 會穩定上升，而 heals 則趨緩甚至在 5 的時候小跌，會造成這個現象或許和兩種補給品之間的性質有關。<br>
<br>

再深入觀差兩種補給品與最終排名之間的關係：<br><br>
Heals:
<div align="center"><img src="https://i.loli.net/2020/04/01/SHCtfamclGE3db2.png" width='700' height='400'></div>
Boosts:
<div align="center"><img src="https://i.loli.net/2020/04/01/kQ8gu41C3IJTnft.png" width='700' height='400'></div>
可以看出兩種補給品與最終排名之間也是有正相關，而 boosts 的關係似乎又高一點。值得注意的是，兩種補給品都在最終排名為最後一名時有異常現象。
<br>
<br>



## Solos, Duos and Squads:<br>

在將近450萬筆的玩家中，有約 16% 的單人遊戲， 74% 的雙人組隊遊戲， 10% 的四人組隊遊戲。<br>
<br>

比較看看三種遊戲模式下，殺敵數與最終排名的關係：
<div align="center"><img src="https://i.loli.net/2020/04/01/3Qm9WM8ZfnIh5gX.png" width='700' height='400'></div>
單人和雙人遊戲的現象較類似，而四人組隊時殺敵數與最終排名的關係則沒有那麼明顯<br>
<br>

再來比較在雙人和四人組隊遊戲時，擊倒數、拯救隊友次數、助攻數，三者與最終排名之間的關係：
<div align="center"><img src="https://i.loli.net/2020/04/01/oKtfXYirk73ZdjQ.png" width='700' height='400'></div>
<br>
<br>



## 最終排名與各項特徵的關係：<br>

首先先畫 heatmap:
<div align="center"><img src="https://i.loli.net/2020/04/01/9BYTISPE6spRzAy.png" width='900' height='600'></div>
可以發現許多變數都與最終排名有中等以上的相關性，其中行走距離的正相關性最高，而 killPlace 的負相關性最高。
<br>
<br>

深入觀察前五個正相關性最高的特徵，前五名由高到低依序分別是：行走距離、獲得武器數量、使用 boosts 數量、造成的傷害量、使用 heals 數量
<div align="center"><img src="https://i.loli.net/2020/04/01/S9T3EvqcCfthdaO.png" width='700' height='500'></div>
從圖中可以發現，各變數除了與最終排名有中等以上的相關性，彼此之間的相關性也不小，因此在建模時要注意共線性（collinarity）
<br>
<br>

## 結論：<br>
此分析所深入探討的各項變數，大部分都和最終排名呈現中等程度以上的正相關，包括殺敵數、行走距離、駕駛距離、游泳距離和使用藥品。
然而，在 PUBG 中，這似乎是個正常且合理的現象：
1. **殺敵數**：每當擊敗一名敵人，代表淘汰掉一名玩家，玩家本身的最終排名就會向前一名，也因此殺敵數與最終排名兩者本身呈現正相關是合理的現象，但不代表高殺敵數一定會換來高排名。<br>
2. **移動距離**：PUBG 獨特的機制 — 毒圈，迫使每位玩家要在時間內朝指定的地點移動，否則生命力會逐漸衰弱最後被淘汰。因次要獲得高排名，就必須不斷的往指定地點移動，因此移動距離也會隨之增加，而移動距離與最終排名自然就會呈現正相關。<br>
3. **藥品**：boosts 的最終排名相較於 heals 更高且有上升趨勢，這可能與兩種藥品性質的差異有關，
heals 是直接回滿生命力，且有部分藥品最多只能回到 75% 的生命力，因此大部分的玩家只有在生命力低於 75% 甚至低於 50% 才會選擇使用治癒品；而 boosts 則是使用後會在時間內
慢慢恢復生命力，因此當玩家的生命力高於 50% 時，較常使用的是 boosts 而非 heals。且當遊戲進行到越後面，玩家更傾向於頻繁使用 boosts ，這樣當玩家
面臨戰鬥時，即便在與敵人對峙期間受傷，也不需要冒險地花時間使用 heals ，而是隨著時間恢復的 boosts 會治癒玩家的生命力，因此遊戲進行越久，遊戲節奏越緊張刺激時，玩家更傾向於使用 boosts，而此時玩家的最終排名已經
處於中高階段以上，因此 boosts 與最終排名之間的正相關性也顯得合理。

### 下一步：
當 EDA 與視覺化分析完，便可開始進行特徵工程，而 EDA 時發現，各特徵之間存在共線性，是在特徵工程時必須解決的問題。否則會使模型中存在著重複的自變數，提高某一自變數的解釋力與預測力，使得理論的建構不正確。

*****

#### The End 
#### 作者：鮑威宇, Albert Pao 





