# spring-boot-starter-web

```
# 地址
https://spring.io
https://spring.io/projects/spring-boot

https://github.com/spring-projects/spring-boot
https://github.com/spring-projects/spring-boot/issues

git://github.com/spring-projects/spring-boot.git
ssh://git@github.com/spring-projects/spring-boot.git

# 构件
org.springframework.boot:spring-boot-starter-web:3.1.3

# 依赖：compile
org.springframework.boot:spring-boot-starter:3.1.3
org.springframework.boot:spring-boot-starter-json:3.1.3
org.springframework.boot:spring-boot-starter-tomcat:3.1.3
org.springframework:spring-web:6.0.11
org.springframework:spring-webmvc:6.0.11
```

## 其他配置属性

```
spring.hateoas.use-hal-as-default-json-media-type

Whether application/hal+json responses should be sent to requests that accept application/json.

true

spring.netty.leak-detection

Level of leak detection for reference-counted buffers. If not configured via 'ResourceLeakDetector.setLevel' or the 'io.netty.leakDetection.level' system property, default to 'simple'.
```

## mvc配置属性

```
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
```

## servlet multipart配置属性

```
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
```

## session配置属性

```
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
```

## web配置属性

```
spring.web.locale

Locale to use. By default, this locale is overridden by the "Accept-Language" header.

spring.web.locale-resolver

Define how the locale should be resolved.

accept-header
```

### web资源配置属性

```
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
```

## java文件

