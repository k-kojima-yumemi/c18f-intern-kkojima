### 概要

Laravelで作成されたWeb APIです。
エンドポイントは`/health-check`しかまだありません。
このAPIをAWS上で実行できるようにしましょう!

### 環境

- PHP 8.1.9
- Laravel 10.32.1
- Docker

### Getting Started

```shell
# docker-compose.yml用の環境変数の設定ファイルを作成する
$ cp .env.example .env

# Laravel用の環境変数の設定ファイルを作成する
$ cp ./src/.env.example ./src/.env

# dockerでApacheとMySQLを起動する
$ docker compose up -d

# 必要なパッケージをインストール
$ docker compose exec app composer install

# APIの実行
$ curl http://localhost:30080/api/health-check
{"message":"OK"}
が返ってきたら成功です

```
