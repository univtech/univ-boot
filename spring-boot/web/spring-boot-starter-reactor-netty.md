# spring-boot-starter-reactor-netty

```
# 地址
https://spring.io
https://spring.io/projects/spring-boot

https://github.com/spring-projects/spring-boot
https://github.com/spring-projects/spring-boot/issues

git://github.com/spring-projects/spring-boot.git
ssh://git@github.com/spring-projects/spring-boot.git

# 构件
org.springframework.boot:spring-boot-starter-reactor-netty:3.1.3

# 依赖：compile
io.projectreactor.netty:reactor-netty-http:1.1.10
```

## 配置属性

```
server.netty.connection-timeout

Connection timeout of the Netty channel.

server.netty.h2c-max-content-length

Maximum content length of an H2C upgrade request.

0B

server.netty.idle-timeout

Idle timeout of the Netty channel. When not specified, an infinite timeout is used.

server.netty.initial-buffer-size

Initial buffer size for HTTP request decoding.

128B

server.netty.max-initial-line-length

Maximum length that can be decoded for an HTTP request's initial line.

4KB

server.netty.max-keep-alive-requests

Maximum number of requests that can be made per connection. By default, a connection serves unlimited number of requests.

server.netty.validate-headers

Whether to validate headers when decoding requests.

true
```
