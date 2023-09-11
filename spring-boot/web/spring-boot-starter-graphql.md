# spring-boot-starter-graphql

```
# 地址
https://spring.io
https://spring.io/projects/spring-boot

https://github.com/spring-projects/spring-boot
https://github.com/spring-projects/spring-boot/issues

git://github.com/spring-projects/spring-boot.git
ssh://git@github.com/spring-projects/spring-boot.git

# 构件
org.springframework.boot:spring-boot-starter-graphql:3.1.3

# 依赖：compile
org.springframework.boot:spring-boot-starter:3.1.3
org.springframework.boot:spring-boot-starter-json:3.1.3
org.springframework.graphql:spring-graphql:1.2.2
```

## graphql配置属性

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
```
