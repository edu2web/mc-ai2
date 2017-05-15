# **第11章　Web API \(WordPress\)**

**  24. Webと通信  
**

**WordPressは人気のCMSであり、サーバセキュリティ、パフォーマンスチューニング、スケールアップ、クラウド対応など沢山ノウハウが蓄積された。WordPressに API機能を追加して、クライドとして利用する方法を試み。**

**    
**

**AppInventorはAndroidのApp作りに簡単な環境です。WordPressをWebコンテンツを作るに最適な環境。**

**WP-TinyWebDB-APIは、両者の長所を連携し、WordPressをAppInventorのTinyWebDBサービスとして利用するためのAPIを、WordPressのプラグインとして提供したもの。**

**本章は、まずWordPressのダウンロード方法及びインストール手順について簡単なリストし、それからWP-TinyWebDB-APIのインストール、Postman を使ってAPIの動作確認を行う。**

#### **WordPressのインストール環境整備**

**WordPress 日本語版の推奨動作環境**

* [**PHP**](http://www.php.net/)**バージョン 5.6 以上**

* [**MySQL**](http://www.mysql.com/)**バージョン 5.6 以上 または**[**MariaDB**](https://mariadb.org/)**バージョン 10.0 以上**

**古い PHP や MySQL しか利用できないレガシーな環境でも、PHP 5.2.4 以上、かつ MySQL 5.0 以上であれば WordPress は動作しますが、公式サポートは終了しており、サイトがセキュリティの脆弱性にさらされる危険があります。**

**テスト用、自宅サーバー用などにローカル環境を構築する際に参考になるリンクです。ローカルマシン上に PHP、Apache、MySQL の環境設定が必要です。**

**もしホスティング提供者 \(レンタルサーバー\) を使っているなら、すでに WordPress 用に設定されたデータベースや簡単インストール用のツールが用意されているかもしれません。ホスティング提供者 \(レンタルサーバー業者\) のサポートページや管理画面で、手動でインストールする必要があるかどうかよく調べてみて下さい。**

**下記のいずれのケースに推奨動作環境を用意してください。**

* **ローカル環境へのインストール（Windows）**

* **ローカル環境へのインストール（Mac の OS X ）**

* **ローカル環境へのインストール（Linux系列）**

* **ホスティング提供者 \(レンタルサーバー\) へのインストール**

**それに合わせて、WordPress 用データベースとユーザを作成**

**例：**

**データベース名 : wpdb  
ユーザー名 : wpadmin  
パスワード : password  
ホスト名 : localhost**

**上記情報メモして、WordPressのインストール際使う。**

### **WordPressのダウンロード**

**WordPressのダウンロードから行います。次のURLから開始します。**

* [**http://ja.wordpress.org/**](http://ja.wordpress.org/)

### **ファイルの配置**

**ダウンロードしたファイルは圧縮ファイルとなっています。解凍した上で使用するWebサーバへ配置します。配置したファイルはインターネット経由でアクセスできる位置に配置して下さい。WebサーバとしてApacheを使用しているのであればドキュメントルートの直下、または任意のディレクトリを作成して配置して下さい。**

**ダウンロードしたファイルは元々「wordpress」というディレクトリの中にファイルが含まれていましたので、今回はローカルで動作させているApacheのドキュメントルートの下にそのまま解凍して配置しました。**

**今回のように「wordpress」と言うディレクトリの中にWordPressで使用するファイルを格納すると、作成したブログのURLは「**[http://localhost/wordpress/」のような形式となります。](http://localhost/wordpress/」のような形式となります。)

### **WordPressのインストール**

**ブラウザで「**[http://localhost/wordpress/」へアクセスして下さい\(URLはWordPressのファイルを配置したWebサーバのURLやディレクトリに合わせて変更して下さい\)。](http://localhost/wordpress/」へアクセスして下さい%28URLはWordPressのファイルを配置したWebサーバのURLやディレクトリに合わせて変更して下さい%29。)

**この際画面の指示に従って、インストール環境整備で作成したWordPress 用データベースとユーザ名など入力する**

**例：**

**データベース名 : wpdb  
ユーザー名 : wpadmin  
パスワード : password  
ホスト名 : localhost**

**これで WordPress はインストールされたはずです。**

## **WP-TinyWebDB-APIのインストール**

**公式サイトをy利用する**

**1. FTPツールでtinywebdb-api ディレクトリー全体を WordPress の pluginsフォルダーにコピーして下さい\(/wp-content/plugins/\).**

**1. FTP the entire tinywebdb-api directory to your WordPress blog’s plugins folder \(/wp-content/plugins/\).**

**2. 管理パネルの「Plugins」タブ上のpluginを有効化してください。**

**2. Activate the plugin on the “Plugins” tab of the administration panel.**

**    
**

**Postman を使ってAPIの動作確認**

