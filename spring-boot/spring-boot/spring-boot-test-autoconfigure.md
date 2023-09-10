# spring-boot-test-autoconfigure

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
org.springframework.boot:spring-boot-test-autoconfigure:3.1.3

# 依赖：compile
org.springframework.boot:spring-boot:3.1.3
org.springframework.boot:spring-boot-test:3.1.3
org.springframework.boot:spring-boot-autoconfigure:3.1.3
```

## java文件

```

org.springframework.boot.test.autoconfigure.actuate.metrics.AutoConfigureMetrics.java

org.springframework.boot.test.autoconfigure.actuate.observability.AutoConfigureObservability.java
org.springframework.boot.test.autoconfigure.actuate.observability.ObservabilityContextCustomizerFactory.java

org.springframework.boot.test.autoconfigure.ConditionReportApplicationContextFailureProcessor.java
org.springframework.boot.test.autoconfigure.core.AutoConfigureCache.java

org.springframework.boot.test.autoconfigure.data.cassandra.AutoConfigureDataCassandra.java
org.springframework.boot.test.autoconfigure.data.cassandra.DataCassandraTest.java
org.springframework.boot.test.autoconfigure.data.cassandra.DataCassandraTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.data.cassandra.DataCassandraTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.data.couchbase.AutoConfigureDataCouchbase.java
org.springframework.boot.test.autoconfigure.data.couchbase.DataCouchbaseTest.java
org.springframework.boot.test.autoconfigure.data.couchbase.DataCouchbaseTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.data.couchbase.DataCouchbaseTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.data.elasticsearch.AutoConfigureDataElasticsearch.java
org.springframework.boot.test.autoconfigure.data.elasticsearch.DataElasticsearchTest.java
org.springframework.boot.test.autoconfigure.data.elasticsearch.DataElasticsearchTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.data.elasticsearch.DataElasticsearchTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.data.jdbc.AutoConfigureDataJdbc.java
org.springframework.boot.test.autoconfigure.data.jdbc.DataJdbcTest.java
org.springframework.boot.test.autoconfigure.data.jdbc.DataJdbcTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.data.jdbc.DataJdbcTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.data.ldap.AutoConfigureDataLdap.java
org.springframework.boot.test.autoconfigure.data.ldap.DataLdapTest.java
org.springframework.boot.test.autoconfigure.data.ldap.DataLdapTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.data.ldap.DataLdapTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.data.mongo.AutoConfigureDataMongo.java
org.springframework.boot.test.autoconfigure.data.mongo.DataMongoTest.java
org.springframework.boot.test.autoconfigure.data.mongo.DataMongoTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.data.mongo.DataMongoTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.data.neo4j.AutoConfigureDataNeo4j.java
org.springframework.boot.test.autoconfigure.data.neo4j.DataNeo4jTest.java
org.springframework.boot.test.autoconfigure.data.neo4j.DataNeo4jTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.data.neo4j.DataNeo4jTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.data.r2dbc.AutoConfigureDataR2dbc.java
org.springframework.boot.test.autoconfigure.data.r2dbc.DataR2dbcTest.java
org.springframework.boot.test.autoconfigure.data.r2dbc.DataR2dbcTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.data.r2dbc.DataR2dbcTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.data.redis.AutoConfigureDataRedis.java
org.springframework.boot.test.autoconfigure.data.redis.DataRedisTest.java
org.springframework.boot.test.autoconfigure.data.redis.DataRedisTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.data.redis.DataRedisTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.filter.AnnotationCustomizableTypeExcludeFilter.java
org.springframework.boot.test.autoconfigure.filter.FilterAnnotations.java

org.springframework.boot.test.autoconfigure.filter.StandardAnnotationCustomizableTypeExcludeFilter.java
org.springframework.boot.test.autoconfigure.filter.TypeExcludeFilters.java
org.springframework.boot.test.autoconfigure.filter.TypeExcludeFiltersContextCustomizer.java
org.springframework.boot.test.autoconfigure.filter.TypeExcludeFiltersContextCustomizerFactory.java
org.springframework.boot.test.autoconfigure.graphql.AutoConfigureGraphQl.java
org.springframework.boot.test.autoconfigure.graphql.GraphQlTest.java
org.springframework.boot.test.autoconfigure.graphql.GraphQlTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.graphql.GraphQlTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.graphql.tester.AutoConfigureGraphQlTester.java
org.springframework.boot.test.autoconfigure.graphql.tester.AutoConfigureHttpGraphQlTester.java
org.springframework.boot.test.autoconfigure.graphql.tester.GraphQlTesterAutoConfiguration.java
org.springframework.boot.test.autoconfigure.graphql.tester.HttpGraphQlTesterAutoConfiguration.java

