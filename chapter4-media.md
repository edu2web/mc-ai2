# **第4章　メディア**

\(Chapter 4. No Texting While Driving\) -- 運転中チャット（Texting）しない

内容はショットメッセージ受信してたら、電話番号とメッセージの音声の読み上げ、自動返信です。

日本では、ショットメッセージあまり普及しないので、このコース実験用スマートフォンは回線契約もないので、実施は困難。

そこで、内容は日本人の間流行っている**Twitterの発信、受信（ 読み上げ？）にアレンジする。**

これをベースに、音声の読み上げ \(発音テスト？\)、翻訳ツールの作成、IoTのセンサー情報の公開も考えられます。

参考ビデオ映像

[https://www.youtube.com/watch?v=5404RBvbvfA](https://www.youtube.com/watch?v=5404RBvbvfA)

### **Twitter とは**

Twitterは、140文字以内の短文「ツイート」の投稿を共有するウェブ上の情報サービスである。

[https://twitter.com/](https://twitter.com/)

Twitterへようこそ. 「いま」起きていることを見つけよう。国内のニュースから身近なできごとまで、みんなの話題がわかる。

#### Twitterアカウント申請

Twitterアプリを作る場合は「Twitter」の「Properties」にある「ConsumerKey」と「ConsumerSecret」が必要になります。これはTwitterアプリの製造者番号のようなので、アプリ単位にTwitterに申請をするともらえます。

番号を取得するためにはTwitterアカウントを持っていてログイン出来ていることが前提条件になります。またアプリ製作者はモバイル登録されていることが条件になっています。**携帯電話の番号**を事前に登録しておきます。

#### Twitter App申請

アプリ登録は下記リンクの「Create New App」からできます。

必要事項を入力して登録が完了すれば「Keys and Access Tokens」から「Consumer Key \(API Key\)」「Consumer Secret \(API Secret\)」がすぐにもらえます。

* ConsumerKey

* ConsumerSecret

Application Management

[https://apps.twitter.com/](https://apps.twitter.com/)

フォームに登録内容を入力してください。

［Name］

自分で考えてアプリの名前を入力。適当でよい。ただし、世界中に唯一無二の名前でないと登録するときに怒られる

［Description］

簡単なアプリの説明を入力。最低でも10文字必要

［Website］

存在するWebサイトのアドレスを入力。お持ちのWebサイトやブログのアドレスがよい。持っていない方は日本App Inventorユーザー会のアドレスである「[http://www.app-inventor.jp」を使ってもらってもよい](http://www.app-inventor.jp」を使ってもらってもよい)

［Callback URL］

Websiteと同じアドレスを入力

［Developer Rules of the Road］

チェックをONに

［CAPTCHA］

画像に表示されている読みにくい文字を入力

申請する際、必須項目は赤い✴️　と表示、しかしCall back URL は必須ではないですが、入れないとアプリで「連携アプリの認証」画面出ないので、必ず入力すること。

上記のフォームを入力し終わったら画面の一番下にある「Create your Twitter application」をクリックして登録を実行してください。

### **Twitter　発信**

![](/assets/twitter1.png)

### ブロックエディタ

ブロックエディタでは以下のイベントを作成します（下記リストは、インデックスになっています）。

1. 起動時にTwitterにログイン
2. Twitterにログインしたらボタンを押せるように
3. 「つぶやく」ボタンを押したらツイートを投稿

App InventorのTwitter機能の多くは非同期になっています。Twitterにログインした後に、認証が通るとお知らせが届くようになっています。それを受け取る部分は別のイベントとして用意する必要があります。

では、上記の機能を1つずつ組み立てていきましょう。

#### 【1】起動時にTwitterにログイン

アプリ起動時に何かさせたい場合に使用するのは「Screen1.Initialize」です。そしてTwitter認証をするためのブロックは「Twitter1.Authorize」です。この2つで「起動時にTwitterにログインする」という動きを表現できます。

ブロックエディタ上では図のようになります。取得元は以下のようになります。この図のようにブロックを組み合わせてください。

ここで使用している「Twitter1.Authorize」を実行すると認証画面が開き、そこにTwitterのログインIDとパスワードを入力すると認証が実施され、アプリからTwitterの各種サービスにアクセス可能になります。

TwitButtonをクリックするとテキストボックスの内容をツイートとして投稿します。同じ内容の投稿して、怒られてしまうことを防ぐため、システム時刻を先頭につけ、クラスの生徒たちの投稿を一覧できるため、ハッシュタグ \#upspress を加えた。

![](/assets/twitter3.png)

#### Appのテスト

Appの初期化する際、Twitterの認証を行う。

利用者のTwitterアカウント情報（Id / Pw）でログインしてください。

![](blob:file:///7d8427f1-7d9b-4e01-8f16-a036d61c2714)

### **Twitter　写真投稿**

### **Twitter 読み上げ？**



