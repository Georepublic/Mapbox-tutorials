# オリジナルデータを登録する

いよいよ、自分で用意したデータを登録してみましょう。
[Dataset Editor](https://studio.mapbox.com/datasets/) から、データを登録できます。

Mapbox Studio から登録できるデータには、データセット(dataset) と、 タイルセット(tileset) という形式があります。

データセットからは、Point, Line, Polygon といったデータや属性(property)へアクセスでき、 共にMapbox Studio dataset editor や Datasets API 経由で編集をすることができます。

タイルセットは、ベクター形式の軽量なデータ集合で、高速な描画に最適化されています。読み取り専用で、Mapbox Studio 上からは編集できません。

更に詳細な比較については、[Mapboxのドキュメント](https://docs.mapbox.com/help/troubleshooting/uploads/)を見てください


## データセットを作る

地理情報を含んだデータをアップロードすることで、dataset を作成できます。
[世田谷区GISオープンデータ](http://data-setagaya.opendata.arcgis.com/)から、選んでみましょう。
今回は保育所のデータセットを作ってみます。[保育所データ](http://data-setagaya.opendata.arcgis.com/datasets/%E4%BF%9D%E8%82%B2%E6%89%80)のページから、ダウンロード→スプレッドシートを選択すると、csvファイルをダウンロードできます。
データに含まれる緯度経度情報を指定するために、ダウンロードしたデータを一度テキストエディットで開いて、1行目の X,Y, の部分をLongitude, Latitude, に変更して保存します。

その後、[Mapbox Studio dataset editor](https://studio.mapbox.com/datasets/)から、先ほど作った csv ファイルをアップロードします。アップロードが完了したら、データセットの名前を入力(Hoikusho)して Confirm を押し、編集画面に移動します。

![image](./images/edit-dataset.jpg)

続いて、[幼稚園データ](http://data-setagaya.opendata.arcgis.com/datasets/%E5%B9%BC%E7%A8%9A%E5%9C%92)もダウンロードして、X,Y, を変更した後に、編集画面から import をします。

合わせて、中心点の緯度経度も世田谷区に編集しておきましょう。(139.646,35.626)

