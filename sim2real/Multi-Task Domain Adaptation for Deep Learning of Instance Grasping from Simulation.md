## INFO
### author
Kuan Fang<sup>1,2</sup>
, Yunfei Bai<sup>1</sup>
, Stefan Hinterstoisser<sup>1</sup>
, Silvio Savarese<sup>2</sup>
, Mrinal Kalakrishnan<sup>1</sup>

### affiliation
<sup>1</sup>X, Mountain View, CA 94043 USA<br>
<sup>2</sup>Stanford University, Stanford, CA 94305 USA

### conference
ICRA 2018

### link
[PDF](https://arxiv.org/abs/1710.06422)



## 概要
ロボットの manipulation に対する学習ベースの取り組みは，データ収集やラベル付けのコストのために，制限されたものとなっている．
本論文では，シミュレーション上での実験を活用して，散らかったシーンにおけるインスタンス把持のための，multi-task domain adaptation framework を提案している．本論文のニューラルネットでは，単眼のRGB画像とターゲットの物体のインスタンスセグメンテーションマスクを入力として，各モーターコマンドの候補についてその把持の成功確率を予測している．ネットワークは，シミュレーション上のインスタント把持を用いて学習し，転移する際に domain shift を緩和するために，仮想空間と実空間の両方から得られる物体を区別しない把持(⇔インスタンス把持)のデータを用いている．
<br>
<br>
![](https://github.com/yiskw713/paper_summary/blob/master/pic/Multi-Task%20Domain%20Adaptation%20for%20Deep%20Learning%20of%20Instance%20Grasping%20from%20Simulation.png)
<br>
得られる物体を区別しない把持(上)とインスタンス把持(下)のサンプル

## date
July 20, 2018