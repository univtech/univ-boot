# Liquibase

## 配置属性

### spring.liquibase.*

```

spring.liquibase.change-log

Change log configuration path.

classpath:/db/changelog/db.changelog-master.yaml

spring.liquibase.clear-checksums

Whether to clear all checksums in the current changelog, so they will be recalculated upon the next update.

false

spring.liquibase.contexts

Comma-separated list of runtime contexts to use.

spring.liquibase.database-change-log-lock-table

Name of table to use for tracking concurrent Liquibase usage.

DATABASECHANGELOGLOCK

spring.liquibase.database-change-log-table

Name of table to use for tracking change history.

DATABASECHANGELOG

spring.liquibase.default-schema

Default database schema.

spring.liquibase.driver-class-name

Fully qualified name of the JDBC driver. Auto-detected based on the URL by default.

spring.liquibase.drop-first

Whether to first drop the database schema.

false

spring.liquibase.enabled

Whether to enable Liquibase support.

true

spring.liquibase.label-filter

Comma-separated list of runtime labels to use.

spring.liquibase.liquibase-schema

Schema to use for Liquibase objects.

spring.liquibase.liquibase-tablespace

Tablespace to use for Liquibase objects.

spring.liquibase.parameters.*

Change log parameters.

spring.liquibase.password

Login password of the database to migrate.

spring.liquibase.rollback-file

File to which rollback SQL is written when an update is performed.

spring.liquibase.tag

Tag name to use when applying database changes. Can also be used with "rollbackFile" to generate a rollback script for all existing changes associated with that tag.

spring.liquibase.test-rollback-on-update

Whether rollback should be tested before update is performed.

false

spring.liquibase.url

JDBC URL of the database to migrate. If not set, the primary configured data source is used.

spring.liquibase.user

Login user of the database to migrate.


```

## Liquibase配置

### LiquibaseAutoConfiguration

```

# @AutoConfiguration：自动配置类：在DataSourceAutoConfiguration和HibernateJpaAutoConfiguration配置之后配置Liquibase。
# @Import：引入配置类：DatabaseInitializationDependencyConfigurer。
# @ImportRuntimeHints：引入RuntimeHints注册器：LiquibaseAutoConfigurationRuntimeHints。
# @ConditionalOnClass：前提条件，类路径中存在类：SpringLiquibase、DatabaseChange。
# @ConditionalOnProperty：前提条件，spring.liquibase.enabled=true或spring.liquibase.enabled不存在。
# @Conditional：前提条件：满足LiquibaseDataSourceCondition，即BeanFactory中存在Bean：DataSource或JdbcConnectionDetails，或者存在spring.liquibase.url。
# 
# liquibaseDefaultDdlModeProvider：
# @Bean：创建Bean：LiquibaseSchemaManagementProvider，依赖Bean：SpringLiquibase。
org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration

```

### LiquibaseConfiguration

```

# @Configuration：配置类：配置Liquibase。
# @EnableConfigurationProperties：启用配置属性：LiquibaseProperties。
# @ConditionalOnClass：前提条件，类路径中存在类：ConnectionCallback。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：SpringLiquibase。
# 
# liquibaseConnectionDetails：
# @Bean：创建Bean：PropertiesLiquibaseConnectionDetails，依赖Bean：LiquibaseProperties、JdbcConnectionDetails。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：LiquibaseConnectionDetails。
# 
# liquibase：
# @Bean：创建Bean：SpringLiquibase，依赖Bean：DataSource、@LiquibaseDataSource注解的DataSource、LiquibaseProperties、LiquibaseConnectionDetails。
org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration.LiquibaseConfiguration

```

## Liquibase条件

### LiquibaseDataSourceCondition

