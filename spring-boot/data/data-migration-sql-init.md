# 数据库初始化

## 初始化属性

### spring.sql.init.*

```

# 配置属性类：SqlInitializationProperties
spring.sql.init.schema-locations  数据库schema脚本（DDL）的位置
spring.sql.init.data-locations    数据库data脚本（DML）的位置
spring.sql.init.platform          默认的schema脚本（DDL）位置和data脚本（DML）位置中使用的平台，schema-${platform}.sql和data-${platform}.sql，默认值：all
spring.sql.init.username          数据库的用户名
spring.sql.init.password          数据库的密码
spring.sql.init.continue-on-error 数据库初始化脚本发生错误时，是否继续，默认值：false
spring.sql.init.separator         数据库初始化脚本的分隔符，默认值：";"
spring.sql.init.encoding          数据库初始化脚本使用的编码
spring.sql.init.mode              数据库初始化模式，默认值：EMBEDDED

```

### SqlInitializationProperties

```

# @ConfigurationProperties：配置属性，SQL数据库初始化配置属性前缀：spring.sql.init。
# schemaLocations：数据库schema脚本（DDL）的位置
# dataLocations：  数据库data脚本（DML）的位置
# platform：       默认的schema脚本（DDL）位置和data脚本（DML）位置中使用的平台，schema-${platform}.sql和data-${platform}.sql，默认值：all
# username：       数据库的用户名
# password：       数据库的密码
# continueOnError：数据库初始化脚本发生错误时，是否继续，默认值：false
# separator：      数据库初始化脚本的分隔符，默认值：";"
# encoding：       数据库初始化脚本使用的编码
# mode：           数据库初始化模式，默认值：EMBEDDED
org.springframework.boot.autoconfigure.sql.init.SqlInitializationProperties

```

### DatabaseInitializationSettings

```

# 数据库初始化设置。
# schemaLocations：数据库schema脚本（DDL）的位置，默认情况下，位置不存在时数据库初始化失败，在位置前面添加optional:前缀可以防止数据库初始化失败
# dataLocations：  数据库data脚本（DML）的位置，默认情况下，位置不存在时数据库初始化失败，在位置前面添加optional:前缀可以防止数据库初始化失败
# continueOnError：schema脚本（DDL）或data脚本（DML）发生错误时，是否继续，默认值：false
# separator：      schema脚本（DDL）或data脚本（DML）的分隔符，默认值：";"
# encoding：       schema脚本（DDL）或data脚本（DML）使用的编码
# mode：           数据库初始化模式，默认值：EMBEDDED
org.springframework.boot.sql.init.DatabaseInitializationSettings

```

### DatabaseInitializationMode

```

# 数据库初始化模式。
# ALWAYS：  总是初始化数据库
# EMBEDDED：只初始化嵌入式数据库
# NEVER：   从不初始化数据库
org.springframework.boot.sql.init.DatabaseInitializationMode

```

### SettingsCreator

```

# 数据库初始化设置创建器。
# 未指定数据库schema脚本（DDL）的位置时，默认为：optional:classpath*:schema-all.sql或optional:classpath*:schema.sql。
# 未指定数据库data脚本（DML）的位置时，默认为：optional:classpath*:data-all.sql或optional:classpath*:data.sql。
# createFrom：根据SqlInitializationProperties创建DatabaseInitializationSettings
org.springframework.boot.autoconfigure.sql.init.SettingsCreator

```

## 初始化配置

### SqlInitializationAutoConfiguration

```

# @AutoConfiguration：自动配置类：SQL数据库初始化。
# @EnableConfigurationProperties：启用配置属性：SqlInitializationProperties。
# @Import：引入配置类：DatabaseInitializationDependencyConfigurer、DataSourceInitializationConfiguration、R2dbcInitializationConfiguration。
# @ConditionalOnProperty：前提条件：spring.sql.init.enabled=true或spring.sql.init.enabled不存在。
# @Conditional：前提条件：满足SqlInitializationModeCondition，即spring.sql.init.mode!=never。
org.springframework.boot.autoconfigure.sql.init.SqlInitializationAutoConfiguration

```

### DatabaseInitializationDependencyConfigurer

