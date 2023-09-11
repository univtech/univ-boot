# spring-boot-starter-undertow

```
# 地址
https://spring.io
https://spring.io/projects/spring-boot

https://github.com/spring-projects/spring-boot
https://github.com/spring-projects/spring-boot/issues

git://github.com/spring-projects/spring-boot.git
ssh://git@github.com/spring-projects/spring-boot.git

# 构件
org.springframework.boot:spring-boot-starter-undertow:3.1.3

# 依赖：compile
io.undertow:undertow-core:2.3.8.Final
io.undertow:undertow-servlet:2.3.8.Final
io.undertow:undertow-websockets-jsr:2.3.8.Final
org.apache.tomcat.embed:tomcat-embed-el:10.1.12
```

## 配置属性

```
server.address

Network address to which the server should bind.

server.compression.enabled

Whether response compression is enabled.

false

server.compression.excluded-user-agents

Comma-separated list of user agents for which responses should not be compressed.

server.compression.mime-types

Comma-separated list of MIME types that should be compressed.

[text/html, text/xml, text/plain, text/css, text/javascript, application/javascript, application/json, application/xml]

server.compression.min-response-size

Minimum "Content-Length" value that is required for compression to be performed.

2KB

server.error.include-binding-errors

When to include "errors" attribute.

never

server.error.include-exception

Include the "exception" attribute.

false

server.error.include-message

When to include "message" attribute.

never

server.error.include-stacktrace

When to include the "trace" attribute.

never

server.error.path

Path of the error controller.

/error

server.error.whitelabel.enabled

Whether to enable the default error page displayed in browsers in case of a server error.

true

server.forward-headers-strategy

Strategy for handling X-Forwarded-* headers.

server.http2.enabled

Whether to enable HTTP/2 support, if the current environment supports it.

false

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

server.max-http-request-header-size

Maximum size of the HTTP request header.

8KB

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

server.port

Server HTTP port.

8080

server.reactive.session.cookie.domain

Domain for the cookie.

server.reactive.session.cookie.http-only

Whether to use "HttpOnly" cookies for the cookie.

server.reactive.session.cookie.max-age

Maximum age of the cookie. If a duration suffix is not specified, seconds will be used. A positive value indicates when the cookie expires relative to the current time. A value of 0 means the cookie should expire immediately. A negative value means no "Max-Age".

server.reactive.session.cookie.name

Name for the cookie.

server.reactive.session.cookie.path

Path of the cookie.

server.reactive.session.cookie.same-site

SameSite setting for the cookie.

server.reactive.session.cookie.secure

Whether to always mark the cookie as secure.

server.reactive.session.timeout

Session timeout. If a duration suffix is not specified, seconds will be used.

30m

server.server-header

Value to use for the Server response header (if empty, no header is sent).

server.servlet.application-display-name

Display name of the application.

application

server.servlet.context-parameters.*

Servlet context init parameters.

server.servlet.context-path

Context path of the application.

server.servlet.encoding.charset

Charset of HTTP requests and responses. Added to the "Content-Type" header if not set explicitly.

UTF-8

server.servlet.encoding.enabled

Whether to enable http encoding support.

true

server.servlet.encoding.force

Whether to force the encoding to the configured charset on HTTP requests and responses.

server.servlet.encoding.force-request

Whether to force the encoding to the configured charset on HTTP requests. Defaults to true when "force" has not been specified.

server.servlet.encoding.force-response

Whether to force the encoding to the configured charset on HTTP responses.

server.servlet.encoding.mapping.*

Mapping of locale to charset for response encoding.

server.servlet.jsp.class-name

Class name of the servlet to use for JSPs. If registered is true and this class * is on the classpath then it will be registered.

org.apache.jasper.servlet.JspServlet

server.servlet.jsp.init-parameters.*

Init parameters used to configure the JSP servlet.

server.servlet.jsp.registered

Whether the JSP servlet is registered.

true

server.servlet.register-default-servlet

Whether to register the default Servlet with the container.

false

server.servlet.session.cookie.domain

Domain for the cookie.

server.servlet.session.cookie.http-only

Whether to use "HttpOnly" cookies for the cookie.

server.servlet.session.cookie.max-age

Maximum age of the cookie. If a duration suffix is not specified, seconds will be used. A positive value indicates when the cookie expires relative to the current time. A value of 0 means the cookie should expire immediately. A negative value means no "Max-Age".

server.servlet.session.cookie.name

Name of the cookie.

server.servlet.session.cookie.path

Path of the cookie.

server.servlet.session.cookie.same-site

SameSite setting for the cookie.

server.servlet.session.cookie.secure

Whether to always mark the cookie as secure.

server.servlet.session.persistent

Whether to persist session data between restarts.

false

server.servlet.session.store-dir

Directory used to store session data.

server.servlet.session.timeout

Session timeout. If a duration suffix is not specified, seconds will be used.

30m

server.servlet.session.tracking-modes

Session tracking modes.

server.shutdown

Type of shutdown that the server will support.

immediate

server.ssl.bundle

The name of a configured SSL bundle.

server.ssl.certificate

Path to a PEM-encoded SSL certificate file.

server.ssl.certificate-private-key

Path to a PEM-encoded private key file for the SSL certificate.

server.ssl.ciphers

Supported SSL ciphers.

server.ssl.client-auth

Client authentication mode. Requires a trust store.

server.ssl.enabled

Whether to enable SSL support.

true

server.ssl.enabled-protocols

Enabled SSL protocols.

server.ssl.key-alias

Alias that identifies the key in the key store.

server.ssl.key-password

Password used to access the key in the key store.

server.ssl.key-store

Path to the key store that holds the SSL certificate (typically a jks file).

server.ssl.key-store-password

Password used to access the key store.

server.ssl.key-store-provider

Provider for the key store.

server.ssl.key-store-type

Type of the key store.

server.ssl.protocol

SSL protocol to use.

TLS

server.ssl.trust-certificate

Path to a PEM-encoded SSL certificate authority file.

server.ssl.trust-certificate-private-key

Path to a PEM-encoded private key file for the SSL certificate authority.

server.ssl.trust-store

Trust store that holds SSL certificates.

server.ssl.trust-store-password

Password used to access the trust store.

server.ssl.trust-store-provider

Provider for the trust store.

server.ssl.trust-store-type

Type of the trust store.

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

server.undertow.accesslog.dir

Undertow access log directory.

server.undertow.accesslog.enabled

Whether to enable the access log.

false

server.undertow.accesslog.pattern

Format pattern for access logs.

common

server.undertow.accesslog.prefix

Log file name prefix.

access_log.

server.undertow.accesslog.rotate

Whether to enable access log rotation.

true

server.undertow.accesslog.suffix

Log file name suffix.

log

server.undertow.always-set-keep-alive

Whether the 'Connection: keep-alive' header should be added to all responses, even if not required by the HTTP specification.

true

server.undertow.buffer-size

Size of each buffer. The default is derived from the maximum amount of memory that is available to the JVM.

server.undertow.decode-slash

Whether encoded slash characters (%2F) should be decoded. Decoding can cause security problems if a front-end proxy does not perform the same decoding. Only enable this if you have a legacy application that requires it. When set, server.undertow.allow-encoded-slash has no effect.

server.undertow.decode-url

Whether the URL should be decoded. When disabled, percent-encoded characters in the URL will be left as-is.

true

server.undertow.direct-buffers

Whether to allocate buffers outside the Java heap. The default is derived from the maximum amount of memory that is available to the JVM.

server.undertow.eager-filter-init

Whether servlet filters should be initialized on startup.

true

server.undertow.max-cookies

Maximum number of cookies that are allowed. This limit exists to prevent hash collision based DOS attacks.

200

server.undertow.max-headers

Maximum number of headers that are allowed. This limit exists to prevent hash collision based DOS attacks.

server.undertow.max-http-post-size

Maximum size of the HTTP post content. When the value is -1, the default, the size is unlimited.

-1B

server.undertow.max-parameters

Maximum number of query or path parameters that are allowed. This limit exists to prevent hash collision based DOS attacks.

server.undertow.no-request-timeout

Amount of time a connection can sit idle without processing a request, before it is closed by the server.

server.undertow.options.server.*

Server options as defined in io.undertow.UndertowOptions.

server.undertow.options.socket.*

Socket options as defined in org.xnio.Options.

server.undertow.preserve-path-on-forward

Whether to preserve the path of a request when it is forwarded.

false

server.undertow.threads.io

Number of I/O threads to create for the worker. The default is derived from the number of available processors.

server.undertow.threads.worker

Number of worker threads. The default is 8 times the number of I/O threads.

server.undertow.url-charset

Charset used to decode URLs.

UTF-8
```
