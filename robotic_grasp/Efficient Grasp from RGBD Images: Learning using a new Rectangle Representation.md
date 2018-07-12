## INFO

Author: \
Yun Jiang, Stephen Moseson, and Ashutosh Saxena
  
2011 IEEE International Conference on Robotics and Automation

[PDF](http://pr.cs.cornell.edu/grasping/jiang_rectanglerepresentation_fastgrasping.pdf)


## 概要

![スクショ]()

新しい7次元の把持位置の表現方法である"Grasp Rectangle" を導入した．この新たな表現方法を用いて，把持位置を推定し，実際にロボットに把持を行わせた．本研究では，RGBDイメージを用い，把持位置推定を2段階に分け，RGBDイメージとその2段階のアルゴリズムの有用性を実証した．

## 提案手法
把持位置の表現方法として，"Grasp Rectangle"を導入した．これは，gripper の2次元的な位置と水平方向角度と開く幅に加えて，三次元的なアームの角度や位置を表したものである．
また，把持位置推定のアルゴリズムとして，two-step learning algorithm というものを提案した．これは，把持位置推定を２つの段階に分け，1段階目で高速だが不正確な推定を，2段階目で遅いが正確な推定を行うものである．

## 検証方法
9つのデータセットを用いて，実際に把持位置を推定させた．平均精度は Point Metric(把持位置の中心の距離で判定)で98.2%, Rectangle Metric(Grasp Rectangleの相関で判定)で95.4%/
いずれも object-wise split で検証

また実際にロボットに把持させた結果は，Grasp/Holding までの成功率 87.9%

## 新規性
* Grasp Rectangle
* two step algorithm
* Cornell grasp dataset の作成\
   [URL](http://pr.cs.cornell.edu/grasping/rect_data/data.php)

## 議論
特に言及されてはいないが，学習に用いたデータセットでは，正解の grasp rectangle が1から3個，不正解のものは5個しかラベル付されていない．本来把持位置はもっとあるべきであり，rectangle で表すより，ログとして表したほうが良いのではないか． 