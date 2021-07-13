# EC-CUBE 4.0

## インストール

### EC-CUBE 4.0のインストール方法

参考URL [EC-CUBE4 独自プラグイン開発](https://qiita.com/haruna-nagayoshi/items/948b196cf4f5186641e9) の手順に従って、

以下のコマンドでインストールしてください。

```shell
# git configがglobalで core.autocrlf=input になっていることを確認する
git config --global core.autocrlf input 

# 任意のディレクトリにcloneする
cd xxx　

git clone https://github.com/longnguyen1009/eccube4-default.git

# Dockerコンテナを起動
docker-compose up -d --build　

#composer install　=> vendor
docker-compose exec ec-cube composer install 

```

### インストールスクリプトを実行する

FIX 60s error limit

vendor/symfony/process/Process.phpに「60」を600にしてください。

```shell

docker-compose exec ec-cube bin/console eccube:install　
#ec-cube はcompoerのサビースの名前

```

詳しくは開発ドキュメントの [システム要件](https://doc4.ec-cube.net/quickstart_requirement) をご確認ください。

## 結果

* フロント側 　[http://localhost:8085/](http://localhost:8085/)
* 管理画面 　[http://localhost:8085/admin](http://localhost:8085/admin)
* データベース 　[http://localhost:9085/](http://localhost:9085/)

```shell

デフォルトのID/PW　公式サイトのデモサイトと同じ。
ID: admin
PW: password

```

以上です。

