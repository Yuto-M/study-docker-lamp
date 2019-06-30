# やんなきゃいけないこと
## apache起動後
```
docker exec -it apache-php bash
cat /etc/httpd/conf/httpd.conf > /var/www/html/apache.conf
```

## コンテナに入ってlaravelセットアップ
```
laravel new lara-d
```

## apache.conf書き換え

## laravelセットアップ後
```
chmod -R 777 storage
php artisan key:generate
config/app.phpのtimezone, localeを変更
```


virtualhostの設定情報
```
/etc/httpd/conf.d/virtualhosts.conf
```

con.d配下の.conf読み込み
```
# Load config files in the "/etc/httpd/conf.d" directory, if any.
IncludeOptional conf.d/*.conf
```

apache相対パス基点
https://www.adminweb.jp/apache/ini/index5.html

## mysql関連
my.cnfの設定は/etc/mysql/conf.d/配下に置くと良い。
http://dqn.sakusakutto.jp/2015/10/docker_mysqld_tutorial.html
ちなみに、!includedirの!はただの記号らしい
https://teratail.com/questions/11664
ちなみに、!includedirでincludeされる設定ファイルは.cnfが拡張子として設定されている必要があるらしい。
https://dev.mysql.com/doc/refman/5.6/ja/option-files.html
