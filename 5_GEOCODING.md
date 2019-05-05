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
  accessToken: mapboxgl.accessToken, // Set the access token
  mapboxgl: mapboxgl, // Set the mapbox-gl instance
  language: 'ja'
});

map.addControl(geocoder, 'top-left');
```

