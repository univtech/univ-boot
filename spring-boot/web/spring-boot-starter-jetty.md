# spring-boot-starter-jetty

```
# 地址
https://spring.io
https://spring.io/projects/spring-boot

https://github.com/spring-projects/spring-boot
https://github.com/spring-projects/spring-boot/issues

git://github.com/spring-projects/spring-boot.git
ssh://git@github.com/spring-projects/spring-boot.git

# 构件
org.springframework.boot:spring-boot-starter-jetty:3.1.3

# 依赖：compile
jakarta.servlet:jakarta.servlet-api:6.0.0
jakarta.websocket:jakarta.websocket-api:2.1.1
jakarta.websocket:jakarta.websocket-client-api:2.1.1
org.apache.tomcat.embed:tomcat-embed-el:10.1.12
org.eclipse.jetty:jetty-servlets:11.0.15
org.eclipse.jetty:jetty-webapp:11.0.15
org.eclipse.jetty.websocket:websocket-jakarta-server:11.0.15
org.eclipse.jetty.websocket:websocket-jetty-server:11.0.15
```

## 配置属性

```
server.jetty.accesslog.append

Append to log.

false

server.jetty.accesslog.custom-format

Custom log format, see org.eclipse.jetty.server.CustomRequestLog. If defined, overrides the "format" configuration key.

server.jetty.accesslog.enabled

Enable access log.

false

server.jetty.accesslog.file-date-format

Date format to place in log file name.

server.jetty.accesslog.filename

Log filename. If not specified, logs redirect to "System.err".

server.jetty.accesslog.format

Log format.

ncsa

server.jetty.accesslog.ignore-paths

Request paths that should not be logged.

server.jetty.accesslog.retention-period

Number of days before rotated log files are deleted.

31

server.jetty.connection-idle-timeout

Time that the connection can be idle before it is closed.

server.jetty.max-http-form-post-size

Maximum size of the form content in any HTTP post request.

200000B

server.jetty.max-http-response-header-size

Maximum size of the HTTP response header.

8KB

server.jetty.threads.acceptors

Number of acceptor threads to use. When the value is -1, the default, the number of acceptors is derived from the operating environment.

-1

server.jetty.threads.idle-timeout

Maximum thread idle time.

60000ms

server.jetty.threads.max

Maximum number of threads.

200

server.jetty.threads.max-queue-capacity

Maximum capacity of the thread pool's backing queue. A default is computed based on the threading configuration.

server.jetty.threads.min

Minimum number of threads.

8

server.jetty.threads.selectors

Number of selector threads to use. When the value is -1, the default, the number of selectors is derived from the operating environment.

-1
```
