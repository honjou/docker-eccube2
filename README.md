<p align="center"><img src="https://raw.githubusercontent.com/honjou/docker_practice/images/logo.png"></p>

# EC-CUBE2 ローカル開発環境（Docker）

Docker（docker-compose）でLAMP環境（PHP/Apache/MySQL）を構築し、EC-CUBE2 の新規プロジェクトをお手軽るに構築できます。

## 前提条件

お使いのPCにDockerをインストールしておいてください。

[「Docker for Windows」をインストール](https://laraweb.net/environment/6402/)

## 使い方

```
$ git clone https://github.com/honjou/doker_eccube2.git .
```

以下のページから ec-cube2.17 のソースをダウンロードしてください。

[EC-CUBE 2.17系（公式）](https://github.com/EC-CUBE/ec-cube2)

ダウンロードしたデータは src/eccube2 フォルダに格納してください。

格納したら、以下のコマンドを実行すると、ローカルでプレビューできます。

```
$ git clone https://github.com/honjou/doker_eccube2.git .
$ docker-compose build
$ docker-compose up -d
```

詳細は[こちら](#)

## ディレクトリ構造

```
ec-cube2
　┣ docker（docker本体）
　┣ src（laravel本体）
    ┗ eccube2 ← ※EC-CUBE2.17 のデータを格納
　┣ .gitignore
　┣ docker-compose.yml
　┣ README.md
```

## コンテナ構成

```
　┣ app（laravelを動かすコンテナ）
　　　・Apache:2
　　　・PHP:7.4
　　　・Composer:2.0.9
     ・Node.js:12
　┣ db（MySQLを動かすコンテナ）
　　　・MySQL:5.7
　┣ phpmyadmin（phpMyAdminを動かすコンテナ）
　　　・PHPMyAdmin:5
　┣ mailcatcher（MailCatcherを動かすコンテナ）
```