```

# ImportBeanDefinitionRegistrar：引入Bean定义的注册器：数据库初始化依赖配置器。
# 把依赖于数据库初始化的Bean配置为依赖于执行数据库初始化的Bean。
# 在定义数据库初始化Bean或定义依赖于数据库初始化的Bean的配置类中引入这个配置器：@Import(DatabaseInitializationDependencyConfigurer.class)。
# DatabaseInitializerDetector：用于检测初始化数据库的Bean。
# DependsOnDatabaseInitializationDetector：用于检测依赖于数据库初始化的Bean。
# registerBeanDefinitions：如果BeanDefinitionRegistry中不存在DependsOnDatabaseInitializationPostProcessor Bean，则构造这个Bean，并把它注册到BeanDefinitionRegistry中。
org.springframework.boot.sql.init.dependency.DatabaseInitializationDependencyConfigurer

# 配置数据库初始化依赖关系的后置处理器。
# BeanFactoryPostProcessor BeanFactory的后置处理器。
# postProcessBeanFactory：检测数据库初始化器和依赖于数据库初始化的Bean，调用BeanDefinition.setDependsOn方法，设置数据库初始化器和依赖于数据库初始化的Bean的依赖关系。
org.springframework.boot.sql.init.dependency.DatabaseInitializationDependencyConfigurer.DependsOnDatabaseInitializationPostProcessor

# 数据库初始化器的Bean名称。
# beanNames：          所有数据库初始化器的Bean名称
# byDetectorBeanNames：数据库初始化器检测器与数据库初始化器的Bean名称之间的映射
org.springframework.boot.sql.init.dependency.DatabaseInitializationDependencyConfigurer.DependsOnDatabaseInitializationPostProcessor.InitializerBeanNames

```

### DataSourceInitializationConfiguration

```

# @Configuration：配置类：配置DataSource访问的SQL数据库初始化。
# @ConditionalOnClass：前提条件，类路径中存在类：DatabasePopulator。
# @ConditionalOnSingleCandidate：前提条件，BeanFactory中存在一个候选Bean：DataSource。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：SqlDataSourceScriptDatabaseInitializer、SqlR2dbcScriptDatabaseInitializer。
#
# dataSourceScriptDatabaseInitializer：
# @Bean：创建Bean：SqlDataSourceScriptDatabaseInitializer，依赖Bean：SqlInitializationProperties、DataSource。
org.springframework.boot.autoconfigure.sql.init.DataSourceInitializationConfiguration

```

### R2dbcInitializationConfiguration

```

# @Configuration：配置类：配置R2DBC ConnectionFactory访问的SQL数据库初始化。
# @ConditionalOnClass：前提条件，类路径中存在类：DatabasePopulator、ConnectionFactory。
# @ConditionalOnSingleCandidate：前提条件，BeanFactory中存在一个候选Bean：ConnectionFactory。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：SqlDataSourceScriptDatabaseInitializer、SqlR2dbcScriptDatabaseInitializer。
#
# r2dbcScriptDatabaseInitializer：
# @Bean：创建Bean：SqlR2dbcScriptDatabaseInitializer，依赖Bean：SqlInitializationProperties、ConnectionFactory。
org.springframework.boot.autoconfigure.sql.init.R2dbcInitializationConfiguration

```

## 初始化条件

### SqlInitializationModeCondition

```

# 数据库初始化条件。
org.springframework.boot.autoconfigure.condition.SpringBootCondition
    org.springframework.boot.autoconfigure.condition.AbstractNestedCondition
        org.springframework.boot.autoconfigure.condition.NoneNestedConditions
            org.springframework.boot.autoconfigure.sql.init.SqlInitializationAutoConfiguration.SqlInitializationModeCondition

# 数据库初始化条件。
# NoneNestedConditions：所有嵌套的条件类都不匹配时，则满足条件。
# 满足条件的情况：spring.sql.init.mode!=never。
# 测试条件的阶段：PARSE_CONFIGURATION（解析配置时）。
# 嵌套的条件类：ModeIsNever。
org.springframework.boot.autoconfigure.sql.init.SqlInitializationAutoConfiguration.SqlInitializationModeCondition

# @ConditionalOnProperty：前提条件：spring.sql.init.mode=never。
org.springframework.boot.autoconfigure.sql.init.SqlInitializationAutoConfiguration.SqlInitializationModeCondition.ModeIsNever

```

### OnDatabaseInitializationCondition

