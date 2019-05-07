# ジオコーダーをつける

[前回まで](4_POPUP.md)の続きです。

場所を検索できるように、ジオコーディング機能をつけてみましょう。
ジオコーディング(Geocoding)とは、住所や場所の文字列を緯度経度情報(Geocode)に変換する機能のことを差します。
Geocoder は、Mapbox のプラグインとして提供されています。プラグインを利用できるように、以下の行を、index.html の `</head>` の前に追記します。

```html
<!-- Geocoder plugin -->
<script src='https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-geocoder/v4.1.2/mapbox-gl-geocoder.min.js'></script>
<link rel='stylesheet' href='https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-geocoder/v4.1.2/mapbox-gl-geocoder.css' type='text/css' />
```

次に、サーチボックスをmapに追加するため、以下のコードをJavaScript部分に追加します。

```javascript
// Geocoder Control
var geocoder = new MapboxGeocoder({
  accessToken: mapboxgl.accessToken, // 既に設定してあるアクセストークン
  mapboxgl: mapboxgl, // mapbox-gl のインスタンス
  language: 'ja'
});

map.addControl(geocoder, 'top-left');
```

これで、地図上に検索ボックスがつきました。
検索ボックスに文字を入力してみると候補が表示され、選択するとその場所へ飛ぶことがわかります。

ただし、詳細の住所などを入力しても、検索結果が表示されません。ゼンリンがデータソースとして活用できるようになるまでは、ジオコーディングの精度の悪さは課題の一つです。
 
ジオコーディングの詳細については、[公式ドキュメント](https://docs.mapbox.com/help/how-mapbox-works/geocoding/)を確認してください。

