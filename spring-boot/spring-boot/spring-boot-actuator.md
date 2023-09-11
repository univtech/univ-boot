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

org.springframework.boot.actuate.amqp.RabbitHealthIndicator.java
org.springframework.boot.actuate.audit.AuditEvent.java
org.springframework.boot.actuate.audit.AuditEventRepository.java
org.springframework.boot.actuate.audit.AuditEventsEndpoint.java
org.springframework.boot.actuate.audit.InMemoryAuditEventRepository.java
org.springframework.boot.actuate.audit.listener.AbstractAuditListener.java
org.springframework.boot.actuate.audit.listener.AuditApplicationEvent.java
org.springframework.boot.actuate.audit.listener.AuditListener.java


org.springframework.boot.actuate.availability.AvailabilityStateHealthIndicator.java
org.springframework.boot.actuate.availability.LivenessStateHealthIndicator.java

org.springframework.boot.actuate.availability.ReadinessStateHealthIndicator.java
org.springframework.boot.actuate.beans.BeansEndpoint.java

org.springframework.boot.actuate.cache.CachesEndpoint.java
org.springframework.boot.actuate.cache.CachesEndpointWebExtension.java
org.springframework.boot.actuate.cache.NonUniqueCacheException.java

org.springframework.boot.actuate.cassandra.CassandraDriverHealthIndicator.java
org.springframework.boot.actuate.cassandra.CassandraDriverReactiveHealthIndicator.java


org.springframework.boot.actuate.context.properties.ConfigurationPropertiesReportEndpoint.java
org.springframework.boot.actuate.context.properties.ConfigurationPropertiesReportEndpointWebExtension.java

org.springframework.boot.actuate.context.ShutdownEndpoint.java
org.springframework.boot.actuate.couchbase.CouchbaseHealth.java
org.springframework.boot.actuate.couchbase.CouchbaseHealthIndicator.java
org.springframework.boot.actuate.couchbase.CouchbaseReactiveHealthIndicator.java

org.springframework.boot.actuate.data.elasticsearch.ElasticsearchReactiveHealthIndicator.java

org.springframework.boot.actuate.data.mongo.MongoHealthIndicator.java
org.springframework.boot.actuate.data.mongo.MongoReactiveHealthIndicator.java



org.springframework.boot.actuate.data.redis.RedisHealth.java
org.springframework.boot.actuate.data.redis.RedisHealthIndicator.java
org.springframework.boot.actuate.data.redis.RedisReactiveHealthIndicator.java
org.springframework.boot.actuate.elasticsearch.ElasticsearchRestClientHealthIndicator.java

org.springframework.boot.actuate.endpoint.AbstractExposableEndpoint.java
org.springframework.boot.actuate.endpoint.annotation.AbstractDiscoveredEndpoint.java
org.springframework.boot.actuate.endpoint.annotation.AbstractDiscoveredOperation.java
org.springframework.boot.actuate.endpoint.annotation.DeleteOperation.java
org.springframework.boot.actuate.endpoint.annotation.DiscoveredEndpoint.java
org.springframework.boot.actuate.endpoint.annotation.DiscoveredOperationMethod.java
org.springframework.boot.actuate.endpoint.annotation.DiscoveredOperationsFactory.java
org.springframework.boot.actuate.endpoint.annotation.DiscovererEndpointFilter.java
org.springframework.boot.actuate.endpoint.annotation.Endpoint.java
org.springframework.boot.actuate.endpoint.annotation.EndpointConverter.java
org.springframework.boot.actuate.endpoint.annotation.EndpointDiscoverer.java
org.springframework.boot.actuate.endpoint.annotation.EndpointExtension.java
org.springframework.boot.actuate.endpoint.annotation.FilteredEndpoint.java
org.springframework.boot.actuate.endpoint.annotation.OperationReflectiveProcessor.java

org.springframework.boot.actuate.endpoint.annotation.ReadOperation.java
org.springframework.boot.actuate.endpoint.annotation.Selector.java
org.springframework.boot.actuate.endpoint.annotation.WriteOperation.java
org.springframework.boot.actuate.endpoint.ApiVersion.java
org.springframework.boot.actuate.endpoint.EndpointFilter.java
org.springframework.boot.actuate.endpoint.EndpointId.java
org.springframework.boot.actuate.endpoint.EndpointsSupplier.java
org.springframework.boot.actuate.endpoint.ExposableEndpoint.java
org.springframework.boot.actuate.endpoint.InvalidEndpointRequestException.java
org.springframework.boot.actuate.endpoint.InvocationContext.java
org.springframework.boot.actuate.endpoint.invoke.convert.ConversionServiceParameterValueMapper.java
org.springframework.boot.actuate.endpoint.invoke.convert.IsoOffsetDateTimeConverter.java

