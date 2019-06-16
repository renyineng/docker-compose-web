# docker-compose-web
Nginx,OpenResty,MySQL,Redis,PHP,Node

# start
Modify the volume fields of the php and openresty services of the docker-compose.yml file
eg. ${HOME}/www:/data/www
cd docker-compose-web && docker-compose up

If it runs in the background  add "&"

If only some containers are started eg.OpenResty && PHP. you can  `docker-compose up openresty php`
