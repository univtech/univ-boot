# tomcat

```


server.tomcat.accept-count
server.tomcat.accesslog.buffered
server.tomcat.accesslog.check-exists
server.tomcat.accesslog.condition-if
server.tomcat.accesslog.condition-unless
server.tomcat.accesslog.directory
server.tomcat.accesslog.enabled
server.tomcat.accesslog.encoding
server.tomcat.accesslog.file-date-format
server.tomcat.accesslog.ipv6-canonical
server.tomcat.accesslog.locale
server.tomcat.accesslog.max-days
server.tomcat.accesslog.pattern
server.tomcat.accesslog.prefix
server.tomcat.accesslog.rename-on-rotate
server.tomcat.accesslog.request-attributes-enabled
server.tomcat.accesslog.rotate
server.tomcat.accesslog.suffix
server.tomcat.additional-tld-skip-patterns
server.tomcat.background-processor-delay
server.tomcat.basedir
server.tomcat.connection-timeout
server.tomcat.keep-alive-timeout
server.tomcat.max-connections
server.tomcat.max-http-form-post-size
server.tomcat.max-http-response-header-size
server.tomcat.max-keep-alive-requests
server.tomcat.max-swallow-size
server.tomcat.mbeanregistry.enabled
server.tomcat.processor-cache
server.tomcat.redirect-context-root
server.tomcat.relaxed-path-chars
server.tomcat.relaxed-query-chars
server.tomcat.remoteip.host-header
server.tomcat.remoteip.internal-proxies
server.tomcat.remoteip.port-header
server.tomcat.remoteip.protocol-header
server.tomcat.remoteip.protocol-header-https-value
server.tomcat.remoteip.remote-ip-header
server.tomcat.remoteip.trusted-proxies
server.tomcat.resource.allow-caching
server.tomcat.resource.cache-ttl
server.tomcat.threads.max
server.tomcat.threads.min-spare
server.tomcat.uri-encoding
server.tomcat.use-relative-redirects

org.springframework.boot.autoconfigure.web.ServerProperties.Tomcat
org.springframework.boot.autoconfigure.web.ServerProperties.Tomcat.Accesslog
org.springframework.boot.autoconfigure.web.ServerProperties.Tomcat.Mbeanregistry
org.springframework.boot.autoconfigure.web.ServerProperties.Tomcat.Remoteip
org.springframework.boot.autoconfigure.web.ServerProperties.Tomcat.Resource
org.springframework.boot.autoconfigure.web.ServerProperties.Tomcat.Threads

```

```

org.springframework.boot.context.embedded.tomcat.empty-web.xml

org.springframework.boot.actuate.metrics.web.tomcat.TomcatMetricsBinder
org.springframework.boot.actuate.autoconfigure.metrics.web.tomcat.TomcatMetricsAutoConfiguration

org.springframework.boot.autoconfigure.web.embedded.TomcatWebServerFactoryCustomizer
org.springframework.boot.autoconfigure.web.embedded.EmbeddedWebServerFactoryCustomizerAutoConfiguration.TomcatWebServerFactoryCustomizerConfiguration





```

### ConfigurableTomcatWebServerFactory

