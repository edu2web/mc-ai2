# **第4章　アニメーション\(Mole Mash\)**

### ![](/assets/molemash.png)

表3- 1 “もぐら叩き”アプリ中のコンポーネント一覧

| コンポーネント | パレット | 命名 | 用途 |
| :--- | :--- | :--- | :--- |
| Canvas | Drawing and Animation | Canvas1 | ImageSpriteのコンテナ |
| ImageSprite | Drawing and Animation | Mole | タッチ目标 |
| Button | User Interface | ResetButton | スコアリセット |
| Clock | Sensors | Clock1 | 移動速度 |
| Sound | Media | Sound1 | 的中された際振動 |
| Label | User Interface | HitsLabel | 的中と表示 |
| Label | User Interface | HitsCountLabel | 的中数の表示 |
| HorizontalArrangement | Layout | HorizontalArrangement1 | HitsLabelとHitsCountLabel置き場 |
| Label | User Interface | MissesLabel | 失敗と表示 |
| Label | User Interface | MissesCountLabel | 失敗回数 |
| HorizontalArrangement | Layout | HorizontalArrangement2 | MissesLabelとMissesCountLabel置き場 |

### デザイナー画面

まずは、新しいプロジェクトを作りましょう。名前は、「mole」としました。

「Screen1」ができております。さっそく「Screen1」のプロパティから変更します。

* Title 　　　　　　　「もぐらたたき」「アプリの名前になります。」
* ScreenOrientation   「Portrait」「縦長固定のアプリにします。」
* Scrollable 　　　　   チェックをはずす。「スクロールするような状況になっても、画面にスクロールバーが表示されず、画面がスクロールしなくなります。

というわけで、ここに置くコンポーネントのHeightのFillParentがきちんと効くようになります。

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0520-1jpg.jpg?d=a1 "0520-1jpg.jpg")

### スコア表示部分を作成

スコア表示部を作ります。

「LayOut」内の「HorizontalArrangement」を置き、その中に、Labelを2つ入れます。

こんな感じ↓

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0521-1.JPG?d=a1 "0521-1.JPG")

後で、ブロックエディタでプログラミングするときに、分からなくならないように「Components」を「Rename」します。

* 「HorizontalArrangement」　→Rename→　「ScoreArrangement」
* 「Label1」　→Rename→　「ScoreTitle」（プロパティのTextを「Score:」に変更する。）
* 「Label2」　→Rename→　「ScoreLabel」（プロパティのTextを「0」に変更する。）

これは、点数を表示させるラベルとなります。

見た目はこうなります。↓

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0521-2.JPG?d=a1 "0521-2.JPG")

### デザイナー画面を完成させます。

1. 「Button」を１つ配置します。「Button1」　→Rename→　「RestartButton」（プロパティのTextを「Restart」にする。
2. 「Canvas1」を配置します。（プロパティWidth:  Fillparent, Height: Fillparent）
3. 「Canvas1」の中に「ImageSprite」を一つ入れます。「ImageSprite1」　→Rename→　「MoleImage1」（プロパティのPictureに「mole.png」を設定し、もぐらを表示します。）![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/mole.png?d=a0 "mole.png")\(mole.png\), 「MoleImage1」の配置は、Canvas内であれば、どこでもかまいません。好きなところにおいてください。
4. 「Clock1」を配置します。Non-visible Componentとして、下に配置されます。（プロパティのTimerIntervalを500に設定します。）
5. 「Sound1」を配置します。これも、Non-visible Componentとして、下に配置されます。（プロパティの変更はなし。） 

これらが完成するとこうなります。↓

![](/assets/mole1.png)

### モグラたたきのブロックエディタその１

「Blocks」のボタンを押し、ブロックエディタを表示します。

まずは、点数を表示するための変数「Score」を設置します。初期値は「０」としておきます。

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0522-1.JPG?d=a0 "0522-1.JPG")

