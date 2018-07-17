## INFO
### author
Konstantinos Bousmalis<sup>*,1</sup>
, Alex Irpan<sup>*,1</sup>
, Paul Wohlhart<sup>*,2</sup>
, Yunfei Bai<sup>2</sup>
, Matthew Kelcey<sup>1</sup>
, Mrinal Kalakrishnan<sup>2</sup>
, Laura Downs<sup>1</sup>
, Julian Ibarz<sup>1</sup>
, Peter Pastor<sup>2</sup>
, Kurt Konolige<sup>2</sup>
, Sergey Levine<sup>1</sup>
, Vincent Vanhoucke<sup>1</sup>

### affiliation
<sup>*</sup>Authors contributed equally\
<sup>1</sup>Google Brain\
<sup>2</sup>X

### conference 
ICRA2018

### link
[PDF](https://arxiv.org/abs/1709.07857)\
[video](https://www.youtube.com/watch?v=-k0MdN7vW_M)\
[blog](https://ai.googleblog.com/2017/10/closing-simulation-to-reality-gap-for.html)


## 概要
![pic]()
<br>

ロボットの物体把持において，アノテーションされたデータセットを用意するのは，時間がかかりコストも高い．ロボティクスの分野においては，シミュレーションを用いて合成データを作ることができるが，実世界に対して汎化性能を持たせることは難しい．そこで本論文では，graspGAN と呼ばれる，domain adaptation を用いた，シミュレーション上の合成画像から，現実世界の画像に似た合成画像を生成するモデルを用いて，学習データを大量に作成した．これにより，あるレベルのパフォーマンスに必要なリアルデータの数を1/50に減らすことができた．加えて，ラベルなしの実際の画像とGraspGANを用いた場合と，およそ100万枚のラベル付けされた画像を用いた場合で，パフォーマンスが同程度であることを確認した．

## 提案手法

## 検証

## 新規性

## 議論，展望

## comment
理解できていない点が多数なので，今後読み込んでいきたいと思います．

## date
July 17th, 2018