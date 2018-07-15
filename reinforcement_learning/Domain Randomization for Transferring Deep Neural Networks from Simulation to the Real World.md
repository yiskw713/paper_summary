## INFO
### author
Josh Tobin<sup>1</sup>, Rachel Fong<sup>2</sup>, Alex Ray<sup>2</sup>, Jonas Schneider<sup>2</sup>, Wojciech Zaremba<sup>2</sup>, Pieter Abbeel<sup>3</sup>

### affiliation
<sup>1</sup>OpenAI and UC Berkeley EECS\
<sup>2</sup>OpenAI\
<sup>3</sup>OpenAI, UC Berkeley EECS & ICSI


[PDF](https://arxiv.org/abs/1703.06907)


## 概要
![]()
<br>
<br>
仮想空間と実空間の差異 "reality gap" のために，仮想空間における行動を実空間へと転移することは難しい問題となっている．\
そこで，この論文ではシミュレーション上でランダムにレンダリングした画像を用いて，実世界に転移可能なモデルを学習するという，domain randomization という手法を提案している．\
これにより，シミュレーション上での RGB image のみを用いて，deep neural network を学習し，実世界に転移させることを可能にした．

## 提案手法
### domain randomization


### ネットワーク
![]()
<br>
<br>


## 検証
![]()
![]()
![]()

## 新規性
* 実際のimageの事前学習無しで，シミュレーション上のRGB image だけを用いて学習し，実空間上に転移を可能にした初めての例
* 

## 議論,展望


## date
July 15th, 2018