# **第7章　位置情報**

\(Chapter 6. Map Tour\)

**（Walking Tour）**

今回はTokyo Map Tourというアプリを作ります。

予め登録してある３つの場所をセレクトボタンから選択すると、その場所のマップやストリートビューが表示される、というものです。

Androidでは、あるアプリから別のアプリを起動して、それに処理を渡したり、別のアプリでの実行結果を受け取ったりすることが比較的簡単にできるのです。  
Tokyo Map Tourでは、Android端末に用意されているGoogle Mapのアプリを利用します。

### **1.Map Tour**

東京の観光地の地図を表示するアプリです。

[![](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-5.png?resize=242%2C484&ssl=1 "image")](https://i2.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-5.png?ssl=1)

[  
](https://edu2web.com/wordpress/wp-content/uploads/2017/06/image-1.png)

\[Choose Destination\]のボタンを押すと、東京の観光地のリストが表示されます。

[![](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-1.png?resize=242%2C484&ssl=1 "image")](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-2.png?ssl=1)

* Tokyo Tower \(東京タワー\)
* Imperial Palace（「皇居」二重橋）
* Sensoji Temple（浅草寺）

リストの中から、行きたい場所を選択すると、

[![](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-2.png?resize=242%2C484&ssl=1 "image")](https://i2.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-3.png?ssl=1)

地図が表示されます。

では、チュートリアルに従って、作ってみます。

#### Designer

まずは、「Designer」ですね。

[![](https://i2.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-3.png?resize=474%2C402&ssl=1 "image")](https://i0.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-1.png?ssl=1)



使用するコンポーネントは、Image、ListPicker、ActiveStarterです。

_Table 6-1. Components for the Paris Map Tour_

| 部品 | PALETTE | 名前 | 用途 |
| :--- | :--- | :--- | :--- |
| Image | User Interface | Image1 | 東京画像 |
| Label | User Interface | Label1 | Androidで東京発見を表示 |
| ListPicker | User Interface | ListPicker1 | 目的地リスト |
| ActivityStarter | Connectivity | ActivityStarter1 | 地図アプリを開く |

Imageに、最初の画面で表示する地図の画像を設定します。

[https://maps.googleapis.com/maps/api/staticmap?center=35.6585805,%20139.7432442%20&zoom=15&size=300×300&maptype=roadmap&markers=color:blue%7Clabel:T%7C35.6585805,%20139.7432442](https://maps.googleapis.com/maps/api/staticmap?center=35.6585805,%20139.7432442%20&zoom=15&size=300x300&maptype=roadmap&markers=color:blue%7Clabel:T%7C35.6585805,%20139.7432442)

ListPickerは、テキストデータのリストから一つのデータを選択するためのコンポーネントです。  
観光地のリストを入れておくためのものです。  
ActiveStarterは、アプリ内から別のアプリを起動するためのコンポーネントです。  
ここでは、Google Mapを起動するように設定しています。

_Table 6-2. ActivityStarter properties for launching Google Maps_

| 属性 | 值 |
| :--- | :--- |
| Action | android.intent.action.VIEW |
| ActivityClass | com.google.android.maps.MapsActivity |
| ActivityPackage | com.google.android.apps.maps |

#### Blocks Editor

続いて、「Blocks Editor」

destinationsというリストを用意して、観光地の名称を入れておきます。

![](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/mt6-2.png?w=474&ssl=1)

_Figure 6-2. Creating a list is easy in App Inventor_  
Screen1.Initializeは、スクリーンが初期化されるときに呼ばれるブロックでしたね。

![](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/mt6-3.png?w=474&ssl=1)

_Figure 6-3. Put anything you want to happen when the app starts in a Screen1.Initialize event handler_  
ListPickerの要素として、destinationsリストを設定します。  
そして、ListPickerが押されたときの処理。  
geo:0,0?q= の文字列の後に、選択された観光地の名称が連結されます。  
別のアプリ（Google Map）を起動したとき、この文字列が渡されます。

![](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/mt6-4.png?w=474&ssl=1)

_Figure 6-4. Setting the DataURI to launch the selected map_

「Blocks Editor」はこれだけです。

[![](https://i2.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image_thumb-4.png?resize=474%2C401&ssl=1 "image")](https://i1.wp.com/edu2web.com/wordpress/wp-content/uploads/2017/06/image-4.png?ssl=1)

検索して、地図が表示するのは、Google Mapの処理です。  
q= の後に、検索したい文字列をくっつけていたのですね。