org.springframework.boot.test.autoconfigure.jdbc.AutoConfigureJdbc.java
org.springframework.boot.test.autoconfigure.jdbc.AutoConfigureTestDatabase.java
org.springframework.boot.test.autoconfigure.jdbc.JdbcTest.java
org.springframework.boot.test.autoconfigure.jdbc.JdbcTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.jdbc.JdbcTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.jdbc.TestDatabaseAutoConfiguration.java
org.springframework.boot.test.autoconfigure.jooq.AutoConfigureJooq.java
org.springframework.boot.test.autoconfigure.jooq.JooqTest.java
org.springframework.boot.test.autoconfigure.jooq.JooqTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.jooq.JooqTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.json.AutoConfigureJson.java
org.springframework.boot.test.autoconfigure.json.AutoConfigureJsonTesters.java
org.springframework.boot.test.autoconfigure.json.JsonTest.java
org.springframework.boot.test.autoconfigure.json.JsonTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.json.JsonTestersAutoConfiguration.java
org.springframework.boot.test.autoconfigure.json.JsonTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.orm.jpa.AutoConfigureDataJpa.java
org.springframework.boot.test.autoconfigure.orm.jpa.AutoConfigureTestEntityManager.java
org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTest.java
org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTypeExcludeFilter.java

org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManager.java
org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManagerAutoConfiguration.java
org.springframework.boot.test.autoconfigure.OverrideAutoConfiguration.java
org.springframework.boot.test.autoconfigure.OverrideAutoConfigurationContextCustomizerFactory.java

org.springframework.boot.test.autoconfigure.properties.AnnotationsPropertySource.java

org.springframework.boot.test.autoconfigure.properties.PropertyMapping.java
org.springframework.boot.test.autoconfigure.properties.PropertyMappingContextCustomizer.java
org.springframework.boot.test.autoconfigure.properties.PropertyMappingContextCustomizerFactory.java
org.springframework.boot.test.autoconfigure.properties.SkipPropertyMapping.java
org.springframework.boot.test.autoconfigure.restdocs.AutoConfigureRestDocs.java

org.springframework.boot.test.autoconfigure.restdocs.RestDocsAutoConfiguration.java
org.springframework.boot.test.autoconfigure.restdocs.RestDocsMockMvcBuilderCustomizer.java
org.springframework.boot.test.autoconfigure.restdocs.RestDocsMockMvcConfigurationCustomizer.java
org.springframework.boot.test.autoconfigure.restdocs.RestDocsProperties.java
org.springframework.boot.test.autoconfigure.restdocs.RestDocsRestAssuredBuilderCustomizer.java
org.springframework.boot.test.autoconfigure.restdocs.RestDocsRestAssuredConfigurationCustomizer.java
org.springframework.boot.test.autoconfigure.restdocs.RestDocsTestExecutionListener.java
org.springframework.boot.test.autoconfigure.restdocs.RestDocsWebTestClientBuilderCustomizer.java
org.springframework.boot.test.autoconfigure.restdocs.RestDocsWebTestClientConfigurationCustomizer.java
org.springframework.boot.test.autoconfigure.restdocs.RestDocumentationContextProviderRegistrar.java
org.springframework.boot.test.autoconfigure.SpringBootDependencyInjectionTestExecutionListener.java
org.springframework.boot.test.autoconfigure.web.client.AutoConfigureMockRestServiceServer.java
org.springframework.boot.test.autoconfigure.web.client.AutoConfigureWebClient.java
org.springframework.boot.test.autoconfigure.web.client.MockRestServiceServerAutoConfiguration.java
org.springframework.boot.test.autoconfigure.web.client.MockRestServiceServerResetTestExecutionListener.java

