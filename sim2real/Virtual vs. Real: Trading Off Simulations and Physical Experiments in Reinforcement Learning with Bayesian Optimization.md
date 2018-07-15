## INFO
Author:Alonso Marco(1,5) and Felix Berkenkamp(2,5) and Philipp Hennig(1,5) and Angela P. Schoellig(3) and Andreas Krause(2,5) and Stefan Schaal(1,4,5) and Sebastian Trimpe(1,5)\
\
Affiliation:
1. Max Planck Institute for Intelligent Systems, Tubingen, Germany.

2. Learning & Adaptive Systems Group (LAS), Department of Computer Science, ETH Zurich, Switzerland.

3. Dynamic Systems Lab (DSL), University of Toronto Institute for Aerospace Studies (UTIAS), Canada.

4. Computational Learning and Motor Control Lab, University of Southern California, USA.

5. Max Planck ETH Center for Learning Systems, Tu ̈bingen, Germany, and Zu ̈rich, Switzerland.

[PDF](https://arxiv.org/abs/1703.01250)

[動画](https://youtube.com/watch?v=oq9Qgq1Ipp8)



## 要旨
強化学習において，シミュレーション上での試行は低コストだが不正確，実環境上での試行は高コストだが正確といったトレードオフの関係がある．そこで，この研究では，エントロピーサーチ(各試行からの情報利得を最大化するベイズ最適化のアルゴリズム)を実環境と仮想環境の複数環境に適応させた．これを有名な倒立振子の実験に用い，その有用性を示した．

## 問題設定
強化学習においては，あるタスクに対する方策のパフォーマンスを表すコスト関数$J(\theta)$を最小にする$'\theta'$を決定するのが目標．\
$\theta_{min} = \underset{\theta\in D}{argmin}J(\theta)$

コスト関数とパラメータ$\theta$の関係は演繹的にはわからないので，ガウス過程を用いてコスト関数を定義する.\
\
この論文では，$J(\theta)$の最小値の位置に対する不確定性を最大限減らすような$\theta$を，エントロピーサーチを用いて求める．エントロピーサーチにより，以下のように最小値の位置の分布のエントロピーによって，不確定性を定量化する\
$p_{min}(\theta)=P(\theta \in \underset{\theta \in D}{argmin}J(\theta))$  
$p_{min}$のエントロピーの変化の割合は，最小値の位置に関する情報をどれだけ得ることができるかを決定するものなので，次のイテレーションでコスト関数を評価するための最適なパラメータは\
$\theta_{n+1}=\underset{\theta \in D}{argmin}E[\Delta H(\theta)]$\
となる．$\Delta H(\theta)$は，位置$\theta$における新しいコストの値を得たことによる$p_{min}$のエントロピーの変化である．

## 提案手法
真のコスト関数は，シミュレーション上での見積もられたコスト関数に，誤差のコスト関数を加えたもので表されるものとしてモデル化した．すなわち\
$J(\theta)=J_{sim}(\theta)+J_{err}(\theta)$
とする．ここで，シミュレーション環境か実環境下を示す関数$\delta$を導入する．$\delta=0$のとき仮想環境，$\delta=1$のとき実環境を表す．これにより，ガウス過程のカーネルを，新たな変数$a=(\theta,\delta)$を用いて，以下のように表した．\
$k(a,a')=k_{sim}(\theta, \theta')+k_{\delta}(\delta,\delta')k_{err}(\theta, \theta')$\
この導入により，実環境でのみ誤差が考慮されることとなる．

エントロピーサーチを用いて，同様に以下のように，最小値付近におけるコスト関数の分布を表せる．
$p_{min}(\theta)=P(\theta \in \underset{\theta \in D, \delta=1}{argmin}J(\theta,\delta))$  

また，特定の情報源から評価を得るためのコスト(例えば，評価にかかる時間)をeffortと定義し，実環境，仮想環境それぞれでのeffortをそれぞれ $t_{exp},t_{sim}$ とする．仮想環境のほうが低コストなので，$t_{exp}>t_{sim}$となる．これらを用いて，実環境，仮想環境それぞれの単位コストあたりの情報利得を計算することで，どちらでの評価が不確定性が低いかを自動的に計算できるようにした．\
$\underset{\theta \in D,i \in (sim,exp)}{argmin}E[\Delta H(\theta)/ t_i]$

このモデルは，エントロピーサーチ(ES)を複数の情報源へ拡張したものなので，_Mulit-fidelity_ _Entropy_ _Search_ (MF-ES)と呼ぶ

## 実験
有名な倒立振子の問題を，ESとMF-ESを比較して行った．

![スクショ](https://github.com/Yuchi713/paper_summary/blob/master/pic/Virtual%20vs.%20Real:%20Trading%20Off%20Simulations%20and%20Physical%20Experiments%20in%20Reinforcement%20Learning%20with%20Bayesian%20Optimization.png)

図5からMF-ESのほうが，コストが低いことがわかる．平均して33.23％コストが削減されたとのこと．さらに，ESと比べてかなり安定していることもわかる．
図6から，実空間上での必要な実験の数も減っていることがわかる．ESと比べて，22.86％減となっている．


## date
July 8th, 2018