org.springframework.boot.actuate.endpoint.invoke.MissingParametersException.java
org.springframework.boot.actuate.endpoint.invoke.OperationInvoker.java
org.springframework.boot.actuate.endpoint.invoke.OperationInvokerAdvisor.java
org.springframework.boot.actuate.endpoint.invoke.OperationParameter.java
org.springframework.boot.actuate.endpoint.invoke.OperationParameters.java

org.springframework.boot.actuate.endpoint.invoke.ParameterMappingException.java
org.springframework.boot.actuate.endpoint.invoke.ParameterValueMapper.java
org.springframework.boot.actuate.endpoint.invoke.reflect.OperationMethod.java
org.springframework.boot.actuate.endpoint.invoke.reflect.OperationMethodParameter.java
org.springframework.boot.actuate.endpoint.invoke.reflect.OperationMethodParameters.java

org.springframework.boot.actuate.endpoint.invoke.reflect.ReflectiveOperationInvoker.java
org.springframework.boot.actuate.endpoint.invoker.cache.CachingOperationInvoker.java
org.springframework.boot.actuate.endpoint.invoker.cache.CachingOperationInvokerAdvisor.java

org.springframework.boot.actuate.endpoint.jackson.EndpointObjectMapper.java

org.springframework.boot.actuate.endpoint.jmx.annotation.DiscoveredJmxEndpoint.java
org.springframework.boot.actuate.endpoint.jmx.annotation.DiscoveredJmxOperation.java
org.springframework.boot.actuate.endpoint.jmx.annotation.EndpointJmxExtension.java
org.springframework.boot.actuate.endpoint.jmx.annotation.JmxEndpoint.java
org.springframework.boot.actuate.endpoint.jmx.annotation.JmxEndpointDiscoverer.java
org.springframework.boot.actuate.endpoint.jmx.annotation.JmxEndpointFilter.java

org.springframework.boot.actuate.endpoint.jmx.EndpointMBean.java
org.springframework.boot.actuate.endpoint.jmx.EndpointObjectNameFactory.java
org.springframework.boot.actuate.endpoint.jmx.ExposableJmxEndpoint.java
org.springframework.boot.actuate.endpoint.jmx.JacksonJmxOperationResponseMapper.java
org.springframework.boot.actuate.endpoint.jmx.JmxEndpointExporter.java
org.springframework.boot.actuate.endpoint.jmx.JmxEndpointsSupplier.java
org.springframework.boot.actuate.endpoint.jmx.JmxOperation.java
org.springframework.boot.actuate.endpoint.jmx.JmxOperationParameter.java
org.springframework.boot.actuate.endpoint.jmx.JmxOperationResponseMapper.java
org.springframework.boot.actuate.endpoint.jmx.MBeanInfoFactory.java

org.springframework.boot.actuate.endpoint.Operation.java
org.springframework.boot.actuate.endpoint.OperationArgumentResolver.java
org.springframework.boot.actuate.endpoint.OperationResponseBody.java
org.springframework.boot.actuate.endpoint.OperationResponseBodyMap.java
org.springframework.boot.actuate.endpoint.OperationType.java

org.springframework.boot.actuate.endpoint.Producible.java
org.springframework.boot.actuate.endpoint.ProducibleOperationArgumentResolver.java
org.springframework.boot.actuate.endpoint.SanitizableData.java
org.springframework.boot.actuate.endpoint.Sanitizer.java
org.springframework.boot.actuate.endpoint.SanitizingFunction.java
org.springframework.boot.actuate.endpoint.SecurityContext.java
org.springframework.boot.actuate.endpoint.Show.java
org.springframework.boot.actuate.endpoint.web.annotation.ControllerEndpoint.java
org.springframework.boot.actuate.endpoint.web.annotation.ControllerEndpointDiscoverer.java
org.springframework.boot.actuate.endpoint.web.annotation.ControllerEndpointFilter.java
org.springframework.boot.actuate.endpoint.web.annotation.ControllerEndpointsSupplier.java
org.springframework.boot.actuate.endpoint.web.annotation.DiscoveredControllerEndpoint.java
org.springframework.boot.actuate.endpoint.web.annotation.DiscoveredServletEndpoint.java
org.springframework.boot.actuate.endpoint.web.annotation.DiscoveredWebEndpoint.java
org.springframework.boot.actuate.endpoint.web.annotation.DiscoveredWebOperation.java
org.springframework.boot.actuate.endpoint.web.annotation.EndpointWebExtension.java
org.springframework.boot.actuate.endpoint.web.annotation.ExposableControllerEndpoint.java