```

# 可配置的TomcatWebServer工厂。
org.springframework.boot.web.server.WebServerFactory/ErrorPageRegistry
    org.springframework.boot.web.server.ConfigurableWebServerFactory
        org.springframework.boot.web.embedded.tomcat.ConfigurableTomcatWebServerFactory
            org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory
            org.springframework.boot.web.embedded.tomcat.TomcatReactiveWebServerFactory
        org.springframework.boot.web.servlet.server.ConfigurableServletWebServerFactory
            org.springframework.boot.web.servlet.server.AbstractServletWebServerFactory
                org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory
        org.springframework.boot.web.reactive.server.ConfigurableReactiveWebServerFactory
            org.springframework.boot.web.reactive.server.AbstractReactiveWebServerFactory
                org.springframework.boot.web.embedded.tomcat.TomcatReactiveWebServerFactory
        org.springframework.boot.web.server.AbstractConfigurableWebServerFactory
            org.springframework.boot.web.servlet.server.AbstractServletWebServerFactory
                org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory
            org.springframework.boot.web.reactive.server.AbstractReactiveWebServerFactory
                org.springframework.boot.web.embedded.tomcat.TomcatReactiveWebServerFactory
    org.springframework.boot.web.servlet.server.ServletWebServerFactory
        org.springframework.boot.web.servlet.server.ConfigurableServletWebServerFactory
            org.springframework.boot.web.servlet.server.AbstractServletWebServerFactory
                org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory
    org.springframework.boot.web.reactive.server.ReactiveWebServerFactory
        org.springframework.boot.web.reactive.server.ConfigurableReactiveWebServerFactory
            org.springframework.boot.web.reactive.server.AbstractReactiveWebServerFactory
                org.springframework.boot.web.embedded.tomcat.TomcatReactiveWebServerFactory

# 可配置的TomcatWebServer工厂。
# setBaseDirectory：             设置Tomcat的基础目录，默认值：临时目录。
# setBackgroundProcessorDelay：  设置后台进程的延时（秒）。
# setUriEncoding：               设置URL解码时的字符集编码，默认值：UTF-8。
# addEngineValves：              添加应用于Tomcat Engine的Valve。
# addContextCustomizers：        添加应用于Tomcat Context的TomcatContextCustomizer。
# addConnectorCustomizers：      添加应用于Tomcat Connector的TomcatConnectorCustomizer。
# addProtocolHandlerCustomizers：添加应用于Tomcat Connector的TomcatProtocolHandlerCustomizer。
org.springframework.boot.web.embedded.tomcat.ConfigurableTomcatWebServerFactory

#
org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory

#
org.springframework.boot.web.embedded.tomcat.TomcatReactiveWebServerFactory

```

### TomcatContextCustomizer

```

# Tomcat Context的定制器。
org.springframework.boot.web.embedded.tomcat.TomcatContextCustomizer
    org.springframework.boot.web.embedded.tomcat.DisableReferenceClearingContextCustomizer

# Tomcat Context的定制器：自定义Tomcat上下文的回调接口。
# customize：自定义Tomcat上下文。
org.springframework.boot.web.embedded.tomcat.TomcatContextCustomizer

# Tomcat Context的定制器：禁用Tomcat的反射引用清除，防止Java 9及之后的JVM出现反射访问警告。
# customize：自定义Tomcat上下文。
org.springframework.boot.web.embedded.tomcat.DisableReferenceClearingContextCustomizer

```

### TomcatConnectorCustomizer

```

# Tomcat Connector的定制器。
org.springframework.boot.web.embedded.tomcat.TomcatConnectorCustomizer
    org.springframework.boot.web.embedded.tomcat.SslConnectorCustomizer
    org.springframework.boot.web.embedded.tomcat.CompressionConnectorCustomizer

# Tomcat Connector的定制器：自定义Tomcat连接器的回调接口。
# customize：自定义Tomcat连接器。
org.springframework.boot.web.embedded.tomcat.TomcatConnectorCustomizer

# Tomcat Connector的定制器：自定义Tomcat连接器的SSL配置。
# clientAuth：               客户端认证类型。
# sslBundle：                建立SSL连接的受信信息包。
# customize：                自定义Tomcat连接器。
# configureSsl：             配置SSL。
# configureEnabledProtocols：配置启用的协议。
# configureSslClientAuth：   配置SSL客户端认证类型。
# configureSslStoreProvider：配置SSL密钥存储库提供者。
org.springframework.boot.web.embedded.tomcat.SslConnectorCustomizer

# Tomcat Connector的定制器：自定义Tomcat连接器的压缩配置。
# compression：          与服务器无关的压缩配置。
# customize：            自定义Tomcat连接器。
# getMinResponseSize：   获取最小响应大小。
# getMimeTypes：         获取MIME类型。
# getExcludedUserAgents：获取排除的用户代理。
org.springframework.boot.web.embedded.tomcat.CompressionConnectorCustomizer

```

