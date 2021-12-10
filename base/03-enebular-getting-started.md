# enebular を動かそう

![image](https://i.gyazo.com/2fe8f1e2d461451f6b5212996272c3ee.jpg)

## このページの概要

このページでは、実際に enebular をブラウザで動かして基本的な使い方やフローの作り方を理解していきます。

## 注意 : enebular には最新の Chrome ブラウザでアクセスしましょう

![image](https://i.gyazo.com/5e1ec175cac8cc7db65c7ce4c04f2bae.png)

enebular には最新の Chrome ブラウザでアクセスしましょう。

## enebular へログイン

![image](https://i.gyazo.com/7f6553a1ad9aaf68d497a8cc6c3805f4.jpg)

[https://www.enebular.com/ja/](https://www.enebular.com/ja/) にアクセスします。

![image](https://i.gyazo.com/aea8ffa24d015ec37c14c444c12a68e8.png)

右上のサインインをクリックしてサインインページを表示します。

![image](https://i.gyazo.com/7e67da7d8aefcf305956822f42a68683.png)

[事前準備](00-preparation.md) でつくった自分の enebular アカウントでサインインします。

![image](https://i.gyazo.com/b40f201363ea704a542c325a31188d86.png)

サインイン後の画面、ダッシュボードが表示されました。

## Project の作成

こちらの [Introduction](https://docs.enebular.com/ja/GetStarted/Introduction.html) を参考に進めていきます。

![image](https://i.gyazo.com/b40f201363ea704a542c325a31188d86.png)

enebular を始めるには、まず Project を作成します。サインイン後の画面にある Create Project からプロジェクトを作成します。

![image](https://i.gyazo.com/dda13a6dbeadafb6491b753406d8155c.png)

Create Project のウィンドウが表示されるので project name を `semboku-digital-2021-day1` と入力して Submit ボタンをクリックします。

![image](https://i.gyazo.com/29f6e5a9940709862b09e375d60bf7ed.png)

入力したプロジェクトで Project が作成されたことがダッシュボードの一覧で確認できます。

## Asset の作成

Project を作成できたら enebular の Asset の 1 つである Flow を作成しましょう。

![image](https://i.gyazo.com/83e489254734c6c2374b0746664b19ba.png)

作成した Project をクリックします。

![image](https://i.gyazo.com/8603d62dde1c42d21bd74bfffdbbc699.png)

Project の管理画面に移動します。

![image](https://i.gyazo.com/513cf5804faa14e1022d09d0d8316123.png)

右下の + ボタンをクリックすると Asset を作成するウィンドウが表示されます。

![image](https://i.gyazo.com/11eb54dc446d6e63f87c1f6394025a6e.png)

Asset Type は flow を選択して、Flow のタイトル `flow-semboku-first-step` とつけます。

Flow へのデフォルトのアクセス権（Default Privilege ）は今回は edit, deploy, publish に設定してください。 Continue ボタンをクリックします。

![image](https://i.gyazo.com/0e74d5e7ed87c7602653f3879790ab91.png)

作成が完了し、Flow の詳細ページに移動します。

![image](https://i.gyazo.com/451dd8ff068ebcd230a77a65f3c68c91.png)

Edit ボタンをクリックします。

![image](https://i.gyazo.com/98736f6f6724b9e6caf6faee92380646.png)

左上に Loading がでたら、しばらく待ちます。

![image](https://i.gyazo.com/24326a0a917c45ac033ca382b83e1b9a.png)

フローを編集する画面が立ち上がります。こちらが、先ほどふれた Node-RED というローコードツールで出来ているところです。

## enebular の活動限界について

![image](https://i.gyazo.com/d4e5595e4ee627fadc4dc5a1008e8ff4.png)

WEBブラウザで enebular のフローエディタを使っている際には、1セッションは「60分まで」となっています。ここでいう「1セッション」は、ダッシュボードから編集するフローを選択し、「Edit」ボタンを押してフローエディタが起動してから始まります。

このあたりの詳細について、以下のページを元に説明します。

[enebularの活動限界について \| enebular blog](https://blog.enebular.com/enebular/session-time/)

## Node-RED とは

![image](https://i.gyazo.com/07c703e8af39a7a5aaf5e660f663b576.png)

[Node\-RED日本ユーザ会](https://nodered.jp/)

enebular のエディタで使われている Node-RED は Node.js で動く仕組みです。

Node-RED はサーバーとフロントエンドの両方を作れる仕組みです。GUI（ビジュアルで見えるUI）によって、APIを取得する仕組みであったり、dashboard のように表示も作れます。

## 動かしてみよう

[はじめてのフロー : Node\-RED日本ユーザ会](https://nodered.jp/docs/tutorials/first-flow)

こちらを元に進めます。

ウォームアップしてみましょう。

![image](https://i.gyazo.com/b94d2d8a7a58febf76226db658c7d5dc.png)

このようなシンプル仕組みをつくります。

## ノードについて

![image](https://i.gyazo.com/4209abfa226dca0d1a4c1d3421768bbe.png)

まず ノード（Node）はNode-REDを構成する基本的な構成要素です。処理をする機能のかたまりです。

![image](https://i.gyazo.com/ac72b467278872701170501f629731ef.png)

ノードはフロー中の前方のノードからメッセージを受け取るか、外部イベントを受け取ることで動き出します。ノードはメッセージまたはイベントを処理し、 フロー中の次のノードにメッセージを送ります。左から右に処理されていきます。

![image](https://i.gyazo.com/b2e38a11e61da1ad55ff387493b71891.png)

メッセージはJSONデータで構成され、`msg` という一番上のオブジェクトにぶら下がっている `payload` というオブジェクトの中で、各ノードで処理された内容がバケツリレーのようにやり取りされていきます。

![image](https://i.gyazo.com/7a554e64647323ace99a930de52bfe67.png)

こんな感じです。

![image](https://i.gyazo.com/20007903edfd97e9aabddeedd5d6d8d5.png)

今回は inject というノードでボタンクリックをきっかけにメッセージを送り、 debug ノードという送られてきたメッセージをサイドバーのデバッグタブに表示するノードに送ります。

## 画面紹介

![image](https://i.gyazo.com/3daddc165d37ee01f4979f41b24aca58.png)

パレットはインストール済みで利用可能なすべてのノードが含まれます。ノードが置かれているエリアです。

![image](https://i.gyazo.com/0585e0413f7414fbd84611d138041dd1.png)

ワークスペースはパレットからノードを配置してフロー（データの流れ）を作るエリアです。

![image](https://i.gyazo.com/56fb7c652379633d8d86c52f5784e799.png)

サイドバーは、エディタ内に多くの便利なツールを提供するエリアです。

* ノードについてのさらなる情報
* ヘルプを確認するパネル
* デバッグメッセージを確認するパネル
* フローの設定ノードを確認するパネル

などがあります。

## inject ノードと debug ノードをつなげていく

![image](https://i.gyazo.com/69d9424ea7db4779794c1d39e1d0a44f.png)

inject ノードをワークスペースにドラックアンドドロップします。

![image](https://i.gyazo.com/4ab5cd15ee540f8b2181cafc29cf9377.png)

inject ノードの横にdebugノードをドラックアンドドロップします。

![image](https://i.gyazo.com/b8eb34fb3296018ddae614e01bd47a50.png)

inject ノードと debug ノードをつなぎます。つなぐものはワイヤーといいます。

![image](https://i.gyazo.com/58de57346d51b7620c32562f9c8690bf.png)

デプロイボタンをクリックすると今作ったものが反映されます。

![image](https://i.gyazo.com/6d69e6990487e06533edba753d67904e.png)

## 動かしてみる

![image](https://i.gyazo.com/486f98add3229d4cc880359bf1b3b643.png)

debugノードでデータがきてるか確認します。

![image](https://i.gyazo.com/6efbc1b0671669a3e5201e23e7298216.png)

debugノードのデータはサイドバーのデバッグタブをクリックすると見れます。

![image](https://i.gyazo.com/f99e3989db06dd84900022d8be76cb75.png)

injectノードの横のボタンを押すとdebugノードにデータが送られます。今回はinjectノードは日付（タイムスタンプ）を送っています。さきほどのデバッグタブでdebugノードが受け付けたデータを確認できます。

## injectノードで送るデータを変更

injectノードをダブルクリックしてデータを変更しましょう。

![image](https://i.gyazo.com/05dc870ae85c44d1be74d97b1a474b41.png)

ノードはダブルクリックすると細かな設定ができます。

![image](https://i.gyazo.com/6416484adf11e2410f0e5e1042da7f53.png)

ペイロードがデータの内容です。数値に変更しましょう。

![image](https://i.gyazo.com/290cce9c52a9736289eb3317a8f18f36.png)

50に設定して完了をクリックします。

![image](https://i.gyazo.com/6d69e6990487e06533edba753d67904e.png)

デプロイボタンをクリックすると今作ったものが反映されます。

![image](https://i.gyazo.com/5ce3b9ec73285db932270eabfab4ac63.png)

動かして、inject ノードから送られるデータが 50 の数値になっているか確認します。


# 質疑応答

![image](https://i.gyazo.com/aba8ccd625e7320883851b71ebd0caf2.png)

ここまでで質問があればどうぞ！

# 次にすすみましょう

左のナビゲーションから「Discover Flow で WEB アプリ体験」にすすみましょう。

