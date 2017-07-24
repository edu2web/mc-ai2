# **第10章　Web API \(WordPress TinyWebDB API\)**

**WordPressは人気のCMSであり、サーバセキュリティ、パフォーマンスチューニング、スケールアップ、クラウド対応など沢山ノウハウが蓄積された。WordPressに API機能を追加して、クライドとして利用する方法を試み。**

### WordPressとApp Inventorの連携

App InventorはAndroidのApp作りに簡単な環境である。そのTinyWebDBコンポーネントは、TinyDBのWeb版といったものです。タグをつけてメッセージをサーバーに保存したり、サーバーにタグ名を送信してその値を受け取ったりすることができます。あらかじめTinyWebDBにあわせてサーバー側にプログラムを用意し、そこにアクセスする形で処理を用意しなければいけません。

WordPressは人気のCMSであり、サーバセキュリティ、パフォーマンスチューニング、スケールアップ、クラウド対応など沢山ノウハウが蓄積された。WordPressをWebコンテンツを作るに最適な環境。WordPressサイトは、App InventorのTinyWebDBサービスとして利用できるか？

[![](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/06/image_thumb-5.png?resize=474%2C401&ssl=1 "image")](https://i2.wp.com/edu2web.com/wp-content/uploads/2017/06/image-5.png?ssl=1)

答えはYes.

### **WordPress に TinyWebDB API**

WordPressに API機能を追加して、クライドとして利用する方法を試み。

WP-TinyWebDB-APIは、両者の長所を連携し、WordPressをAppInventorのTinyWebDBサービスとして利用するためのAPIを、WordPressのプラグインとして提供したもの。

本章は、WP-TinyWebDB-APIのインストール、Postman を使ってAPIの動作確認, そして第９章のWebデータベースに応用する検証を行う。

#### 

## **WP-TinyWebDB-APIのインストール**

公式サイトを利用する

1. FTPツールでtinywebdb-api ディレクトリー全体を WordPress の pluginsフォルダーにコピーして下さい\(/wp-content/plugins/\).

2. FTP the entire tinywebdb-api directory to your WordPress blog’s plugins folder \(/wp-content/plugins/\).

3. 管理パネルの「Plugins」タブ上のpluginを有効化してください。

4. Activate the plugin on the “Plugins” tab of the administration panel.**          
   **

### **Postman を使ってAPIの動作確認**

サイトをブラウザーで開くと、普通のWordPressのサイトに見える

[http://tinywebdb.ai2.work/](http://tinywebdb.ai2.work/)

追加したAPI機能をみる。\(これをServiceURLにセットする\)

[http://tinywebdb.ai2.work/api](http://tinywebdb.ai2.work/api)

### データの取得

[http://tinywebdb.ai2.work/api/getvalue/](http://tinywebdb.ai2.work/api/getvalue/)

[http://tinywebdb.ai2.work/api/getvalue/?tag=questionsChenLab](http://tinywebdb.ai2.work/api/getvalue/?tag=questionsChenLab)

[![](https://i2.wp.com/edu2web.com/wp-content/uploads/2017/07/image_thumb.png?resize=474%2C235&ssl=1 "image")](https://i1.wp.com/edu2web.com/wp-content/uploads/2017/07/image.png?ssl=1)

ブラウザから取得したデータは、少々見にくい。PostmanというChrome の拡張を使うと、便利。認証、パラメタ引き渡しもできる。

[![](https://i1.wp.com/edu2web.com/wp-content/uploads/2017/07/image_thumb-1.png?resize=474%2C252&ssl=1 "image")](https://i1.wp.com/edu2web.com/wp-content/uploads/2017/07/image-1.png?ssl=1)

### データの送信

[http://tinywebdb.ai2.work/api/storeavalue/](http://tinywebdb.ai2.work/api/storeavalue/)

### **Webデータベースのアプリで検証**

第9章のアプリから、上記のAPIへアクセスして見た。

問題なく、問題が保存できる。

### [![](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/06/image_thumb-9.png?resize=242%2C484&ssl=1 "image")](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/06/image-9.png?ssl=1)

ブラウザーからも、保存したデータの確認できる。

[![](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/06/image_thumb-8.png?resize=474%2C499&ssl=1 "image")](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/06/image-8.png?ssl=1)

