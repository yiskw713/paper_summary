## INFO
### author
Josh Tobin<sup>1</sup>, Rachel Fong<sup>2</sup>, Alex Ray<sup>2</sup>, Jonas Schneider<sup>2</sup>, Wojciech Zaremba<sup>2</sup>, Pieter Abbeel<sup>3</sup>

### affiliation
<sup>1</sup>OpenAI and UC Berkeley EECS\
<sup>2</sup>OpenAI\
<sup>3</sup>OpenAI, UC Berkeley EECS & ICSI


[PDF](https://arxiv.org/abs/1703.06907)


## 概要
![](https://github.com/Yuchi713/paper_summary/blob/master/pic/domain%20randomization%20for%20transferring%20deep%20neural%20networks%20from%20simulation%20to%20the%20real%20world1.png)
<br>
<br>
仮想空間と実空間の差異 "reality gap" のために，仮想空間における行動を実空間へと転移することは難しい問題となっている．\
そこで，この論文ではシミュレーション上でランダムにレンダリングした画像を用いて，実世界に転移可能なモデルを学習するという，domain randomization という手法を提案している．\
これにより，シミュレーション上での RGB image のみを用いて，deep neural network を学習し，実世界に転移させることを可能にした．

## 提案手法
### domain randomization
仮想空間上でランダムにレンダリングした画像を用いて，学習することを domain randomization というが，これの目的は 実世界上で汎化性能を得るために，学習時に多様なデータを与えることである．\
そのため以下の点をランダムに変えて画像をレンダリングする．
* distractor の数と形
* 物体の位置とテクスチャー
* テーブルや床，ロボットのテクスチャー
* カメラの位置や方向，視野
* シーンにおけるライトの数
* ライトの位置や方向，反射特性
* 画像に加えられるノイズのタイプや量

### ネットワーク
![](https://github.com/Yuchi713/paper_summary/blob/master/pic/domain%20randomization%20for%20transferring%20deep%20neural%20networks%20from%20simulation%20to%20the%20real%20world2.png)
<br>
<br>
上図のようなネットワークを用いている．VGG-16 を用いているが，全結合層はよりサイズの小さいものを用いていて，dropout は使用していない．
loss は L2 loss を用いていて，Adam optimizer を使用，学習率は 1e-4 としている．

## 検証
### 実空間上での精度
仮想空間上で学習した後，実空間上で物体の位置検出のタスクを行ったところ，平均して 1.5cm以内 の精度で検出を行うことができた．
<br>
<br>

### ablation study
以下3つは，ablation study として，domain randomization のいくつかの要素を変化させてみて，それがどのような影響を及ぼすかを検証した結果である

![](https://github.com/Yuchi713/paper_summary/blob/master/pic/domain%20randomization%20for%20transferring%20deep%20neural%20networks%20from%20simulation%20to%20the%20real%20world3.png)
<br>
<br>
上図は，domain randomization において，学習サンプルの数と平均誤差の関係を表したグラフである．サンプル数が多いほうが誤差は低くなっていることがわかる
<br>
<br>

![](https://github.com/Yuchi713/paper_summary/blob/master/pic/domain%20randomization%20for%20transferring%20deep%20neural%20networks%20from%20simulation%20to%20the%20real%20world4.png)
<br>
<br>
上図は，texture の数を変えた場合と平均精度の関係を表したグラフである．こちらも　texture　の数を増やすと，平均誤差が減少することがわかる．
<br>
<br>

![](https://github.com/Yuchi713/paper_summary/blob/master/pic/domain%20randomization%20for%20transferring%20deep%20neural%20networks%20from%20simulation%20to%20the%20real%20world5.png)
<br>
<br>
この図は，ノイズ，distractor，カメラそれぞれを，ランダムに変更しなかった場合の精度をまとめた表である．すべての randomization を行った場合のほうが精度が良いことが確かめられる．
<br>
<br>
### 実際の実験
既存のアルゴリズムを用いて，実環境上でロボットを動作させたところ，38/40 の精度で物体把持に成功している．


## 新規性
* domain randomization の提案
* 実際のimageの事前学習無しで，シミュレーション上のRGB image だけを用いて学習し，実空間上に転移を可能にした初めての例

## 議論,展望
* 高画素カメラ，ステレオカメラ，depth カメラの使用で精度向上が望める
* ネットワーク構造の最適化
* domain randomization と domain adaptation を組み合わせる
* 学習に幾何学モデルを用いているので，幾何学モデルに近似できない物体は対応できないのでは?

## date
July 15th, 2018