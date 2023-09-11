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
