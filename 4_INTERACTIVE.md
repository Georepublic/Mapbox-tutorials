# インタラクティブな機能をつける

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
    .setLngLat(feature.geometry.coordinates)
    .addTo(map);
});
```