```

# 数据库初始化条件。
org.springframework.boot.autoconfigure.condition.SpringBootCondition
    org.springframework.boot.autoconfigure.sql.init.OnDatabaseInitializationCondition
        org.springframework.boot.autoconfigure.batch.BatchAutoConfiguration.OnBatchDatasourceInitializationCondition
        org.springframework.boot.autoconfigure.integration.IntegrationAutoConfiguration.OnIntegrationDatasourceInitializationCondition
        org.springframework.boot.autoconfigure.quartz.QuartzAutoConfiguration.JdbcStoreTypeConfiguration.OnQuartzDatasourceInitializationCondition
        org.springframework.boot.autoconfigure.session.JdbcSessionConfiguration.OnJdbcSessionDatasourceInitializationCondition

# 数据库初始化条件：检查是否应该执行特定组件的数据库初始化。
# name：           组件名称。
# propertyNames：  属性名称，根据属性名称查找配置属性，使用第一个查找到的配置属性，忽略剩余的属性名称。
# getMatchOutcome：根据查找到的配置属性的值（默认为EMBEDDED）进行检测，配置属性的值不等于NEVER时，则满足条件。
org.springframework.boot.autoconfigure.sql.init.OnDatabaseInitializationCondition

# Spring Batch的数据库初始化条件。
# spring.batch.jdbc.initialize-schema!=NEVER
# spring.batch.initialize-schema!=NEVER
org.springframework.boot.autoconfigure.batch.BatchAutoConfiguration.OnBatchDatasourceInitializationCondition

# Spring Integration的数据库初始化条件。
# spring.integration.jdbc.initialize-schema!=NEVER
org.springframework.boot.autoconfigure.integration.IntegrationAutoConfiguration.OnIntegrationDatasourceInitializationCondition

# Quartz Scheduler的数据库初始化条件。
# spring.quartz.jdbc.initialize-schema!=NEVER
org.springframework.boot.autoconfigure.quartz.QuartzAutoConfiguration.JdbcStoreTypeConfiguration.OnQuartzDatasourceInitializationCondition

# Spring Session JDBC的数据库初始化条件。
# spring.session.jdbc.initialize-schema!=NEVER
org.springframework.boot.autoconfigure.session.JdbcSessionConfiguration.OnJdbcSessionDatasourceInitializationCondition

```

## 初始化器

### AbstractScriptDatabaseInitializer

