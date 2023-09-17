# flyway

```

org.springframework.boot.autoconfigure.flyway.FlywayProperties

org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration

org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayConfiguration

org.springframework.boot.actuate.autoconfigure.flyway.FlywayEndpointAutoConfiguration

org.springframework.boot.autoconfigure.flyway.FlywayConfigurationCustomizer


org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayAutoConfigurationRuntimeHints

org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition.DataSourceBeanCondition
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition.FlywayUrlCondition
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition.JdbcConnectionDetailsCondition

org.springframework.boot.autoconfigure.flyway.FlywayConnectionDetails

org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.LocationResolver
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.PropertiesFlywayConnectionDetails
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.StringOrNumberToMigrationVersionConverter

org.springframework.boot.autoconfigure.flyway.FlywayDataSource
org.springframework.boot.autoconfigure.flyway.FlywayMigrationInitializer
org.springframework.boot.autoconfigure.flyway.FlywayMigrationStrategy
org.springframework.boot.autoconfigure.flyway.FlywaySchemaManagementProvider
org.springframework.boot.autoconfigure.flyway.NativeImageResourceProvider.LocatedResource
org.springframework.boot.autoconfigure.flyway.NativeImageResourceProvider
org.springframework.boot.autoconfigure.flyway.NativeImageResourceProviderCustomizer
org.springframework.boot.autoconfigure.flyway.ResourceProviderCustomizer
org.springframework.boot.autoconfigure.flyway.ResourceProviderCustomizerBeanRegistrationAotProcessor.AotContribution
org.springframework.boot.autoconfigure.flyway.ResourceProviderCustomizerBeanRegistrationAotProcessor













































```

















```


```





## Flyway检测器

### FlywayDatabaseInitializerDetector

```

# 数据库初始化器检测器。
org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector
    org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDatabaseInitializerDetector
        org.springframework.boot.flyway.FlywayDatabaseInitializerDetector

# 数据库初始化器检测器，检测指定类型的Bean：Flyway。
org.springframework.boot.flyway.FlywayDatabaseInitializerDetector

```

### FlywayMigrationInitializerDatabaseInitializerDetector

```

# 数据库初始化器检测器。
org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector
    org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDatabaseInitializerDetector
        org.springframework.boot.autoconfigure.flyway.FlywayMigrationInitializerDatabaseInitializerDetector

# 数据库初始化器检测器，检测指定类型的Bean：FlywayMigrationInitializer。
# 优先级顺序：1。
org.springframework.boot.autoconfigure.flyway.FlywayMigrationInitializerDatabaseInitializerDetector

```

## Flyway端点

### FlywayEndpoint

```

# @Endpoint：端点，暴露Flyway信息的端点ID：flyway。
# context：应用程序上下文。
#
# flywayBeans：
# @ReadOperation：读取操作，读取Flyway Bean信息，创建FlywayBeansDescriptor。
org.springframework.boot.actuate.flyway.FlywayEndpoint

```

### FlywayBeansDescriptor

```

# 应用程序的Flyway Bean描述符。
org.springframework.boot.actuate.endpoint.OperationResponseBody
    org.springframework.boot.actuate.flyway.FlywayEndpoint.FlywayBeansDescriptor

# 应用程序的Flyway Bean描述符。
# contexts：   应用程序上下文与ContextFlywayBeansDescriptor的映射。
# getContexts：获取应用程序上下文与ContextFlywayBeansDescriptor的映射。
org.springframework.boot.actuate.flyway.FlywayEndpoint.FlywayBeansDescriptor

# 应用程序上下文的Flyway Bean描述符。
# flywayBeans：   应用程序上下文与FlywayDescriptor的映射。
# parentId：      父应用程序上下文的ID。
# getFlywayBeans：获取应用程序上下文与FlywayDescriptor的映射。
# getParentId：   获取父应用程序上下文的ID。
org.springframework.boot.actuate.flyway.FlywayEndpoint.ContextFlywayBeansDescriptor

# Flyway Bean描述符。
# migrations：   FlywayMigrationDescriptor列表。
# getMigrations：获取FlywayMigrationDescriptor列表。
org.springframework.boot.actuate.flyway.FlywayEndpoint.FlywayDescriptor

# Flyway迁移描述符。
# type：         迁移类型。
# checksum：     校验和。
# version：      迁移版本。
# description：  迁移描述。
# script：       迁移脚本。
# state：        迁移状态（MigrationState）。
# installedBy：  安装迁移的用户。
# installedOn：  安装迁移的时间点（Instant）。
# installedRank：安装迁移的等级。
# executionTime：执行迁移的时间。
# getXXX：       获取XXX。
org.springframework.boot.actuate.flyway.FlywayEndpoint.FlywayMigrationDescriptor

```

## Flyway容器

### JdbcAdaptingFlywayConnectionDetailsFactory

```

# Flyway JDBC的连接详情工厂。
# getConnectionDetails：根据JdbcConnectionDetails获取FlywayConnectionDetails。
org.springframework.boot.docker.compose.service.connection.flyway.JdbcAdaptingFlywayConnectionDetailsFactory

```

## Flyway容器测试

### FlywayContainerConnectionDetailsFactory

```

# Flyway容器的连接详情工厂。
org.springframework.boot.autoconfigure.service.connection.ConnectionDetailsFactory
    org.springframework.boot.testcontainers.service.connection.ContainerConnectionDetailsFactory
        org.springframework.boot.testcontainers.service.connection.flyway.FlywayContainerConnectionDetailsFactory

# Flyway容器的连接详情工厂。
# JdbcDatabaseContainer：@ServiceConnection注解的JDBC数据库容器。
# getContainerConnectionDetails：根据ContainerConnectionSource<JdbcDatabaseContainer<?>>获取FlywayConnectionDetails。
org.springframework.boot.testcontainers.service.connection.flyway.FlywayContainerConnectionDetailsFactory

```

### FlywayContainerConnectionDetails

```

# Flyway容器的连接详情。
org.springframework.boot.autoconfigure.service.connection.ConnectionDetails
    org.springframework.boot.autoconfigure.flyway.FlywayConnectionDetails
        org.springframework.boot.testcontainers.service.connection.flyway.FlywayContainerConnectionDetailsFactory.FlywayContainerConnectionDetails

# Flyway容器的连接详情。
# getUsername：       根据ContainerConnectionSource<JdbcDatabaseContainer<?>>获取数据库的用户名。
# getPassword：       根据ContainerConnectionSource<JdbcDatabaseContainer<?>>获取数据库的密码。
# getJdbcUrl：        根据ContainerConnectionSource<JdbcDatabaseContainer<?>>获取数据库的JDBC URL。
# getDriverClassName：根据ContainerConnectionSource<JdbcDatabaseContainer<?>>获取数据库的驱动器类名，默认值：JDBC URL中指定的驱动器类名。
org.springframework.boot.testcontainers.service.connection.flyway.FlywayContainerConnectionDetailsFactory.FlywayContainerConnectionDetails

```
