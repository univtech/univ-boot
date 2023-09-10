# spring-boot-docker-compose

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
org.springframework.boot:spring-boot-docker-compose:3.1.3

# 依赖：compile
org.springframework.boot:spring-boot:3.1.3

# 依赖：runtime
com.fasterxml.jackson.core:jackson-databind:2.15.2
com.fasterxml.jackson.module:jackson-module-parameter-names:2.15.2
```

## java文件

```

org.springframework.boot.docker.compose.core.ConnectionPorts.java
org.springframework.boot.docker.compose.core.DefaultConnectionPorts.java
org.springframework.boot.docker.compose.core.DefaultDockerCompose.java
org.springframework.boot.docker.compose.core.DefaultRunningService.java
org.springframework.boot.docker.compose.core.DockerCli.java
org.springframework.boot.docker.compose.core.DockerCliCommand.java
org.springframework.boot.docker.compose.core.DockerCliComposeConfigResponse.java
org.springframework.boot.docker.compose.core.DockerCliComposePsResponse.java
org.springframework.boot.docker.compose.core.DockerCliComposeVersionResponse.java
org.springframework.boot.docker.compose.core.DockerCliContextResponse.java
org.springframework.boot.docker.compose.core.DockerCliInspectResponse.java
org.springframework.boot.docker.compose.core.DockerCompose.java
org.springframework.boot.docker.compose.core.DockerComposeFile.java
org.springframework.boot.docker.compose.core.DockerComposeOrigin.java
org.springframework.boot.docker.compose.core.DockerEnv.java
org.springframework.boot.docker.compose.core.DockerException.java
org.springframework.boot.docker.compose.core.DockerHost.java
org.springframework.boot.docker.compose.core.DockerJson.java
org.springframework.boot.docker.compose.core.DockerNotRunningException.java
org.springframework.boot.docker.compose.core.DockerOutputParseException.java
org.springframework.boot.docker.compose.core.DockerProcessStartException.java
org.springframework.boot.docker.compose.core.ImageName.java
org.springframework.boot.docker.compose.core.ImageReference.java

org.springframework.boot.docker.compose.core.ProcessExitException.java
org.springframework.boot.docker.compose.core.ProcessRunner.java
org.springframework.boot.docker.compose.core.ProcessStartException.java
org.springframework.boot.docker.compose.core.Regex.java
org.springframework.boot.docker.compose.core.RunningService.java
org.springframework.boot.docker.compose.lifecycle.DockerComposeLifecycleManager.java
org.springframework.boot.docker.compose.lifecycle.DockerComposeListener.java
org.springframework.boot.docker.compose.lifecycle.DockerComposeProperties.java
org.springframework.boot.docker.compose.lifecycle.DockerComposeServicesReadyEvent.java
org.springframework.boot.docker.compose.lifecycle.DockerComposeSkipCheck.java
org.springframework.boot.docker.compose.lifecycle.LifecycleManagement.java

org.springframework.boot.docker.compose.lifecycle.ReadinessTimeoutException.java
org.springframework.boot.docker.compose.lifecycle.ServiceNotReadyException.java
org.springframework.boot.docker.compose.lifecycle.ServiceReadinessChecks.java
org.springframework.boot.docker.compose.lifecycle.StartCommand.java
org.springframework.boot.docker.compose.lifecycle.StopCommand.java
org.springframework.boot.docker.compose.lifecycle.TcpConnectServiceReadinessCheck.java
org.springframework.boot.docker.compose.service.connection.cassandra.CassandraDockerComposeConnectionDetailsFactory.java
org.springframework.boot.docker.compose.service.connection.cassandra.CassandraEnvironment.java

org.springframework.boot.docker.compose.service.connection.ConnectionNamePredicate.java
org.springframework.boot.docker.compose.service.connection.DockerComposeConnectionDetailsFactory.java
org.springframework.boot.docker.compose.service.connection.DockerComposeConnectionSource.java
org.springframework.boot.docker.compose.service.connection.DockerComposeServiceConnectionsApplicationListener.java
org.springframework.boot.docker.compose.service.connection.elasticsearch.ElasticsearchDockerComposeConnectionDetailsFactory.java
org.springframework.boot.docker.compose.service.connection.elasticsearch.ElasticsearchEnvironment.java

org.springframework.boot.docker.compose.service.connection.flyway.JdbcAdaptingFlywayConnectionDetailsFactory.java

org.springframework.boot.docker.compose.service.connection.jdbc.JdbcUrlBuilder.java

org.springframework.boot.docker.compose.service.connection.liquibase.JdbcAdaptingLiquibaseConnectionDetailsFactory.java

org.springframework.boot.docker.compose.service.connection.mariadb.MariaDbEnvironment.java
org.springframework.boot.docker.compose.service.connection.mariadb.MariaDbJdbcDockerComposeConnectionDetailsFactory.java
org.springframework.boot.docker.compose.service.connection.mariadb.MariaDbR2dbcDockerComposeConnectionDetailsFactory.java

org.springframework.boot.docker.compose.service.connection.mongo.MongoDockerComposeConnectionDetailsFactory.java
org.springframework.boot.docker.compose.service.connection.mongo.MongoEnvironment.java

org.springframework.boot.docker.compose.service.connection.mysql.MySqlEnvironment.java
org.springframework.boot.docker.compose.service.connection.mysql.MySqlJdbcDockerComposeConnectionDetailsFactory.java
org.springframework.boot.docker.compose.service.connection.mysql.MySqlR2dbcDockerComposeConnectionDetailsFactory.java

org.springframework.boot.docker.compose.service.connection.oracle.OracleEnvironment.java
org.springframework.boot.docker.compose.service.connection.oracle.OracleJdbcDockerComposeConnectionDetailsFactory.java
org.springframework.boot.docker.compose.service.connection.oracle.OracleR2dbcDockerComposeConnectionDetailsFactory.java



org.springframework.boot.docker.compose.service.connection.postgres.PostgresEnvironment.java
org.springframework.boot.docker.compose.service.connection.postgres.PostgresJdbcDockerComposeConnectionDetailsFactory.java
org.springframework.boot.docker.compose.service.connection.postgres.PostgresR2dbcDockerComposeConnectionDetailsFactory.java
org.springframework.boot.docker.compose.service.connection.r2dbc.ConnectionFactoryOptionsBuilder.java


org.springframework.boot.docker.compose.service.connection.rabbit.RabbitDockerComposeConnectionDetailsFactory.java
org.springframework.boot.docker.compose.service.connection.rabbit.RabbitEnvironment.java

org.springframework.boot.docker.compose.service.connection.redis.RedisDockerComposeConnectionDetailsFactory.java

org.springframework.boot.docker.compose.service.connection.sqlserver.SqlServerEnvironment.java
org.springframework.boot.docker.compose.service.connection.sqlserver.SqlServerJdbcDockerComposeConnectionDetailsFactory.java
org.springframework.boot.docker.compose.service.connection.sqlserver.SqlServerR2dbcDockerComposeConnectionDetailsFactory.java

org.springframework.boot.docker.compose.service.connection.zipkin.ZipkinDockerComposeConnectionDetailsFactory.java

```
