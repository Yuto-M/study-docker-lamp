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
