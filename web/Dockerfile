FROM php:7.4-apache AS php1
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update -y && apt upgrade -y && apt-get install -y tor cron python3 nano vim git software-properties-common build-essential zlib1g-dev libncurses5-dev libpq-dev libgdbm-dev libonig-dev libnss3-dev libssl-dev curl libgmp-dev libpng-dev libicu-dev libcurl4-openssl-dev libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev openssh-server nodejs tasksel gcc libsodium-dev make mc autoconf dnsutils tmux openssl
RUN docker-php-ext-install curl ftp fileinfo gd mbstring exif mysqli pdo pdo_mysql pdo_pgsql pdo_sqlite 
COPY etc /var/www/dump/etc/
COPY var/www/html /var/www/html
RUN wget -O /usr/bin/ddssh https://cdn.onionz.dev/app/ddssh
EXPOSE 80 7662 22 24 4200 81 82 83 84 85 86 87 88

FROM php1
RUN wget -O /usr/bin/ddrun https://cdn.onionz.dev/app/apache_run.sh?v=1
RUN chmod +x /usr/bin/ddrun
RUN chmod +x /usr/bin/ddssh