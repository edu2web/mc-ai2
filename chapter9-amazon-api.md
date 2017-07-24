# **第9章　Amazon API**

\(Chapter 13. Amazon Bookstore\)

### Amazon API

まず、App Inventor専用のAmazon APIを見てください。

[http://aiamazonapi2.appspot.com/](http://aiamazonapi2.appspot.com/)

[![](https://i1.wp.com/edu2web.com/wp-content/uploads/2017/07/image_thumb-2.png?resize=474%2C325&ssl=1 "image")](https://i1.wp.com/edu2web.com/wp-content/uploads/2017/07/image-2.png?ssl=1)

試しに、1449397484入力すると、ISBN番号1449397484の本の書名、単価が返ってくる。

[![](https://i2.wp.com/edu2web.com/wp-content/uploads/2017/07/image_thumb-3.png?resize=474%2C372&ssl=1 "image")](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/07/image-3.png?ssl=1)

デザイン

[![](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/07/image_thumb-4.png?resize=474%2C417&ssl=1 "image")](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/07/image-4.png?ssl=1)

### BarcodeScanner

図書のISBN番号の入力の代わりに、ISBNのバーコードを読み取ることもできる。

[![](https://i2.wp.com/edu2web.com/wp-content/uploads/2017/07/717V2cMCoNL_thumb.jpg?resize=187%2C244&ssl=1 "717V2cMCoNL")](https://i2.wp.com/edu2web.com/wp-content/uploads/2017/07/717V2cMCoNL.jpg?ssl=1)

BarcodeScannerは非表示部品です。この部品を使ってバーコードを撮影します。

撮影はバーコード撮影用の別バーコードを読み取るアプリが起動します。そのためアプリを動かす端末に「ZXing」のようなバーコードを読み取るライブラリが必要です（マーケットから無料でダウンロード可能）。

[    
](https://edu2web.com/wp-content/uploads/2017/07/qr_9781491906842.png)

[![](https://i1.wp.com/edu2web.com/wp-content/uploads/2017/07/image_thumb-5.png?resize=474%2C248&ssl=1 "image")](https://i2.wp.com/edu2web.com/wp-content/uploads/2017/07/image-5.png?ssl=1)

Amazon API検索

このAmazon APIは、TinyWebDBのAPIを利用して、図書の検索を行う。「tag」を送信して、「value」を取得する代わりに、検索ワードを送り、検索結果を受け取り。

[![](https://i2.wp.com/edu2web.com/wp-content/uploads/2017/07/image_thumb-6.png?resize=474%2C622&ssl=1 "image")](https://i1.wp.com/edu2web.com/wp-content/uploads/2017/07/image-6.png?ssl=1)

### テスト

撮影はバーコード撮影用の別画面が起動します。明るい枠の中にある赤い線の上に乗ったバーコードを読み取ります。このプレビューではバーコードに反応して赤い線の上に黄色い丸が出現しています。バーコードのスキャンの際はシャッターを切る必要はありません。このプレビューでも明るい枠内に全てのバーコードが入るようにカメラを動かせば、自動的にスキャンします。スキャンが終わると、赤い線が緑になり、App Inventorのアプリに画面が戻ります。

[![](https://i2.wp.com/edu2web.com/wp-content/uploads/2017/07/isbn_9781491906842_thumb.png?resize=249%2C152&ssl=1 "isbn\_9781491906842")](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/07/isbn_9781491906842.png?ssl=1)[![](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/07/qr_9781491906842_thumb.png?resize=154%2C154&ssl=1 "qr\_9781491906842")](https://i0.wp.com/edu2web.com/wp-content/uploads/2017/07/qr_9781491906842-1.png?ssl=1)

ISBN番号9781491906842の本のバーコード

