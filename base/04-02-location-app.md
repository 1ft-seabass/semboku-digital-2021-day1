# 位置情報メモ投稿アプリフロー体験してみよう

![image](https://i.gyazo.com/2fe8f1e2d461451f6b5212996272c3ee.jpg)

## 今回の仕組み

![image](https://i.gyazo.com/587e13c10ad85a84e73c2725b1b1ee72.png)

この仕組みは、位置情報メモ投稿アプリフロー体験します。

まず、Node-RED のダッシュボード機能でできた WEB アプリに地図機能があり、その地図に対して位置情報を伝えます。地図に登録した地点のメッセージを書き込み、LINE Notify 確認します。

みなさんの URL を教え合って、みなさんの WEB アプリを操作してみましょう

## Discover Flow

以下のフローを [先ほど学んだ手順](04-00-discover-flow.md) を参考にインポートしましょう。

[flow-semboku-location-app](https://enebular.com/discover/flow/31781034-83fe-4933-aae8-af2195a29394)

![image](https://i.gyazo.com/6d5e3f7ee520af333a5c838f1156645b.png)

## インポート出来たらフローをエディタで見てみよう

![image](https://i.gyazo.com/040208eb0965169117e7170adbc0d169.png)

Edit ボタンをクリックしてエディタを起動しましょう。

![image](https://i.gyazo.com/3f3fb9f2c4de48ac04dbee9dbea0e06e.png)

フローが表示されます。

## フローを設定してみよう

みなさんが事前準備で作成した LINE Notify のアクセストークンを使います。

![image](https://i.gyazo.com/1d81e2af8ad0916785bb3eeb8aedf94d.png)

LINE Notify フローをダブルクリックしてプロパティ画面を表示します。

![image](https://i.gyazo.com/c7abb2032c8f52b172a9e71f9bc348f6.png)

LINE Notify フローのプロパティ画面が表示されます。

![image](https://i.gyazo.com/6fb6268c14f75b900992d808fd56c6db.png)

LINE Notify AccessToken のテキストエリアに LINE Notify のアクセストークンを入力して、完了ボタンをクリックします。

![image](https://i.gyazo.com/bba94631fb00ffb9f83804e5fff9cf99.png)

デプロイボタンをクリックして、今回の変更をフローに反映します。

## 動かしてみる

![image](https://i.gyazo.com/17ce8db81a3ef51ab06bef4b8ef7a59a.png)

フローを体験してみましょう。

![image](https://i.gyazo.com/f1aae1ca905dcaa3433e1cdfaa36559b.png)

サイドバーから Dashboard のタブを表示します。

![image](https://i.gyazo.com/c504b26edfe858dc68b8eff5c6f0f75b.png)

このボタンクリックしてダッシュボードを表示します。

![image](https://i.gyazo.com/2f460db53eb194b20f1233f4c3bfaaff.png)

PC でダッシュボードでつくられた WEB アプリを表示します。

## マップに登録した地点のメッセージを書き込み、LINE Notify 確認

![image](https://i.gyazo.com/b601cc80efb75bccba1680d7e6e356dc.png)

マップで左クリックすると情報が書き込めます。

![image](https://i.gyazo.com/834fdd4c72a049e20290335ee70300d0.png)

テキストエリアに、登録するメッセージを入力します。

![image](https://i.gyazo.com/cf881f43c096a0acbdaa86a74abfa197.png)

登録した地点にピンが表示されます。

![image](https://i.gyazo.com/36b75292254b7ad3f582206d001305d7.png)

LINE Notify をスマートフォンで見てみると、登録された地点とメッセージが確認できます。

## スマートフォンで表示します

![image](https://i.gyazo.com/e43c8f60ac53d382180a24ea45560926.png)

こちらの仕組みを、ぜひスマートフォンでも試してみましょう。PCの場合は左クリックでしたが、スマートフォンの場合は、タップ（クリック）で登録できます。

## エクストラ：みなさんのURLを教え合ってみなさんの WEB アプリを操作してみましょう

![image](https://i.gyazo.com/9c6c71fc0c3a966232825beefbe0b8d6.png)

もし、時間があれば、みんなのアプリを動かしていきましょう。

- まず Slack にみなさんの enebular URL を教えてください。
- 全員はできないかもしれませんが、数人ピックアップしてやってみます。
- ひとりの田中の Chrome で表示して QR コードを表示します。
- みんなで入ってみて、地点を登録してみましょう！

## エクストラ：スマートフォンの現在地を取得してみる

スマートフォンと OS によってはうまくいかないケースもあるのでエクストラです。

スマートフォンの現在地を取得できる機能もあります。

![image](https://i.gyazo.com/ec6be7fa6cae1194b47b8b021c457ffc.png)

下にスクロールすると、スマートフォンの現在地を取得するボタンがあるのでクリックします。

![image](https://i.gyazo.com/2e01f3d96f6e56209d59d12153aa5c28.png)

ブラウザ右上のアドレスバーでユーザーの現在地の許可がでてくるので `許可` をクリックします。

![image](https://i.gyazo.com/5c5a8d4740968d186a5be85a33f5f03c.png)

みなさんの現在地が表示されます。

## 仕組みの説明

![image](https://i.gyazo.com/3f3fb9f2c4de48ac04dbee9dbea0e06e.png)

こちらの仕組みを説明します。

## フローの仕組みを少し変えてみましょう

![image](https://i.gyazo.com/c41ee556554ede26d1155cb3156591c6.png)

## LINE の通知の緯度経度を Google マップで見れるリンクにしてみよう

![image](https://i.gyazo.com/42d26f43a67eec260adf15099093beb8.png)

こちらのメッセージですが、投稿テキストと緯度経度はわかりますが、実際の位置を知りたいですよね。

Google マップでは `https://www.google.com/maps?q=緯度,経度` と URL を指定すると、その緯度経度の位置にピンが立って分かりやすく位置を表示してくれます。

今回のメッセージに加えてみましょう。

![image](https://i.gyazo.com/38eb84edc1417e4040fd98fcc768d77a.png)

こちらの change ノードをダブルクリックしてプロパティを表示します。

![image](https://i.gyazo.com/543c6905402f82448a4f687b8e47ac0c.png)

JSONata式で書かれているの JSONata 詳細画面をこちらのボタンをクリックして表示します。

```
"地点 緯度:" & payload.lat & " 経度:" & payload.lon & "にメッセージ「" & payload.name & "」が登録されました。"
```

を、

```
"地点 緯度:" & payload.lat & " 経度:" & payload.lon & "にメッセージ「" & payload.name & "」が登録されました。Map : https://www.google.com/maps?q=" & payload.lat & "," & payload.lon
```

に変更してみましょう。

![image](https://i.gyazo.com/bba94631fb00ffb9f83804e5fff9cf99.png)

デプロイボタンをクリックして、今回の変更をフローに反映します。

![image](https://i.gyazo.com/fc0af718f87ddf8b69699d81ba49208d.png)

こちらで地点登録を行うと、Google マップの URL が追加されます。

![image](https://i.gyazo.com/bd232236f56241d0d7e3214432b4b2b1.png)

クリックしてみると地点が Google マップで確認できます。

## worldmap ノードを試したい人、プロパティを見たい人

![image](https://i.gyazo.com/045320ab365b3bf91706a31c3685284e.png)

2021/12 現在、実は enebular で worldmap ノードを使うときに、ノードをダブルクリックしてもプロパティがでてきません。

![image](https://i.gyazo.com/796a996b56fa012afe95b59a33e1b952.png)

そのときは、適当な別のノード（たとえば、debug ノード）をクリックして、

![image](https://i.gyazo.com/5f74bbcbca0f0c1ba7b731c4101b9000.png)

そのノードプロパティ表示してから、中止をクリックしましょう。

![image](https://i.gyazo.com/ea035e1988a43279aa81c251bcad8b86.png)

そうすると、worldmap ノードの設定ができます。一時しのぎではありますが、試してみてください。

# 質疑応答

![image](https://i.gyazo.com/aba8ccd625e7320883851b71ebd0caf2.png)

ここまでで質問があればどうぞ！

# 次にすすみましょう

左のナビゲーションから「フローの仕組みを理解して少し変えてみよう」にすすみましょう。