```

# Liquibase DataSource条件。
org.springframework.boot.autoconfigure.condition.SpringBootCondition
    org.springframework.boot.autoconfigure.condition.AbstractNestedCondition
        org.springframework.boot.autoconfigure.condition.AnyNestedCondition
            org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration.LiquibaseDataSourceCondition

# Liquibase DataSource条件。
# AnyNestedCondition：任何嵌套的条件类匹配时，则满足条件。
# 满足条件的情况：BeanFactory中存在Bean：DataSource或JdbcConnectionDetails，或者存在spring.liquibase.url。
# 测试条件的阶段：REGISTER_BEAN（注册Bean时）。
# 嵌套的条件类：DataSourceBeanCondition、JdbcConnectionDetailsCondition、LiquibaseUrlCondition。
org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration.LiquibaseDataSourceCondition

# @ConditionalOnBean：前提条件，BeanFactory中存在Bean：DataSource。
org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration.LiquibaseDataSourceCondition.DataSourceBeanCondition

# @ConditionalOnBean：前提条件，BeanFactory中存在Bean：JdbcConnectionDetails。
org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration.LiquibaseDataSourceCondition.JdbcConnectionDetailsCondition

# @ConditionalOnProperty：前提条件，存在spring.liquibase.url
org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration.LiquibaseDataSourceCondition.LiquibaseUrlCondition

```

### LiquibaseEndpointAutoConfiguration

```
# @AutoConfiguration：自动配置类：在LiquibaseAutoConfiguration配置之后配置LiquibaseEndpoint。
# @ConditionalOnClass：前提条件，类路径中存在类：SpringLiquibase。
# @ConditionalOnAvailableEndpoint：前提条件，端点可用：LiquibaseEndpoint。
# 
# liquibaseEndpoint：
# @Bean：创建Bean：LiquibaseEndpoint，依赖Bean：ApplicationContext。
# @ConditionalOnBean：前提条件，BeanFactory中存在Bean：SpringLiquibase。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：LiquibaseEndpoint。
# 
# preventDataSourceCloseBeanPostProcessor：
# @Bean：创建Bean：阻止关闭DataSource的Bean后置处理器（BeanPostProcessor），调用DataSourceClosingSpringLiquibase.setCloseDataSourceOnceMigrated(false)。
# @ConditionalOnBean：前提条件，BeanFactory中存在Bean：SpringLiquibase。
org.springframework.boot.actuate.autoconfigure.liquibase.LiquibaseEndpointAutoConfiguration

```

### LiquibaseAutoConfigurationRuntimeHints

```

# Liquibase自动配置的RuntimeHints注册器（RuntimeHintsRegistrar）。
# registerHints：注册资源模式：db/changelog/*。
org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration.LiquibaseAutoConfigurationRuntimeHints

```

## Liquibase属性

### LiquibaseProperties

```

# @ConfigurationProperties：配置属性，Liquibase配置属性前缀：spring.liquibase，不忽略未知字段。
# changeLog：                 Change log configuration path. = "classpath:/db/changelog/db.changelog-master.yaml";
# clearChecksums：            Whether to clear all checksums in the current changelog, so they will be recalculated upon the next update.
# contexts：                  Comma-separated list of runtime contexts to use.
# defaultSchema：             Default database schema.
# liquibaseSchema：           Schema to use for Liquibase objects.
# liquibaseTablespace：       Tablespace to use for Liquibase objects.
# databaseChangeLogTable：    Name of table to use for tracking change history. = "DATABASECHANGELOG"; 
# databaseChangeLogLockTable：Name of table to use for tracking concurrent Liquibase usage. = "DATABASECHANGELOGLOCK";
# dropFirst：                 Whether to first drop the database schema.
# enabled：                   Whether to enable Liquibase support. = true
# user：                      Login user of the database to migrate.
# password：                  Login password of the database to migrate.
# driverClassName：           Fully qualified name of the JDBC driver. Auto-detected based on the URL by default.
# url：                       JDBC URL of the database to migrate. If not set, the primary configured data source is used.
# labelFilter：               Comma-separated list of runtime labels to use.
# parameters：                Map<String, String>  Change log parameters.
# rollbackFile：              File File to which rollback SQL is written when an update is performed.
# testRollbackOnUpdate：      Whether rollback should be tested before update is performed.
# tag：                       Tag name to use when applying database changes. Can also be used with "rollbackFile" to generate a rollback script for all existing changes associated with that tag.
# getXXX：                     获取XXX
# isXXX：                      是否XXX
# setXXX：                     设置XXX
org.springframework.boot.autoconfigure.liquibase.LiquibaseProperties

```

### LiquibaseConnectionDetails