### TomcatProtocolHandlerCustomizer

```

# Tomcat Connector上的ProtocolHandler的定制器：自定义Tomcat连接器上的协议处理器的回调接口。
# customize：自定义Tomcat连接器上的协议处理器。
org.springframework.boot.web.embedded.tomcat.TomcatProtocolHandlerCustomizer

```

### ConnectorStartFailureAnalyzer

```

# Tomcat Connector启动失败异常分析器。
org.springframework.boot.web.embedded.tomcat.ConnectorStartFailureAnalyzer

```

### ConnectorStartFailedException

```

# Tomcat Connector启动失败时抛出的异常，例如：端口冲突或SSL配置错误。
# port：   端口。
# getPort：获取端口。
org.springframework.boot.web.embedded.tomcat.ConnectorStartFailedException

```

### TomcatStarter

```

# Tomcat启动器：触发ServletContextInitializer并跟踪启动错误的ServletContainerInitializer。
# initializers：       Servlet上下文初始化器（ServletContextInitializer）。
# startUpException：   启动异常。
# onStartup：          触发ServletContextInitializer并跟踪启动错误。
# getStartUpException：获取启动异常。
org.springframework.boot.web.embedded.tomcat.TomcatStarter

```

### GracefulShutdown

```

# 优雅关闭Tomcat。
# tomcat：            Tomcat实例。
# aborted：           是否中止，默认值：false。
# shutDownGracefully：优雅关闭Tomcat。
# doShutdown：        优雅关闭Tomcat。
# getConnectors：     获取Connector列表。
# close：             关闭Connector。
# isActive：          Container是否存活。
# abort：             中止优雅关闭。
org.springframework.boot.web.embedded.tomcat.GracefulShutdown

```

### TldPatterns

```

# Spring Boot使用的TLD跳过和扫描模式。
# TOMCAT_SKIP：    Tomcat TLD跳过模式。
# ADDITIONAL_SKIP：其他TLD跳过模式。
# DEFAULT_SKIP：   默认的TLD跳过模式：TOMCAT_SKIP、ADDITIONAL_SKIP。
# TOMCAT_SCAN：    Tomcat TLD扫描模式。
# DEFAULT_SCAN：   默认的TLD扫描模式：TOMCAT_SCAN。
org.springframework.boot.web.embedded.tomcat.TldPatterns

```

### LazySessionIdGenerator

```

# 延迟会话ID生成器：延迟初始化SecureRandom的StandardSessionIdGenerator。
# startInternal：内部启动，设置生命周期状态：STARTING。
org.springframework.boot.web.embedded.tomcat.LazySessionIdGenerator

```













```

org.springframework.boot.web.embedded.tomcat.TomcatWebServer
org.springframework.boot.web.embedded.tomcat.TomcatWebServer.1

org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.DisablePersistSessionListener
org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.LoaderHidingResourceRoot
org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.LoaderHidingWebResourceSet
org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.StaticResourceConfigurer
org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.SuppliedSameSiteCookieProcessor

```























### TomcatEmbeddedContext

```

org.springframework.boot.web.embedded.tomcat.TomcatEmbeddedContext

```

### TomcatEmbeddedWebappClassLoader

```

org.springframework.boot.web.embedded.tomcat.TomcatEmbeddedWebappClassLoader

```



