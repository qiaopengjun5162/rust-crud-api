# rust-crud-api

## Explain this code

这段代码是一个简单的基于TCP的服务器，用于处理与用户相关的HTTP请求，并将其转发到PostgreSQL数据库进行处理。

代码的主要步骤如下：

1. 导入所需的库和模块。
2. 定义了一个名为User的结构体，用于表示用户的id、name和email。
3. 定义了一些常量，包括数据库连接URL、HTTP响应状态码和消息。
4. 主函数main()：
   - 设置数据库连接。
   - 绑定TCP监听器，并打印监听的端口号。
   - 处理客户端请求：循环接受传入的流，对每个流调用handle_client()函数进行处理。
5. handle_client()函数：
   - 读取请求数据到缓冲区。
   - 解析请求并根据请求路径调用相应的处理函数。
   - 将处理结果作为HTTP响应发送回客户端。
6. 处理函数：
   - handle_post_request()：处理POST请求，将用户信息插入数据库。
   - handle_get_request()：处理GET请求，根据用户ID从数据库中获取用户信息。
   - handle_get_all_request()：处理GET请求，从数据库中获取所有用户信息。
   - handle_put_request()：处理PUT请求，更新数据库中的用户信息。
   - handle_delete_request()：处理DELETE请求，从数据库中删除用户信息。
7. set_database()函数：连接到数据库并创建用户表。
8. get_id()函数：从请求路径中获取用户ID。
9. get_user_request_body()函数：从请求体中反序列化用户信息。

总体而言，这段代码实现了一个简单的基于TCP的服务器，用于处理与用户相关的HTTP请求，并将其转发到PostgreSQL数据库进行处理。

## 实操

```shell
cargo new rust-crud-api
cd rust-crud-api/
c
cargo add postgres
cargo add serde_json
cargo add serde
cargo add serde_derive
touch .dockerignore Dockerfile docker-compose.yml
podman ps -a
podman machine init
podman machine start
podman machine rm --force
docker compose up -d db
brew install podman-compose
podman-compose --version
podman-compose --help
podman compose up -d db
podman ps -a
docker exec -it db psql -U postgres
docker compose build
docker compose up rustapp
docker ps -a
docker exec -it db psql -U postgres
```
