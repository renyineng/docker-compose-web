###安装protobuf

下载releases 版本 之后编译 安装
php 用户 www-data
### 安装php 的grpc和protobuf扩展

### 编写proto文件

### 生成php请求参数类  php_out  和grpc客户端调用代码 grpc_out 指定

```/usr/local/protobuf/bin/protoc --proto_path=/data/grpc/grpc/examples/protos   --php_out=./   --grpc_out=./   --plugin=protoc-gen-grpc=/data/grpc/grpc_php_plugin   /data/grpc/grpc/examples/protos/helloworld.proto```

cd /data/grpc/learn_protos/users
/usr/local/protobuf/bin/protoc --go_out=plugins=grpc:/data/go/grpc/vendor/users users.proto

protoc  --php_out=/data/grpc/laravel_learn/app/Services/Grpc   --grpc_out=/data/grpc/laravel_learn/app/Services   --plugin=protoc-gen-grpc=/data/grpc/grpc_php_plugin  users.proto

```docker exec -it php /usr/local/protobuf/bin/protoc --proto_path=/data/grpc/laravel_learn/app/Services/Grpc/Lib/Protos   --php_out=./app/Services/Grpc/Lib   --grpc_out=./app/Services/Grpc/Lib   --plugin=protoc-gen-grpc=/usr/bin/grpc_php_plugin   /app/Services/Grpc/Lib/Protos/helloworld.proto```