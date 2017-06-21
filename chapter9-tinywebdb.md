# \*\* 第９章　Web データベース \*\*

TinyWebDB

\(Chapter 10. MakeQuiz and TakeQuiz\)

 Chapter 8 に、TinyDBを使って簡単なメッセージを保存する処理を作成しました。

 Androidでは、ネットワーク経由でサーバーにアクセスするアプリが多数あります。Androidのシステムにネットワーク通信のための機能が備わっており、それを利用して非常に簡単にサーバーとやり取りするアプリを作れるのです。



App Inventorでも、サーバーとやり取りするアプリを作ることができます。これは「TinyWebDB」という部品として用意されています。

TinyWebDBは、TinyDBのWeb版といったものです。タグをつけてメッセージをサーバーに保存したり、サーバーにタグ名を送信してその値を受け取ったりすることができます。ただし、それ以上に複雑なことは、現時点ではできません。ですから、あらかじめTinyWebDBにあわせてサーバー側にプログラムを用意し、そこにアクセスする形で処理を用意しなければいけません。

※TinyWebDBの仕様

では、TinyWebDBは、どのような形でサーバーにアクセスするのでしょうか。データの保管と取得について、その仕様をざっと整理しておきましょう。

○データの送信

```
URL: アドレス/storeavalue
パラメータ: tag=タグ名
&
value=値
```

データをサーバーに送信する場合、送信先となるWebサイトのアドレスの./storeavalueというURLにアクセスをします。送られるタグ名と値は、それぞれ「tag」「value」というパラメータとして送られます。

○データの取得

```
URL: アドレス/getvalue
パラメータ: tag=タグ名
```

サーバーからデータを受け取る場合、送信先となるWebサイトのアドレスの./getvalueというURLにアクセスをします。取得したい値のタグ名が「tag」パラメータで送信されます。

注意しておきたいのは、「サーバーからTinyWebDBが受け取るデータは、JSON形式でなければいけない」という点です。JSONというのは「JavaScript Object Notation」というもので、JavaScriptのオブジェクトを記述するためのフォーマットです。これを利用して、テキストやリストなどを送れるようにしています。

TinyWebDBでは、あらかじめ決められた形式でまとめられたJSONデータを受け取り、それを利用します。また送信先のURLや、送付するパラメータ名なども決まっています。それらに従って、サーバー側に処理用のプログラムを用意しなければいけないのです。

Make Quiz

[![](https://i0.wp.com/sites.google.com/site/jamescarrportfolio/_/rsrc/1468742382861/app-inventor/make-quiz-take-quiz/makequizint.PNG?w=474&ssl=1 "Make Quiz Interface")](https://sites.google.com/site/jamescarrportfolio/app-inventor/make-quiz-take-quiz/makequizint.PNG?attredirects=0)

Take Quiz

[![](https://i0.wp.com/sites.google.com/site/jamescarrportfolio/_/rsrc/1468742382183/app-inventor/make-quiz-take-quiz/takequizint.PNG?w=474&ssl=1 "Take Quiz Interface")](https://sites.google.com/site/jamescarrportfolio/app-inventor/make-quiz-take-quiz/takequizint.PNG?attredirects=0)

Components:

Make Quiz:

[![](https://i2.wp.com/sites.google.com/site/jamescarrportfolio/_/rsrc/1468742382446/app-inventor/make-quiz-take-quiz/MakeQuiz%20Comps.PNG?w=474&ssl=1 "Make Quiz Components")](https://sites.google.com/site/jamescarrportfolio/app-inventor/make-quiz-take-quiz/MakeQuiz%20Comps.PNG?attredirects=0)

Take Quiz:

[![](https://i2.wp.com/sites.google.com/site/jamescarrportfolio/_/rsrc/1468742381880/app-inventor/make-quiz-take-quiz/Take%20Quiz%20Comps.PNG?w=474&ssl=1 "Take Quiz Comps")](https://sites.google.com/site/jamescarrportfolio/app-inventor/make-quiz-take-quiz/Take%20Quiz%20Comps.PNG?attredirects=0)

Blocks:

Make Quiz:

[![](https://i2.wp.com/sites.google.com/site/jamescarrportfolio/_/rsrc/1468742382329/app-inventor/make-quiz-take-quiz/Make%20Quiz.PNG?w=474&ssl=1 "Make Quiz Blocks")](https://sites.google.com/site/jamescarrportfolio/app-inventor/make-quiz-take-quiz/Make%20Quiz.PNG?attredirects=0)

Take Quiz:

[![](https://i2.wp.com/sites.google.com/site/jamescarrportfolio/_/rsrc/1468742384434/app-inventor/make-quiz-take-quiz/take%20quiz%20blocks.PNG?w=474&ssl=1 "Take Quiz Blocks")](https://sites.google.com/site/jamescarrportfolio/app-inventor/make-quiz-take-quiz/take%20quiz%20blocks.PNG?attredirects=0)

### Refer:

* http://www.appinventor.org/MakeQuiz10 – \(English\)
* https://edu2web.github.io/ai2bookcn/chapter10.html – \(Chinese\)



