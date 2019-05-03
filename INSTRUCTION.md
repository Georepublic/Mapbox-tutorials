# 1. Mapbox のアカウントを取得する

https://account.mapbox.com/auth/signup/ からサインアップをする

# 2. Github のアカウントを取得する

https://github.com/join?source=header-home からサインアップする

# 3. 早速地図を表示してみる

## Github に、コードを掲載する準備をする

https://github.com/new より、新たに リポジトリ(repository) を作成する

リポジトリ名（repository name）を mb-turorials として、あとはデフォルトのままで OK

[こちら](https://qiita.com/elu_jaune/items/eb354558d0dc39add152) を参考に、先程作ったリポジトリをローカル環境にclone(複製)する

## index.html を作る

Ctrl(CMD) + N を押し、新規ファイルを作成、index.html という名前で保存する。

## 最初のコードを書いてみる

まずはhtmlファイルを書いて公開してみましょう。先ほどの index.html に下記の内容をコピペして、github にPushしてみます

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <h1>すごい地図</h1>
  </body>
</html>
```

