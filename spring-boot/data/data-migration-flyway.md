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

management.endpoint.flyway.cache.time-to-live：缓存响应的最长时间，默认值：0ms。
management.endpoint.flyway.enabled：           是否启用flyway端点，默认值：true。

```

### FlywayProperties

```

# @ConfigurationProperties：    配置属性，Flyway数据库迁移的配置属性前缀：spring.flyway。
# enabled：                     是否启用Flyway，默认值：true。
# failOnMissingLocations：      迁移脚本的位置不存在时是否抛出异常。
# locations：                   迁移脚本的位置列表，"{vendor}"占位符用于供应商特定的位置，默认值："classpath:db/migration"。
# encoding：                    SQL迁移的编码，默认值：UTF-8。
# connectRetries：              尝试连接数据库时的最大重试次数。
# connectRetriesInterval：      尝试连接数据库时的最大重试时间间隔，默认时间后缀为秒（SECONDS），默认值：120秒。
# lockRetryCount：              尝试获取锁时的最大重试次数，默认值：50。
# defaultSchema：               Flyway管理的默认Schema名称（区分大小写）。
# schemas：                     Flyway管理的Schema名称（区分大小写）。
# createSchemas：               Flyway是否应该尝试创建schemas属性中指定的Schema，默认值：true。
# table：                       Flyway使用的Schema历史表，默认值："flyway_schema_history"。
# tablespace：                  创建Schema历史表的表空间，使用不支持表空间的数据库时会被忽略，默认为Flyway使用的连接的默认表空间。
# baselineDescription：         应用基线时，标记现有Schema的描述，默认值："<< Flyway Baseline >>"。
# baselineVersion：             执行基线时，标记现有Schema的版本，默认值："1"。
# installedBy：                 Schema历史表中记录的已应用迁移的用户名。
# placeholders：                应用于SQL迁移脚本的占位符及其替代值key=value。
# placeholderPrefix：           迁移脚本中占位符的前缀，默认值："${"。
# placeholderSuffix：           迁移脚本中占位符的后缀，默认值："}"。
# placeholderSeparator：        默认占位符的分隔符，默认值：":"。
# placeholderReplacement：      是否替换迁移脚本中的占位符，默认值：true。
# sqlMigrationPrefix：          SQL迁移的文件名前缀，默认值："V"。
# sqlMigrationSuffixes：        SQL迁移的文件名后缀列表，默认值：".sql"。
# sqlMigrationSeparator：       SQL迁移的文件名分隔符，默认值："__"。
# repeatableSqlMigrationPrefix：可重复的SQL迁移的文件名前缀，默认值："R"。
# target：                      迁移的目标版本，默认值："latest"。
# user：                        迁移数据库的用户名。
# password：                    迁移数据库的密码。
# driverClassName：             JDBC驱动的全限定类名，默认根据URL自动检测。
# url：                         迁移数据库的JDBC URL，未设置时，使用配置的主数据源。
# initSqls：                    获得连接后立即初始化连接时执行的SQL语句列表。
# baselineOnMigrate：           迁移非空Schema时是否自动调用基线。
# cleanDisabled：               是否禁用数据库清理，默认值：true。
# cleanOnValidationError：      验证错误时是否自动调用清理。
# group：                       应用所有挂起的迁移时，是否把它们分组到同一事务中。
# mixed：                       同一迁移中是否允许混合事务和非事务语句。
# outOfOrder：                  是否允许不按顺序运行迁移。
# skipDefaultCallbacks：        是否跳过默认回调，true：只使用自定义回调。
# skipDefaultResolvers：        是否跳过默认解析器，true：只使用自定义解析器。
# validateMigrationNaming：     是否验证脚本不遵循正确命名约定的迁移和回调，默认值：false。
# validateOnMigrate：           执行迁移时是否自动调用验证，默认值：true。
# scriptPlaceholderPrefix：     迁移脚本中占位符的前缀，默认值："FP__"。
# scriptPlaceholderSuffix：     迁移脚本中占位符的后缀，默认值："__"。
# executeInTransaction：        Flyway是否应该在事务中执行SQL，默认值：true。
# loggers：                     Flyway使用的日志记录器，默认值：{ "slf4j" }。
# batch：                       执行SQL语句时是否批量处理，需要Flyway Team的支持。
# dryRunOutput：                试运行迁移的SQL语句输出的文件，需要Flyway Team的支持。
# errorOverrides：              内置的错误处理规则，以覆盖特定的SQL状态和错误代码，需要Flyway Team的支持。
# licenseKey：                  Flyway Team的许可密钥。
# oracleSqlplus：               是否启用Oracle SQL*Plus命令，需要Flyway Team的支持。
# oracleSqlplusWarn：           碰到不支持的Oracle SQL*Plus语句时，是否发出警告，而不是错误，需要Flyway Team的支持。
# stream：                      执行SQL语句时是否流式处理，需要Flyway Team的支持。
# undoSqlMigrationPrefix：      撤销SQL迁移的文件名前缀，需要Flyway Team的支持。
# cherryPick：                  迁移或撤销时，Flyway应该考虑的迁移，为空时，考虑所有可用迁移，需要Flyway Team的支持。
# jdbcProperties：              JDBC驱动的属性key=value，需要Flyway Team的支持。
# kerberosConfigFile：          Kerberos配置文件的路径，需要Flyway Team的支持。
# oracleKerberosCacheFile：     Oracle Kerberos缓存文件的路径，需要Flyway Team的支持。
# oracleWalletLocation：        Oracle Wallet的位置，用于自动登录数据库，需要Flyway Team的支持。
# outputQueryResults：          执行迁移时，Flyway是否应该输出包含查询结果的表，需要Flyway Team的支持。
# sqlServerKerberosLoginFile：  SQL服务器的Kerberos登录文件路径，需要Flyway Team的支持。
# skipExecutingMigrations：     Flyway是否应该跳过迁移内容的执行，只更新Schema的历史表，需要Flyway Team的支持。
# ignoreMigrationPatterns：     逗号分隔的模式列表，验证迁移时，忽略的迁移，需要Flyway Team的支持。
# detectEncoding：              是否尝试自动检测SQL迁移文件的编码，需要Flyway Team的支持。
# getXXX：                      获取XXX
# isXXX：                       是否XXX
# setXXX：                      设置XXX
org.springframework.boot.autoconfigure.flyway.FlywayProperties

```

## Flyway配置

### FlywayAutoConfiguration

```

# @AutoConfiguration：自动配置类：在DataSourceAutoConfiguration、JdbcTemplateAutoConfiguration和HibernateJpaAutoConfiguration配置之后配置Flyway数据库迁移。
# @Import：引入配置类：DatabaseInitializationDependencyConfigurer。
# @ImportRuntimeHints：引入RuntimeHints注册器：FlywayAutoConfigurationRuntimeHints。
# @ConditionalOnClass：前提条件，类路径中存在类：Flyway。
# @ConditionalOnProperty：前提条件：spring.flyway.enabled=true或spring.flyway.enabled不存在。
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

# @ConditionalOnProperty：前提条件：存在spring.flyway.url
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
