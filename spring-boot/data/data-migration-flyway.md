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
# @Conditional：前提条件：满足FlywayDataSourceCondition，即BeanFactory中存在Bean：DataSource或JdbcConnectionDetails，或者存在spring.flyway.url。
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

### NativeImageResourceProvider

```

# 支持GraalVM Native镜像的Flyway资源提供者（ResourceProvider）。
# 委托Flyways Scanner，并使用PathMatchingResourcePatternResolver在Native镜像中查找迁移文件。
# scanner：               扫描器（Scanner<?>）。
# classLoader：           类加载器（ClassLoader）。
# locations：             位置（Location）集合。
# encoding：              字符集（Charset）。
# failOnMissingLocations：位置错误时是否抛出异常。
# locatedResources：      定位到的资源（LocatedResource）列表。
# lock：                  锁（ReentrantLock）。
# initialized：           是否已经初始化。
# getResource：           获取资源。
org.springframework.boot.autoconfigure.flyway.NativeImageResourceProvider

# 定位到的资源。
org.springframework.boot.autoconfigure.flyway.NativeImageResourceProvider.LocatedResource

```

### ResourceProviderCustomizer

```

org.springframework.boot.autoconfigure.flyway.ResourceProviderCustomizer
    org.springframework.boot.autoconfigure.flyway.NativeImageResourceProviderCustomizer

# 资源提供者定制器。
# 在Native镜像中运行时，会被NativeImageResourceProviderCustomizer替代。
# customize：自定义FluentConfiguration。
org.springframework.boot.autoconfigure.flyway.ResourceProviderCustomizer

# Native镜像的资源提供者定制器。
# 把NativeImageResourceProvider注册为Flyway的ResourceProvider。
# customize：自定义FluentConfiguration。
org.springframework.boot.autoconfigure.flyway.NativeImageResourceProviderCustomizer

```

### ResourceProviderCustomizerBeanRegistrationAotProcessor

```

# ResourceProviderCustomizer Bean注册的AOT处理器（BeanRegistrationAotProcessor）。
# 把ResourceProviderCustomizer Bean替换为NativeImageResourceProviderCustomizer Bean。
# processAheadOfTime：根据RegisteredBean创建BeanRegistrationAotContribution（AotContribution）。
org.springframework.boot.autoconfigure.flyway.ResourceProviderCustomizerBeanRegistrationAotProcessor

# AOT Bean注册代码片段装饰器。
# registeredBean：              注册的Bean（RegisteredBean）。
# generateInstanceSupplierCode：生成实例的Supplier代码。
org.springframework.boot.autoconfigure.flyway.ResourceProviderCustomizerBeanRegistrationAotProcessor.AotContribution

```

## Flyway条件

### FlywayDataSourceCondition

```

# Flyway DataSource条件。
org.springframework.boot.autoconfigure.condition.SpringBootCondition
    org.springframework.boot.autoconfigure.condition.AbstractNestedCondition
        org.springframework.boot.autoconfigure.condition.AnyNestedCondition
            org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition

# Flyway DataSource条件。
# AnyNestedCondition：任何嵌套的条件类匹配时，则满足条件。
# 满足条件的情况：BeanFactory中存在Bean：DataSource或JdbcConnectionDetails，或者存在spring.flyway.url。
# 测试条件的阶段：REGISTER_BEAN（注册Bean时）。
# 嵌套的条件类：DataSourceBeanCondition、JdbcConnectionDetailsCondition、FlywayUrlCondition。
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition

# @ConditionalOnBean：前提条件，BeanFactory中存在Bean：DataSource。
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition.DataSourceBeanCondition

# @ConditionalOnBean：前提条件，BeanFactory中存在Bean：JdbcConnectionDetails。
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition.JdbcConnectionDetailsCondition

# @ConditionalOnProperty：前提条件，存在spring.flyway.url
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.FlywayDataSourceCondition.FlywayUrlCondition

```

