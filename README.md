# study-docker-lamp

# 概要
dockerでlamp環境構築（勉強用）

## Goal
- `docker-compose up -d`でlamp環境が作成できるようにする。
    - docker-compose.ymlを書く
        - ~~apacheが起動する~~
        - ~~phpが使えるようにする~~
        - mysqlが起動するようにする
        - phpからmysqlに接続可能にする
- コンテナを削除してもデータが消えないように永続化する。
    - data volumeを使用して永続化
    - data volume conainerを使用して永続化
- 永続化したデータのbackup・restoreができるようにする。
    - ホストマシンのディレクトリとマウントしている、data volume containerをマウントしたコンテナを立ち上げて、そこでtarでbackupを固めてだす（backupの取得）。
    - そのあと、そのbackupを使用してdata volume containerを立ち上げてそのcontainerにマウントする。
- phpMyAdminが使用できるようにする
- phpのversionを7系にする


## 参考にした
元ネタ
https://qiita.com/ProjectEuropa/items/5fbb00848cd8d5b57182#dockerfile%E3%81%AE%E8%A8%98%E8%BF%B0
