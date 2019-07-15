# study-docker-lamp

# 概要
dockerでlamp環境構築（勉強用）
||version|
|---|---|
|OS|centos7.6.1810|
|php|7.2.15|
|mysql|5.7.25|
|phpmyadmin|4.8.5|

# 立ち上げ方
cd study-docker-lamp
docker-compose up -d

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