org.springframework.boot.actuate.endpoint.web.annotation.RequestPredicateFactory.java
org.springframework.boot.actuate.endpoint.web.annotation.RestControllerEndpoint.java
org.springframework.boot.actuate.endpoint.web.annotation.ServletEndpoint.java
org.springframework.boot.actuate.endpoint.web.annotation.ServletEndpointDiscoverer.java
org.springframework.boot.actuate.endpoint.web.annotation.ServletEndpointFilter.java
org.springframework.boot.actuate.endpoint.web.annotation.ServletEndpointsSupplier.java
org.springframework.boot.actuate.endpoint.web.annotation.WebEndpoint.java
org.springframework.boot.actuate.endpoint.web.annotation.WebEndpointDiscoverer.java
org.springframework.boot.actuate.endpoint.web.annotation.WebEndpointFilter.java
org.springframework.boot.actuate.endpoint.web.EndpointLinksResolver.java
org.springframework.boot.actuate.endpoint.web.EndpointMapping.java
org.springframework.boot.actuate.endpoint.web.EndpointMediaTypes.java
org.springframework.boot.actuate.endpoint.web.EndpointServlet.java
org.springframework.boot.actuate.endpoint.web.ExposableServletEndpoint.java
org.springframework.boot.actuate.endpoint.web.ExposableWebEndpoint.java
org.springframework.boot.actuate.endpoint.web.jersey.JerseyEndpointResourceFactory.java
org.springframework.boot.actuate.endpoint.web.jersey.JerseyHealthEndpointAdditionalPathResourceFactory.java
org.springframework.boot.actuate.endpoint.web.jersey.JerseyRemainingPathSegmentProvider.java

org.springframework.boot.actuate.endpoint.web.Link.java

org.springframework.boot.actuate.endpoint.web.PathMappedEndpoint.java
org.springframework.boot.actuate.endpoint.web.PathMappedEndpoints.java
org.springframework.boot.actuate.endpoint.web.PathMapper.java
org.springframework.boot.actuate.endpoint.web.reactive.AbstractWebFluxEndpointHandlerMapping.java
org.springframework.boot.actuate.endpoint.web.reactive.AdditionalHealthEndpointPathsWebFluxHandlerMapping.java
org.springframework.boot.actuate.endpoint.web.reactive.ControllerEndpointHandlerMapping.java

org.springframework.boot.actuate.endpoint.web.reactive.WebFluxEndpointHandlerMapping.java
org.springframework.boot.actuate.endpoint.web.servlet.AbstractWebMvcEndpointHandlerMapping.java
org.springframework.boot.actuate.endpoint.web.servlet.AdditionalHealthEndpointPathsWebMvcHandlerMapping.java
org.springframework.boot.actuate.endpoint.web.servlet.ControllerEndpointHandlerMapping.java

org.springframework.boot.actuate.endpoint.web.servlet.SkipPathExtensionContentNegotiation.java
org.springframework.boot.actuate.endpoint.web.servlet.WebMvcEndpointHandlerMapping.java
org.springframework.boot.actuate.endpoint.web.ServletEndpointRegistrar.java
org.springframework.boot.actuate.endpoint.web.WebEndpointHttpMethod.java
org.springframework.boot.actuate.endpoint.web.WebEndpointResponse.java
org.springframework.boot.actuate.endpoint.web.WebEndpointsSupplier.java
org.springframework.boot.actuate.endpoint.web.WebOperation.java
org.springframework.boot.actuate.endpoint.web.WebOperationRequestPredicate.java
org.springframework.boot.actuate.endpoint.web.WebServerNamespace.java
org.springframework.boot.actuate.env.EnvironmentEndpoint.java
org.springframework.boot.actuate.env.EnvironmentEndpointWebExtension.java

