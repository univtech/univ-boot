# Flyway

## Flyway属性

### spring.flyway.*

```

spring.flyway.baseline-description
spring.flyway.baseline-on-migrate
spring.flyway.baseline-version
spring.flyway.batch
spring.flyway.cherry-pick
spring.flyway.clean-disabled
spring.flyway.clean-on-validation-error
spring.flyway.connect-retries
spring.flyway.connect-retries-interval
spring.flyway.create-schemas
spring.flyway.default-schema
spring.flyway.detect-encoding
spring.flyway.driver-class-name
spring.flyway.enabled
spring.flyway.encoding
spring.flyway.error-overrides
spring.flyway.execute-in-transaction
spring.flyway.fail-on-missing-locations
spring.flyway.group
spring.flyway.ignore-migration-patterns
spring.flyway.init-sqls
spring.flyway.installed-by
spring.flyway.jdbc-properties.*
spring.flyway.kerberos-config-file
spring.flyway.license-key
spring.flyway.locations
spring.flyway.lock-retry-count
spring.flyway.loggers
spring.flyway.mixed
spring.flyway.oracle-kerberos-cache-file
spring.flyway.oracle-sqlplus
spring.flyway.oracle-sqlplus-warn
spring.flyway.oracle-wallet-location
spring.flyway.out-of-order
spring.flyway.output-query-results
spring.flyway.password
spring.flyway.placeholder-prefix
spring.flyway.placeholder-replacement
spring.flyway.placeholder-separator
spring.flyway.placeholder-suffix
spring.flyway.placeholders.*
spring.flyway.repeatable-sql-migration-prefix
spring.flyway.schemas
spring.flyway.script-placeholder-prefix
spring.flyway.script-placeholder-suffix
spring.flyway.skip-default-callbacks
spring.flyway.skip-default-resolvers
spring.flyway.skip-executing-migrations
spring.flyway.sql-migration-prefix
spring.flyway.sql-migration-separator
spring.flyway.sql-migration-suffixes
spring.flyway.sql-server-kerberos-login-file
spring.flyway.stream
spring.flyway.table
spring.flyway.tablespace
spring.flyway.target
spring.flyway.url
spring.flyway.user
spring.flyway.validate-migration-naming
spring.flyway.validate-on-migrate

```

### management.endpoint.flyway.*

```

management.endpoint.flyway.cache.time-to-live
management.endpoint.flyway.enabled

```

### FlywayProperties

```

org.springframework.boot.autoconfigure.flyway.FlywayProperties

```

## Flyway配置

### FlywayAutoConfiguration

```

# @AutoConfiguration：自动配置类：在DataSourceAutoConfiguration、JdbcTemplateAutoConfiguration和HibernateJpaAutoConfiguration配置之后配置Flyway数据库迁移。
# @Import：引入配置类：DatabaseInitializationDependencyConfigurer。
# @ImportRuntimeHints：引入RuntimeHints注册器：FlywayAutoConfigurationRuntimeHints。
# @ConditionalOnClass：前提条件，类路径中存在类：Flyway。
# @ConditionalOnProperty：前提条件，spring.flyway.enabled=true或spring.flyway.enabled不存在。
# @Conditional：前提条件：满足FlywayDataSourceCondition，即。
#
# stringOrNumberMigrationVersionConverter：
# @Bean：创建Bean：StringOrNumberToMigrationVersionConverter。
# @ConfigurationPropertiesBinding：需要配置@ConfigurationProperties的绑定。
#
# flywayDefaultDdlModeProvider：
# @Bean：创建Bean：FlywaySchemaManagementProvider，依赖Bean：Flyway。
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration

```

### FlywayConfiguration

```

# @Configuration：配置类：配置Flyway。
# @EnableConfigurationProperties：启用配置属性：FlywayProperties。
# @ConditionalOnClass：前提条件，类路径中存在类：JdbcUtils。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：Flyway。
#
# resourceProviderCustomizer：
# @Bean：创建Bean：ResourceProviderCustomizer。
#
# flywayConnectionDetails：
# @Bean：创建Bean：PropertiesFlywayConnectionDetails，依赖Bean：FlywayProperties。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：FlywayConnectionDetails。
#
# flyway：
# @Bean：创建Bean：Flyway，依赖Bean：FlywayProperties、FlywayConnectionDetails、FlywayConfigurationCustomizer、ResourceLoader、ResourceProviderCustomizer、DataSource、@FlywayDataSource注解的DataSource、JavaMigration、Callback。
#
# flywayInitializer：
# @Bean：创建Bean：FlywayMigrationInitializer，依赖Bean：FlywayMigrationStrategy。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：FlywayMigrationInitializer。
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayConfiguration

```

### FlywayConfigurationCustomizer

```

# FlywayConfiguration定制器。
# 要自定义Flyway配置的Bean实现的回调接口。
# customize：自定义Flyway配置（FluentConfiguration）。
org.springframework.boot.autoconfigure.flyway.FlywayConfigurationCustomizer

```

### FlywayEndpointAutoConfiguration

```

# @AutoConfiguration：自动配置类：在FlywayAutoConfiguration配置之后配置FlywayEndpoint。
# @ConditionalOnClass：前提条件，类路径中存在类：Flyway。
# @ConditionalOnAvailableEndpoint：前提条件，端点可用：FlywayEndpoint。
#
# flywayEndpoint：
# @Bean：创建Bean：FlywayEndpoint，依赖Bean：ApplicationContext。
# @ConditionalOnBean：前提条件，BeanFactory中存在Bean：Flyway。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：FlywayEndpoint。
org.springframework.boot.actuate.autoconfigure.flyway.FlywayEndpointAutoConfiguration

```

## Flyway资源

### FlywayAutoConfigurationRuntimeHints

```

# Flyway自动配置的RuntimeHints注册器（RuntimeHintsRegistrar）。
# registerHints：注册资源模式：db/migration/*。
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayAutoConfigurationRuntimeHints

```

## XXX

```




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