```

# 数据库初始化器。
org.springframework.boot.sql.init.AbstractScriptDatabaseInitializer
    org.springframework.boot.jdbc.init.DataSourceScriptDatabaseInitializer
        org.springframework.boot.autoconfigure.sql.init.SqlDataSourceScriptDatabaseInitializer
        org.springframework.boot.autoconfigure.batch.BatchDataSourceScriptDatabaseInitializer
        org.springframework.boot.autoconfigure.integration.IntegrationDataSourceScriptDatabaseInitializer
        org.springframework.boot.autoconfigure.quartz.QuartzDataSourceScriptDatabaseInitializer
        org.springframework.boot.autoconfigure.session.JdbcSessionDataSourceScriptDatabaseInitializer
    org.springframework.boot.r2dbc.init.R2dbcScriptDatabaseInitializer
        org.springframework.boot.autoconfigure.sql.init.SqlR2dbcScriptDatabaseInitializer

# 数据库初始化器：获取schema脚本（DDL）脚本或data脚本（DML），执行脚本，初始化SQL数据库。
# OPTIONAL_LOCATION_PREFIX：可选位置前缀，默认值："optional:"。
# settings：                数据库初始化配置（DatabaseInitializationSettings）。
# resourceLoader：          资源加载器（ResourceLoader）。
# setResourceLoader：       设置资源加载器（ResourceLoaderAware）。
# afterPropertiesSet：      属性设置之后（InitializingBean），调用initializeDatabase。
# initializeDatabase：      初始化数据库。
# runScripts：              执行数据库初始化脚本。
# isEmbeddedDatabase：      是否嵌入式数据库。
org.springframework.boot.sql.init.AbstractScriptDatabaseInitializer

# DataSource的数据库初始化器。
# dataSource：        数据源（DataSource）。
# getDataSource：     获取DataSource。
# customize：         自定义ResourceDatabasePopulator。
# runScripts：        通过ResourceDatabasePopulator.populate执行数据库初始化脚本。
# isEmbeddedDatabase：通过EmbeddedDatabaseConnection.isEmbedded检查是否嵌入式数据库。
org.springframework.boot.jdbc.init.DataSourceScriptDatabaseInitializer

# SQL DataSource的数据库初始化器。
# 可以注册自定义SqlDataSourceScriptDatabaseInitializer Bean，覆盖自动化配置。
# @ImportRuntimeHints：引入RuntimeHints注册器：SqlInitializationScriptsRuntimeHints。
# getSettings：根据SqlInitializationProperties创建DatabaseInitializationSettings。
org.springframework.boot.autoconfigure.sql.init.SqlDataSourceScriptDatabaseInitializer

# Spring Batch DataSource的数据库初始化器。
# 可以注册自定义BatchDataSourceScriptDatabaseInitializer Bean，覆盖自动化配置。
# getSettings：根据BatchProperties.Jdbc创建DatabaseInitializationSettings。
org.springframework.boot.autoconfigure.batch.BatchDataSourceScriptDatabaseInitializer

# Spring Integration DataSource的数据库初始化器。
# 可以注册自定义IntegrationDataSourceScriptDatabaseInitializer Bean，覆盖自动化配置。
# getSettings：根据IntegrationProperties.Jdbc创建DatabaseInitializationSettings。
org.springframework.boot.autoconfigure.integration.IntegrationDataSourceScriptDatabaseInitializer

# Quartz Scheduler DataSource的数据库初始化器。
# 可以注册自定义QuartzDataSourceScriptDatabaseInitializer Bean，覆盖自动化配置。
# commentPrefixes：注释前缀。
# customize：      commentPrefixes不为空时，设置ResourceDatabasePopulator的注释前缀。
# getSettings：    根据QuartzProperties创建DatabaseInitializationSettings。
org.springframework.boot.autoconfigure.quartz.QuartzDataSourceScriptDatabaseInitializer

# Spring Session JDBC DataSource的数据库初始化器。
# 可以注册自定义JdbcSessionDataSourceScriptDatabaseInitializer Bean，覆盖自动化配置。
# getSettings：根据JdbcSessionProperties创建DatabaseInitializationSettings。
org.springframework.boot.autoconfigure.session.JdbcSessionDataSourceScriptDatabaseInitializer

# R2DBC ConnectionFactory的数据库初始化器。
# connectionFactory： 连接工厂（ConnectionFactory）。
# runScripts：        通过ResourceDatabasePopulator.populate执行数据库初始化脚本。
# isEmbeddedDatabase：通过EmbeddedDatabaseConnection.isEmbedded检查是否嵌入式数据库。
org.springframework.boot.r2dbc.init.R2dbcScriptDatabaseInitializer

# SQL R2DBC ConnectionFactory的数据库初始化器。
# 可以注册自定义SqlR2dbcScriptDatabaseInitializer Bean，覆盖自动化配置。
# @ImportRuntimeHints：引入RuntimeHints注册器：SqlInitializationScriptsRuntimeHints。
# getSettings：根据SqlInitializationProperties创建DatabaseInitializationSettings。
org.springframework.boot.autoconfigure.sql.init.SqlR2dbcScriptDatabaseInitializer

```

### ScriptLocationResolver

```

# 数据库初始化脚本的位置解析器。
# resourcePatternResolver：资源模式解析器（ResourcePatternResolver）。
org.springframework.boot.sql.init.AbstractScriptDatabaseInitializer.ScriptLocationResolver

```

### Scripts

```

# 数据库初始化脚本（Resource）。
# resources：      数据库初始化脚本。
# continueOnError：数据库初始化脚本发生错误时，是否继续，默认值：false。
# separator：      数据库初始化脚本的分隔符，默认值：";"。
# encoding：       数据库初始化脚本使用的编码。
org.springframework.boot.sql.init.AbstractScriptDatabaseInitializer.Scripts

```

### SqlInitializationScriptsRuntimeHints

```

# SQL数据库初始化脚本的RuntimeHints注册器（RuntimeHintsRegistrar）。
# registerHints：注册资源模式：schema.sql、schema-*.sql、data.sql、data-*.sql。
org.springframework.boot.autoconfigure.sql.init.SqlInitializationScriptsRuntimeHints

```

## 检测器

### BeansOfTypeDetector

```

# Bean检测器：检测指定类型的Bean。
# types： 检测的Bean类型。
# detect：检测ListableBeanFactory中types类型的Bean。
org.springframework.boot.sql.init.dependency.BeansOfTypeDetector

```

### DatabaseInitializerDetector

