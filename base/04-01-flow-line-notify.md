# LINE Notify フロー体験してみよう

![image](https://i.gyazo.com/2fe8f1e2d461451f6b5212996272c3ee.jpg)

## 今回の仕組み

![image](https://i.gyazo.com/ed2e7f058f3c5f23dfef14eadd702f3f.png)

![image](https://i.gyazo.com/1ac48b18d79a5bb34242985d01395928.png)

この仕組みは、みなさんが事前準備で作成した LINE Notify のアクセストークンを使い、Discover Flow を使って LINE Notify フロー体験をします。

inject ノードをクリックすると LINE Nofify フローにタイムスタンプのデータが送られて LINE の今回作った LINE Notify チャットにメッセージが到着します。

Node-RED のダッシュボード機能でできた WEB アプリからメッセージを送って LINE Notify チャットにメッセージが到着する流れも体験します。

## Discover Flow

以下のフローを [先ほど学んだ手順](04-00-discover-flow.md) を参考にインポートしましょう。

[flow-semboku-linenotify-app](https://enebular.com/discover/flow/6c483a2c-80d7-472e-9330-7df30f109f73)

![image](https://i.gyazo.com/c9ea8432185179645a15d4eda21334a3.png)

## インポート出来たらフローをエディタで見てみよう

![image](https://i.gyazo.com/040208eb0965169117e7170adbc0d169.png)

Edit ボタンをクリックしてエディタを起動しましょう。

![image](https://i.gyazo.com/32e8986a067b70c373380c7f0bf06581.png)

フローが表示されます。

## フローを設定してみよう

みなさんが事前準備で作成した LINE Notify のアクセストークンを使います。

![image](https://i.gyazo.com/9a770a5bb1d80613ba78d13c250cfb70.png)

LINE Notify フローをダブルクリックしてプロパティ画面を表示します。

![image](https://i.gyazo.com/c7abb2032c8f52b172a9e71f9bc348f6.png)

LINE Notify フローのプロパティ画面が表示されます。

![image](https://i.gyazo.com/6fb6268c14f75b900992d808fd56c6db.png)

LINE Notify AccessToken のテキストエリアに LINE Notify のアクセストークンを入力して、完了ボタンをクリックします。

![image](https://i.gyazo.com/bba94631fb00ffb9f83804e5fff9cf99.png)

デプロイボタンをクリックして、今回の変更をフローに反映します。

## 動かしてみる

### タイムスタンプを LINE Notify に送る

![image](https://i.gyazo.com/137253b911a4841f593b8ba255174a7b.png)

こちらの inject ノードをクリックしてみましょう。

![image](https://i.gyazo.com/186ca6eac43a3e36cade24e1137d6b04.png)

クリックすると LINE Nofify フローにタイムスタンプのデータが送られて LINE の今回作った LINE Notify チャットにメッセージが到着します。

### 何かの文字を LINE Notify に送る

![image](https://i.gyazo.com/047a00d0f57e16df4ad440ae67c0c296.png)

こちらの inject ノードをクリックしてみましょう。

![image](https://i.gyazo.com/76651e3b50e8576dfe3aa85168d2d4fb.png)

クリックすると LINE Nofify フローに「やっほー」という文字列データが送られて LINE の今回作った LINE Notify チャットにメッセージが到着します。

### ダッシュボードの内容を LINE Notify に送る

![image](https://i.gyazo.com/b8450500d48c3cd5ac0995cb9faec543.png)

つづいて、ダッシュボードの内容を LINE Notify に送ります。

![image](https://i.gyazo.com/5901df29d86de6fb53e7b06a2acbc8c7.png)

こちらから Dashboard をクリックして、サイドバーに Dashboard を表示します。

![image](https://i.gyazo.com/e37aaf7d2a036831de128b2b1c189642.png)

このボタンクリックしてダッシュボードを表示します。

![image](https://i.gyazo.com/34774ae2a7b3e2c86e44c98e7fbd93ea.png)

Node-RED のダッシュボード機能でできた WEB アプリが表示されます。

![image](https://i.gyazo.com/ed2e7f058f3c5f23dfef14eadd702f3f.png)

メッセージのテキストエリアに、100文字程度までで自由にメッセージを入力して送信ボタンをクリックしてみましょう！

![image](https://i.gyazo.com/1ac48b18d79a5bb34242985d01395928.png)

LINE Nofify フローに入力したメッセージが送られて LINE の今回作った LINE Notify チャットにメッセージが到着します。

## 仕組みの説明

![image](https://i.gyazo.com/32e8986a067b70c373380c7f0bf06581.png)

こちらの仕組みを説明します。

## 今回のまとめ

（作成中）

□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■□□□□□□□□□■

# 質疑応答

![image](https://i.gyazo.com/aba8ccd625e7320883851b71ebd0caf2.png)

ここまでで質問があればどうぞ！

# 次にすすみましょう

左のナビゲーションから「位置情報メモ投稿アプリフロー体験」にすすみましょう。