次は、モグラをランダムに表示させるブロックを作ります。左側にあるBlocksの「Clock1」をクリックし、「When Clock1.Timer」ブロックをドラッグします。

これです。↓

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0522-2.JPG?d=a0 "0522-2.JPG")

これは、「Clock1」のTimerIntervalで指定した時間ごとにイベントを発生するためのブロックです。プロパティで500 msと設定したので、0.5秒ごとにこのブロック内のイベントを発生させます。0.5秒ごとにモグラのを表示させるようにします。

モグラを表示させるのは「MoleImage1」をクリックし、「call MoleImage1.MoveTo」をはめ込みます。このブロックは、「x」と「y」に指定した場所に「モグラの図」を表示します。

「MoveTo」となっているブロックなので、その位置にアニメーションしながら動いていくのかと思いがちですが、「x」「y」の座標の位置までジャンプしていくイメージです。動いている様子は、エミュレートして見て下さい。モグラたたきっぽくなっています。

ここまでだとこうなります。↓

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0522-3.JPG?d=a1 "0522-3.JPG")

最後に「x」と「y」の部分に入れるものは、ランダムで表示させるブロック「random integer　from ① to ②」のブロックを使います。

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0522-5.jpg?d=a0 "0522-5.jpg")

「x」の①から②の範囲は、下の図を参考に考えて下さい。①は「０」、②は、「Canvas1.width - MoleImage1.Width」となります。

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0522-4.jpg?d=a0 "0522-4.jpg")

ということで、ここを完成するとこうなります。↓

![](/assets/import.png)

### モグラたたきのブロックエディタその２

「when MoleImage1.Touched」のブロックを使います。

これです。↓

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0523-1.JPG?d=a0 "0523-1.JPG")

カンバス内の「MoleImage1」にタッチしたときの処理を決めるブロックです。

この中に入れるブロックは、次のものになります。

１，変数「Score」の値を１増やす。

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0523-2.JPG?d=a1 "0523-2.JPG")

２．変数「Score」の値を「ScoreLabel」に表示する。

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0523-3.JPG?d=a1 "0523-3.JPG")

３．0.1 秒間\(100 ms\)スマートフォンを振動させる。

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0523-4.JPG?d=a1 "0523-4.JPG")

これらを組み合わせて完成させます。

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0523-5.JPG?d=a2 "0523-5.JPG")

### モグラたたきのブロックエディタその３

「Restart」ボタンを動かすブロックです。今回の「Restart」ボタンは、ただ、点数を「０」にもどすだけです。

ブロックエディタで、「RestartButton」ボタンをクリックし、「when RestartButton.click」をドラッグします。

これです。↓

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0524-1.JPG?d=a1 "0524-1.JPG")

中は、こんなブロックです。

１．変数「Score」を「0」にします。

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0524-2.JPG?d=a1 "0524-2.JPG")

２．変数「Score」の値を「ScoreLabel」に表示する。

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0523-3.JPG?d=a1 "0523-3.JPG")

（これは、「モグラたたきのブロックエディタその２」の時に作ったブロックと全く同じものなので、それをクリックし、「Ctrl+C」キーを押し、「Ctrl+V」キーを押す。つまりコピーアンドペーストが使用できます。１．の変数もコピー＆ペースとしてから、数値の部分を変えた方が楽です。）

全部一緒にするとこんな感じです。↓

![](http://netandapri.up.n.seesaa.net/netandapri/mole_mash/0524-3.JPG?d=a0 "0524-3.JPG")

MITでのサンプルはここで終わりです。ここから先は、自分で工夫してみます。

1. 応用例１：もぐらを３匹にしてみよう。
2. 応用例２：もぐらを叩いたら音が出るようにしてみよう。
3. 応用例３：猫を１匹足してみよう。
4. 応用例４：「Restart」ボタンを、「Start」ボタンに変更。
5. 応用例５：制限時間を３０秒に設定。



