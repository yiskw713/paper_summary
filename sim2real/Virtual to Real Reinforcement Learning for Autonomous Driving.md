## INFO
### author
Xinlei Pan<sup>∗1</sup>,
Yurong You<sup>∗2</sup>,
Ziyan Wang<sup>3</sup>,
Cewu Lu<sup>2</sup>

### affiliation
<sup>1</sup>University of California, Berkeley, Berkeley, CA, USA\
<sup>2</sup>Shanghai Jiao Tong University, Shanghai, China\
<sup>3</sup>Tsinghua University, Beijing, China

### conference
BMVC 2017

### link
[PDF](https://arxiv.org/abs/1704.03952)\
[video](https://youtube.com/watch?v=Bce2ZSlMuqY)\


## 概要
強化学習は自動運転において前途有望な方法ではあるが，安全面の観点から仮想空間上で学習する必要があり，仮想空間から実空間への転移が問題となる．そこで本論文では，仮想環境で学習した自動運転モデルを実空間上に適応させることを可能にする *realistic translation network* を提案している．実空間上と仮想空間上では，画像は異なるが，semantic segmentation は
ほとんど一致するはずなので，これを用いてシミュレーション上における画像を，本物っぽい画像に変換する．これによって，本物っぽいが合成画像で強化学習を行うことができ，実空間上にも上手く転移できる．
<br>
<br>
![]()
<br>
ネットワーク構造は上図のようになっている．仮想空間上の画像を一旦 semantic segmentation し，これから合成画像を出力して強化学習を行っている．