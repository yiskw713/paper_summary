## info
 Author:
 Fereshteh Sadeghi †, Alexander Toshev ‡, Eric Jang ‡, Sergey Levine ‡

affiliation: † University of Washington, ‡ Google Brain

 [PDF](https://arxiv.org/abs/1712.07642)

[video](https://youtube.com/watch?v=oLgM2Bnb7fo)

## 概要
人間は様々な視点や角度から，手足を動かし道具を用いることに長けている．これをロボティクスの分野では，visual servo(主に視覚情報を用いて，道具を動かしたり，手先を目的の物体へ動かすこと)と呼ぶ．\
visual servo では，視点は変化するものであるため，単一の　feedforward な操作から行動を決めることは不可能な場合がある．\
そこで本論文では，過去の動作の記録を用いて，現在の視点においてaction がどのようにロボットの動きに影響を与えるかを理解し，間違いを正し，目的の物体に徐々に近づいていくようなシステムを提案している．\
このシステムでは，Reccurent Controller と 強化学習をベースにしていて，従来の研究とは対象的に，力学が既知であることを仮定せず，また calibration の段階を必要としていない．学習はシュミレーション上で行われ，視覚的特徴を少量のラベル付された画像で学習するだけで，実世界への転移を可能にした．


## 提案手法
![スクショ](https://github.com/Yuchi713/paper_summary/blob/master/pic/Sim2Real%20View%20Invariant%20Visual%20Servoing%20by%20Recurrent%20Control2.png)

上図のようなネットワークを提案している．

このシステムでは，従来の visual servo にあるような，行動と物体の動きの間の関係(Jacobian)に関する知識や，前持った visual features の学習を必要とせず，すべてデータから学ぶ．ターゲットに関する知識も与えられないので，query の画像からターゲットを特定する．

RNNを用いることで，過去の行動の結果を用いて，手と視覚情報の位置合わせに関する知識を抽出し獲得している．これをシミュレーション上でランダムに作られた大量のシーンで学習させることで，視点や物体の外見に対して汎化性能を持つことを可能にしている．

![スクショ](https://github.com/Yuchi713/paper_summary/blob/master/pic/Sim2Real%20View%20Invariant%20Visual%20Servoing%20by%20Recurrent%20Control3.png)

シミュレーション上では，照明を変えたり，種類，色やテクスチャ，姿勢の違う物体を用いて，様々なレイアウトを作成している．上図参照

学習においては，loss はアームから物体へのベクトルと出力のactionのL2距離の二乗としている．また，Q-Learning を用いて学習を行っている．

実世界へモデルを転移させる場合は，視覚的特徴のみを adaptation させる．この際，モデルの畳み込み層だけをファインチューニングさせている.



## 検証
![スクショ](https://github.com/Yuchi713/paper_summary/blob/master/pic/Sim2Real%20View%20Invariant%20Visual%20Servoing%20by%20Recurrent%20Control1.png)

上図は，recurrent control と reactive control の２つを，物体が２つの場合と3つの場合で，それぞれどれほど query の物体に近づくかを比較したものである．いずれの結果からも，recurrent control のほうが，物体の近くまでアームを動かすことができ，recurrent control の有用性が確かめられる．  
    


![スクショ](https://github.com/Yuchi713/paper_summary/blob/master/pic/Sim2Real%20View%20Invariant%20Visual%20Servoing%20by%20Recurrent%20Control4.png)

上図は，実世界の視覚的特徴を用いてモデルを適応させた場合とそうでない場合を比較した表である．実際に adaptation させた場合のほうが精度は高く，その有用性が確かめられる．

## 新規性
* RNNを用いている点
* 事前知識なくすべてを学習する点
* query の画像から，支持された物体を特定し，ロボットアームを動かす点



## 議論,展望
* depthやステレオ画像を用いることで，精度向上が望める
* より複雑な動作が生成可能になるか？
* 実験では 2物体までしか行っていない．それ以上では精度は相当低そう 