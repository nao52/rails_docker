# DockerでRails環境を構築するためのテストアプリケーション

これは、チーム開発を行うにあたり、開発環境をDockerを用いて共有できるかテストするためのアプリケーションです。

## 使い方

このアプリケーションを動かす場合は、まずはリポジトリを手元にクローンしてください。
その後、Dockerを使った環境構築を行います。

Dockerを使った環境準備(イメージのビルド)
```
$ docker compose build
```

railsサーバーの起動(バックグラウンドでのコンテナの立ち上げとrailsサーバーの起動)
```
$ docker compose up -d
```

コンテナ内に入る(rails・bundlerのコマンドはコンテナ内で実行します)
```
$ docker compose exec web bash
```

### 以下はコンテナ内で実行する

データベースの作成(コンテナ内で実行してください)
```
$ rails db:create
```

テーブルの作成
```
$ rails db:migrate
```

テストデータの作成
```
$ rails db:seed
```

### 以下のURLにアクセスしてください

[アプリケーションが正しく表示されるか確認する](http://localhost:3000/)

### 以下の画面が表示されていれば成功！(ユーザー名は人によって違うかも？)

<img width="1430" alt="スクリーンショット 2023-10-04 15 47 18" src="https://github.com/nao52/rails_docker/assets/76091895/b243284b-2179-4af1-ba35-bbfad9812e94">