org.springframework.boot.actuate.flyway.FlywayEndpoint.java

org.springframework.boot.actuate.hazelcast.HazelcastHealthIndicator.java

org.springframework.boot.actuate.health.AbstractHealthIndicator.java
org.springframework.boot.actuate.health.AbstractReactiveHealthIndicator.java
org.springframework.boot.actuate.health.AdditionalHealthEndpointPath.java
org.springframework.boot.actuate.health.CompositeHealth.java
org.springframework.boot.actuate.health.CompositeHealthContributor.java
org.springframework.boot.actuate.health.CompositeHealthContributorMapAdapter.java
org.springframework.boot.actuate.health.CompositeHealthContributorReactiveAdapter.java
org.springframework.boot.actuate.health.CompositeReactiveHealthContributor.java
org.springframework.boot.actuate.health.CompositeReactiveHealthContributorMapAdapter.java
org.springframework.boot.actuate.health.ContributorRegistry.java
org.springframework.boot.actuate.health.DefaultContributorRegistry.java
org.springframework.boot.actuate.health.DefaultHealthContributorRegistry.java
org.springframework.boot.actuate.health.DefaultReactiveHealthContributorRegistry.java
org.springframework.boot.actuate.health.Health.java
org.springframework.boot.actuate.health.HealthComponent.java
org.springframework.boot.actuate.health.HealthContributor.java
org.springframework.boot.actuate.health.HealthContributorNameFactory.java
org.springframework.boot.actuate.health.HealthContributorRegistry.java
org.springframework.boot.actuate.health.HealthEndpoint.java
org.springframework.boot.actuate.health.HealthEndpointGroup.java
org.springframework.boot.actuate.health.HealthEndpointGroups.java
org.springframework.boot.actuate.health.HealthEndpointGroupsPostProcessor.java
org.springframework.boot.actuate.health.HealthEndpointSupport.java
org.springframework.boot.actuate.health.HealthEndpointWebExtension.java
org.springframework.boot.actuate.health.HealthEndpointWebExtensionRuntimeHints.java
org.springframework.boot.actuate.health.HealthIndicator.java
org.springframework.boot.actuate.health.HealthIndicatorReactiveAdapter.java
org.springframework.boot.actuate.health.HttpCodeStatusMapper.java
org.springframework.boot.actuate.health.NamedContributor.java
org.springframework.boot.actuate.health.NamedContributors.java
org.springframework.boot.actuate.health.NamedContributorsMapAdapter.java

org.springframework.boot.actuate.health.PingHealthIndicator.java
org.springframework.boot.actuate.health.ReactiveHealthContributor.java
org.springframework.boot.actuate.health.ReactiveHealthContributorRegistry.java
org.springframework.boot.actuate.health.ReactiveHealthEndpointWebExtension.java
org.springframework.boot.actuate.health.ReactiveHealthIndicator.java
org.springframework.boot.actuate.health.SimpleHttpCodeStatusMapper.java
org.springframework.boot.actuate.health.SimpleStatusAggregator.java
org.springframework.boot.actuate.health.Status.java
org.springframework.boot.actuate.health.StatusAggregator.java
org.springframework.boot.actuate.health.SystemHealth.java
org.springframework.boot.actuate.influx.InfluxDbHealthIndicator.java

org.springframework.boot.actuate.info.BuildInfoContributor.java
org.springframework.boot.actuate.info.EnvironmentInfoContributor.java
org.springframework.boot.actuate.info.GitInfoContributor.java
org.springframework.boot.actuate.info.Info.java
org.springframework.boot.actuate.info.InfoContributor.java
org.springframework.boot.actuate.info.InfoEndpoint.java
org.springframework.boot.actuate.info.InfoPropertiesInfoContributor.java
org.springframework.boot.actuate.info.JavaInfoContributor.java
org.springframework.boot.actuate.info.MapInfoContributor.java
org.springframework.boot.actuate.info.OsInfoContributor.java

org.springframework.boot.actuate.info.SimpleInfoContributor.java
org.springframework.boot.actuate.integration.IntegrationGraphEndpoint.java

org.springframework.boot.actuate.jdbc.DataSourceHealthIndicator.java

org.springframework.boot.actuate.jms.JmsHealthIndicator.java

org.springframework.boot.actuate.ldap.LdapHealthIndicator.java

