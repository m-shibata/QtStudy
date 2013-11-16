==================
MatsuyaBoardの改修
==================

usersの削除
===========

- GitHubへpull requestする際のベストプラクティス
    http://d.hatena.ne.jp/hnw/20110528

- Pull Requestの方法
    http://rcmdnk.github.io/blog/2013/05/19/computer-git-github/

git checkout -b myFeatureSpike
（変更）
git commit

git remote add upstream git://...
git checkout master
git pull upstream master
git checkout myFeatureSpike
git rebase master myFeatureSpike

git checkout -b myFeature
git rebase -i master
（squashを選択）
git push origin myFeature

（pull requestはwebで）

マージされたら
git branch -D myFeature
git push origin :myFeature
git pull upstream master


MatsuyaBoardの近代化改修
========================

Ubuntu.Componetを使うかどうかを分けるには
  http://qt-project.org/doc/qt-5.0/qtqml/qtqml-javascript-dynamicobjectcreation.html
  普通にimportをエラー検知はできない


MultiPointTouchArea
===================

- QMLのドキュメント
  http://qt-project.org/doc/qt-5.1/qtdoc/qtquick-usecase-userinput.html

  MultiPointTouchArea
  PinchArea
  Flickable

- サンプル
    sudo apt-get install qtdeclarative5-examples
    cd /usr/lib/x86_64-linux-gnu/qt5/examples/quick/touchinteraction/
    ./touchinteraction

    flickresizeがよさそう。

- タップ
- ダブルタップ
- 二本指タップ
- ロングプレス
- ピンチイン・アウト
- 二本指で回転

