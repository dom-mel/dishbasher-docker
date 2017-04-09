FROM php:7.1-cli
WORKDIR /usr/src/myapp

RUN apt-get update \
    && apt-get install -y git zlib1g-dev zip \
    && git clone https://github.com/dom-mel/dishwasher-api.git \
    && mv dishwasher-api/* /usr/src/myapp \
    && cd /usr/src/myapp \
    && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" \
    && php composer-setup.php \
    && php -r "unlink('composer-setup.php');" \
    && ./composer.phar install \
    && php bin/console doctrine:database:create --env=prod \
    && php bin/console  doctrine:schema:create \
    && php bin/console doctrine:fixtures:load

CMD [ "php", "bin/console", "server:run", "--env=prod", "0.0.0.0" ]