```

# 数据库初始化器检测器。
org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector
    org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDatabaseInitializerDetector
        org.springframework.boot.jdbc.init.DataSourceScriptDatabaseInitializerDetector
        org.springframework.boot.orm.jpa.JpaDatabaseInitializerDetector
        org.springframework.boot.r2dbc.init.R2dbcScriptDatabaseInitializerDetector

# 数据库初始化器检测器。
# 实现类应该注册在META-INF/spring.factories的org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector下面。
# detect：           检测ConfigurableListableBeanFactory中定义的初始化DataSource的Bean。
# detectionComplete：所有数据库初始化器检测器都已调用，并且初始化DataSource的Bean都已检测完成后的回调方法。
# getOrder：         获取优先级顺序，数值越小，优先级越高，默认值：0。
org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector

# 数据库初始化器检测器：检测指定类型的Bean。
# getDatabaseInitializerBeanTypes：获取数据库初始化器的Bean类型。
org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDatabaseInitializerDetector

# 数据库初始化器检测器，检测指定类型的Bean：DataSourceScriptDatabaseInitializer。
# 优先级顺序：Ordered.LOWEST_PRECEDENCE - 100。
org.springframework.boot.jdbc.init.DataSourceScriptDatabaseInitializerDetector

# 数据库初始化器检测器，检测指定类型的Bean：。
# spring.jpa.defer-datasource-initialization=true时：检测：EntityManagerFactory。
# spring.jpa.defer-datasource-initialization=false或不存在时：不进行检测。
# detectionComplete：配置其他依赖于JPA初始化器的初始化器。
org.springframework.boot.orm.jpa.JpaDatabaseInitializerDetector

# 数据库初始化器检测器，检测指定类型的Bean：R2dbcScriptDatabaseInitializer。
org.springframework.boot.r2dbc.init.R2dbcScriptDatabaseInitializerDetector

```

### DependsOnDatabaseInitializationDetector

```

# 依赖于数据库初始化的Bean检测器。
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector
    org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDependsOnDatabaseInitializationDetector
        org.springframework.boot.jdbc.SpringJdbcDependsOnDatabaseInitializationDetector
        org.springframework.boot.orm.jpa.JpaDependsOnDatabaseInitializationDetector
        org.springframework.boot.autoconfigure.batch.JobRepositoryDependsOnDatabaseInitializationDetector
        org.springframework.boot.autoconfigure.quartz.SchedulerDependsOnDatabaseInitializationDetector
        org.springframework.boot.autoconfigure.session.JdbcIndexedSessionRepositoryDependsOnDatabaseInitializationDetector
    org.springframework.boot.sql.init.dependency.AnnotationDependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器。
# 实现类应该注册在META-INF/spring.factories的org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector下面。
# detect：检测ConfigurableListableBeanFactory中定义的依赖于数据库初始化的Bean。
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器：检测指定类型的Bean。
# getDependsOnDatabaseInitializationBeanTypes：获取依赖于数据库初始化的Bean的类型。
org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器，检测指定类型的Bean：JdbcOperations、NamedParameterJdbcOperations。
org.springframework.boot.jdbc.SpringJdbcDependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器，检测指定类型的Bean：
# spring.jpa.defer-datasource-initialization=true时：不进行检测。
# spring.jpa.defer-datasource-initialization=false或不存在时：检测EntityManagerFactory、AbstractEntityManagerFactoryBean。
org.springframework.boot.orm.jpa.JpaDependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器，检测指定类型的Bean：JobRepository。
org.springframework.boot.autoconfigure.batch.JobRepositoryDependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器，检测指定类型的Bean：Scheduler、SchedulerFactoryBean。
org.springframework.boot.autoconfigure.quartz.SchedulerDependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器，检测指定类型的Bean：JdbcIndexedSessionRepository。
org.springframework.boot.autoconfigure.session.JdbcIndexedSessionRepositoryDependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器，检测指定注解注释的Bean：@DependsOnDatabaseInitialization。
org.springframework.boot.sql.init.dependency.AnnotationDependsOnDatabaseInitializationDetector

```

### DependsOnDatabaseInitialization

```

# 注解@DependsOnDatabaseInitialization：表示Bean的创建和初始化依赖于数据库初始化。
# @Target：注解的目标：Bean的class类（TYPE）、@Bean注解的方法（METHOD）。
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitialization

```
