## INFO
### author
Jan Matas, 
Stephen James, 
Andrew J. Davison

### affiliation
Department of Computing Imperial College London

### link
[PDF](https://arxiv.org/abs/1806.07851)<br>
[video](https://youtube.com/watch?v=Dr0RvX1F-YQ)<br>
[summary](https://medium.com/intelligentunit/paper-review-3-sim-to-real-reinforcement-learning-for-deformable-object-manipulation-d847b9c26cc)



## 概要
end-to-endな学習や，シミュレーション上で学習した方策を実空間上に転移することが盛んに行われている一方で，変形する物体の manipulation に対して，それらが有用であるかどうかは検証されてこなかった．そこで本論文では，SOTAな深層強化学習を組み合わせて，それらが変形する物体に対して有用性を持つことを確認した．シミュレーションから実空間へ転移させる方法としては，[domain randomization](https://github.com/yiskw713/paper_summary/blob/master/sim2real/Domain%20Randomization%20for%20Transferring%20Deep%20Neural%20Networks%20from%20Simulation%20to%20the%20Real%20World.md)が用いられている．強化学習の方法としては，Deep Deterministic Policy Gradients(DDPG)を改良したものを用いている．
<br>
<br>
![]()
<br>
上図は，本論文における Domain Randomization の例．