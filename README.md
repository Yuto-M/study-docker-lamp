# study-docker-lamp

# 概要
dockerでlamp環境構築（勉強用）

## Goal
- `docker-compose up -d`でlamp環境が作成できるようにする。
    - docker-compose.ymlを書く
        - ~~apacheが起動する~~
        - ~~phpが使えるようにする~~
        - ~~mysqlが起動するようにする~~
        - ~~phpからmysqlに接続可能にする~~
- コンテナを削除してもデータが消えないように永続化する。
    - ~~data volumeを使用して永続化~~
    - ~~data volume conainerを使用して永続化~~
        - ~~data volume containerは不要っぽいので作らないことにした~~
- 永続化したデータのbackup・restoreができるようにする。
    - ホストマシンのディレクトリとマウントしている、data volume をマウントしたコンテナを立ち上げて、そこでtarでbackupを固めてだす（backupの取得）。
    - そのあと、そのbackupを使用してdata volumeを復元する。
- ~~phpMyAdminが使用できるようにする~~
- ~~phpのversionを7系にする~~
- phpの設定ファイルを用意してそれを読み込むようにする
- laravelは別プロジェクトに置いてdocker環境と分離させる
- virtualhostを設定してドメイン名によりDocumentRootを変更する
  - virtualhostの設定をhttpd.confではなく、各virtualhost用のファイルを作成してそこに書いて読み込むようにする。
  - log出力先も各プロジェクト毎のディレクトリ配下に出力されるようにする。

## 参考にした
元ネタ
https://qiita.com/ProjectEuropa/items/5fbb00848cd8d5b57182#dockerfile%E3%81%AE%E8%A8%98%E8%BF%B0

remiやEPELレポジトリの説明  
https://weblabo.oscasierra.net/centos7-php72-install/

remiレポジトリからphpを取得する際のyumコマンドの説明
https://akamist.com/blog/archives/648

composerのhomeディレクトリとは
https://getcomposer.org/doc/03-cli.md#composer-home

volumeに関する公式doc
https://docs.docker.com/compose/compose-file/#volumes

volumeについて色々説明している
https://higechira.hatenablog.com/entry/2017/06/01/000108

version3のdocker-compose.ymlでは、gatewayの指定はなしになった
https://qiita.com/ken992/items/e8fb65238112850ba186
