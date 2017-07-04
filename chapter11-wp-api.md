# **第11章　Web API \(WordPress TinyWebDB API\)**

**  24. Webと通信    
**

**WordPressは人気のCMSであり、サーバセキュリティ、パフォーマンスチューニング、スケールアップ、クラウド対応など沢山ノウハウが蓄積された。WordPressに API機能を追加して、クライドとして利用する方法を試み。**

### **     **WordPressとApp Inventorの連携

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

1. FTP the entire tinywebdb-api directory to your WordPress blog’s plugins folder \(/wp-content/plugins/\).

2. 管理パネルの「Plugins」タブ上のpluginを有効化してください。

2. Activate the plugin on the “Plugins” tab of the administration panel.**  
**

### **Postman を使ってAPIの動作確認**







### **Webデータベースのアプリで検証**

これは普通のWordPressのサイトに見える

[http://tinywebdb.ai2.work/](http://tinywebdb.ai2.work/)

追加したAPI機能をみる。\(これをServiceURLにセットする\)

[**http://tinywebdb.ai2.work/api**](http://tinywebdb.ai2.work/api)

### データの取得

[http://tinywebdb.ai2.work/api/getvalue/](http://tinywebdb.ai2.work/api/storeavalue/)

[http://tinywebdb.ai2.work/api/getvalue/?tag=questionsChenLab](http://tinywebdb.ai2.work/api/getvalue/?tag=questionsChenLab)

### データの送信

[http://tinywebdb.ai2.work/api/storeavalue/](http://tinywebdb.ai2.work/api/storeavalue/)

[![](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/06/image_thumb-8.png?resize=474%2C499&ssl=1 "image")](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/06/image-8.png?ssl=1)