org.springframework.boot.actuate.liquibase.LiquibaseEndpoint.java

org.springframework.boot.actuate.mail.MailHealthIndicator.java

org.springframework.boot.actuate.management.HeapDumpWebEndpoint.java

org.springframework.boot.actuate.management.PlainTextThreadDumpFormatter.java
org.springframework.boot.actuate.management.ThreadDumpEndpoint.java

org.springframework.boot.actuate.metrics.amqp.RabbitMetrics.java

org.springframework.boot.actuate.metrics.annotation.TimedAnnotations.java
org.springframework.boot.actuate.metrics.AutoTimer.java
org.springframework.boot.actuate.metrics.cache.Cache2kCacheMeterBinderProvider.java
org.springframework.boot.actuate.metrics.cache.CacheMeterBinderProvider.java
org.springframework.boot.actuate.metrics.cache.CacheMetricsRegistrar.java
org.springframework.boot.actuate.metrics.cache.CaffeineCacheMeterBinderProvider.java
org.springframework.boot.actuate.metrics.cache.HazelcastCacheMeterBinderProvider.java
org.springframework.boot.actuate.metrics.cache.JCacheCacheMeterBinderProvider.java

org.springframework.boot.actuate.metrics.cache.RedisCacheMeterBinderProvider.java
org.springframework.boot.actuate.metrics.cache.RedisCacheMetrics.java
org.springframework.boot.actuate.metrics.data.DefaultRepositoryTagsProvider.java
org.springframework.boot.actuate.metrics.data.MetricsRepositoryMethodInvocationListener.java

org.springframework.boot.actuate.metrics.data.RepositoryTagsProvider.java

org.springframework.boot.actuate.metrics.export.prometheus.PrometheusPushGatewayManager.java
org.springframework.boot.actuate.metrics.export.prometheus.PrometheusScrapeEndpoint.java
org.springframework.boot.actuate.metrics.export.prometheus.TextOutputFormat.java
org.springframework.boot.actuate.metrics.http.Outcome.java

org.springframework.boot.actuate.metrics.jdbc.DataSourcePoolMetrics.java

org.springframework.boot.actuate.metrics.MetricsEndpoint.java

org.springframework.boot.actuate.metrics.r2dbc.ConnectionPoolMetrics.java


org.springframework.boot.actuate.metrics.startup.StartupTimeMetricsListener.java
org.springframework.boot.actuate.metrics.system.DiskSpaceMetricsBinder.java

org.springframework.boot.actuate.metrics.web.client.DefaultRestTemplateExchangeTagsProvider.java
org.springframework.boot.actuate.metrics.web.client.ObservationRestTemplateCustomizer.java

org.springframework.boot.actuate.metrics.web.client.RestTemplateExchangeTags.java
org.springframework.boot.actuate.metrics.web.client.RestTemplateExchangeTagsProvider.java
org.springframework.boot.actuate.metrics.web.jetty.AbstractJettyMetricsBinder.java
org.springframework.boot.actuate.metrics.web.jetty.JettyConnectionMetricsBinder.java
org.springframework.boot.actuate.metrics.web.jetty.JettyServerThreadPoolMetricsBinder.java
org.springframework.boot.actuate.metrics.web.jetty.JettySslHandshakeMetricsBinder.java

org.springframework.boot.actuate.metrics.web.reactive.client.DefaultWebClientExchangeTagsProvider.java
org.springframework.boot.actuate.metrics.web.reactive.client.ObservationWebClientCustomizer.java

org.springframework.boot.actuate.metrics.web.reactive.client.WebClientExchangeTags.java
org.springframework.boot.actuate.metrics.web.reactive.client.WebClientExchangeTagsProvider.java
org.springframework.boot.actuate.metrics.web.reactive.server.DefaultWebFluxTagsProvider.java

org.springframework.boot.actuate.metrics.web.reactive.server.WebFluxTags.java
org.springframework.boot.actuate.metrics.web.reactive.server.WebFluxTagsContributor.java
org.springframework.boot.actuate.metrics.web.reactive.server.WebFluxTagsProvider.java
org.springframework.boot.actuate.metrics.web.servlet.DefaultWebMvcTagsProvider.java

org.springframework.boot.actuate.metrics.web.servlet.WebMvcTags.java
org.springframework.boot.actuate.metrics.web.servlet.WebMvcTagsContributor.java
org.springframework.boot.actuate.metrics.web.servlet.WebMvcTagsProvider.java