## Flyway连接

### FlywayConnectionDetails

```

# Flyway连接详情。
org.springframework.boot.autoconfigure.service.connection.ConnectionDetails
    org.springframework.boot.autoconfigure.flyway.FlywayConnectionDetails
        org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.PropertiesFlywayConnectionDetails

# Flyway连接详情：使用JDBC建立SQL服务连接。
# getUsername：       获取数据库的用户名。
# getPassword：       获取数据库的密码。
# getJdbcUrl：        获取数据库的JDBC URL。
# getDriverClassName：获取数据库的驱动器类名，默认值：JDBC URL中指定的驱动器类名。
org.springframework.boot.autoconfigure.flyway.FlywayConnectionDetails

# Flyway属性的连接详情。
# properties：        Flyway配置属性：FlywayProperties。
# getUsername：       根据FlywayProperties获取数据库的用户名。
# getPassword：       根据FlywayProperties获取数据库的密码。
# getJdbcUrl：        根据FlywayProperties获取数据库的JDBC URL。
# getDriverClassName：根据FlywayProperties获取数据库的驱动器类名，默认值：JDBC URL中指定的驱动器类名。
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.PropertiesFlywayConnectionDetails

```

## Flyway策略

### FlywayMigrationStrategy

```

# Flyway迁移策略：初始化Flyway迁移。
# 可以注册自定义FlywayMigrationStrategy Bean，覆盖自动配置的迁移行为。
# migrate：执行Flyway迁移。
org.springframework.boot.autoconfigure.flyway.FlywayMigrationStrategy

```

### FlywayMigrationInitializer

```

# Flyway迁移初始化器：通过FlywayMigrationStrategy执行Flyway迁移。
# flyway：            Flyway对象。
# migrationStrategy： Flyway迁移策略。
# order：             优先级顺序，默认值：0，最高优先级。
# afterPropertiesSet：属性设置之后，通过FlywayMigrationStrategy执行Flyway迁移。
# getOrder：          获取优先级顺序。
# setOrder：          设置优先级顺序。
org.springframework.boot.autoconfigure.flyway.FlywayMigrationInitializer

```

## Flyway数据源

### FlywayDataSource

```

# 注解@FlywayDataSource：注入到Flyway的DataSource的限定符注解。
# 如果用于注解第二个DataSource，则第一个主DataSource应该标记为@Primary。
# @Target：注解的目标：类（TYPE）、注解（ANNOTATION_TYPE）、字段（FIELD）、方法（METHOD）、参数（PARAMETER）。
# @Qualifier：限定符注解。
org.springframework.boot.autoconfigure.flyway.FlywayDataSource

```

### FlywaySchemaManagementProvider

```

# Flyway Schema管理提供者。
org.springframework.boot.jdbc.SchemaManagementProvider
    org.springframework.boot.autoconfigure.flyway.FlywaySchemaManagementProvider

# Flyway Schema管理提供者（SchemaManagementProvider）。
# 通过查找可用的Flyway实例来确定是否管理Schema。
# flywayInstances：    Flyway实例。
# getSchemaManagement：根据DataSource获取SchemaManagement。
org.springframework.boot.autoconfigure.flyway.FlywaySchemaManagementProvider

```

## Flyway转换器

### LocationResolver

```

# 位置解析器。
# VENDOR_PLACEHOLDER：供应商占位符："{vendor}"。
# dataSource：        DataSource对象。
# resolveLocations：  解析位置列表。
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.LocationResolver

```

### StringOrNumberToMigrationVersionConverter

```

# 迁移版本转换器。
# CONVERTIBLE_TYPES：  获取可转换的类型集合，把String或Number转换为MigrationVersion的ConvertiblePair集合。
# getConvertibleTypes：获取可转换的类型集合。
# convert：            把String或Number转换为MigrationVersion的ConvertiblePair集合。
org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration.StringOrNumberToMigrationVersionConverter

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