org.springframework.boot.test.autoconfigure.web.client.RestClientTest.java
org.springframework.boot.test.autoconfigure.web.client.RestClientTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.web.client.RestClientTypeExcludeFilter.java
org.springframework.boot.test.autoconfigure.web.client.WebClientRestTemplateAutoConfiguration.java
org.springframework.boot.test.autoconfigure.web.reactive.AutoConfigureWebFlux.java
org.springframework.boot.test.autoconfigure.web.reactive.AutoConfigureWebTestClient.java

org.springframework.boot.test.autoconfigure.web.reactive.SpringBootWebTestClientBuilderCustomizer.java
org.springframework.boot.test.autoconfigure.web.reactive.WebFluxTest.java
org.springframework.boot.test.autoconfigure.web.reactive.WebFluxTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.web.reactive.WebFluxTypeExcludeFilter.java
org.springframework.boot.test.autoconfigure.web.reactive.WebTestClientAutoConfiguration.java
org.springframework.boot.test.autoconfigure.web.reactive.WebTestClientSecurityConfiguration.java
org.springframework.boot.test.autoconfigure.web.servlet.AutoConfigureMockMvc.java
org.springframework.boot.test.autoconfigure.web.servlet.AutoConfigureWebMvc.java
org.springframework.boot.test.autoconfigure.web.servlet.MockMvcAutoConfiguration.java
org.springframework.boot.test.autoconfigure.web.servlet.MockMvcBuilderCustomizer.java
org.springframework.boot.test.autoconfigure.web.servlet.MockMvcPrint.java
org.springframework.boot.test.autoconfigure.web.servlet.MockMvcPrintOnlyOnFailureTestExecutionListener.java
org.springframework.boot.test.autoconfigure.web.servlet.MockMvcSecurityConfiguration.java
org.springframework.boot.test.autoconfigure.web.servlet.MockMvcWebClientAutoConfiguration.java
org.springframework.boot.test.autoconfigure.web.servlet.MockMvcWebDriverAutoConfiguration.java

org.springframework.boot.test.autoconfigure.web.servlet.SpringBootMockMvcBuilderCustomizer.java
org.springframework.boot.test.autoconfigure.web.servlet.WebDriverContextCustomizer.java
org.springframework.boot.test.autoconfigure.web.servlet.WebDriverContextCustomizerFactory.java
org.springframework.boot.test.autoconfigure.web.servlet.WebDriverScope.java
org.springframework.boot.test.autoconfigure.web.servlet.WebDriverTestExecutionListener.java
org.springframework.boot.test.autoconfigure.web.servlet.WebMvcTest.java
org.springframework.boot.test.autoconfigure.web.servlet.WebMvcTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.web.servlet.WebMvcTypeExcludeFilter.java
org.springframework.boot.test.autoconfigure.webservices.client.AutoConfigureMockWebServiceServer.java
org.springframework.boot.test.autoconfigure.webservices.client.AutoConfigureWebServiceClient.java
org.springframework.boot.test.autoconfigure.webservices.client.MockWebServiceServerAutoConfiguration.java
org.springframework.boot.test.autoconfigure.webservices.client.MockWebServiceServerTestExecutionListener.java
org.springframework.boot.test.autoconfigure.webservices.client.MockWebServiceServerWebServiceTemplateCustomizer.java

org.springframework.boot.test.autoconfigure.webservices.client.TestMockWebServiceServer.java
org.springframework.boot.test.autoconfigure.webservices.client.WebServiceClientExcludeFilter.java
org.springframework.boot.test.autoconfigure.webservices.client.WebServiceClientTemplateAutoConfiguration.java
org.springframework.boot.test.autoconfigure.webservices.client.WebServiceClientTest.java
org.springframework.boot.test.autoconfigure.webservices.client.WebServiceClientTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.webservices.server.AutoConfigureMockWebServiceClient.java
org.springframework.boot.test.autoconfigure.webservices.server.AutoConfigureWebServiceServer.java
org.springframework.boot.test.autoconfigure.webservices.server.MockWebServiceClientAutoConfiguration.java

org.springframework.boot.test.autoconfigure.webservices.server.WebServiceServerTest.java
org.springframework.boot.test.autoconfigure.webservices.server.WebServiceServerTestContextBootstrapper.java
org.springframework.boot.test.autoconfigure.webservices.server.WebServiceServerTypeExcludeFilter.java

```
