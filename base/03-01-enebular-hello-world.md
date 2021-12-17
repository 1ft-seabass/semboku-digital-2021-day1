# enebular から WEB に Hello World しよう

![image](https://i.gyazo.com/2fe8f1e2d461451f6b5212996272c3ee.jpg)

## このページの概要

enebular および Node-RED の操作がつかめてきたところで、enebular から WEB に Hello World してみます。

![image](https://i.gyazo.com/9ba52abefc2a1ead6d834379103dcc46.png)

enebular はいま作業している仕組みをデプロイすると WEB サーバーに反映されます。

今回は WEB からアクセスできる `/hello` という窓口を用意して、そこに PC やスマートフォンでアクセスすると `Hello World!` という文字を返してブラウザに表示する仕組みをつくります。

## 前回のフローを閉じる

enebular のエディタは一つだけ開いて編集することができます。つまり、前回のフローを閉じてから、今回のフローを作っていきます。

![image](https://i.gyazo.com/5dd595f5123837c177af62a0b1f2045b.png)

いま、Chrome ブラウザのタブで前回のフローが表示されています。

![image](https://i.gyazo.com/40dd653508a959f24323f56815997101.png)

タブを閉じましょう。

![image](https://i.gyazo.com/3967b715fd9a451ba57e3f65831ff125.png)

このような「このサイトを離れますか？」というウィンドウが表示されるので、このページを離れるボタンをクリックして閉じます。

## フローの詳細に戻る

![image](https://i.gyazo.com/ed472d20b0215523922cb02793bbafaa.png)

フローのタブを閉じると、Edit ボタンをクリックする前のフローの詳細が別タブに残っていて表示されているはずです。

## プロジェクトに戻る

![image](https://i.gyazo.com/af42a9ab00382c6f93557579b8d03b92.png)

左上のナビゲーションからプロジェクト名をクリックしてプロジェクトに戻ります。

## Assets の作成

![image](https://i.gyazo.com/52cf959b332bb1040e3c1cce6634cdeb.png)

右下の + ボタンをクリックすると Asset を作成します。

![image](https://i.gyazo.com/27bc1b763fdab6c5584722338cb007a4.png)

以前の章で学んだ Asset の作成を参考に Flow のタイトル `flow-semboku-hello-world-web` にしてフローを作成しましょう。

作成が完了し、Flow の詳細ページに移動します。

## フローエディタを表示する

![image](https://i.gyazo.com/4fa8dd59baa8ea3922b76ff2cc9405d3.png)

Edit ボタンをクリックします。

![image](https://i.gyazo.com/98736f6f6724b9e6caf6faee92380646.png)

左上に Loading がでたら、しばらく待ちます。

## http in ノードを配置してプロパティ設定

![image](https://i.gyazo.com/75b20fcc55290b1db7856639eb3ef2de.png)

パレットから HTTP の入り口をつくる http in ノードを探します。

![image](https://i.gyazo.com/988036239c5ea1de5dcdbc1d97d1e68b.png)

ワークスペースに配置します。

![image](https://i.gyazo.com/d32a1c1f9468610a9418b2a0b3e21947.png)

http in ノードをダブルクリックしてプロパティを表示して、今回はいま表示している enebular エディタのフローの `/hello` という HTTP の入り口をつくる設定します。

完了ボタンをクリックしてワークスペースに戻ります。

## template ノードを配置してプロパティ設定

![image](https://i.gyazo.com/5255bc836d7361771ad3d8f74995e5c8.png)

パレットから template ノードを探してワークスペースに配置します。

![image](https://i.gyazo.com/d74f53b7cc594d0d34e6f6a1c3077305.png)

このように http in ノードの隣に配置してワイヤーでつなぎます。

![image](https://i.gyazo.com/cec1c5a2f6502bd8af1b33e26c840bc4.png)

template ノードをダブルクリックしてプロパティをプロパティを表示します。

![image](https://i.gyazo.com/28531568e254337e0a51aff69b7c2150.png)

テンプレートの項目に元々書いてある内容を上書きして `Hello World!` と入力して完了ボタンをクリックします。

## http response ノードを配置する

![image](https://i.gyazo.com/d03b6c8867ffad9aead817cb0043fbab.png)

パレットから http response ノードを探してワークスペースに配置します。

![image](https://i.gyazo.com/77a85016e2623240f3dd9221db04a470.png)

このように template ノードの隣に配置してワイヤーでつなぎます。

![image](https://i.gyazo.com/6abc382d3d9875421b4e5640fc703aa6.png)

デプロイボタンをクリックすると今作ったものが反映されます。

## PC から enebular エディタのフローの URL にアクセスする

この入り口は `enebular エディタのフローの URL` + `/hello` でアクセスできます。

![image](https://i.gyazo.com/bb8451a3c03d9b0ba7b228e41364e924.png)

いま表示している enebular エディタのフローの URL はこちらの i アイコン ![image](https://i.gyazo.com/844f1e2731ba35ff5f170dae3afad53a.png) にマウスを乗せると確認できます。

![image](https://i.gyazo.com/c73da781b8181d4f4682750573264b60.png)

マウスを乗せて確認して、`https://*******************.herokuapp.com/` の部分をクリックしましょう。セッションの残り時間も書いてありますね。

![image](https://i.gyazo.com/08def14e591a3d52c5e7ba4aee67aade.png)

まだ `/hello` にはアクセスしてないので `Cannot GET /` で大丈夫です。

## さらに `/hello` にアクセスしてみる

`先ほどメモしたenebular エディタのフローの URL` に `/hello` を加えて、今回の仕組みにアクセスしてみましょう。

![image](https://i.gyazo.com/93767c7245b176f3d15fdbac509c3f44.png)

アドレスバーに `/hello` を加えて Enter キーを押してアクセスします。

![image](https://i.gyazo.com/99ef30728044d3c1a95c7c049a859626.png)

Hello World! と表示されました！

これで enebular でつくった仕組みが WEB に表示できることが分かり、WEB アプリの入り口となることが体験できました！

## スマートフォンでも見てみましょう

![image](https://i.gyazo.com/e43c8f60ac53d382180a24ea45560926.png)

今回の場合、PC から見てもスマートフォンから見ても同じように見えますが、ここで PC で見ているものを Chrome から QR コードに表示して、みなさんが普段使ってるスマートフォンの QR コード読み取りアプリを利用して スマートフォンのブラウザに表示してみましょう。

![image](https://i.gyazo.com/bcfe1414ed043b88c72abc086224fb2a.png)

ここでみなさんに聞いてみます！みなさん、スマートフォンの QR コード読み取りアプリでスマートフォンのブラウザに表示したことってありますかー？

![image](https://i.gyazo.com/28d68e5b0c12f7b97180729fa674c0e9.png)

`/hello` にアクセスできた Chrome ブラウザタブのアドレスバーの横にある、こちらのアイコンをクリックします。

![image](https://i.gyazo.com/b959d0b62dbccda75df08df84a5bd727.png)

色々な機能が表示されるので QR コードをクリックします。

![image](https://i.gyazo.com/7e334699ec1923afc8541e3101d27019.png)

かわいい QR コードが表示されるので、このままにしておきましょう。

![image](https://i.gyazo.com/cea6b2baf6cccef5823e59d9cee4ab4c.png)

みなさんが普段使ってるスマートフォンの QR コード読み取りアプリを利用して スマートフォンのブラウザに表示してみましょう。

### もし QR コードをスマートフォンで読んだことがない方は

スマートフォンの LINE アプリの QR コード読み取り機能があります。これを利用して スマートフォンのブラウザに表示してみましょう。

![image](https://i.gyazo.com/8f6219d5b0cf3827e144667837bf8c86.png)

スマートフォンの LINE アプリを起動して、トークのリスト画面のこちらのアイコンをクリックしてカメラを起動します。（こちらは Android の LINE アプリの画面です。もしかすると iPhone のアプリ画面では少し違うかもしれないですが、読み替えてみてください。）

![image](https://i.gyazo.com/d765715ded01bef52c019d8e00a83831.png)

カメラが起動したら QR コードの読み取りになっているかを確認して、さきほど QR コードを読み取ってみましょう。

![image](https://i.gyazo.com/46645973dd77cfdcb462584c629d1e8f.jpg)

うまく読み込めると URL の候補が表示されるのでクリックします。

![image](https://i.gyazo.com/096a1d2aa2a0dd4fb43dc48b559cfd20.png)

LINE 内のブラウザで表示されて確認することができます！

## そのほか template ノード例

（まとめ中）

# 質疑応答

![image](https://i.gyazo.com/aba8ccd625e7320883851b71ebd0caf2.png)

ここまでで質問があればどうぞ！

# 次にすすみましょう

左のナビゲーションから「enebular のダッシュボードを動かそう」にすすみましょう。

