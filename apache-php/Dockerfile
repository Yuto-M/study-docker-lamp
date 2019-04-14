FROM centos:7.4.1708

LABEL  maintainer "miyakawa <miyakaway7@gmail.com>"
RUN yum -y update

# 外部リポジトリ（EPEL, Remi）を追加
RUN yum -y install epel-release
RUN yum -y install http://rpms.remirepo.net/enterprise/remi-release-7.rpm

# apache・phpパッケージを導入
RUN yum -y install httpd
RUN yum -y install --enablerepo=remi,remi-php72 php php-cli php-common php-devel php-fpm php-gd php-mbstring php-mysqlnd php-pdo php-pear php-pecl-apcu php-soap php-xml php-xmlrpc php-zip

RUN yum -y install zip unzip which

# composerインストール
#Composer install
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php -r "if (hash_file('sha384', 'composer-setup.php') === '48e3236262b34d30969dca3c37281b3b4bbe3221bda826ac6a9a62d6444cdb0dcd0615698a5cbe587c3f0fe57a54d8f5') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/bin/composer

# rootユーザーでのcomposer installを許可
ENV COMPOSER_ALLOW_SUPERUSER 1

#composerのhomeディレクトリを変更
ENV COMPOSER_HOME /composer

# 変更後のcomposerパッケージ実行ディレクトリをPATH変数に追加
ENV PATH $PATH:/composer/vendor/bin

# Laravel installerをインストール
RUN composer global require "laravel/installer"

# httpdをforegroundで動かしてコンテナが終了しないようにする
CMD ["/usr/sbin/httpd","-D","FOREGROUND"]

WORKDIR /var/www/html