```

# Liquibase连接详情。
org.springframework.boot.autoconfigure.service.connection.ConnectionDetails
    org.springframework.boot.autoconfigure.liquibase.LiquibaseConnectionDetails
        org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration.PropertiesLiquibaseConnectionDetails
        org.springframework.boot.testcontainers.service.connection.liquibase.LiquibaseContainerConnectionDetailsFactory.LiquibaseContainerConnectionDetails

# Liquibase连接详情。
# getUsername：       获取数据库的用户名。
# getPassword：       获取数据库的密码。
# getJdbcUrl：        获取数据库的JDBC URL。
# getDriverClassName：获取数据库的驱动器类名，默认值：JDBC URL中指定的驱动器类名。
org.springframework.boot.autoconfigure.liquibase.LiquibaseConnectionDetails

# Liquibase属性的连接详情。
# properties：        Liquibase配置属性：LiquibaseProperties。
# getUsername：       根据LiquibaseProperties获取数据库的用户名。
# getPassword：       根据LiquibaseProperties获取数据库的密码。
# getJdbcUrl：        根据LiquibaseProperties获取数据库的JDBC URL。
# getDriverClassName：根据LiquibaseProperties获取数据库的驱动器类名，默认值：JDBC URL中指定的驱动器类名。
org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration.PropertiesLiquibaseConnectionDetails

# Liquibase容器的连接详情。
# getUsername：       根据ContainerConnectionSource<JdbcDatabaseContainer<?>获取数据库的用户名。
# getPassword：       根据ContainerConnectionSource<JdbcDatabaseContainer<?>获取数据库的密码。
# getJdbcUrl：        根据ContainerConnectionSource<JdbcDatabaseContainer<?>获取数据库的JDBC URL。
# getDriverClassName：根据ContainerConnectionSource<JdbcDatabaseContainer<?>获取数据库的驱动器类名，默认值：JDBC URL中指定的驱动器类名。
org.springframework.boot.testcontainers.service.connection.liquibase.LiquibaseContainerConnectionDetailsFactory.LiquibaseContainerConnectionDetails

```

## Liquibase数据源

### LiquibaseDataSource

```

# @LiquibaseDataSource注解：注入到Liquibase的DataSource的限定符注解。
# 如果用于第二个DataSource，则第一个主DataSource通常标记为@Primary。
# @Target：注解的目标：
# ElementType.FIELD：          字段
# ElementType.METHOD：         方法
# ElementType.PARAMETER：      参数
# ElementType.TYPE：           类
# ElementType.ANNOTATION_TYPE：注解
# @Qualifier：限定符注解。
org.springframework.boot.autoconfigure.liquibase.LiquibaseDataSource

```

### DataSourceClosingSpringLiquibase

```

# 数据库迁移完成之后关闭底层DataSource的自定义SpringLiquibase。
# closeDataSourceOnceMigrated：   是否关闭数据源。
# setCloseDataSourceOnceMigrated：设置是否关闭数据源。
# afterPropertiesSet：            关闭数据源，通过反射调用DataSource.close方法。
# destroy：                       销毁DataSourceClosingSpringLiquibase时的回调方法。
org.springframework.boot.autoconfigure.liquibase.DataSourceClosingSpringLiquibase

```

### LiquibaseSchemaManagementProvider

```

# Liquibase Schema管理提供者。
org.springframework.boot.jdbc.SchemaManagementProvider
    org.springframework.boot.autoconfigure.liquibase.LiquibaseSchemaManagementProvider

# Liquibase Schema管理提供者（SchemaManagementProvider）。
# 通过查找可用的SpringLiquibase实例来确定是否管理Schema。
# liquibaseInstances:  Liquibase实例。
# getSchemaManagement：根据DataSource获取SchemaManagement。
org.springframework.boot.autoconfigure.liquibase.LiquibaseSchemaManagementProvider

```

## Liquibase端点

### LiquibaseEndpoint

```

# @Endpoint：端点，暴露liquibase信息的端点ID：liquibase。
# context：应用程序上下文。
# liquibaseBeans：
# @ReadOperation：读取操作，读取liquibase信息，创建LiquibaseBeansDescriptor。
org.springframework.boot.actuate.liquibase.LiquibaseEndpoint

```

### LiquibaseBeansDescriptor

