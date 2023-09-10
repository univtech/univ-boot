# spring-boot-testcontainers

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
org.springframework.boot:spring-boot-testcontainers:3.1.3

# 依赖：compile
org.springframework.boot:spring-boot-autoconfigure:3.1.3
org.testcontainers:testcontainers:1.18.3
```

## java文件

```

org.springframework.boot.testcontainers.beans.TestcontainerBeanDefinition.java
org.springframework.boot.testcontainers.context.ContainerFieldsImporter.java
org.springframework.boot.testcontainers.context.DynamicPropertySourceMethodsImporter.java
org.springframework.boot.testcontainers.context.ImportTestcontainers.java
org.springframework.boot.testcontainers.context.ImportTestcontainersRegistrar.java

org.springframework.boot.testcontainers.context.TestcontainerFieldBeanDefinition.java

org.springframework.boot.testcontainers.lifecycle.TestcontainersLifecycleApplicationContextInitializer.java
org.springframework.boot.testcontainers.lifecycle.TestcontainersLifecycleBeanFactoryPostProcessor.java
org.springframework.boot.testcontainers.lifecycle.TestcontainersLifecycleBeanPostProcessor.java


org.springframework.boot.testcontainers.properties.TestcontainersPropertySource.java
org.springframework.boot.testcontainers.properties.TestcontainersPropertySourceAutoConfiguration.java

org.springframework.boot.testcontainers.service.connection.amqp.RabbitContainerConnectionDetailsFactory.java
org.springframework.boot.testcontainers.service.connection.BeanOrigin.java
org.springframework.boot.testcontainers.service.connection.cassandra.CassandraContainerConnectionDetailsFactory.java

org.springframework.boot.testcontainers.service.connection.ConnectionDetailsRegistrar.java
org.springframework.boot.testcontainers.service.connection.ContainerConnectionDetailsFactory.java
org.springframework.boot.testcontainers.service.connection.ContainerConnectionSource.java
org.springframework.boot.testcontainers.service.connection.couchbase.CouchbaseContainerConnectionDetailsFactory.java

org.springframework.boot.testcontainers.service.connection.elasticsearch.ElasticsearchContainerConnectionDetailsFactory.java

org.springframework.boot.testcontainers.service.connection.FieldOrigin.java
org.springframework.boot.testcontainers.service.connection.flyway.FlywayContainerConnectionDetailsFactory.java

org.springframework.boot.testcontainers.service.connection.jdbc.JdbcContainerConnectionDetailsFactory.java

org.springframework.boot.testcontainers.service.connection.kafka.KafkaContainerConnectionDetailsFactory.java

org.springframework.boot.testcontainers.service.connection.liquibase.LiquibaseContainerConnectionDetailsFactory.java

org.springframework.boot.testcontainers.service.connection.mongo.MongoContainerConnectionDetailsFactory.java

org.springframework.boot.testcontainers.service.connection.neo4j.Neo4jContainerConnectionDetailsFactory.java


org.springframework.boot.testcontainers.service.connection.r2dbc.MariaDbR2dbcContainerConnectionDetailsFactory.java
org.springframework.boot.testcontainers.service.connection.r2dbc.MySqlR2dbcContainerConnectionDetailsFactory.java
org.springframework.boot.testcontainers.service.connection.r2dbc.OracleR2dbcContainerConnectionDetailsFactory.java

org.springframework.boot.testcontainers.service.connection.r2dbc.PostgresR2dbcContainerConnectionDetailsFactory.java
org.springframework.boot.testcontainers.service.connection.r2dbc.SqlServerR2dbcContainerConnectionDetailsFactory.java

org.springframework.boot.testcontainers.service.connection.redis.RedisContainerConnectionDetailsFactory.java

org.springframework.boot.testcontainers.service.connection.redpanda.RedpandaContainerConnectionDetailsFactory.java
org.springframework.boot.testcontainers.service.connection.ServiceConnection.java
org.springframework.boot.testcontainers.service.connection.ServiceConnectionAutoConfiguration.java
org.springframework.boot.testcontainers.service.connection.ServiceConnectionAutoConfigurationRegistrar.java
org.springframework.boot.testcontainers.service.connection.ServiceConnectionContextCustomizer.java
org.springframework.boot.testcontainers.service.connection.ServiceConnectionContextCustomizerFactory.java

org.springframework.boot.testcontainers.service.connection.zipkin.ZipkinContainerConnectionDetailsFactory.java

```
