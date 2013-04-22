=======================
maliit-pluginの日本語化
=======================

目標
====

- maliit-pluginsに日本語キーボードを追加する
- 上記をUbuntu Touchで動かす
- 上記をUpstreamにコミットする


リファレンス
============

- 本家のMaliit

  - http://gitorious.org/maliit/maliit-framework

  - http://gitorious.org/maliit/maliit-plugins

- Ubuntu TouchのMaliit

  - https://code.launchpad.net/~phablet-team/phablet-extras/maliit-framework

  - https://code.launchpad.net/~phablet-team/phablet-extras/maliit-plugins

- maliit-plugin-jp

  - http://code.google.com/p/maliit-plugin-jp/


方針
====

- maliit-plugin-jpについて

  0.8以前のMaliitをベースに当時足りなかったものをいろいろと自前で追加したので、
  これのポーティングは大変なのであまりおすすめしないらしい。

  あくまで「参考」に止める程度で。

- Maliitについて

  デスクトップで動作させるのは難しい。OnBoardと違い物理キーボードのあるなしに
  関わらず問答無用でオンスクリーンキーボードが起動しキーイベントを奪うようなので
  少なくとも仮想環境でないとダメかもしれない。

  あと開発者Michaelは日本語キーボード追加に乗り気らしい。

- Maliitのバージョンについて

  - 本家：0.99（Wayland対応とか入ってる）

  - Raring：0.94.2（たぶんplane）

  - Touch: 0.94.0 + かなり独自実装

    - maliit-keyboardを有効にするMRはでている

    - https://code.launchpad.net/~thomas-moenicke/phablet-extras/maliit-plugins_maliit-keyboard/+merge/158101

- どれをベースにする？

  - 将来性を考えると本家をベースにするのがベスト

  - ただしテスト環境にTouchを使うことを考えるとTouchでまともに動いている
    0.94.0 + phabletをベースにせざるを得ない

  - VirtualBoxでMaliitを動かせるようなら、0.99ベースも可能かもしれない

  => MRがすぐに終わりそうならTouchベースで


下準備
======
 ::

    $ sudo add-apt-repository ppa:ubuntu-sdk-team/ppa
    $ sudo apt-get update
    $ sudo apt-get install ubuntu-sdk maliit-framework-dev