```

org.springframework.boot.web.client.BasicAuthentication
org.springframework.boot.web.client.ClientHttpRequestFactories
org.springframework.boot.web.client.ClientHttpRequestFactoriesRuntimeHints
org.springframework.boot.web.client.ClientHttpRequestFactorySettings
org.springframework.boot.web.client.ClientHttpRequestFactorySupplier

org.springframework.boot.web.client.RestTemplateBuilder
org.springframework.boot.web.client.RestTemplateBuilderClientHttpRequestInitializer
org.springframework.boot.web.client.RestTemplateCustomizer
org.springframework.boot.web.client.RestTemplateRequestCustomizer
org.springframework.boot.web.client.RootUriTemplateHandler
org.springframework.boot.web.codec.CodecCustomizer

org.springframework.boot.web.context.ConfigurableWebServerApplicationContext
org.springframework.boot.web.context.MissingWebServerFactoryBeanException
org.springframework.boot.web.context.MissingWebServerFactoryBeanFailureAnalyzer

org.springframework.boot.web.context.ServerPortInfoApplicationContextInitializer
org.springframework.boot.web.context.WebServerApplicationContext
org.springframework.boot.web.context.WebServerGracefulShutdownLifecycle
org.springframework.boot.web.context.WebServerInitializedEvent
org.springframework.boot.web.context.WebServerPortFileWriter
org.springframework.boot.web.embedded.jetty.ConfigurableJettyWebServerFactory
org.springframework.boot.web.embedded.jetty.ForwardHeadersCustomizer
org.springframework.boot.web.embedded.jetty.GracefulShutdown
org.springframework.boot.web.embedded.jetty.JasperInitializer
org.springframework.boot.web.embedded.jetty.JettyEmbeddedErrorHandler
org.springframework.boot.web.embedded.jetty.JettyEmbeddedWebAppContext
org.springframework.boot.web.embedded.jetty.JettyHandlerWrappers
org.springframework.boot.web.embedded.jetty.JettyReactiveWebServerFactory
org.springframework.boot.web.embedded.jetty.JettyServerCustomizer
org.springframework.boot.web.embedded.jetty.JettyServletWebServerFactory
org.springframework.boot.web.embedded.jetty.JettyWebServer

org.springframework.boot.web.embedded.jetty.ServletContextInitializerConfiguration
org.springframework.boot.web.embedded.jetty.SslServerCustomizer
org.springframework.boot.web.embedded.netty.CompressionCustomizer
org.springframework.boot.web.embedded.netty.GracefulShutdown
org.springframework.boot.web.embedded.netty.NettyReactiveWebServerFactory
org.springframework.boot.web.embedded.netty.NettyRouteProvider
org.springframework.boot.web.embedded.netty.NettyServerCustomizer
org.springframework.boot.web.embedded.netty.NettyWebServer

org.springframework.boot.web.embedded.netty.SslServerCustomizer
org.springframework.boot.web.embedded.tomcat.CompressionConnectorCustomizer
org.springframework.boot.web.embedded.tomcat.ConfigurableTomcatWebServerFactory
org.springframework.boot.web.embedded.tomcat.ConnectorStartFailedException
org.springframework.boot.web.embedded.tomcat.ConnectorStartFailureAnalyzer
org.springframework.boot.web.embedded.tomcat.DisableReferenceClearingContextCustomizer
org.springframework.boot.web.embedded.tomcat.GracefulShutdown
org.springframework.boot.web.embedded.tomcat.LazySessionIdGenerator

org.springframework.boot.web.embedded.tomcat.SslConnectorCustomizer
org.springframework.boot.web.embedded.tomcat.TldPatterns
org.springframework.boot.web.embedded.tomcat.TomcatConnectorCustomizer
org.springframework.boot.web.embedded.tomcat.TomcatContextCustomizer
org.springframework.boot.web.embedded.tomcat.TomcatEmbeddedContext
org.springframework.boot.web.embedded.tomcat.TomcatEmbeddedWebappClassLoader
org.springframework.boot.web.embedded.tomcat.TomcatProtocolHandlerCustomizer
org.springframework.boot.web.embedded.tomcat.TomcatReactiveWebServerFactory
org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory
org.springframework.boot.web.embedded.tomcat.TomcatStarter
org.springframework.boot.web.embedded.tomcat.TomcatWebServer
org.springframework.boot.web.embedded.undertow.AccessLogHttpHandlerFactory
org.springframework.boot.web.embedded.undertow.CompositeResourceManager
org.springframework.boot.web.embedded.undertow.CompressionHttpHandlerFactory
org.springframework.boot.web.embedded.undertow.ConfigurableUndertowWebServerFactory
org.springframework.boot.web.embedded.undertow.DeploymentManagerHttpHandlerFactory
org.springframework.boot.web.embedded.undertow.FileSessionPersistence
org.springframework.boot.web.embedded.undertow.HttpHandlerFactory
org.springframework.boot.web.embedded.undertow.JarResourceManager

org.springframework.boot.web.embedded.undertow.SslBuilderCustomizer
org.springframework.boot.web.embedded.undertow.UndertowBuilderCustomizer
org.springframework.boot.web.embedded.undertow.UndertowDeploymentInfoCustomizer
org.springframework.boot.web.embedded.undertow.UndertowReactiveWebServerFactory
org.springframework.boot.web.embedded.undertow.UndertowServletWebServer
org.springframework.boot.web.embedded.undertow.UndertowServletWebServerFactory
org.springframework.boot.web.embedded.undertow.UndertowWebServer
org.springframework.boot.web.embedded.undertow.UndertowWebServerFactoryDelegate
org.springframework.boot.web.error.ErrorAttributeOptions

org.springframework.boot.web.reactive.context.AnnotationConfigReactiveWebApplicationContext
org.springframework.boot.web.reactive.context.AnnotationConfigReactiveWebServerApplicationContext
org.springframework.boot.web.reactive.context.ApplicationReactiveWebEnvironment
org.springframework.boot.web.reactive.context.ConfigurableReactiveWebApplicationContext
org.springframework.boot.web.reactive.context.ConfigurableReactiveWebEnvironment
org.springframework.boot.web.reactive.context.FilteredReactiveWebContextResource
org.springframework.boot.web.reactive.context.GenericReactiveWebApplicationContext

org.springframework.boot.web.reactive.context.ReactiveWebApplicationContext
org.springframework.boot.web.reactive.context.ReactiveWebServerApplicationContext
org.springframework.boot.web.reactive.context.ReactiveWebServerApplicationContextFactory
org.springframework.boot.web.reactive.context.ReactiveWebServerInitializedEvent
org.springframework.boot.web.reactive.context.StandardReactiveWebEnvironment
org.springframework.boot.web.reactive.context.WebServerManager
org.springframework.boot.web.reactive.context.WebServerStartStopLifecycle
org.springframework.boot.web.reactive.error.DefaultErrorAttributes
org.springframework.boot.web.reactive.error.ErrorAttributes
org.springframework.boot.web.reactive.error.ErrorWebExceptionHandler

org.springframework.boot.web.reactive.filter.OrderedHiddenHttpMethodFilter
org.springframework.boot.web.reactive.filter.OrderedWebFilter


org.springframework.boot.web.reactive.function.client.WebClientCustomizer
org.springframework.boot.web.reactive.result.view.MustacheView
org.springframework.boot.web.reactive.result.view.MustacheViewResolver

org.springframework.boot.web.reactive.server.AbstractReactiveWebServerFactory
org.springframework.boot.web.reactive.server.ConfigurableReactiveWebServerFactory

org.springframework.boot.web.reactive.server.ReactiveWebServerFactory
org.springframework.boot.web.server.AbstractConfigurableWebServerFactory
org.springframework.boot.web.server.CertificateFileSslStoreProvider
org.springframework.boot.web.server.Compression
org.springframework.boot.web.server.ConfigurableWebServerFactory
org.springframework.boot.web.server.Cookie
org.springframework.boot.web.server.ErrorPage
org.springframework.boot.web.server.ErrorPageRegistrar
org.springframework.boot.web.server.ErrorPageRegistrarBeanPostProcessor
org.springframework.boot.web.server.ErrorPageRegistry
org.springframework.boot.web.server.GracefulShutdownCallback
org.springframework.boot.web.server.GracefulShutdownResult
org.springframework.boot.web.server.Http2
org.springframework.boot.web.server.MimeMappings

org.springframework.boot.web.server.PortInUseException
org.springframework.boot.web.server.Shutdown
org.springframework.boot.web.server.Ssl
org.springframework.boot.web.server.SslConfigurationValidator
org.springframework.boot.web.server.SslStoreProvider
org.springframework.boot.web.server.WebServer
org.springframework.boot.web.server.WebServerException
org.springframework.boot.web.server.WebServerFactory
org.springframework.boot.web.server.WebServerFactoryCustomizer
org.springframework.boot.web.server.WebServerFactoryCustomizerBeanPostProcessor
org.springframework.boot.web.server.WebServerSslBundle
org.springframework.boot.web.servlet.AbstractFilterRegistrationBean
org.springframework.boot.web.servlet.context.AnnotationConfigServletWebApplicationContext
org.springframework.boot.web.servlet.context.AnnotationConfigServletWebServerApplicationContext
org.springframework.boot.web.servlet.context.ApplicationServletEnvironment

org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext
org.springframework.boot.web.servlet.context.ServletWebServerApplicationContextFactory
org.springframework.boot.web.servlet.context.ServletWebServerInitializedEvent
org.springframework.boot.web.servlet.context.WebApplicationContextServletContextAwareProcessor
org.springframework.boot.web.servlet.context.WebServerStartStopLifecycle
org.springframework.boot.web.servlet.context.XmlServletWebServerApplicationContext
org.springframework.boot.web.servlet.DelegatingFilterProxyRegistrationBean
org.springframework.boot.web.servlet.DispatcherType
org.springframework.boot.web.servlet.DynamicRegistrationBean
org.springframework.boot.web.servlet.error.DefaultErrorAttributes
org.springframework.boot.web.servlet.error.ErrorAttributes
org.springframework.boot.web.servlet.error.ErrorController

org.springframework.boot.web.servlet.filter.ApplicationContextHeaderFilter
org.springframework.boot.web.servlet.filter.OrderedCharacterEncodingFilter
org.springframework.boot.web.servlet.filter.OrderedFilter
org.springframework.boot.web.servlet.filter.OrderedFormContentFilter
org.springframework.boot.web.servlet.filter.OrderedHiddenHttpMethodFilter
org.springframework.boot.web.servlet.filter.OrderedRequestContextFilter

org.springframework.boot.web.servlet.FilterRegistrationBean
org.springframework.boot.web.servlet.MultipartConfigFactory

org.springframework.boot.web.servlet.RegistrationBean
org.springframework.boot.web.servlet.server.AbstractServletWebServerFactory
org.springframework.boot.web.servlet.server.ConfigurableServletWebServerFactory
org.springframework.boot.web.servlet.server.CookieSameSiteSupplier
org.springframework.boot.web.servlet.server.DocumentRoot
org.springframework.boot.web.servlet.server.Encoding
org.springframework.boot.web.servlet.server.Jsp

org.springframework.boot.web.servlet.server.ServletWebServerFactory
org.springframework.boot.web.servlet.server.Session
org.springframework.boot.web.servlet.server.SessionStoreDirectory
org.springframework.boot.web.servlet.server.StaticResourceJars
org.springframework.boot.web.servlet.ServletComponentHandler
org.springframework.boot.web.servlet.ServletComponentRegisteringPostProcessor
org.springframework.boot.web.servlet.ServletComponentScan
org.springframework.boot.web.servlet.ServletComponentScanRegistrar
org.springframework.boot.web.servlet.ServletContextInitializer
org.springframework.boot.web.servlet.ServletContextInitializerBeans
org.springframework.boot.web.servlet.ServletListenerRegistrationBean
org.springframework.boot.web.servlet.ServletRegistrationBean
org.springframework.boot.web.servlet.support.ErrorPageFilter
org.springframework.boot.web.servlet.support.ErrorPageFilterConfiguration

org.springframework.boot.web.servlet.support.ServletContextApplicationContextInitializer
org.springframework.boot.web.servlet.support.SpringBootServletInitializer
org.springframework.boot.web.servlet.view.MustacheView
org.springframework.boot.web.servlet.view.MustacheViewResolver

org.springframework.boot.web.servlet.WebFilterHandler
org.springframework.boot.web.servlet.WebListenerHandler
org.springframework.boot.web.servlet.WebListenerRegistrar
org.springframework.boot.web.servlet.WebListenerRegistry
org.springframework.boot.web.servlet.WebServletHandler



org.springframework.boot.autoconfigure.web.client.RestTemplateAutoConfiguration
org.springframework.boot.autoconfigure.web.client.RestTemplateBuilderConfigurer
org.springframework.boot.autoconfigure.web.ConditionalOnEnabledResourceChain
org.springframework.boot.autoconfigure.web.embedded.EmbeddedWebServerFactoryCustomizerAutoConfiguration
org.springframework.boot.autoconfigure.web.embedded.JettyWebServerFactoryCustomizer
org.springframework.boot.autoconfigure.web.embedded.NettyWebServerFactoryCustomizer

org.springframework.boot.autoconfigure.web.embedded.TomcatWebServerFactoryCustomizer
org.springframework.boot.autoconfigure.web.embedded.UndertowWebServerFactoryCustomizer
org.springframework.boot.autoconfigure.web.ErrorProperties
org.springframework.boot.autoconfigure.web.OnEnabledResourceChainCondition

org.springframework.boot.autoconfigure.web.reactive.error.AbstractErrorWebExceptionHandler
org.springframework.boot.autoconfigure.web.reactive.error.DefaultErrorWebExceptionHandler
org.springframework.boot.autoconfigure.web.reactive.error.ErrorWebFluxAutoConfiguration

org.springframework.boot.autoconfigure.web.reactive.function.client.AutoConfiguredWebClientSsl
org.springframework.boot.autoconfigure.web.reactive.function.client.ClientHttpConnectorAutoConfiguration
org.springframework.boot.autoconfigure.web.reactive.function.client.ClientHttpConnectorFactory
org.springframework.boot.autoconfigure.web.reactive.function.client.ClientHttpConnectorFactoryConfiguration
org.springframework.boot.autoconfigure.web.reactive.function.client.HttpComponentsClientHttpConnectorFactory
org.springframework.boot.autoconfigure.web.reactive.function.client.JdkClientHttpConnectorFactory
org.springframework.boot.autoconfigure.web.reactive.function.client.JettyClientHttpConnectorFactory

org.springframework.boot.autoconfigure.web.reactive.function.client.ReactorClientHttpConnectorFactory
org.springframework.boot.autoconfigure.web.reactive.function.client.ReactorNettyHttpClientMapper
org.springframework.boot.autoconfigure.web.reactive.function.client.WebClientAutoConfiguration
org.springframework.boot.autoconfigure.web.reactive.function.client.WebClientCodecCustomizer
org.springframework.boot.autoconfigure.web.reactive.function.client.WebClientSsl
org.springframework.boot.autoconfigure.web.reactive.HttpHandlerAutoConfiguration

org.springframework.boot.autoconfigure.web.reactive.ProblemDetailsExceptionHandler
org.springframework.boot.autoconfigure.web.reactive.ReactiveMultipartAutoConfiguration
org.springframework.boot.autoconfigure.web.reactive.ReactiveMultipartProperties
org.springframework.boot.autoconfigure.web.reactive.ReactiveWebServerFactoryAutoConfiguration
org.springframework.boot.autoconfigure.web.reactive.ReactiveWebServerFactoryConfiguration
org.springframework.boot.autoconfigure.web.reactive.ReactiveWebServerFactoryCustomizer
org.springframework.boot.autoconfigure.web.reactive.ResourceChainResourceHandlerRegistrationCustomizer
org.springframework.boot.autoconfigure.web.reactive.ResourceHandlerRegistrationCustomizer
org.springframework.boot.autoconfigure.web.reactive.TomcatReactiveWebServerFactoryCustomizer
org.springframework.boot.autoconfigure.web.reactive.WebFluxAutoConfiguration
org.springframework.boot.autoconfigure.web.reactive.WebFluxProperties
org.springframework.boot.autoconfigure.web.reactive.WebFluxRegistrations
org.springframework.boot.autoconfigure.web.reactive.WebSessionIdResolverAutoConfiguration
org.springframework.boot.autoconfigure.web.reactive.WelcomePageRouterFunctionFactory
org.springframework.boot.autoconfigure.web.ServerProperties
org.springframework.boot.autoconfigure.web.servlet.ConditionalOnMissingFilterBean
org.springframework.boot.autoconfigure.web.servlet.DefaultJerseyApplicationPath
org.springframework.boot.autoconfigure.web.servlet.DispatcherServletAutoConfiguration
org.springframework.boot.autoconfigure.web.servlet.DispatcherServletPath
org.springframework.boot.autoconfigure.web.servlet.DispatcherServletRegistrationBean
org.springframework.boot.autoconfigure.web.servlet.error.AbstractErrorController
org.springframework.boot.autoconfigure.web.servlet.error.BasicErrorController
org.springframework.boot.autoconfigure.web.servlet.error.DefaultErrorViewResolver
org.springframework.boot.autoconfigure.web.servlet.error.ErrorMvcAutoConfiguration
org.springframework.boot.autoconfigure.web.servlet.error.ErrorViewResolver

org.springframework.boot.autoconfigure.web.servlet.HttpEncodingAutoConfiguration
org.springframework.boot.autoconfigure.web.servlet.JerseyApplicationPath
org.springframework.boot.autoconfigure.web.servlet.JspTemplateAvailabilityProvider
org.springframework.boot.autoconfigure.web.servlet.MultipartAutoConfiguration
org.springframework.boot.autoconfigure.web.servlet.MultipartProperties

org.springframework.boot.autoconfigure.web.servlet.ProblemDetailsExceptionHandler
org.springframework.boot.autoconfigure.web.servlet.ServletWebServerFactoryAutoConfiguration
org.springframework.boot.autoconfigure.web.servlet.ServletWebServerFactoryConfiguration
org.springframework.boot.autoconfigure.web.servlet.ServletWebServerFactoryCustomizer
org.springframework.boot.autoconfigure.web.servlet.TomcatServletWebServerFactoryCustomizer
org.springframework.boot.autoconfigure.web.servlet.UndertowServletWebServerFactoryCustomizer
org.springframework.boot.autoconfigure.web.servlet.WebMvcAutoConfiguration
org.springframework.boot.autoconfigure.web.servlet.WebMvcProperties
org.springframework.boot.autoconfigure.web.servlet.WebMvcRegistrations
org.springframework.boot.autoconfigure.web.servlet.WelcomePage
org.springframework.boot.autoconfigure.web.servlet.WelcomePageHandlerMapping
org.springframework.boot.autoconfigure.web.servlet.WelcomePageNotAcceptableHandlerMapping
org.springframework.boot.autoconfigure.web.WebProperties
org.springframework.boot.autoconfigure.web.WebResourcesRuntimeHints



org.springframework.boot.actuate.web.exchanges.HttpExchange
org.springframework.boot.actuate.web.exchanges.HttpExchangeRepository
org.springframework.boot.actuate.web.exchanges.HttpExchangesEndpoint
org.springframework.boot.actuate.web.exchanges.Include
org.springframework.boot.actuate.web.exchanges.InMemoryHttpExchangeRepository

org.springframework.boot.actuate.web.exchanges.reactive.HttpExchangesWebFilter

org.springframework.boot.actuate.web.exchanges.reactive.RecordableServerHttpRequest
org.springframework.boot.actuate.web.exchanges.reactive.RecordableServerHttpResponse
org.springframework.boot.actuate.web.exchanges.RecordableHttpRequest
org.springframework.boot.actuate.web.exchanges.RecordableHttpResponse
org.springframework.boot.actuate.web.exchanges.servlet.HttpExchangesFilter

org.springframework.boot.actuate.web.exchanges.servlet.RecordableServletHttpRequest
org.springframework.boot.actuate.web.exchanges.servlet.RecordableServletHttpResponse
org.springframework.boot.actuate.web.mappings.HandlerMethodDescription
org.springframework.boot.actuate.web.mappings.MappingDescriptionProvider
org.springframework.boot.actuate.web.mappings.MappingsEndpoint

org.springframework.boot.actuate.web.mappings.reactive.DispatcherHandlerMappingDescription
org.springframework.boot.actuate.web.mappings.reactive.DispatcherHandlerMappingDetails
org.springframework.boot.actuate.web.mappings.reactive.DispatcherHandlersMappingDescriptionProvider
org.springframework.boot.actuate.web.mappings.reactive.HandlerFunctionDescription

org.springframework.boot.actuate.web.mappings.reactive.RequestMappingConditionsDescription
org.springframework.boot.actuate.web.mappings.servlet.DispatcherServletHandlerMappings
org.springframework.boot.actuate.web.mappings.servlet.DispatcherServletMappingDescription
org.springframework.boot.actuate.web.mappings.servlet.DispatcherServletMappingDetails
org.springframework.boot.actuate.web.mappings.servlet.DispatcherServletsMappingDescriptionProvider
org.springframework.boot.actuate.web.mappings.servlet.FilterRegistrationMappingDescription
org.springframework.boot.actuate.web.mappings.servlet.FiltersMappingDescriptionProvider

org.springframework.boot.actuate.web.mappings.servlet.RegistrationMappingDescription
org.springframework.boot.actuate.web.mappings.servlet.RequestMappingConditionsDescription
org.springframework.boot.actuate.web.mappings.servlet.ServletRegistrationMappingDescription
org.springframework.boot.actuate.web.mappings.servlet.ServletsMappingDescriptionProvider



org.springframework.boot.actuate.autoconfigure.web.exchanges.HttpExchangesAutoConfiguration
org.springframework.boot.actuate.autoconfigure.web.exchanges.HttpExchangesEndpointAutoConfiguration
org.springframework.boot.actuate.autoconfigure.web.exchanges.HttpExchangesProperties

org.springframework.boot.actuate.autoconfigure.web.jersey.JerseyChildManagementContextConfiguration
org.springframework.boot.actuate.autoconfigure.web.jersey.JerseyManagementContextConfiguration
org.springframework.boot.actuate.autoconfigure.web.jersey.JerseySameManagementContextConfiguration
org.springframework.boot.actuate.autoconfigure.web.jersey.ManagementContextResourceConfigCustomizer

org.springframework.boot.actuate.autoconfigure.web.ManagementContextConfiguration
org.springframework.boot.actuate.autoconfigure.web.ManagementContextFactory
org.springframework.boot.actuate.autoconfigure.web.ManagementContextType
org.springframework.boot.actuate.autoconfigure.web.mappings.MappingsEndpointAutoConfiguration



org.springframework.boot.actuate.autoconfigure.web.reactive.ReactiveManagementChildContextConfiguration
org.springframework.boot.actuate.autoconfigure.web.reactive.ReactiveManagementContextAutoConfiguration
org.springframework.boot.actuate.autoconfigure.web.server.ChildManagementContextInitializer
org.springframework.boot.actuate.autoconfigure.web.server.ConditionalOnManagementPort
org.springframework.boot.actuate.autoconfigure.web.server.EnableChildManagementContextConfiguration
org.springframework.boot.actuate.autoconfigure.web.server.EnableManagementContext
org.springframework.boot.actuate.autoconfigure.web.server.ManagementContextAutoConfiguration
org.springframework.boot.actuate.autoconfigure.web.server.ManagementContextConfigurationImportSelector
org.springframework.boot.actuate.autoconfigure.web.server.ManagementPortType
org.springframework.boot.actuate.autoconfigure.web.server.ManagementServerProperties
org.springframework.boot.actuate.autoconfigure.web.server.ManagementWebServerFactoryCustomizer
org.springframework.boot.actuate.autoconfigure.web.server.OnManagementPortCondition

org.springframework.boot.actuate.autoconfigure.web.servlet.CompositeHandlerAdapter
org.springframework.boot.actuate.autoconfigure.web.servlet.CompositeHandlerExceptionResolver
org.springframework.boot.actuate.autoconfigure.web.servlet.CompositeHandlerMapping
org.springframework.boot.actuate.autoconfigure.web.servlet.ManagementErrorEndpoint
org.springframework.boot.actuate.autoconfigure.web.servlet.ManagementServletContext

org.springframework.boot.actuate.autoconfigure.web.servlet.ServletManagementChildContextConfiguration
org.springframework.boot.actuate.autoconfigure.web.servlet.ServletManagementContextAutoConfiguration
org.springframework.boot.actuate.autoconfigure.web.servlet.WebMvcEndpointChildContextConfiguration

```
































