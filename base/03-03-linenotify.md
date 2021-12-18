# LINE Notify にメッセージを送ろう

![image](https://i.gyazo.com/2fe8f1e2d461451f6b5212996272c3ee.jpg)

## このページの概要

enebular から LINE Notify にメッセージを送ります。LINE Notify ノードは enebular には事前にインストールされていないため、ノードの追加からインストールしてノードを使えることも体験します。

## LINE Notify とは

![image](https://i.gyazo.com/e3d3568d86c27b2ba377aa3726106e8d.png)

[LINE Notify](https://notify-bot.line.me/ja/)

> Webサービスからの通知をLINEで受信
> Webサービスと連携すると、LINEが提供する公式アカウント"LINE Notify"から通知が届きます。
> 複数のサービスと連携でき、グループでも通知を受信することが可能です。

![image](https://i.gyazo.com/d4c9ebc3e2fee7879bbd183e241c832b.png)

このように、Webサービスからの通知を LINE 側のメッセージシステムが受け付けてユーザーの LINE アプリにメッセージを配信します。

![image](https://i.gyazo.com/a2776766858a54cd0ae3ccf0941b1d97.png)

自分の LINE に通知としてメッセージを受け取ることができる仕組みです。

- 自分から見に行かなくてもメッセージで知らせてくれる仕組み
- 複数人に一斉にメッセージを受け取る仕組み
- 何かしらの情報をまとめて知らせてくれる仕組み

といったものを作ることができます。

自分たちが設定した情報だけを手軽に LINE ユーザーに配信できるので、WEB アプリの仕組みと相性がよく「こういう通知内容は実際役に立つだろうか？」といった形で、自分たちの考えた発想を試しやすいです。

また、そういったメッセージを受け付ける部分を LINE に任せることで、LINE アプリの使い慣れた洗練されたレイアウトで、すぐにメッセージを表示できることも良い点です。

もし、このレベルに使いやすい仕組みを自分でイチからつくるとなると、WEB サーバーの知識・HTML/CSS/JavaScript といった WEB 表示の知識・セキュリティへの配慮・多くのユーザーがいる状況などなど整えるべきことが数多くあります。「こういう通知内容は実際役に立つだろうか？」というシンプルな試行錯誤をするまでに、たくさんの時間がかかります。

このあたりを、LINE Nofity および LINE アプリで、すぐに試せるというのは、自分たちの構想を試して良くしていくときには強い味方になります！

![image](https://i.gyazo.com/160d13cd5d0c8aff4207771863479a7e.png)

では、早速、enebular から LINE Notify にメッセージを送ってみましょう。

## 準備から Assets の作成

[前の章](03-01-enebular-hello-world.md) でお伝えした、

- 前回のフローを閉じる
- フローの詳細に戻る
- プロジェクトに戻る

まで進めます。

![image](https://i.gyazo.com/52cf959b332bb1040e3c1cce6634cdeb.png)

右下の + ボタンをクリックすると Asset を作成します。

![image](https://i.gyazo.com/72c4b3513fa324d043db00e2d0eda85c.png)

以前の章で学んだ Asset の作成を参考に Flow のタイトル `flow-semboku-linenotify-simple` にしてフローを作成しましょう。

作成が完了し、Flow の詳細ページに移動します。

## フローエディタを表示する

![image](https://i.gyazo.com/4fa8dd59baa8ea3922b76ff2cc9405d3.png)

Edit ボタンをクリックします。

![image](https://i.gyazo.com/98736f6f6724b9e6caf6faee92380646.png)

左上に Loading がでたら、しばらく待ちます。

## LINE Notify ノード

![image](https://i.gyazo.com/ef7aa63b1f9279306948017a56a8d1ac.png)

enebular および Node-RED では、LINE のメッセージを送るサービスを扱える LINE Notify ノード [node\-red\-contrib\-line\-messaging\-api](https://flows.nodered.org/node/node-red-contrib-line-messaging-api) があります。

もちろん LINE Notify も、この node-red-contrib-line-messaging-api に含まれています。

## ノードの追加

[パレットにノードを追加する : Node\-RED日本ユーザ会](https://nodered.jp/docs/user-guide/runtime/adding-nodes) を参考に今回のフローで LINE Notify ノードをインストールして使えるようにしましょう。

![image](https://i.gyazo.com/01a2e4abe23999069f59a9592ac9dfb8.png)

右上の ![image](https://i.gyazo.com/f2513e4b439966d15aa0d7c63fc71dd5.png) メニューをクリックします。

![image](https://i.gyazo.com/152de459bf73ad640bbb5a03b76ac4e5.png)

パレットの管理をクリックします。

![image](https://i.gyazo.com/6507f78ec8d4f4a8f4983ad9f1c84970.png)

パレットの管理が表示され、現在のノードタブに現在のインストールされているノードが表示されているので `ノードを追加` をクリックします。

![image](https://i.gyazo.com/2ebd3052f1de3180987d580571d97c56.png)

ノードを追加タブが表示されるので、ノードを検索するエリアに `node-red-contrib-line-messaging-api` と入力して検索します。

![image](https://i.gyazo.com/d2de9292f0b62f5c7b262817272f1672.png)

ノードを追加をクリックします。

![image](https://i.gyazo.com/e38e8a102795734c9825de82032b4b36.png)

このような説明がでてくるので追加をクリックしてインストールを開始します。

![image](https://i.gyazo.com/b618bacabf0462c8a5ed9918b4717a58.png)

インストールを待ちます。

![image](https://i.gyazo.com/6e49e2c75d6170e7200b2906cdcc209f.png)

このような説明が出ればインストール完了です。閉じるボタンをクリックして、パレットの管理ウィンドウを閉じます。

![image](https://i.gyazo.com/1a0f3af4b957baeade0711f090ca896a.png)

パレットで今回のノード群がインストールされているか確認します。こちらの Nofity が LINE Notify のノードです。

![image](https://i.gyazo.com/ba2eb7c97b9d339405e54fae20aeb5ce.png)

このように、ノードの追加機能で enebular で使えるノードを加えることができます。

Node-RED のサイトにある [ノード検索](https://flows.nodered.org/) で多種多様な機能のノードを確認することができ、使いたくなったノードを、さきほどのノードの追加機能で追加することができます。

## LINE Noftify ノードを配置して設定する

さて、エディタ画面を見てみましょう。パレットで LINE Notify ノードがあることを確認できました。

![image](https://i.gyazo.com/1a0f3af4b957baeade0711f090ca896a.png)

パレットからダッシュボードにボタンを作る LINE Noftify ノードを探して配置します。

![image](https://i.gyazo.com/2e074ae0844e7d5fca33700aee166a65.png)

配置したらダブルクリックしてプロパティを表示します。

![image](https://i.gyazo.com/1bb814fa2b980dd6778f294f521c541e.png)

LINE Notify AccessToken のテキストエリアに LINE Notify のアクセストークンを入力して、完了ボタンをクリックします。

## LINE Notify ノードのデータを送る inject ノードを設定

![image](https://i.gyazo.com/1bafb0a1839662dd65cd660805e273c7.png)

inject ノードをパレットから配置して、このように LINE Notify ノードにつなぎます。

こうすることで、inject ノードから送られたタイムスタンプが LINE Notify ノードに送られて、実際に LINE アプリの LINE Notify にメッセージが配信されます。

![image](https://i.gyazo.com/6abc382d3d9875421b4e5640fc703aa6.png)

デプロイボタンをクリックすると今作ったものが反映されます。

## 動かしてみる

![image](https://i.gyazo.com/00479a4c75aa549cb0f6d4ad820a2701.png)

inject ノードをクリックしてみましょう。

inject ノードから送られたタイムスタンプが LINE Notify ノードに送られて、実際に LINE アプリの LINE Notify にメッセージが配信されます。

![image](https://i.gyazo.com/579776460366346cd4ee3da17898bb0d.png)

LINE アプリの LINE Notify を見てみると、メッセージが到着しています！

# 質疑応答

![image](https://i.gyazo.com/aba8ccd625e7320883851b71ebd0caf2.png)

ここまでで質問があればどうぞ！

# 次にすすみましょう

左のナビゲーションから「Discover Flow で WEB アプリ体験」にすすみましょう。

