# flyway

```

org.springframework.boot.flyway.FlywayDatabaseInitializerDetector

org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayAutoConfigurationRuntimeHints
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayConfiguration
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition.DataSourceBeanCondition
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition.FlywayUrlCondition
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition.JdbcConnectionDetailsCondition
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.LocationResolver
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.PropertiesFlywayConnectionDetails
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.StringOrNumberToMigrationVersionConverter
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration
org.springframework.boot.autoconfigure.flyway.FlywayConfigurationCustomizer
org.springframework.boot.autoconfigure.flyway.FlywayConnectionDetails
org.springframework.boot.autoconfigure.flyway.FlywayDataSource
org.springframework.boot.autoconfigure.flyway.FlywayMigrationInitializer
org.springframework.boot.autoconfigure.flyway.FlywayMigrationInitializerDatabaseInitializerDetector
org.springframework.boot.autoconfigure.flyway.FlywayMigrationStrategy
org.springframework.boot.autoconfigure.flyway.FlywayProperties
org.springframework.boot.autoconfigure.flyway.FlywaySchemaManagementProvider
org.springframework.boot.autoconfigure.flyway.NativeImageResourceProvider.LocatedResource
org.springframework.boot.autoconfigure.flyway.NativeImageResourceProvider
org.springframework.boot.autoconfigure.flyway.NativeImageResourceProviderCustomizer
org.springframework.boot.autoconfigure.flyway.ResourceProviderCustomizer
org.springframework.boot.autoconfigure.flyway.ResourceProviderCustomizerBeanRegistrationAotProcessor.AotContribution
org.springframework.boot.autoconfigure.flyway.ResourceProviderCustomizerBeanRegistrationAotProcessor

org.springframework.boot.actuate.flyway.FlywayEndpoint.ContextFlywayBeansDescriptor
org.springframework.boot.actuate.flyway.FlywayEndpoint.FlywayBeansDescriptor
org.springframework.boot.actuate.flyway.FlywayEndpoint.FlywayDescriptor
org.springframework.boot.actuate.flyway.FlywayEndpoint.FlywayMigrationDescriptor
org.springframework.boot.actuate.flyway.FlywayEndpoint

org.springframework.boot.actuate.autoconfigure.flyway.FlywayEndpointAutoConfiguration

org.springframework.boot.docker.compose.service.connection.flyway.JdbcAdaptingFlywayConnectionDetailsFactory.1
org.springframework.boot.docker.compose.service.connection.flyway.JdbcAdaptingFlywayConnectionDetailsFactory

org.springframework.boot.testcontainers.service.connection.flyway.FlywayContainerConnectionDetailsFactory.FlywayContainerConnectionDetails
org.springframework.boot.testcontainers.service.connection.flyway.FlywayContainerConnectionDetailsFactory









































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











