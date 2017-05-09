# **第4章 Paint Pot**

PaintPotはネコの顔に赤青緑の線を引いたり点をうったりでき、書いたものを消したり、点を打つ大きさを変えたり、背景の写真をカメラで撮ったりできるアプリです。

**          
**[![](http://app.edu2web.com/wp-content/uploads/2017/04/PaintPotPart1PhoneImage.png)](http://app.edu2web.com/wp-content/uploads/2017/04/PaintPotPart1PhoneImage.png)

### 簡略な手順

[http://ai2.appinventor.mit.edu/](http://ai2.appinventor.mit.edu/)　を開いて、gmailで登録してください。

#### デザイン

これがDesignerの画面です。左側のPaletteから、HorizontalArrangement持って来て、

上に3個ボタンを持って来てレイアウトの中にセット！

![](https://lh3.googleusercontent.com/sygRTpMS-NepALhLIxbTrzM5D2K5-GYLXUmxt3MXLt3y9e7pLLO7K_FVLsI9Yr6nxV9tTvJQLSEbkb0zp1z3gj7vKCVmVW9gU3sGDnwRBi7icZKXkZFfsBNty3ZF92MxIQFyvUeA)

左側のPaletteから、Drawing and AnimationからCanvasを1個持って来て、置いたCanvasをクリックしてPropertiesから大きさを変更しましょう。今回は横幅をFill parentに、縦幅を300ピクセルに設定しました。Propertiesからボタンの色やテキストも変更できます。ついでにボタンごとの呼び名もわかりやすいように変えておくといいと思います。Componentsから対象のボタンを選択して、下のRenameから変更できます。

次にCanvasのBackgroundImageを選択します。

![](https://lh5.googleusercontent.com/8KSyk6rQbU81udH-3PzmZWQBTWgUvL1ZPXfsDNJrTy53Ug_z2VVhphpNQCQ0rdQ8wjkKYA04EW68X532baI6ufitaK3OSCULlW6e-sBuMr4LhoWsM2fXoUAZiih_AaOiPBpqnYn6)

LayoutからHorizontalArrangementを1個持って来て、

左からボタンを持って来てレイアウトの中に4個置きます。こんな感じに並べましょう

最後にMediaからCameraを持って来てDesignerでの作業は終了になります。**          
**

![](https://lh4.googleusercontent.com/obUijJ_Hr67a49zYuzNjLNZUz8FXD8yOa0Xl0in7hnUoZbr2ZAFfB7lA2lK-XYAUw-iFA8YuI9pO8g_SRWc7yNyXB8SQ-m1yCvK0c-ONSS7GcPVZioATwJuPEOAPmiht9tCrpWZ8)

#### プログラミング

次はいよいよBlocksでの作業になります。右上のBlocksと書いてあるボタンを押してBlocks編集画面へ移動します。まずはなぞった部分に線を引いていく処理を作ります。左側のCanvasからwhen canvas1 .Draggedというブロックを持ってきます。その中に同じくCanvasから持ってきたcall Canvas1 .DrawLineをセットします。次に始点と終点の座標は下の図のようにセットしてください。これだけで画面に線が引けるようになりました！

次はボタンを押たときに線や点の色を変更できるようにします。対象のボタンのとこからwhenなんとか .ClickBlockを持って来て、Canvasから色をセットするブロックを、色は左のColorsから持ってきましょう。

![](https://lh4.googleusercontent.com/8Pc7gfihKw0IH2wfuYtyMl9U0pXXXtuPyymwkqVOZPIZIp4bCBvX53mL_pbXyGimyjXbZkoMaHSeseXYBJPYgZTTPyA5FEdHVUuhhzYqh2fL6MR_qqExx1dDf-SW3FTBPzTDnbrF)

また、似たような処理はCtrl+C Ctrl+Vでコピペすることが出来ます。

![](http://cdn-ak.f.st-hatena.com/images/fotolife/s/shunXnegi/20141226/20141226174814.png "f:id:shunXnegi:20141226174814p:plain")

次にタッチしたところに点を打てるようにします。…って言ってもやることはさっきとほとんど一緒です。こんな感じ。点の大きさはMathのとこから数字を持って来て、とりあえず5をセットしました。**          
**

![](https://lh4.googleusercontent.com/KuTyp43SJA8P_mua8KDYK3k056YK_gBJbe--3kDoaG39DyWrJCfrGyqR1Dxf_C2FAKJ1GZjFHmXynJPvdafRZjuO7Hsk54NVuZmZyJLsf20Lj9GMh2qNLsvjXU1JA1-S1tAI8f7_)

最後にカメラを使えるようにしましょう。といってもMIT AI2ではカメラ画面をそのまま使えるわけではなく、端末のカメラアプリを起動して、戻り値としてカメラの画像を受け取ることになります。Cameraからcall Camera1.TakePictureを持って来て、カメラで写真をとったらCanvasの背景に設定するようにします。

![](/assets/takepic.png)

これでPaintPotは完成です！

