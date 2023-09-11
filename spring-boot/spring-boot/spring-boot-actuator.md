# spring-boot-actuator

## 构件信息

```
# 地址
https://spring.io
https://spring.io/projects/spring-boot

https://github.com/spring-projects/spring-boot
https://github.com/spring-projects/spring-boot/issues

git://github.com/spring-projects/spring-boot.git
ssh://git@github.com/spring-projects/spring-boot.git

# 构件
org.springframework.boot:spring-boot-actuator:3.1.3

# 依赖：compile
org.springframework.boot:spring-boot:3.1.3
```

## java文件

```

org.springframework.boot.actuate.amqp.RabbitHealthIndicator
org.springframework.boot.actuate.audit.AuditEvent
org.springframework.boot.actuate.audit.AuditEventRepository
org.springframework.boot.actuate.audit.AuditEventsEndpoint
org.springframework.boot.actuate.audit.InMemoryAuditEventRepository
org.springframework.boot.actuate.audit.listener.AbstractAuditListener
org.springframework.boot.actuate.audit.listener.AuditApplicationEvent
org.springframework.boot.actuate.audit.listener.AuditListener


org.springframework.boot.actuate.availability.AvailabilityStateHealthIndicator
org.springframework.boot.actuate.availability.LivenessStateHealthIndicator

org.springframework.boot.actuate.availability.ReadinessStateHealthIndicator
org.springframework.boot.actuate.beans.BeansEndpoint

org.springframework.boot.actuate.cache.CachesEndpoint
org.springframework.boot.actuate.cache.CachesEndpointWebExtension
org.springframework.boot.actuate.cache.NonUniqueCacheException

org.springframework.boot.actuate.cassandra.CassandraDriverHealthIndicator
org.springframework.boot.actuate.cassandra.CassandraDriverReactiveHealthIndicator


org.springframework.boot.actuate.context.properties.ConfigurationPropertiesReportEndpoint
org.springframework.boot.actuate.context.properties.ConfigurationPropertiesReportEndpointWebExtension

org.springframework.boot.actuate.context.ShutdownEndpoint
org.springframework.boot.actuate.couchbase.CouchbaseHealth
org.springframework.boot.actuate.couchbase.CouchbaseHealthIndicator
org.springframework.boot.actuate.couchbase.CouchbaseReactiveHealthIndicator

org.springframework.boot.actuate.data.elasticsearch.ElasticsearchReactiveHealthIndicator

org.springframework.boot.actuate.data.mongo.MongoHealthIndicator
org.springframework.boot.actuate.data.mongo.MongoReactiveHealthIndicator



org.springframework.boot.actuate.data.redis.RedisHealth
org.springframework.boot.actuate.data.redis.RedisHealthIndicator
org.springframework.boot.actuate.data.redis.RedisReactiveHealthIndicator
org.springframework.boot.actuate.elasticsearch.ElasticsearchRestClientHealthIndicator

org.springframework.boot.actuate.endpoint.AbstractExposableEndpoint
org.springframework.boot.actuate.endpoint.annotation.AbstractDiscoveredEndpoint
org.springframework.boot.actuate.endpoint.annotation.AbstractDiscoveredOperation
org.springframework.boot.actuate.endpoint.annotation.DeleteOperation
org.springframework.boot.actuate.endpoint.annotation.DiscoveredEndpoint
org.springframework.boot.actuate.endpoint.annotation.DiscoveredOperationMethod
org.springframework.boot.actuate.endpoint.annotation.DiscoveredOperationsFactory
org.springframework.boot.actuate.endpoint.annotation.DiscovererEndpointFilter
org.springframework.boot.actuate.endpoint.annotation.Endpoint
org.springframework.boot.actuate.endpoint.annotation.EndpointConverter
org.springframework.boot.actuate.endpoint.annotation.EndpointDiscoverer
org.springframework.boot.actuate.endpoint.annotation.EndpointExtension
org.springframework.boot.actuate.endpoint.annotation.FilteredEndpoint
org.springframework.boot.actuate.endpoint.annotation.OperationReflectiveProcessor

org.springframework.boot.actuate.endpoint.annotation.ReadOperation
org.springframework.boot.actuate.endpoint.annotation.Selector
org.springframework.boot.actuate.endpoint.annotation.WriteOperation
org.springframework.boot.actuate.endpoint.ApiVersion
org.springframework.boot.actuate.endpoint.EndpointFilter
org.springframework.boot.actuate.endpoint.EndpointId
org.springframework.boot.actuate.endpoint.EndpointsSupplier
org.springframework.boot.actuate.endpoint.ExposableEndpoint
org.springframework.boot.actuate.endpoint.InvalidEndpointRequestException
org.springframework.boot.actuate.endpoint.InvocationContext
org.springframework.boot.actuate.endpoint.invoke.convert.ConversionServiceParameterValueMapper
org.springframework.boot.actuate.endpoint.invoke.convert.IsoOffsetDateTimeConverter

org.springframework.boot.actuate.endpoint.invoke.MissingParametersException
org.springframework.boot.actuate.endpoint.invoke.OperationInvoker
org.springframework.boot.actuate.endpoint.invoke.OperationInvokerAdvisor
org.springframework.boot.actuate.endpoint.invoke.OperationParameter
org.springframework.boot.actuate.endpoint.invoke.OperationParameters

org.springframework.boot.actuate.endpoint.invoke.ParameterMappingException
org.springframework.boot.actuate.endpoint.invoke.ParameterValueMapper
org.springframework.boot.actuate.endpoint.invoke.reflect.OperationMethod
org.springframework.boot.actuate.endpoint.invoke.reflect.OperationMethodParameter
org.springframework.boot.actuate.endpoint.invoke.reflect.OperationMethodParameters

org.springframework.boot.actuate.endpoint.invoke.reflect.ReflectiveOperationInvoker
org.springframework.boot.actuate.endpoint.invoker.cache.CachingOperationInvoker
org.springframework.boot.actuate.endpoint.invoker.cache.CachingOperationInvokerAdvisor

org.springframework.boot.actuate.endpoint.jackson.EndpointObjectMapper

org.springframework.boot.actuate.endpoint.jmx.annotation.DiscoveredJmxEndpoint
org.springframework.boot.actuate.endpoint.jmx.annotation.DiscoveredJmxOperation
org.springframework.boot.actuate.endpoint.jmx.annotation.EndpointJmxExtension
org.springframework.boot.actuate.endpoint.jmx.annotation.JmxEndpoint
org.springframework.boot.actuate.endpoint.jmx.annotation.JmxEndpointDiscoverer
org.springframework.boot.actuate.endpoint.jmx.annotation.JmxEndpointFilter

org.springframework.boot.actuate.endpoint.jmx.EndpointMBean
org.springframework.boot.actuate.endpoint.jmx.EndpointObjectNameFactory
org.springframework.boot.actuate.endpoint.jmx.ExposableJmxEndpoint
org.springframework.boot.actuate.endpoint.jmx.JacksonJmxOperationResponseMapper
org.springframework.boot.actuate.endpoint.jmx.JmxEndpointExporter
org.springframework.boot.actuate.endpoint.jmx.JmxEndpointsSupplier
org.springframework.boot.actuate.endpoint.jmx.JmxOperation
org.springframework.boot.actuate.endpoint.jmx.JmxOperationParameter
org.springframework.boot.actuate.endpoint.jmx.JmxOperationResponseMapper
org.springframework.boot.actuate.endpoint.jmx.MBeanInfoFactory

org.springframework.boot.actuate.endpoint.Operation
org.springframework.boot.actuate.endpoint.OperationArgumentResolver
org.springframework.boot.actuate.endpoint.OperationResponseBody
org.springframework.boot.actuate.endpoint.OperationResponseBodyMap
org.springframework.boot.actuate.endpoint.OperationType

org.springframework.boot.actuate.endpoint.Producible
org.springframework.boot.actuate.endpoint.ProducibleOperationArgumentResolver
org.springframework.boot.actuate.endpoint.SanitizableData
org.springframework.boot.actuate.endpoint.Sanitizer
org.springframework.boot.actuate.endpoint.SanitizingFunction
org.springframework.boot.actuate.endpoint.SecurityContext
org.springframework.boot.actuate.endpoint.Show
org.springframework.boot.actuate.endpoint.web.annotation.ControllerEndpoint
org.springframework.boot.actuate.endpoint.web.annotation.ControllerEndpointDiscoverer
org.springframework.boot.actuate.endpoint.web.annotation.ControllerEndpointFilter
org.springframework.boot.actuate.endpoint.web.annotation.ControllerEndpointsSupplier
org.springframework.boot.actuate.endpoint.web.annotation.DiscoveredControllerEndpoint
org.springframework.boot.actuate.endpoint.web.annotation.DiscoveredServletEndpoint
org.springframework.boot.actuate.endpoint.web.annotation.DiscoveredWebEndpoint
org.springframework.boot.actuate.endpoint.web.annotation.DiscoveredWebOperation
org.springframework.boot.actuate.endpoint.web.annotation.EndpointWebExtension
org.springframework.boot.actuate.endpoint.web.annotation.ExposableControllerEndpoint

org.springframework.boot.actuate.endpoint.web.annotation.RequestPredicateFactory
org.springframework.boot.actuate.endpoint.web.annotation.RestControllerEndpoint
org.springframework.boot.actuate.endpoint.web.annotation.ServletEndpoint
org.springframework.boot.actuate.endpoint.web.annotation.ServletEndpointDiscoverer
org.springframework.boot.actuate.endpoint.web.annotation.ServletEndpointFilter
org.springframework.boot.actuate.endpoint.web.annotation.ServletEndpointsSupplier
org.springframework.boot.actuate.endpoint.web.annotation.WebEndpoint
org.springframework.boot.actuate.endpoint.web.annotation.WebEndpointDiscoverer
org.springframework.boot.actuate.endpoint.web.annotation.WebEndpointFilter
org.springframework.boot.actuate.endpoint.web.EndpointLinksResolver
org.springframework.boot.actuate.endpoint.web.EndpointMapping
org.springframework.boot.actuate.endpoint.web.EndpointMediaTypes
org.springframework.boot.actuate.endpoint.web.EndpointServlet
org.springframework.boot.actuate.endpoint.web.ExposableServletEndpoint
org.springframework.boot.actuate.endpoint.web.ExposableWebEndpoint
org.springframework.boot.actuate.endpoint.web.jersey.JerseyEndpointResourceFactory
org.springframework.boot.actuate.endpoint.web.jersey.JerseyHealthEndpointAdditionalPathResourceFactory
org.springframework.boot.actuate.endpoint.web.jersey.JerseyRemainingPathSegmentProvider

org.springframework.boot.actuate.endpoint.web.Link

org.springframework.boot.actuate.endpoint.web.PathMappedEndpoint
org.springframework.boot.actuate.endpoint.web.PathMappedEndpoints
org.springframework.boot.actuate.endpoint.web.PathMapper
org.springframework.boot.actuate.endpoint.web.reactive.AbstractWebFluxEndpointHandlerMapping
org.springframework.boot.actuate.endpoint.web.reactive.AdditionalHealthEndpointPathsWebFluxHandlerMapping
org.springframework.boot.actuate.endpoint.web.reactive.ControllerEndpointHandlerMapping

org.springframework.boot.actuate.endpoint.web.reactive.WebFluxEndpointHandlerMapping
org.springframework.boot.actuate.endpoint.web.servlet.AbstractWebMvcEndpointHandlerMapping
org.springframework.boot.actuate.endpoint.web.servlet.AdditionalHealthEndpointPathsWebMvcHandlerMapping
org.springframework.boot.actuate.endpoint.web.servlet.ControllerEndpointHandlerMapping

org.springframework.boot.actuate.endpoint.web.servlet.SkipPathExtensionContentNegotiation
org.springframework.boot.actuate.endpoint.web.servlet.WebMvcEndpointHandlerMapping
org.springframework.boot.actuate.endpoint.web.ServletEndpointRegistrar
org.springframework.boot.actuate.endpoint.web.WebEndpointHttpMethod
org.springframework.boot.actuate.endpoint.web.WebEndpointResponse
org.springframework.boot.actuate.endpoint.web.WebEndpointsSupplier
org.springframework.boot.actuate.endpoint.web.WebOperation
org.springframework.boot.actuate.endpoint.web.WebOperationRequestPredicate
org.springframework.boot.actuate.endpoint.web.WebServerNamespace
org.springframework.boot.actuate.env.EnvironmentEndpoint
org.springframework.boot.actuate.env.EnvironmentEndpointWebExtension

org.springframework.boot.actuate.flyway.FlywayEndpoint

org.springframework.boot.actuate.hazelcast.HazelcastHealthIndicator

org.springframework.boot.actuate.health.AbstractHealthIndicator
org.springframework.boot.actuate.health.AbstractReactiveHealthIndicator
org.springframework.boot.actuate.health.AdditionalHealthEndpointPath
org.springframework.boot.actuate.health.CompositeHealth
org.springframework.boot.actuate.health.CompositeHealthContributor
org.springframework.boot.actuate.health.CompositeHealthContributorMapAdapter
org.springframework.boot.actuate.health.CompositeHealthContributorReactiveAdapter
org.springframework.boot.actuate.health.CompositeReactiveHealthContributor
org.springframework.boot.actuate.health.CompositeReactiveHealthContributorMapAdapter
org.springframework.boot.actuate.health.ContributorRegistry
org.springframework.boot.actuate.health.DefaultContributorRegistry
org.springframework.boot.actuate.health.DefaultHealthContributorRegistry
org.springframework.boot.actuate.health.DefaultReactiveHealthContributorRegistry
org.springframework.boot.actuate.health.Health
org.springframework.boot.actuate.health.HealthComponent
org.springframework.boot.actuate.health.HealthContributor
org.springframework.boot.actuate.health.HealthContributorNameFactory
org.springframework.boot.actuate.health.HealthContributorRegistry
org.springframework.boot.actuate.health.HealthEndpoint
org.springframework.boot.actuate.health.HealthEndpointGroup
org.springframework.boot.actuate.health.HealthEndpointGroups
org.springframework.boot.actuate.health.HealthEndpointGroupsPostProcessor
org.springframework.boot.actuate.health.HealthEndpointSupport
org.springframework.boot.actuate.health.HealthEndpointWebExtension
org.springframework.boot.actuate.health.HealthEndpointWebExtensionRuntimeHints
org.springframework.boot.actuate.health.HealthIndicator
org.springframework.boot.actuate.health.HealthIndicatorReactiveAdapter
org.springframework.boot.actuate.health.HttpCodeStatusMapper
org.springframework.boot.actuate.health.NamedContributor
org.springframework.boot.actuate.health.NamedContributors
org.springframework.boot.actuate.health.NamedContributorsMapAdapter

org.springframework.boot.actuate.health.PingHealthIndicator
org.springframework.boot.actuate.health.ReactiveHealthContributor
org.springframework.boot.actuate.health.ReactiveHealthContributorRegistry
org.springframework.boot.actuate.health.ReactiveHealthEndpointWebExtension
org.springframework.boot.actuate.health.ReactiveHealthIndicator
org.springframework.boot.actuate.health.SimpleHttpCodeStatusMapper
org.springframework.boot.actuate.health.SimpleStatusAggregator
org.springframework.boot.actuate.health.Status
org.springframework.boot.actuate.health.StatusAggregator
org.springframework.boot.actuate.health.SystemHealth
org.springframework.boot.actuate.influx.InfluxDbHealthIndicator

org.springframework.boot.actuate.info.BuildInfoContributor
org.springframework.boot.actuate.info.EnvironmentInfoContributor
org.springframework.boot.actuate.info.GitInfoContributor
org.springframework.boot.actuate.info.Info
org.springframework.boot.actuate.info.InfoContributor
org.springframework.boot.actuate.info.InfoEndpoint
org.springframework.boot.actuate.info.InfoPropertiesInfoContributor
org.springframework.boot.actuate.info.JavaInfoContributor
org.springframework.boot.actuate.info.MapInfoContributor
org.springframework.boot.actuate.info.OsInfoContributor

org.springframework.boot.actuate.info.SimpleInfoContributor
org.springframework.boot.actuate.integration.IntegrationGraphEndpoint

org.springframework.boot.actuate.jdbc.DataSourceHealthIndicator

org.springframework.boot.actuate.jms.JmsHealthIndicator

org.springframework.boot.actuate.ldap.LdapHealthIndicator

org.springframework.boot.actuate.liquibase.LiquibaseEndpoint

org.springframework.boot.actuate.mail.MailHealthIndicator

org.springframework.boot.actuate.management.HeapDumpWebEndpoint

org.springframework.boot.actuate.management.PlainTextThreadDumpFormatter
org.springframework.boot.actuate.management.ThreadDumpEndpoint

org.springframework.boot.actuate.metrics.amqp.RabbitMetrics

org.springframework.boot.actuate.metrics.annotation.TimedAnnotations
org.springframework.boot.actuate.metrics.AutoTimer
org.springframework.boot.actuate.metrics.cache.Cache2kCacheMeterBinderProvider
org.springframework.boot.actuate.metrics.cache.CacheMeterBinderProvider
org.springframework.boot.actuate.metrics.cache.CacheMetricsRegistrar
org.springframework.boot.actuate.metrics.cache.CaffeineCacheMeterBinderProvider
org.springframework.boot.actuate.metrics.cache.HazelcastCacheMeterBinderProvider
org.springframework.boot.actuate.metrics.cache.JCacheCacheMeterBinderProvider

org.springframework.boot.actuate.metrics.cache.RedisCacheMeterBinderProvider
org.springframework.boot.actuate.metrics.cache.RedisCacheMetrics
org.springframework.boot.actuate.metrics.data.DefaultRepositoryTagsProvider
org.springframework.boot.actuate.metrics.data.MetricsRepositoryMethodInvocationListener

org.springframework.boot.actuate.metrics.data.RepositoryTagsProvider

org.springframework.boot.actuate.metrics.export.prometheus.PrometheusPushGatewayManager
org.springframework.boot.actuate.metrics.export.prometheus.PrometheusScrapeEndpoint
org.springframework.boot.actuate.metrics.export.prometheus.TextOutputFormat
org.springframework.boot.actuate.metrics.http.Outcome

org.springframework.boot.actuate.metrics.jdbc.DataSourcePoolMetrics

org.springframework.boot.actuate.metrics.MetricsEndpoint

org.springframework.boot.actuate.metrics.r2dbc.ConnectionPoolMetrics


org.springframework.boot.actuate.metrics.startup.StartupTimeMetricsListener
org.springframework.boot.actuate.metrics.system.DiskSpaceMetricsBinder

org.springframework.boot.actuate.metrics.web.client.DefaultRestTemplateExchangeTagsProvider
org.springframework.boot.actuate.metrics.web.client.ObservationRestTemplateCustomizer

org.springframework.boot.actuate.metrics.web.client.RestTemplateExchangeTags
org.springframework.boot.actuate.metrics.web.client.RestTemplateExchangeTagsProvider
org.springframework.boot.actuate.metrics.web.jetty.AbstractJettyMetricsBinder
org.springframework.boot.actuate.metrics.web.jetty.JettyConnectionMetricsBinder
org.springframework.boot.actuate.metrics.web.jetty.JettyServerThreadPoolMetricsBinder
org.springframework.boot.actuate.metrics.web.jetty.JettySslHandshakeMetricsBinder

org.springframework.boot.actuate.metrics.web.reactive.client.DefaultWebClientExchangeTagsProvider
org.springframework.boot.actuate.metrics.web.reactive.client.ObservationWebClientCustomizer

org.springframework.boot.actuate.metrics.web.reactive.client.WebClientExchangeTags
org.springframework.boot.actuate.metrics.web.reactive.client.WebClientExchangeTagsProvider
org.springframework.boot.actuate.metrics.web.reactive.server.DefaultWebFluxTagsProvider

org.springframework.boot.actuate.metrics.web.reactive.server.WebFluxTags
org.springframework.boot.actuate.metrics.web.reactive.server.WebFluxTagsContributor
org.springframework.boot.actuate.metrics.web.reactive.server.WebFluxTagsProvider
org.springframework.boot.actuate.metrics.web.servlet.DefaultWebMvcTagsProvider

org.springframework.boot.actuate.metrics.web.servlet.WebMvcTags
org.springframework.boot.actuate.metrics.web.servlet.WebMvcTagsContributor
org.springframework.boot.actuate.metrics.web.servlet.WebMvcTagsProvider

org.springframework.boot.actuate.metrics.web.tomcat.TomcatMetricsBinder
org.springframework.boot.actuate.neo4j.Neo4jHealthDetails
org.springframework.boot.actuate.neo4j.Neo4jHealthDetailsHandler
org.springframework.boot.actuate.neo4j.Neo4jHealthIndicator
org.springframework.boot.actuate.neo4j.Neo4jReactiveHealthIndicator


org.springframework.boot.actuate.quartz.QuartzEndpoint
org.springframework.boot.actuate.quartz.QuartzEndpointWebExtension
org.springframework.boot.actuate.r2dbc.ConnectionFactoryHealthIndicator


org.springframework.boot.actuate.scheduling.ScheduledTasksEndpoint
org.springframework.boot.actuate.security.AbstractAuthenticationAuditListener
org.springframework.boot.actuate.security.AbstractAuthorizationAuditListener
org.springframework.boot.actuate.security.AuthenticationAuditListener
org.springframework.boot.actuate.security.AuthorizationAuditListener


org.springframework.boot.actuate.session.SessionsEndpoint

org.springframework.boot.actuate.startup.StartupEndpoint
org.springframework.boot.actuate.system.DiskSpaceHealthIndicator

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

```

