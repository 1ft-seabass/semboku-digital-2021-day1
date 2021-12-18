# enebular のダッシュボードを動かそう

![image](https://i.gyazo.com/2fe8f1e2d461451f6b5212996272c3ee.jpg)

## このページの概要

![image](https://i.gyazo.com/d75c2f6861d40b92a9afd3d1a6cfaee8.png)

enebular でより手軽に WEB アプリのパーツが作れるダッシュボードノードを使ってボタンを押したら Node-RED で値が確認できる仕組みを体験します。

## ダッシュボードノード

![image](https://i.gyazo.com/b028724a2564aecb8641d17e971059cf.png)

引用: [node\-red\-dashboard \(node\) \- Node\-RED](https://flows.nodered.org/node/node-red-dashboard)

ダッシュボードノードは、フォーム入力・テキスト入力・ボタンのようなユーザーから入力を待つような UI パーツをはじめ、折れ線グラフや円グラフのようなデータを可視化するパーツが扱えるノードです。

また、レイアウト機能も優れており直感的に配置することができます。PC やスマートフォンに応じた表示（レスポンシブレイアウト）も対応しています。

![image](https://i.gyazo.com/2f3a06a2af4566361954d4499551ba00.png)

パレットには、このようなノードが揃っています。

もちろん、さきほどの http in + template + http response の仕組みでも HTML や CSS といった WEB 技術を駆使して、イチから画面や機能を作ることも可能ですが、どうしても時間がかかります。

enebular および Node-RED では、このダッシュボードノードを使って WEB アプリにおけるユーザー画面を作っていくことができるので、より素早く作りたいものを作って試すことができます。

早速、試してみましょう。

## 準備から Assets の作成

[前の章](03-01-enebular-hello-world.md) でお伝えした、

- 前回のフローを閉じる
- フローの詳細に戻る
- プロジェクトに戻る

まで進めます。

![image](https://i.gyazo.com/52cf959b332bb1040e3c1cce6634cdeb.png)

右下の + ボタンをクリックすると Asset を作成します。

![image](https://i.gyazo.com/f4094b88ca7ad33e2f16cb7765f2448c.png)

以前の章で学んだ Asset の作成を参考に Flow のタイトル `flow-semboku-dashboard-webapp` にしてフローを作成しましょう。

作成が完了し、Flow の詳細ページに移動します。

## フローエディタを表示する

![image](https://i.gyazo.com/4fa8dd59baa8ea3922b76ff2cc9405d3.png)

Edit ボタンをクリックします。

![image](https://i.gyazo.com/98736f6f6724b9e6caf6faee92380646.png)

左上に Loading がでたら、しばらく待ちます。

## dashboard button ノードを配置して設定する

![image](https://i.gyazo.com/93ee99b774fbe8589031e65a30912fdb.png)

パレットからダッシュボードにボタンを作る dashboard button ノードを探して配置します。

![image](https://i.gyazo.com/c5553a5a37d72d8602ac7e5760d62db1.png)

配置したらダブルクリックしてプロパティを表示します。

![image](https://i.gyazo.com/7ee0689928abf9e8ba3f6ef6a7113502.png)

プロパティを表示したら、Group の 新規に ui_group を追加... となっていることを確認して、鉛筆ボタンをクリックします。

![image](https://i.gyazo.com/d76a121af0e1cfd1d58727061501095a.png)

これで、画面表示時の 1 画面の中で区分けされた1単位「グループ」がデフォルトという名前で仮決定されました。

引き続き進めます。

タブの 新規に ui_tab を追加... となっていることを確認して、鉛筆ボタンをクリックします。

![image](https://i.gyazo.com/868e4f80c8a9e22a61f3de1b5925a7a5.png)

これで、画面表示時の 1 画面分の大きな単位となる「タブ」がホームという名前で仮決定されました。

追加ボタンをクリックして仮決定されていたタブを正式に追加します。

![image](https://i.gyazo.com/e5151d7a59f3f0724c06cedc35648706.png)

グループの設定画面に戻ってくるので、グループも追加ボタンをクリックして仮決定されていたグループを正式に追加します。

![image](https://i.gyazo.com/84ed4ae4d446d7036fa50eca628b3a31.png)

button ノードを編集画面まで戻ってくるので、ボタンが押されたときにどういうデータを出すかを決める Payload 項目を設定します。

![image](https://i.gyazo.com/086cf9257e91a4720bacf07333a54fe6.png)

あいさつのような言葉を入力します。

![image](https://i.gyazo.com/eceb00886b9b41351c647f227f2b39fb.png)

設定できたら完了ボタンをクリックします。

## 今回の dashboard 配置イメージ

プロパティからタブやグループを新規に作ったので、実際にどのように作られたかイメージが湧きづらいかもしれないので、補足します。

![image](https://i.gyazo.com/2b54e9c0dfe904b05d217ce1d38338e5.png)

ダッシュボードのタブやグループの配置については、こちらのサイドバーの Dashboard 管理タブに集まっています。

![image](https://i.gyazo.com/e479886d841a4a0853373768b988267f.png)

このように、配置からホームタブがありタブ内にデフォルトというグループが配置されていることが確認できます。タブやグループを増やしてレイアウトを変更するときは、こちらから行えます。

![image](https://i.gyazo.com/ff5525086b1a60bda9f1732ec950226f.png)

配置イメージはこのような感じです。タブは、その時に表示される画面全体をつかさどるものです。グループはタブの中で、ダッシュボードの各パーツが配置されるときの1つの集まりです。

![image](https://i.gyazo.com/9b4ccd27af5ae758c6b1f3dd604c1341.png)

デフォルトのツリーをクリックして開くと今回の button が配置されていることが分かります。

![image](https://i.gyazo.com/3f160f014fe68fe2c64d9c49abf122ec.png)

この デフォルト の横の編集ボタンをクリックして、このグループのプロパティを見てみましょう。

![image](https://i.gyazo.com/3dfbb3e92f29aa82316139d72a6c6b78.png)

dashboard button ノードの中の設定でも見たグループのプロパティと同じものです。こちらの幅が 6 というのが、グループがタブ内のどれくらいの幅を確保しているかを設定しています。通常 6 で設定されています。

![image](https://i.gyazo.com/4fa747b258943e64e7c176ffece6ac5b.png)

幅の確保はこのようなイメージです。

このように、ダッシュボードはレイアウトの概念をうまく肩代わりしてくれて気を利かして設定してくれるので、サッと作るぶんには、これだけでかなりのレイアウトを構築できます。

ユーザーとのやり取りの入口となるユーザーインターフェースの部分を、自分の発想に応じてすぐ試すことができるので、今後使えるようにしていきましょう！

- 時間があれば、もう少し、ダッシュボード管理の詳細を説明してみる。

## dashboard button ノードのデータを受け取る debug ノードを設定

![image](https://i.gyazo.com/cbdee93cae3a83830f4e79243782b27d.png)

debug ノードをパレットから配置して、このように dashboard button ノードからつなぎます。

こうすることで、dashboard button ノードがクリックされたときに、さきほどの Payload 項目で設定した値が送られて debug ノードで確認できます。

![image](https://i.gyazo.com/6abc382d3d9875421b4e5640fc703aa6.png)

デプロイボタンをクリックすると今作ったものが反映されます。

## ダッシュボードを表示してみる

サイドバーを見てみましょう。

![image](https://i.gyazo.com/901ecccb7326bf64f3971d2a81f9e1d7.png)

このボタンをクリックするとサイドバーで見ることのできるものが表示されるので、Dashboard をクリックしましょう。

![image](https://i.gyazo.com/06ae892c6925a1b2284d76a9d36b632d.png)

Dashboard の情報が表示されました。

![image](https://i.gyazo.com/3706426fa9790e6d23742725330344fd.png)

こちらのボタンをクリックすると、別の Chrome タブでダッシュボードが表示できます。`enebular エディタのフローの URL` + `/ui` という URL です。

![image](https://i.gyazo.com/72447e56c3a104bd40b7929c6bba2b5f.png)

このように、先ほど設定したホームという名前のタブで1画面が構成されていて、デフォルトというグループが真ん中に表示されています。今回の dashboard button ノードは、このタブの中のグループに配置されるよう設定していました。

![image](https://i.gyazo.com/b444b8ece034d7f67b4711973c342593.png)

ボタンをクリックしてみましょう。

![image](https://i.gyazo.com/7c5d346e4981653e3d58076c7c26d203.png)

これでデータが送られたはずなのでエディタの Chrome タブに戻ってみます。

![image](https://i.gyazo.com/a0f8cc607639f114168ed252fc963c62.png)

サイドバーをデバックに戻します。

![image](https://i.gyazo.com/91636e872cdfbe6cf94651804053d24c.png)

すると dashboard button ノードがクリックされたときに、さきほどの Payload 項目で設定した値が送られて debug ノードで確認できます。

## スマートフォンでも見てみましょう

![image](https://i.gyazo.com/e43c8f60ac53d382180a24ea45560926.png)

ぜひ、スマートフォンでも表示して見て、良い感じに表示されるダッシュボードを体験してみましょう。

![image](https://i.gyazo.com/9d543bdd42fd26a58c1ed48b38d5345d.png)

スマートフォンだと、タブとグループのレイアウトブロックがスマートフォンの縦長のレイアウトに合わせて調節しくれます。

## ダッシュボードノードで手軽に画面が作れる

![image](https://i.gyazo.com/b028724a2564aecb8641d17e971059cf.png)

引用: [node\-red\-dashboard \(node\) \- Node\-RED](https://flows.nodered.org/node/node-red-dashboard)

このようにダッシュボードノードで手軽に画面が作れましたね。ぜひ、ほかのダッシュボードノードの部品も試してみましょう。

このあとお伝えする Discover Flow でもダッシュボードノードの利用例が見れます！

# 質疑応答

![image](https://i.gyazo.com/aba8ccd625e7320883851b71ebd0caf2.png)

ここまでで質問があればどうぞ！

# 次にすすみましょう

左のナビゲーションから「LINE Notify にメッセージを送ろう」にすすみましょう。

