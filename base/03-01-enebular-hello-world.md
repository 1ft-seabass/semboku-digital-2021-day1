# enebular から WEB に Hello World しよう

![image](https://i.gyazo.com/2fe8f1e2d461451f6b5212996272c3ee.jpg)

## このページの概要

enebular および Node-RED の操作がつかめてきたところで、enebular から WEB に Hello World してみます。

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

## enebular エディタのフローの URL にアクセスする

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

## そのほか template ノード例

（まとめ中）

# 質疑応答

![image](https://i.gyazo.com/aba8ccd625e7320883851b71ebd0caf2.png)

ここまでで質問があればどうぞ！

# 次にすすみましょう

左のナビゲーションから「enebular のダッシュボードを動かそう」にすすみましょう。