org.springframework.boot.actuate.metrics.web.tomcat.TomcatMetricsBinder.java
org.springframework.boot.actuate.neo4j.Neo4jHealthDetails.java
org.springframework.boot.actuate.neo4j.Neo4jHealthDetailsHandler.java
org.springframework.boot.actuate.neo4j.Neo4jHealthIndicator.java
org.springframework.boot.actuate.neo4j.Neo4jReactiveHealthIndicator.java


org.springframework.boot.actuate.quartz.QuartzEndpoint.java
org.springframework.boot.actuate.quartz.QuartzEndpointWebExtension.java
org.springframework.boot.actuate.r2dbc.ConnectionFactoryHealthIndicator.java


org.springframework.boot.actuate.scheduling.ScheduledTasksEndpoint.java
org.springframework.boot.actuate.security.AbstractAuthenticationAuditListener.java
org.springframework.boot.actuate.security.AbstractAuthorizationAuditListener.java
org.springframework.boot.actuate.security.AuthenticationAuditListener.java
org.springframework.boot.actuate.security.AuthorizationAuditListener.java


org.springframework.boot.actuate.session.SessionsEndpoint.java

org.springframework.boot.actuate.startup.StartupEndpoint.java
org.springframework.boot.actuate.system.DiskSpaceHealthIndicator.java

org.springframework.boot.actuate.web.exchanges.HttpExchange.java
org.springframework.boot.actuate.web.exchanges.HttpExchangeRepository.java
org.springframework.boot.actuate.web.exchanges.HttpExchangesEndpoint.java
org.springframework.boot.actuate.web.exchanges.Include.java
org.springframework.boot.actuate.web.exchanges.InMemoryHttpExchangeRepository.java

org.springframework.boot.actuate.web.exchanges.reactive.HttpExchangesWebFilter.java

org.springframework.boot.actuate.web.exchanges.reactive.RecordableServerHttpRequest.java
org.springframework.boot.actuate.web.exchanges.reactive.RecordableServerHttpResponse.java
org.springframework.boot.actuate.web.exchanges.RecordableHttpRequest.java
org.springframework.boot.actuate.web.exchanges.RecordableHttpResponse.java
org.springframework.boot.actuate.web.exchanges.servlet.HttpExchangesFilter.java

org.springframework.boot.actuate.web.exchanges.servlet.RecordableServletHttpRequest.java
org.springframework.boot.actuate.web.exchanges.servlet.RecordableServletHttpResponse.java
org.springframework.boot.actuate.web.mappings.HandlerMethodDescription.java
org.springframework.boot.actuate.web.mappings.MappingDescriptionProvider.java
org.springframework.boot.actuate.web.mappings.MappingsEndpoint.java

org.springframework.boot.actuate.web.mappings.reactive.DispatcherHandlerMappingDescription.java
org.springframework.boot.actuate.web.mappings.reactive.DispatcherHandlerMappingDetails.java
org.springframework.boot.actuate.web.mappings.reactive.DispatcherHandlersMappingDescriptionProvider.java
org.springframework.boot.actuate.web.mappings.reactive.HandlerFunctionDescription.java

org.springframework.boot.actuate.web.mappings.reactive.RequestMappingConditionsDescription.java
org.springframework.boot.actuate.web.mappings.servlet.DispatcherServletHandlerMappings.java
org.springframework.boot.actuate.web.mappings.servlet.DispatcherServletMappingDescription.java
org.springframework.boot.actuate.web.mappings.servlet.DispatcherServletMappingDetails.java
org.springframework.boot.actuate.web.mappings.servlet.DispatcherServletsMappingDescriptionProvider.java
org.springframework.boot.actuate.web.mappings.servlet.FilterRegistrationMappingDescription.java
org.springframework.boot.actuate.web.mappings.servlet.FiltersMappingDescriptionProvider.java

org.springframework.boot.actuate.web.mappings.servlet.RegistrationMappingDescription.java
org.springframework.boot.actuate.web.mappings.servlet.RequestMappingConditionsDescription.java
org.springframework.boot.actuate.web.mappings.servlet.ServletRegistrationMappingDescription.java
org.springframework.boot.actuate.web.mappings.servlet.ServletsMappingDescriptionProvider.java

```

