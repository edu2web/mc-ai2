# **第6章　センサー\(1\) 加速度センサー**

\(chapter 5. Ladybug Chase\)

てんとう虫の冒険

[![](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/Ladybug1.jpg?resize=244%2C392&ssl=1)](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/Ladybug1.jpg?ssl=1)

スマホの傾きでてんとう虫をコントロール。

てんとう虫は、アブラ虫を食べて、エネルギーを蓄え。カエルに食べられたらおしまい。

| コンポーネント | パレット | 命名 | 用途 |
| :--- | :--- | :--- | :--- |
| Canvas | Drawing and Amination | FieldCanvas | 運動場 |
| ImageSprite | Drawing and Amination | Ladybug | てんとう虫 |
| OrientationSensor | Sensor | OrientationSensor1 | スマホの傾きでてんとう虫をコントロール |
| Clock | User Interface | Clock1 | 向き変更 |
| ImageSprite | Drawing and Amination | Aphid | アブラ虫（餌） |
| ImageSprite | Drawing and Amination | Frog | カエル（敵） |
| Canvas | Drawing and Amination | EnergyCanvas | てんとう虫のエネルギー |
| Button | User Interface | RestartButton | 再スタート |
| Sound | Media | Sound1 | 食べられた |

### デザイナー画面

まずは、新しいプロジェクトを作りましょう。名前は、「Ladybug」としました。

[![](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88-2017-05-24-03.03.55.png?resize=474%2C411&ssl=1)](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88-2017-05-24-03.03.55.png?ssl=1)

### ブロックエディタ

#### てんとう虫

* 運動
* エネジー
* 餓死
* 再生

#### アブラ虫

* 食べられ
* 再生

#### 再スタート

#### カエル

* 運動
* 食べる

### リソース

* [frog.png](http://app.edu2web.com/ai2cn/files/2015/11/frog.png)
* [ladybug.png](http://app.edu2web.com/ai2cn/files/2015/11/ladybug.png)
* [deadladybug.png](http://app.edu2web.com/ai2cn/files/2015/11/deadladybug.png)
* [aphid.png](http://app.edu2web.com/ai2cn/files/2015/11/aphid.png)
* [frog.wav](http://web.17coding.net/download/5/frog.wav)