```


spring.datasource.tomcat.abandon-when-percentage-full
spring.datasource.tomcat.access-to-underlying-connection-allowed
spring.datasource.tomcat.alternate-username-allowed
spring.datasource.tomcat.commit-on-return
spring.datasource.tomcat.connection-properties
spring.datasource.tomcat.data-source-j-n-d-i
spring.datasource.tomcat.db-properties
spring.datasource.tomcat.default-auto-commit
spring.datasource.tomcat.default-catalog
spring.datasource.tomcat.default-read-only
spring.datasource.tomcat.default-transaction-isolation
spring.datasource.tomcat.driver-class-name
spring.datasource.tomcat.fair-queue
spring.datasource.tomcat.ignore-exception-on-pre-load
spring.datasource.tomcat.init-s-q-l
spring.datasource.tomcat.initial-size
spring.datasource.tomcat.jdbc-interceptors
spring.datasource.tomcat.jmx-enabled
spring.datasource.tomcat.log-abandoned
spring.datasource.tomcat.log-validation-errors
spring.datasource.tomcat.login-timeout
spring.datasource.tomcat.max-active
spring.datasource.tomcat.max-age
spring.datasource.tomcat.max-idle
spring.datasource.tomcat.max-wait
spring.datasource.tomcat.min-evictable-idle-time-millis
spring.datasource.tomcat.min-idle
spring.datasource.tomcat.name
spring.datasource.tomcat.num-tests-per-eviction-run
spring.datasource.tomcat.password
spring.datasource.tomcat.propagate-interrupt-state
spring.datasource.tomcat.remove-abandoned
spring.datasource.tomcat.remove-abandoned-timeout
spring.datasource.tomcat.rollback-on-return
spring.datasource.tomcat.suspect-timeout
spring.datasource.tomcat.test-on-borrow
spring.datasource.tomcat.test-on-connect
spring.datasource.tomcat.test-on-return
spring.datasource.tomcat.test-while-idle
spring.datasource.tomcat.time-between-eviction-runs-millis
spring.datasource.tomcat.url
spring.datasource.tomcat.use-disposable-connection-facade
spring.datasource.tomcat.use-equals
spring.datasource.tomcat.use-lock
spring.datasource.tomcat.use-statement-facade
spring.datasource.tomcat.username
spring.datasource.tomcat.validation-interval
spring.datasource.tomcat.validation-query
spring.datasource.tomcat.validation-query-timeout
spring.datasource.tomcat.validator-class-name

```


```

org.springframework.boot.jdbc.DataSourceBuilder.TomcatPoolDataSourceProperties
org.springframework.boot.jdbc.metadata.TomcatDataSourcePoolMetadata
org.springframework.boot.autoconfigure.jdbc.DataSourceConfiguration.Tomcat
org.springframework.boot.autoconfigure.jdbc.DataSourceJmxConfiguration.TomcatDataSourceJmxConfiguration
org.springframework.boot.autoconfigure.jdbc.metadata.DataSourcePoolMetadataProvidersConfiguration.TomcatDataSourcePoolMetadataProviderConfiguration
org.springframework.boot.autoconfigure.jdbc.TomcatJdbcConnectionDetailsBeanPostProcessor

org.springframework.boot.autoconfigure.web.servlet.TomcatServletWebServerFactoryCustomizer
org.springframework.boot.autoconfigure.web.reactive.TomcatReactiveWebServerFactoryCustomizer

org.springframework.boot.actuate.autoconfigure.web.servlet.ServletManagementChildContextConfiguration.TomcatAccessLogCustomizer

org.springframework.boot.autoconfigure.websocket.servlet.TomcatWebSocketServletWebServerCustomizer
org.springframework.boot.autoconfigure.websocket.reactive.TomcatWebSocketReactiveWebServerCustomizer

org.springframework.boot.autoconfigure.websocket.servlet.WebSocketServletAutoConfiguration.TomcatWebSocketConfiguration
org.springframework.boot.autoconfigure.websocket.reactive.WebSocketReactiveAutoConfiguration.TomcatWebSocketConfiguration

org.springframework.boot.actuate.web.mappings.servlet.DispatcherServletHandlerMappings.TomcatServletInitializer

org.springframework.boot.autoconfigure.web.servlet.ServletWebServerFactoryConfiguration.EmbeddedTomcat
org.springframework.boot.autoconfigure.web.reactive.ReactiveWebServerFactoryConfiguration.EmbeddedTomcat
```