```

# 应用程序的SpringLiquibase Bean描述符。
org.springframework.boot.actuate.endpoint.OperationResponseBody
    org.springframework.boot.actuate.liquibase.LiquibaseEndpoint.LiquibaseBeansDescriptor

# 应用程序的SpringLiquibase Bean描述符。
# contexts：   应用程序上下文与ContextLiquibaseBeansDescriptor的映射。
# getContexts：获取应用程序上下文与ContextLiquibaseBeansDescriptor的映射。
org.springframework.boot.actuate.liquibase.LiquibaseEndpoint.LiquibaseBeansDescriptor

# 应用程序上下文的SpringLiquibase Bean描述符。
# liquibaseBeans：   应用程序上下文与LiquibaseBeanDescriptor的映射。
# parentId：         父应用程序上下文的ID。
# getLiquibaseBeans：获取应用程序上下文与LiquibaseBeanDescriptor的映射。
# getParentId：      获取父应用程序上下文的ID。
org.springframework.boot.actuate.liquibase.LiquibaseEndpoint.ContextLiquibaseBeansDescriptor

# SpringLiquibase Bean描述符。
# changeSets：   ChangeSetDescriptor列表。
# getChangeSets：获取ChangeSetDescriptor列表。
org.springframework.boot.actuate.liquibase.LiquibaseEndpoint.LiquibaseBeanDescriptor

# Liquibase变更集描述符。
# author：       作者。
# changeLog：    变更日志。
# comments：     注释。
# contexts：     上下文名称集合。
# dateExecuted： 执行时间点Instant。
# deploymentId： 部署ID。
# description：  描述。
# execType：     执行类型。
# id：           ID。
# labels：       标签集合。
# checksum：     校验和。
# orderExecuted：执行顺序。
# tag：          标记。
# getXXX：       获取XXX。
org.springframework.boot.actuate.liquibase.LiquibaseEndpoint.ChangeSetDescriptor

# ChangeSetDescriptor中的上下文表达式描述符。
# contexts：   上下文名称集合。
# getContexts：获取上下文名称集合。
org.springframework.boot.actuate.liquibase.LiquibaseEndpoint.ContextExpressionDescriptor

```

## Liquibase异常

### LiquibaseChangelogMissingFailureAnalyzer

```

# Liquibase Changelog缺失的失败分析器。
org.springframework.boot.diagnostics.FailureAnalyzer
    org.springframework.boot.diagnostics.AbstractFailureAnalyzer
        org.springframework.boot.liquibase.LiquibaseChangelogMissingFailureAnalyzer

# Liquibase Changelog缺失的失败分析器。
# analyze：分析ChangeLogParseException异常。
org.springframework.boot.liquibase.LiquibaseChangelogMissingFailureAnalyzer

```

## Liquibase容器

### JdbcAdaptingLiquibaseConnectionDetailsFactory

```

# Liquibase JDBC的连接详情工厂。
# getConnectionDetails：根据JdbcConnectionDetails获取LiquibaseConnectionDetails。
org.springframework.boot.docker.compose.service.connection.liquibase.JdbcAdaptingLiquibaseConnectionDetailsFactory

```

## Liquibase容器测试

### LiquibaseContainerConnectionDetailsFactory

```

# Liquibase容器的连接详情工厂。
org.springframework.boot.autoconfigure.service.connection.ConnectionDetailsFactory
    org.springframework.boot.testcontainers.service.connection.ContainerConnectionDetailsFactory
        org.springframework.boot.testcontainers.service.connection.liquibase.LiquibaseContainerConnectionDetailsFactory

# Liquibase容器的连接详情工厂。
# JdbcDatabaseContainer：@ServiceConnection注解的JDBC数据库容器。
# getContainerConnectionDetails：根据ContainerConnectionSource<JdbcDatabaseContainer<?>>获取LiquibaseConnectionDetails。
org.springframework.boot.testcontainers.service.connection.liquibase.LiquibaseContainerConnectionDetailsFactory

```

### LiquibaseDatabaseInitializerDetector

```

# 数据库初始化器检测器。
org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector
    org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDatabaseInitializerDetector
        org.springframework.boot.liquibase.LiquibaseDatabaseInitializerDetector

# 数据库初始化器检测器，检测指定类型的Bean：SpringLiquibase。
org.springframework.boot.liquibase.LiquibaseDatabaseInitializerDetector

```

