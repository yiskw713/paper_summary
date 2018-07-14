## info
 Author:
 Fereshteh Sadeghi †, Alexander Toshev ‡, Eric Jang ‡, Sergey Levine ‡

affiliation: † University of Washington, ‡ Google Brain

 [PDF](https://arxiv.org/abs/1712.07642)

[video](https://youtube.com/watch?v=oLgM2Bnb7fo)

## 概要
人間は様々な視点や角度から，手足を動かし道具を用いることに長けている．これをロボティクスの分野では，visual servo(主に視覚情報を用いて，道具を動かしたり，手先を目的の物体へ動かすこと)と呼ぶ．visual servo では，視点は変化するものであるため，単一の　feedforward な操作から行動を決めることは不可能な場合がある．そこで本論文では，過去の動作の記録を用いて，現在の視点においてaction がどのようにロボットの動きに影響を与えるかを理解し，間違いを正し，目的の物体に徐々に近づいていくようなシステムを提案している．このシステムでは，Reccurent Controller と 強化学習をベースにしていて，従来の研究とは対象的に，力学が既知であることを仮定せず，また calibration の段階を必要としていない．学習はシュミレーション上で行われ，視覚的特徴を少量のラベル付された画像で学習するだけで，実世界への転移を可能にした．


## 提案手法
[スクショ](../pic/Sim2Real View Invariant Visual Servoing by Recurrent Control2)


## 検証方法

## 新規性

## 議論展望
* depthやステレオ画像を用いることで，精度向上が望める
* より複雑な動作が生成可能になるか？