## INFO
### Author
Xue Bin Peng<sup>1,2</sup>
, Marcin Andrychowicz<sup>1</sup>
, Wojciech Zaremba<sup>1</sup>
 and Pieter Abbeel<sup>1,2</sup>

### Affiliation
<sup>1</sup>OpenAI\
<sup>2</sup>UC Berkeley, Department of Electrical Engineering and Computer Science

### Link
[PDF](https://arxiv.org/abs/1710.06537)\
[Video](https://www.youtube.com/watch?v=XUW0cnvqbwM)


## 概要
![]()

シミュレーション上での学習は，低コストでデータを豊富に得られる点で有益であるが，実際は仮想空間と実空間との差異のために，仮想空間上で学習したモデルを，実空間に転移することが難しくなっている．そこで本研究では，学習中のシミュレーション上の dynamics (上図にあるような要素)をランダムに変更すること(Domain Randomization)で，実空間上での学習なしに実世界に対して汎化性能をもたせることを可能にしている．この手法をロボットが物体を押すタスクに応用し，実際のロボットだけで学習した場合と同程度のパフォーマンスができることを確認した．\
<br>
<br>
![]()
<br>
上図は仮想空間上のみで学習させたロボットを，仮想空間と実空間上で動作させた場合の精度を表したものである．両空間においてそれほど大差はないことが確認できる．