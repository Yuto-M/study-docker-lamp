# study-docker-lamp

# 概要
dockerでlamp環境構築（勉強用）

## Goal
- `docker-compose up -d`でlamp環境が作成できるようにする。
    - docker-compose.ymlを書く
- コンテナを削除してもデータが消えないように永続化する。
    - data volumeを使用して永続化
    - data volume conainerを使用して永続化
- 永続化したデータのbackup・restoreができるようにする。
    - ホストマシンのディレクトリとマウントしている、data volume containerをマウントしたコンテナを立ち上げて、そこでtarでbackupを固めてだす（backupの取得）。
    - そのあと、そのbackupを使用してdata volume containerを立ち上げてそのcontainerにマウントする。
- phpMyAdminが使用できるようにする
