# LINE Notify フロー体験してみよう

![image](https://i.gyazo.com/2fe8f1e2d461451f6b5212996272c3ee.jpg)

## 今回の仕組み

![image](https://i.gyazo.com/ed2e7f058f3c5f23dfef14eadd702f3f.png)

![image](https://i.gyazo.com/1ac48b18d79a5bb34242985d01395928.png)

この仕組みは、みなさんが事前準備で作成した LINE Notify のアクセストークンを使い、Discover Flow を使って LINE Notify フロー体験をします。

inject ノードをクリックすると LINE Nofify フローにタイムスタンプのデータが送られて LINE の今回作った LINE Notify チャットにメッセージが到着します。

![image](https://i.gyazo.com/de8a891f0c2baede37ca047ed3f8decb.png)

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

## フローの仕組みを少し変えてみましょう

![image](https://i.gyazo.com/c41ee556554ede26d1155cb3156591c6.png)

## ダッシュボードのカラーを LINE のようなカラーに変えてみる

![image](https://i.gyazo.com/a98a01c8bcd37ee36b972fc473b653b6.png)

サイドバーからダッシュボードの設定タブを表示します。

![image](https://i.gyazo.com/3c9564924d742f27d9f648741385d519.png)

ダッシュボードの設定タブが表示されたらテーマのタブをクリックしましょう。

![image](https://i.gyazo.com/f27b086593b8f56fbb1882d15ef8fc2d.png)

基本設定の色を設定します。

![image](https://i.gyazo.com/1832443125dc3b8ee3e4f3c1aef415e5.png)

色の設定はこのようになっています。

![image](https://i.gyazo.com/9ad4569d5f9bee42ccc286dabab7eb85.png)

[LINE APP ICON GUIDELINE](https://line.me/ja/logo) のロゴのガイドラインからLINE のカラーコードを見てみると `#06c755` です。RGB 値でいうと `R 6, G 199, B 85` です。

![image](https://i.gyazo.com/bba94631fb00ffb9f83804e5fff9cf99.png)

デプロイボタンをクリックして、今回の変更をフローに反映します。

![image](https://i.gyazo.com/310c7dc76fff5f31c3ce26490277f551.png)

すぐに反映されます。

このように自分好みにカラーを変更することができます。スタイルをカスタムに変更するとより細かく変更できますが、設定項目が多いので、少しずつ試しながら進めましょう。

## 送る文言を変えてみる

![image](https://i.gyazo.com/2e2f3453ee934f50852960aab89d7033.png)

送る文言を決めている change ノードをダブルクリックしてプロパティを表示します。

![image](https://i.gyazo.com/0e967b7c0b9afa4e100b0b1865d76ad4.png)

表示したら対象の値の設定を `JSONata式` に変更します。

JSONata は、JSONデータの軽量クエリおよび変換言語です。簡単な計算や文字列処理をはじめ、複雑な配列やオブジェクトの操作まで色々なことができます。

より詳しい使い方が気になる方は、以下を参考にしてください。

- [JSONata の言語ガイドを訳してみた \- Qiita](https://qiita.com/yamachan360/items/91805334890d18ef6e23)
- （英語）[JSONata Documentation · JSONata](http://docs.jsonata.org/overview.html)

さて、

![image](https://i.gyazo.com/01f626e42fe04a0b03c49a845007f315.png)

これを使って LINE Notify に送る文言を変更してみましょう。

![image](https://i.gyazo.com/2c22c9a1cc63e19588e5caa695ce5dc0.png)

こちらのボタンをクリックして、詳細表示にします。

![image](https://i.gyazo.com/84fe605dd51c91f4fb1252c90e93ff2f.png)

JSONata が詳細に設定できるウィンドウが表示されました。

![image](https://i.gyazo.com/1581910d4448a6833c387afb363fa5f5.png)

`"今回メッセージが送信された内容は「" & payload.memo & "」です！"` という内容に変更したら、完了ボタンをクリックします。

![image](https://i.gyazo.com/6a01bb28216b8b1b43cbed19e692c450.png)

反映できたので、こちらも完了ボタンをクリックします。

![image](https://i.gyazo.com/bba94631fb00ffb9f83804e5fff9cf99.png)

デプロイボタンをクリックして、今回の変更をフローに反映します。

![image](https://i.gyazo.com/5da7e73976654ed02368f7a0a29826f0.png)

反映したら、ダッシュボードからまたメッセージを送ってみましょう！

![image](https://i.gyazo.com/ca1d13a00241448eb55a4f29aa4c7597.png)

送る内容を変更することができました。

## スマートフォンでも見てみましょう

![image](https://i.gyazo.com/e43c8f60ac53d382180a24ea45560926.png)

スマートフォンでも、LINE にメッセージが送れてしまう、この仕組みを体験してみましょう。

# 質疑応答

![image](https://i.gyazo.com/aba8ccd625e7320883851b71ebd0caf2.png)

ここまでで質問があればどうぞ！

# 次にすすみましょう

左のナビゲーションから「位置情報メモ投稿アプリフロー体験」にすすみましょう。

