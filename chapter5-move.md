# **第5章　加速度センサー**

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

[![](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/スクリーンショット-2017-05-24-03.03.55.png?resize=474%2C411&ssl=1)](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/スクリーンショット-2017-05-24-03.03.55.png?ssl=1)

### ブロックエディタ

#### てんとう虫

* 運動
* エネジー
* 餓死
* 再生

[![](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/image_thumb-4.png?resize=474%2C365&ssl=1 "image")](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/image-4.png?ssl=1)

#### アブラ虫

* 食べられ
* 再生

[![](https://i2.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/image_thumb-3.png?resize=474%2C365&ssl=1 "image")](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/image-3.png?ssl=1)

#### 再スタート

#### カエル

* 運動
* 食べる

[![](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/image_thumb-5.png?resize=474%2C365&ssl=1 "image")](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/image-5.png?ssl=1)

### リソース

* [frog.png](https://edu2web.com/2017/05/mobile-computing-6-ladybug-chase/#)
* [ladybug.png](https://edu2web.com/2017/05/mobile-computing-6-ladybug-chase/#)
* [deadladybug.png](https://edu2web.com/2017/05/mobile-computing-6-ladybug-chase/#)
* [aphid.png](https://edu2web.com/2017/05/mobile-computing-6-ladybug-chase/#)
* [frog.wav](https://edu2web.com/2017/05/mobile-computing-6-ladybug-chase/#)

#### OrientationSensorがないの対策

OrientationSensorがない場合、AccelerometerSensorで代用可能。下記のコードを変えてください。

[![](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/image_thumb-6.png?resize=474%2C365&ssl=1 "image")](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/05/image-6.png?ssl=1)

