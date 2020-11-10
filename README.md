git clone https://github.com/multitoys/craft.git

cd craft/
cp .env.example .env

docker-compose up -d
docker-compose exec php sh
composer install
php craft setup/security-key
exit
docker-compose down

chmod 777 .env && chmod 777 composer.json && chmod 777 composer.lock && chmod 777 -R config/license.key && chmod 777 -R config/project/ && chmod 777 -R storage/ && chmod 777 -R vendor/ && chmod 777 -R web/cpresources/
docker-compose up -d
docker-compose exec php sh

php craft setup

Which database driver are you using? [mysql,pgsql,?]: mysql
Database server name or IP address: [127.0.0.1] db
Database port: [3306] 3306
Database username: [root] user
Database password: password
Database name: craft_cms
Database table prefix: 
Install Craft now? (yes|no) [yes]:yes

