ARG PHP_VERSION
FROM php:7.2-cli

# install wget plugin
RUN apt-get update -y
RUN apt-get install wget -y
# install composer with building-arg version
ENV COMPOSER_VERSION=1.8.0
RUN wget "https://getcomposer.org/download/${COMPOSER_VERSION}/composer.phar" -O /tmp/composer.phar
RUN chmod a+x /tmp/composer.phar
RUN cp /tmp/composer.phar /usr/local/bin/composer.phar
CMD ["echo \"alias composer='/usr/local/bin/composer.phar'\" >> ~/.bashrc"]
CMD ["source ~/.bashrc"]
CMD ["cat ~/.bashrc"]

CMD ["php -S=\"0.0.0.0:9000\" -t=\"/var/www/html\""]
EXPOSE ${PHP_FPM_PORT}