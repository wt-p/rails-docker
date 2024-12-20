<div id="top"></div>

# 目次

1. [rails-docker プロジェクトについて](#1-rails-docker-プロジェクトについて)
2. [環境](#2-環境)
3. [環境構築](#3-環境構築)

# 1. rails-docker プロジェクトについて

このプロジェクトでは、Docker を使用して簡単に Rails アプリケーション環境を構築できるようになっています。

# 2. 環境

## 使用技術一覧

<!-- シールド一覧 -->
<p style="display: inline">
  <!-- フロントエンドのフレームワーク一覧 -->
  <img src="https://img.shields.io/badge/-Node.js-000000.svg?logo=node.js&style=for-the-badge">
  <!-- バックエンドのフレームワーク一覧 -->
  <img src="https://img.shields.io/badge/-Rails-CC0000.svg?logo=rails&style=for-the-badge">
  <!-- バックエンドの言語一覧 -->
  <img src="https://img.shields.io/badge/-Ruby-CC342D.svg?logo=ruby&style=for-the-badge">
  <!-- ミドルウェア一覧 -->
  <img src="https://img.shields.io/badge/-Postgresql-336791.svg?logo=postgresql&style=for-the-badge">
  <!-- インフラ一覧 -->
  <img src="https://img.shields.io/badge/-Docker-1488C6.svg?logo=docker&style=for-the-badge">
</p>

| 言語・フレームワーク等 | バージョン        |
| ---------------------- | ----------------- |
| Ruby                   | 3.2.2             |
| Rails                  | 7.0.6             |
| PostgreSQL             | 12.0              |
| Docker                 | 27.3.1            |
| Docker Compose         | v2.29.7-desktop.1 |

※事前に Docker と Docker Compose をインストールしておいてください。

# 3. 環境構築

以下の手順を実行することで、このプロジェクトをローカル環境で動作させることができます。

## i. リポジトリをクローン

プロジェクトを作成したいディレクトリに移動し、ターミナルで以下のコマンドを実行してください。

```
% git clone https://github.com/wt-p/rails-docker
```

## ii. DB とテーブルの作成

i の工程で作成された rails-docker ディレクトリに移動してください。<br>
その後、以下のコマンドを実行してデータベースをセットアップします。

```
% docker compose run --rm web rake db:create
% docker compose run --rm web rake db:migrate
```

--rm をつけることで上記を実行した際にできる不要なコンテナを削除できます。

## iii. コンテナの作成と起動

コンテナの作成と起動を行います。<br>
以下を実行してください。

```
% docker compose up -d
```

ここではログ表示がされないように、-d でディタッチモードで起動します。<br>
サービスが正常に起動すると、Rails サーバーが http://localhost:3000 でアクセス可能になります。

## iiii. Rails アプリにアクセス

ブラウザを開き、以下の URL にアクセスしてください。<br>
http://localhost:3000

<p align="right">(<a href="#top">トップへ</a>)</p>
