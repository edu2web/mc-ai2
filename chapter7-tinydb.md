# **第7章　データベース　**

**（TinyDB）**

\(Chapter 7. Android, Where’s My Car?’\)  
ANDROID 、私の車はどこですか

アプリの内容はロケーションセンサ\(LocationSensor\)でケータイの位置を記憶\(TinyDB\)し、別の場所に移動した後に記憶した場所がどの方向にあるかを示すものです。なお、ロケーションセンサはエミュレータでは動作しません。動作の確認はAndroidケータイで行ってください。

[![](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-14.png?resize=242%2C484&ssl=1 "image")](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-14.png?ssl=1)

### データベース

TinyDB : アプリを終了させても残るデ－タを持つことができる部品。デ－タはキ－とバリュ－の対で記憶される.

### デザイン

デザイン画面

[![](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-6.png?resize=474%2C365&ssl=1 "image")](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-6.png?ssl=1)

コンポーネントリストの後半

[![](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-9.png?resize=171%2C484&ssl=1 "image")](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-9.png?ssl=1)

部品の一覧（プロパティ名も変更してください）

| グル－プ | 部品名 | COMPONENT上の部品名 | プロパティ名 | プロパティ値 |
| :--- | :--- | :--- | :--- | :--- |
| － | Screen | Screen1 | Title | 私の車はどこですか？ |
| Basic | Label | CurrentHeaderLabel | FontBold | ON |
|  |  |  | Text | あなたの現在位置 |
| Screen Arrangement | HorizontalArrangement | HorizontalArrangement1 | － | － |
| Screen Arrangement | HorizontalArrangement | HorizontalArrangement2 | － | － |
| Basic | Button | RememberButton | Text | 現在位置を記憶 |
|  |  |  | Enabled | OFF |
| Basic | Label | RememberedHeaderLabel | FontBold | ON |
|  |  |  | Text | 記憶した位置 |
| Screen Arrangement | HorizontalArrangement | HorizontalArrangement3 | － | － |
| Screen Arrangement | HorizontalArrangement | HorizontalArrangement4 | － | － |
| Basic | Button | DirectionsButton | Text | 現在位置から記憶した位置の方向を表示 |
|  |  |  | Enabled | OFF |
| Sensors | LocationSensor | LocationSensor1 | － | － |
| Basic | TinyDB | TinyDB1 | － | － |
| Other Staff | **ActivityStarter** | **ActivityStarter1** | **Action** | **android.intent.action.VIEW** |
|  |  |  | **ActivityClass** | **com.google.android.maps.MapsActivity** |
|  |  |  | **ActivityPackage** | **com.google.android.apps.maps** |
|  |  |  |  | HorizontalArrangement1の中 |
| Basic | Label | CurrentAddressLabel | Text | Address: |
| Basic | Label | CurrentAddressDataLabel | Text | 値は空にしておく |
|  |  |  |  | HorizontalArrangement2の中 |
| Basic | Label | GPSLabel | Text | GPS: |
| Basic | Label | CurrentLatLabel | Text | 0.0 |
| Basic | Label | CommaLabel | Text | ,（カンマ） |
| Basic | Label | CurrentLongLabel | Text | 0.0 |
|  |  |  |  | HorizontalArrangement3の中 |
| Basic | Label | RememberedAddressLabel | Text | Address: |
| Basic | Label | RememberedAddressDataLabel | Text | 空にする |
|  |  |  |  | HorizontalArrangement4の中 |
| Basic | Label | RememberedGPSLabel | Text | GPS: |
| Basic | Label | RememberedLatLabel | Text | 0.0 |
| Basic | Label | Comma2Label | Text | ,（カンマ） |
| Basic | Label | RememberedLongLabel | Text | 0.0 |
|  |  |  |  |  |

### ブロックエディタ

このアプリでは以下の4つのイベントを使用します。

1. 位置情報が更新されたら現在位置の表示を更新
2. 「RememberButton」をクリックしたら現在位置を記憶
3. 「DirectionsButton」をクリックしたら現在位置から記憶した位置の方向を表示
4. アプリ起動時に現在位置を記憶している場合復元し、画面に表示

必要なイベントが分かり、このアプリがどのように動くかの大まかなイメージができたと思います。以下にイベントごとのブロックを組み立てた完成図と使用する部品を表に示しますので、それに倣って組み立てましょう。

#### 【1】現在位置更新時のイベント

位置情報更新時のイベントでは、現在位置を表示するラベルに値を反映し、現在の位置を記憶するボタンを使用可能にします。以下の図5の完成図のように表にある部品を組み立ててください。

[![](https://i2.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-10.png?resize=474%2C127&ssl=1 "image")](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-10.png?ssl=1)

#### 【2】RememberButtonがクリックされたときのイベント

RememberButtonがクリックされたときのイベントでは、記憶する位置情報を表示するためのラベルに現在の位置情報反映し、TinyDB1に同じ内容を記録します。また、位置を記憶したら方向を表示するボタンを使用可能にします。

では、先ほどと同じように部品を組み立ててください。

[![](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-11.png?resize=474%2C244&ssl=1 "image")](https://i2.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-11.png?ssl=1)

#### 【3】DirectionsButtonがクリックされたときのイベント

DIrectionsButtonがクリックされたときのイベントでは、現在の位置情報と記憶した位置情報を使って方向を表示するためのGoogleマップ用のリクエストURIを組み立ててActivityStarterに渡し、別のアプリを起動します。このイベントも先ほどと同じように例に倣って部品を組み立ててください。

[![](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-12.png?resize=474%2C169&ssl=1 "image")](https://i2.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-12.png?ssl=1)

#### 【4】アプリ起動時のイベント

アプリ起動時のイベントでは、TinyDB1に位置を保存していれば画面上の記憶した位置情報を表示するラベルに復元します。例によって、図と一覧表を見て部品を組み立ててください。

これでアプリは完成です。最後に、実際に動かしてみましょう。

[![](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-13.png?resize=474%2C269&ssl=1 "image")](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-13.png?ssl=1)

### センサアプリを実機でテストするには

今回使ったロケーションセンサはエミュレータでは動かないのでAndroid端末の実機で動かします。また、ケーブルを抜いても動かすために今までと違う手順でAndroid端末の実機にインストールします。

ブロックエディタでAndroid端末に接続し、一度アプリを起動します。その後、デザイナ画面の右上にある［Package for Phone］の［Download to Connected Phone］を選ぶと、Android端末の実機にダウンロードされます。

後は普通のアプリのように起動すれば、このように起動します。お好きな場所で「現在位置を記憶する」ボタンを押し、少し移動して「現在位置から記憶した位置の方向を表示」を押しすと、別のアクティビティ（Activity）が開き、現在位置から記憶した位置の方向を表示してくれます。

このとき、ケータイの位置情報を取得する機能をONにしておくことを忘れないでください。位置情報のONの仕方はAndroid端末の［設定］画面の［現在位置とセキュリティ］内の［GPS機能を使用］のチェックボックスを［ON］にすればOKです。

