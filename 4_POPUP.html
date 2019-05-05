# ポップアップ機能をつける

ユーザーの操作に応じた動作をつけてみましょう。Mapbox GL JS を活用することで、様々な機能を地図上に付加することができます。

## ピンをクリックしたらポップアップに内容を表示する

地図を使った場合によくあるユースケースです。[前回まで](3_DATASET.md)で作成した、Hoikusho データセットを使って、地図上の保育園や幼稚園をクリックしたらポップアップで名前などの詳細を表示するようにしてみましょう。

アイコンをクリックした時にポップアップを表示するには、以下の3つの要素を加える必要があります。

* `queryRenderedFeatures`: この Mapbox GL JS メソッドを使うと、指定したレイヤーにある全てのポイントおよびプロパティのリストを取得することができます。
* `mapboxgl.Popup`: このメソッドはプロパティの情報を含んだポップアップを作成することができます。
* イベントリスナー: ユーザがアイコンをクリックした時にのみポップアップを行うように、クリックイベントをハンドリングします。

index.html を再度開き、以下のコードを`</script>`の前に追加します。

```javascript
// Popup event
map.on('click', function(e) {
  var features = map.queryRenderedFeatures(e.point, {
    layers: ['hoikusho'] // 前回作成した Hoikusho のタイルセットを表示しているレイヤーの名前を使います。
  });

  if (!features.length) {
    return;
  }

  var feature = features[0];

  var popup = new mapboxgl.Popup({ offset: [0, -15] })
    .setLngLat(feature.geometry.coordinates)
    .setHTML('<h3>' + feature.properties.SAFIELD000 + '</h3><p>' + feature.properties.SAFIELD002 + '<br/>' + feature.properties.SAFIELD003 + '</p>')
    .addTo(map);
});
```

これを保存し、ブラウザで開いたのちに、地図上のアイコンをクリックしてみてください。ポップアップが表示されると思います。

![image](images/popup.jpg)

コードについて解説をしていきます。

```script
map.on('click', function(e) {
```
マップがクリックされた際に、以下のコードが実行されるという意味です。

```javascript
  var features = map.queryRenderedFeatures(e.point, {
    layers: ['hoikusho'] // 前回作成した Hoikusho のタイルセットを表示しているレイヤーの名前を使います。
  });
```
この行では、Mapbos Studio の左側のレイヤーリストの中の、hoikusho レイヤーから `e.point` (クリックした場所) の情報のみを取り出しています。

```javascript
  if (!features.length) {
    return;
  }
```
クリックした場所に、Hoikusho レイヤーの情報がなければ何もせずに終わります。

```javascript
  var feature = features[0];
```
最初のデータを取得します

```javascript
  var popup = new mapboxgl.Popup({ offset: [0, -15] })
    .setLngLat(feature.geometry.coordinates)
    .setHTML('<h3>' + feature.properties.SAFIELD000 + '</h3><p>' + feature.properties.SAFIELD002 + '<br/>' + feature.properties.SAFIELD003 + '</p>')
    .addTo(map);
```
mapboxgl.Popup という関数を呼び出し、緯度経度やHTMLを設定し、map に追加しています。
`feature.geometry.coordinates`はデータの緯度経度で、`feature.propertries` には、データのプロパティが含まれています。
データにどんなプロパティが存在しているのかは、`Dataset Editor` から参照できます。
保育所データの場合、SAFIELD000 が施設名、 SAFIELD002 が施設の分類、 SAFIELD003 が住所になっています。

