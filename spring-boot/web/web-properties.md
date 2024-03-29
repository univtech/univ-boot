## Web Properties

```
spring.graphql.cors.allow-credentials

Whether credentials are supported. When not set, credentials are not supported.

spring.graphql.cors.allowed-headers

Comma-separated list of HTTP headers to allow in a request. '*' allows all headers.

spring.graphql.cors.allowed-methods

Comma-separated list of HTTP methods to allow. '*' allows all methods. When not set, defaults to GET.

spring.graphql.cors.allowed-origin-patterns

Comma-separated list of origin patterns to allow. Unlike allowed origins which only support '*', origin patterns are more flexible, e.g. 'https://*.example.com', and can be used with allow-credentials. When neither allowed origins nor allowed origin patterns are set, cross-origin requests are effectively disabled.

spring.graphql.cors.allowed-origins

Comma-separated list of origins to allow with '*' allowing all origins. When allow-credentials is enabled, '*' cannot be used, and setting origin patterns should be considered instead. When neither allowed origins nor allowed origin patterns are set, cross-origin requests are effectively disabled.

spring.graphql.cors.exposed-headers

Comma-separated list of headers to include in a response.

spring.graphql.cors.max-age

How long the response from a pre-flight request can be cached by clients. If a duration suffix is not specified, seconds will be used.

1800s

spring.graphql.graphiql.enabled

Whether the default GraphiQL UI is enabled.

false

spring.graphql.graphiql.path

Path to the GraphiQL UI endpoint.

/graphiql

spring.graphql.path

Path at which to expose a GraphQL request HTTP endpoint.

/graphql

spring.graphql.rsocket.mapping

Mapping of the RSocket message handler.

spring.graphql.schema.file-extensions

File extensions for GraphQL schema files.

.graphqls,.gqls

spring.graphql.schema.introspection.enabled

Whether field introspection should be enabled at the schema level.

true

spring.graphql.schema.locations

Locations of GraphQL schema files.

classpath:graphql/**/

spring.graphql.schema.printer.enabled

Whether the endpoint that prints the schema is enabled. Schema is available under spring.graphql.path + "/schema".

false

spring.graphql.websocket.connection-init-timeout

Time within which the initial {@code CONNECTION_INIT} type message must be received.

60s

spring.graphql.websocket.path

Path of the GraphQL WebSocket subscription endpoint.

spring.hateoas.use-hal-as-default-json-media-type

Whether application/hal+json responses should be sent to requests that accept application/json.

true

spring.jersey.application-path

Path that serves as the base URI for the application. If specified, overrides the value of "@ApplicationPath".

spring.jersey.filter.order

Jersey filter chain order.

0

spring.jersey.init.*

Init parameters to pass to Jersey through the servlet or filter.

spring.jersey.servlet.load-on-startup

Load on startup priority of the Jersey servlet.

-1

spring.jersey.type

Jersey integration type.

servlet

spring.mvc.async.request-timeout

Amount of time before asynchronous request handling times out. If this value is not set, the default timeout of the underlying implementation is used.

spring.mvc.contentnegotiation.favor-parameter

Whether a request parameter ("format" by default) should be used to determine the requested media type.

false

spring.mvc.contentnegotiation.media-types.*

Map file extensions to media types for content negotiation. For instance, yml to text/yaml.

spring.mvc.contentnegotiation.parameter-name

Query parameter name to use when "favor-parameter" is enabled.

spring.mvc.converters.preferred-json-mapper

Preferred JSON mapper to use for HTTP message conversion. By default, auto-detected according to the environment.

spring.mvc.dispatch-options-request

Whether to dispatch OPTIONS requests to the FrameworkServlet doService method.

true

spring.mvc.dispatch-trace-request

Whether to dispatch TRACE requests to the FrameworkServlet doService method.

false

spring.mvc.format.date

Date format to use, for example 'dd/MM/yyyy'.

spring.mvc.format.date-time

Date-time format to use, for example 'yyyy-MM-dd HH:mm:ss'.

spring.mvc.format.time

Time format to use, for example 'HH:mm:ss'.

spring.mvc.formcontent.filter.enabled

Whether to enable Spring's FormContentFilter.

true

spring.mvc.hiddenmethod.filter.enabled

Whether to enable Spring's HiddenHttpMethodFilter.

false

spring.mvc.log-request-details

Whether logging of (potentially sensitive) request details at DEBUG and TRACE level is allowed.

false

spring.mvc.log-resolved-exception

Whether to enable warn logging of exceptions resolved by a "HandlerExceptionResolver", except for "DefaultHandlerExceptionResolver".

false

spring.mvc.message-codes-resolver-format

Formatting strategy for message codes. For instance, 'PREFIX_ERROR_CODE'.

spring.mvc.pathmatch.matching-strategy

Choice of strategy for matching request paths against registered mappings.

path-pattern-parser

spring.mvc.problemdetails.enabled

Whether RFC 7807 Problem Details support should be enabled.

false

spring.mvc.publish-request-handled-events

Whether to publish a ServletRequestHandledEvent at the end of each request.

true

spring.mvc.servlet.load-on-startup

Load on startup priority of the dispatcher servlet.

-1

spring.mvc.servlet.path

Path of the dispatcher servlet. Setting a custom value for this property is not compatible with the PathPatternParser matching strategy.

/

spring.mvc.static-path-pattern

Path pattern used for static resources.

/**

spring.mvc.throw-exception-if-no-handler-found

Whether a "NoHandlerFoundException" should be thrown if no Handler was found to process a request.

false

spring.mvc.view.prefix

Spring MVC view prefix.

spring.mvc.view.suffix

Spring MVC view suffix.

spring.mvc.webjars-path-pattern

Path pattern used for WebJar assets.

/webjars/**

spring.netty.leak-detection

Level of leak detection for reference-counted buffers. If not configured via 'ResourceLeakDetector.setLevel' or the 'io.netty.leakDetection.level' system property, default to 'simple'.

spring.servlet.multipart.enabled

Whether to enable support of multipart uploads.

true

spring.servlet.multipart.file-size-threshold

Threshold after which files are written to disk.

0B

spring.servlet.multipart.location

Intermediate location of uploaded files.

spring.servlet.multipart.max-file-size

Max file size.

1MB

spring.servlet.multipart.max-request-size

Max request size.

10MB

spring.servlet.multipart.resolve-lazily

Whether to resolve the multipart request lazily at the time of file or parameter access.

false

spring.session.hazelcast.flush-mode

Sessions flush mode. Determines when session changes are written to the session store.

on-save

spring.session.hazelcast.map-name

Name of the map used to store sessions.

spring:session:sessions

spring.session.hazelcast.save-mode

Sessions save mode. Determines how session changes are tracked and saved to the session store.

on-set-attribute

spring.session.jdbc.cleanup-cron

Cron expression for expired session cleanup job.

0 * * * * *

spring.session.jdbc.flush-mode

Sessions flush mode. Determines when session changes are written to the session store.

on-save

spring.session.jdbc.initialize-schema

Database schema initialization mode.

embedded

spring.session.jdbc.platform

Platform to use in initialization scripts if the @@platform@@ placeholder is used. Auto-detected by default.

spring.session.jdbc.save-mode

Sessions save mode. Determines how session changes are tracked and saved to the session store.

on-set-attribute

spring.session.jdbc.schema

Path to the SQL file to use to initialize the database schema.

classpath:org/springframework/session/jdbc/schema-@@platform@@.sql

spring.session.jdbc.table-name

Name of the database table used to store sessions.

SPRING_SESSION

spring.session.mongodb.collection-name

Collection name used to store sessions.

sessions

spring.session.redis.cleanup-cron

Cron expression for expired session cleanup job. Only supported when repository-type is set to indexed.

0 * * * * *

spring.session.redis.configure-action

The configure action to apply when no user defined ConfigureRedisAction bean is present.

notify-keyspace-events

spring.session.redis.flush-mode

Sessions flush mode. Determines when session changes are written to the session store.

on-save

spring.session.redis.namespace

Namespace for keys used to store sessions.

spring:session

spring.session.redis.repository-type

Type of Redis session repository to configure.

default

spring.session.redis.save-mode

Sessions save mode. Determines how session changes are tracked and saved to the session store.

on-set-attribute

spring.session.servlet.filter-dispatcher-types

Session repository filter dispatcher types.

[async, error, request]

spring.session.servlet.filter-order

Session repository filter order.

spring.session.timeout

Session timeout. If a duration suffix is not specified, seconds will be used.

spring.web.locale

Locale to use. By default, this locale is overridden by the "Accept-Language" header.

spring.web.locale-resolver

Define how the locale should be resolved.

accept-header

spring.web.resources.add-mappings

Whether to enable default resource handling.

true

spring.web.resources.cache.cachecontrol.cache-private

Indicate that the response message is intended for a single user and must not be stored by a shared cache.

spring.web.resources.cache.cachecontrol.cache-public

Indicate that any cache may store the response.

spring.web.resources.cache.cachecontrol.max-age

Maximum time the response should be cached, in seconds if no duration suffix is not specified.

spring.web.resources.cache.cachecontrol.must-revalidate

Indicate that once it has become stale, a cache must not use the response without re-validating it with the server.

spring.web.resources.cache.cachecontrol.no-cache

Indicate that the cached response can be reused only if re-validated with the server.

spring.web.resources.cache.cachecontrol.no-store

Indicate to not cache the response in any case.

spring.web.resources.cache.cachecontrol.no-transform

Indicate intermediaries (caches and others) that they should not transform the response content.

spring.web.resources.cache.cachecontrol.proxy-revalidate

Same meaning as the "must-revalidate" directive, except that it does not apply to private caches.

spring.web.resources.cache.cachecontrol.s-max-age

Maximum time the response should be cached by shared caches, in seconds if no duration suffix is not specified.

spring.web.resources.cache.cachecontrol.stale-if-error

Maximum time the response may be used when errors are encountered, in seconds if no duration suffix is not specified.

spring.web.resources.cache.cachecontrol.stale-while-revalidate

Maximum time the response can be served after it becomes stale, in seconds if no duration suffix is not specified.

spring.web.resources.cache.period

Cache period for the resources served by the resource handler. If a duration suffix is not specified, seconds will be used. Can be overridden by the 'spring.web.resources.cache.cachecontrol' properties.

spring.web.resources.cache.use-last-modified

Whether we should use the "lastModified" metadata of the files in HTTP caching headers.

true

spring.web.resources.chain.cache

Whether to enable caching in the Resource chain.

true

spring.web.resources.chain.compressed

Whether to enable resolution of already compressed resources (gzip, brotli). Checks for a resource name with the '.gz' or '.br' file extensions.

false

spring.web.resources.chain.enabled

Whether to enable the Spring Resource Handling chain. By default, disabled unless at least one strategy has been enabled.

spring.web.resources.chain.strategy.content.enabled

Whether to enable the content Version Strategy.

false

spring.web.resources.chain.strategy.content.paths

Comma-separated list of patterns to apply to the content Version Strategy.

[/**]

spring.web.resources.chain.strategy.fixed.enabled

Whether to enable the fixed Version Strategy.

false

spring.web.resources.chain.strategy.fixed.paths

Comma-separated list of patterns to apply to the fixed Version Strategy.

[/**]

spring.web.resources.chain.strategy.fixed.version

Version string to use for the fixed Version Strategy.

spring.web.resources.static-locations

Locations of static resources. Defaults to classpath:[/META-INF/resources/, /resources/, /static/, /public/].

[classpath:/META-INF/resources/, classpath:/resources/, classpath:/static/, classpath:/public/]

spring.webflux.base-path

Base path for all web handlers.

spring.webflux.format.date

Date format to use, for example 'dd/MM/yyyy'.

spring.webflux.format.date-time

Date-time format to use, for example 'yyyy-MM-dd HH:mm:ss'.

spring.webflux.format.time

Time format to use, for example 'HH:mm:ss'.

spring.webflux.hiddenmethod.filter.enabled

Whether to enable Spring's HiddenHttpMethodFilter.

false

spring.webflux.multipart.file-storage-directory

Directory used to store file parts larger than 'maxInMemorySize'. Default is a directory named 'spring-multipart' created under the system temporary directory. Ignored when streaming is enabled.

spring.webflux.multipart.headers-charset

Character set used to decode headers.

UTF-8

spring.webflux.multipart.max-disk-usage-per-part

Maximum amount of disk space allowed per part. Default is -1 which enforces no limits. Ignored when streaming is enabled.

-1B

spring.webflux.multipart.max-headers-size

Maximum amount of memory allowed per headers section of each part. Set to -1 to enforce no limits.

10KB

spring.webflux.multipart.max-in-memory-size

Maximum amount of memory allowed per part before it's written to disk. Set to -1 to store all contents in memory. Ignored when streaming is enabled.

256KB

spring.webflux.multipart.max-parts

Maximum number of parts allowed in a given multipart request. Default is -1 which enforces no limits.

-1

spring.webflux.problemdetails.enabled

Whether RFC 7807 Problem Details support should be enabled.

false

spring.webflux.static-path-pattern

Path pattern used for static resources.

/**

spring.webflux.webjars-path-pattern

Path pattern used for WebJar assets.

/webjars/**

```
