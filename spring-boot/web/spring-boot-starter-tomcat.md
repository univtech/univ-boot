# spring-boot-starter-tomcat

```
# 地址
https://spring.io
https://spring.io/projects/spring-boot

https://github.com/spring-projects/spring-boot
https://github.com/spring-projects/spring-boot/issues

git://github.com/spring-projects/spring-boot.git
ssh://git@github.com/spring-projects/spring-boot.git

# 构件
org.springframework.boot:spring-boot-starter-tomcat:3.1.3

# 依赖：compile
jakarta.annotation:jakarta.annotation-api:2.1.1
org.apache.tomcat.embed:tomcat-embed-core:10.1.12
org.apache.tomcat.embed:tomcat-embed-el:10.1.12
org.apache.tomcat.embed:tomcat-embed-websocket:10.1.12
```

## 配置属性

```
server.tomcat.accept-count

Maximum queue length for incoming connection requests when all possible request processing threads are in use.

100

server.tomcat.accesslog.buffered

Whether to buffer output such that it is flushed only periodically.

true

server.tomcat.accesslog.check-exists

Whether to check for log file existence so it can be recreated if an external process has renamed it.

false

server.tomcat.accesslog.condition-if

Whether logging of the request will only be enabled if "ServletRequest.getAttribute(conditionIf)" does not yield null.

server.tomcat.accesslog.condition-unless

Whether logging of the request will only be enabled if "ServletRequest.getAttribute(conditionUnless)" yield null.

server.tomcat.accesslog.directory

Directory in which log files are created. Can be absolute or relative to the Tomcat base dir.

logs

server.tomcat.accesslog.enabled

Enable access log.

false

server.tomcat.accesslog.encoding

Character set used by the log file. Default to the system default character set.

server.tomcat.accesslog.file-date-format

Date format to place in the log file name.

.yyyy-MM-dd

server.tomcat.accesslog.ipv6-canonical

Whether to use IPv6 canonical representation format as defined by RFC 5952.

false

server.tomcat.accesslog.locale

Locale used to format timestamps in log entries and in log file name suffix. Default to the default locale of the Java process.

server.tomcat.accesslog.max-days

Number of days to retain the access log files before they are removed.

-1

server.tomcat.accesslog.pattern

Format pattern for access logs.

common

server.tomcat.accesslog.prefix

Log file name prefix.

access_log

server.tomcat.accesslog.rename-on-rotate

Whether to defer inclusion of the date stamp in the file name until rotate time.

false

server.tomcat.accesslog.request-attributes-enabled

Set request attributes for the IP address, Hostname, protocol, and port used for the request.

false

server.tomcat.accesslog.rotate

Whether to enable access log rotation.

true

server.tomcat.accesslog.suffix

Log file name suffix.

.log

server.tomcat.additional-tld-skip-patterns

Comma-separated list of additional patterns that match jars to ignore for TLD scanning. The special '?' and '*' characters can be used in the pattern to match one and only one character and zero or more characters respectively.

server.tomcat.background-processor-delay

Delay between the invocation of backgroundProcess methods. If a duration suffix is not specified, seconds will be used.

10s

server.tomcat.basedir

Tomcat base directory. If not specified, a temporary directory is used.

server.tomcat.connection-timeout

Amount of time the connector will wait, after accepting a connection, for the request URI line to be presented.

server.tomcat.keep-alive-timeout

Time to wait for another HTTP request before the connection is closed. When not set the connectionTimeout is used. When set to -1 there will be no timeout.

server.tomcat.max-connections

Maximum number of connections that the server accepts and processes at any given time. Once the limit has been reached, the operating system may still accept connections based on the "acceptCount" property.

8192

server.tomcat.max-http-form-post-size

Maximum size of the form content in any HTTP post request.

2MB

server.tomcat.max-http-response-header-size

Maximum size of the HTTP response header.

8KB

server.tomcat.max-keep-alive-requests

Maximum number of HTTP requests that can be pipelined before the connection is closed. When set to 0 or 1, keep-alive and pipelining are disabled. When set to -1, an unlimited number of pipelined or keep-alive requests are allowed.

100

server.tomcat.max-swallow-size

Maximum amount of request body to swallow.

2MB

server.tomcat.mbeanregistry.enabled

Whether Tomcat's MBean Registry should be enabled.

false

server.tomcat.processor-cache

Maximum number of idle processors that will be retained in the cache and reused with a subsequent request. When set to -1 the cache will be unlimited with a theoretical maximum size equal to the maximum number of connections.

200

server.tomcat.redirect-context-root

Whether requests to the context root should be redirected by appending a / to the path. When using SSL terminated at a proxy, this property should be set to false.

true

server.tomcat.relaxed-path-chars

Comma-separated list of additional unencoded characters that should be allowed in URI paths. Only "< > [ \ ] ^ ` { | }" are allowed.

server.tomcat.relaxed-query-chars

Comma-separated list of additional unencoded characters that should be allowed in URI query strings. Only "< > [ \ ] ^ ` { | }" are allowed.

server.tomcat.remoteip.host-header

Name of the HTTP header from which the remote host is extracted.

X-Forwarded-Host

server.tomcat.remoteip.internal-proxies

Regular expression that matches proxies that are to be trusted.

10\\.\\d{1,3}\\.\\d{1,3}\\.\\d{1,3}|192\\.168\\.\\d{1,3}\\.\\d{1,3}|169\\.254\\.\\d{1,3}\\.\\d{1,3}|127\\.\\d{1,3}\\.\\d{1,3}\\.\\d{1,3}|100\\.6[4-9]{1}\\.\\d{1,3}\\.\\d{1,3}|100\\.[7-9]{1}\\d{1}\\.\\d{1,3}\\.\\d{1,3}|100\\.1[0-1]{1}\\d{1}\\.\\d{1,3}\\.\\d{1,3}|100\\.12[0-7]{1}\\.\\d{1,3}\\.\\d{1,3}|172\\.1[6-9]{1}\\.\\d{1,3}\\.\\d{1,3}|172\\.2[0-9]{1}\\.\\d{1,3}\\.\\d{1,3}|172\\.3[0-1]{1}\\.\\d{1,3}\\.\\d{1,3}|0:0:0:0:0:0:0:1|::1

server.tomcat.remoteip.port-header

Name of the HTTP header used to override the original port value.

X-Forwarded-Port

server.tomcat.remoteip.protocol-header

Header that holds the incoming protocol, usually named "X-Forwarded-Proto".

server.tomcat.remoteip.protocol-header-https-value

Value of the protocol header indicating whether the incoming request uses SSL.

https

server.tomcat.remoteip.remote-ip-header

Name of the HTTP header from which the remote IP is extracted. For instance, 'X-FORWARDED-FOR'.

server.tomcat.remoteip.trusted-proxies

Regular expression defining proxies that are trusted when they appear in the "remote-ip-header" header.

server.tomcat.resource.allow-caching

Whether static resource caching is permitted for this web application.

true

server.tomcat.resource.cache-ttl

Time-to-live of the static resource cache.

server.tomcat.threads.max

Maximum amount of worker threads.

200

server.tomcat.threads.min-spare

Minimum amount of worker threads.

10

server.tomcat.uri-encoding

Character encoding to use to decode the URI.

UTF-8

server.tomcat.use-relative-redirects

Whether HTTP 1.1 and later location headers generated by a call to sendRedirect will use relative or absolute redirects.

false
```
