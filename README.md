### docker-compose安装
mac 和windows 已经自带无需安装
linux下安装方法如下：
curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

参考文档 https://docs.docker.com/compose/install/


### docker-compose-web
Nginx,OpenResty,MySQL,Redis,PHP,Node

### start
Modify the volume fields of the php and openresty services of the docker-compose.yml file
eg. ${HOME}/www:/data/www
cd docker-compose-web && docker-compose up

If it runs in the background  add "&"

If only some containers are started eg.OpenResty && PHP. you can  `docker-compose up openresty php`
