# JPA

org.springframework.boot.orm.jpa
org.springframework.boot.orm.jpa.hibernate
org.springframework.boot.autoconfigure.orm.jpa
org.springframework.boot.actuate.autoconfigure.metrics.orm.jpa
org.springframework.boot.test.autoconfigure.orm.jpa

## JPA属性

### spring.jpa.*

```

spring.jpa.database
spring.jpa.database-platform
spring.jpa.defer-datasource-initialization
spring.jpa.generate-ddl
spring.jpa.hibernate.ddl-auto
spring.jpa.hibernate.naming.implicit-strategy
spring.jpa.hibernate.naming.physical-strategy
spring.jpa.mapping-resources
spring.jpa.open-in-view
spring.jpa.properties.*
spring.jpa.show-sql

```

### spring.data.jpa.repositories.*

```

spring.data.jpa.repositories.enabled
spring.data.jpa.repositories.bootstrap-mode

org.springframework.boot.autoconfigure.orm.jpa.JpaProperties
org.springframework.boot.autoconfigure.orm.jpa.HibernateProperties
org.springframework.boot.autoconfigure.orm.jpa.HibernateProperties.Naming
org.springframework.boot.autoconfigure.orm.jpa.HibernatePropertiesCustomizer
org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaConfiguration.NamingStrategiesHibernatePropertiesCustomizer
```

## JPA配置

```

org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaAutoConfiguration
org.springframework.boot.actuate.autoconfigure.metrics.orm.jpa.HibernateMetricsAutoConfiguration

org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaConfiguration

org.springframework.boot.autoconfigure.orm.jpa.JpaBaseConfiguration
org.springframework.boot.autoconfigure.orm.jpa.JpaBaseConfiguration.JpaWebConfiguration
org.springframework.boot.autoconfigure.orm.jpa.JpaBaseConfiguration.JpaWebConfiguration.1
org.springframework.boot.autoconfigure.orm.jpa.JpaBaseConfiguration.PersistenceManagedTypesConfiguration
```

```


org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaConfiguration.HibernateRuntimeHints

org.springframework.boot.autoconfigure.orm.jpa.EntityManagerFactoryBuilderCustomizer
org.springframework.boot.autoconfigure.orm.jpa.EntityManagerFactoryDependsOnPostProcessor
org.springframework.boot.autoconfigure.orm.jpa.HibernateDefaultDdlAutoProvider
org.springframework.boot.autoconfigure.orm.jpa.HibernateSettings
```

### EntityManagerFactoryBuilder

```

# JPA EntityManagerFactory实例的构造器。
# 在构造时收集常见配置，通过流式构造器可以创建一个或多个LocalContainerEntityManagerFactoryBean。
# 构造器中包含了最常见的选项，也可以@Bean注解的方法返回LocalContainerEntityManagerFactoryBean之前执行更多的操作。
# jpaVendorAdapter：                JPA供应商适配器。
# persistenceUnitManager：          持久化单元管理器。
# jpaProperties：                   JPA属性。
# persistenceUnitRootLocation：     持久化单元的根目录。
# bootstrapExecutor：               启动时的异步任务执行器。
# persistenceUnitPostProcessors：   持久化单元的后置处理器。
#
# dataSource：                      根据DataSource，创建EntityManagerFactoryBuilder.Builder。
# setBootstrapExecutor：            设置AsyncTaskExecutor，用于LocalContainerEntityManagerFactoryBean。
# setPersistenceUnitPostProcessors：设置PersistenceUnitPostProcessor，应用于创建LocalContainerEntityManagerFactoryBean的PersistenceUnitInfo。
org.springframework.boot.orm.jpa.EntityManagerFactoryBuilder

# LocalContainerEntityManagerFactoryBean的流式构造器。
# dataSource：      数据源。
# managedTypes：    持久化托管的类型。
# packagesToScan：  扫描@Entity注解的包名。
# persistenceUnit： 持久化单元的名称。
# properties：      标准JPA或供应商特定配置的属性key=value。
# mappingResources：持久化单元的映射资源。
# jta：             是否使用JTA数据源。
#
# managedTypes：    配置持久化托管的类型。
# packages：        配置扫描@Entity注解的包名。
# persistenceUnit： 配置持久化单元的名称。
# properties：      配置标准JPA或供应商特定配置的属性。
# mappingResources：配置持久化单元的映射资源（等同于persistence.xml中的<mapping-file>）。映射资源必须相对于类路径的根目录，例如："META-INF/mappings.xml"或"com/mycompany/repository/mappings.xml"。
# jta：             配置是否使用JTA数据源。
# build：           构造LocalContainerEntityManagerFactoryBean。
org.springframework.boot.orm.jpa.EntityManagerFactoryBuilder.Builder

```

### JpaDatabaseInitializerDetector

```

# 数据库初始化器检测器。
org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector
    org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDatabaseInitializerDetector
        org.springframework.boot.jdbc.init.DataSourceScriptDatabaseInitializerDetector
        org.springframework.boot.orm.jpa.JpaDatabaseInitializerDetector

# 数据库初始化器检测器，检测指定类型的Bean：
# spring.jpa.defer-datasource-initialization=true时：检测：EntityManagerFactory。
# spring.jpa.defer-datasource-initialization=false或不存在时：不进行检测。
# detectionComplete：配置其他依赖于JPA初始化器的初始化器。
org.springframework.boot.orm.jpa.JpaDatabaseInitializerDetector

```

### JpaDependsOnDatabaseInitializationDetector

```

# 依赖于数据库初始化的Bean检测器。
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector
    org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDependsOnDatabaseInitializationDetector
        org.springframework.boot.jdbc.SpringJdbcDependsOnDatabaseInitializationDetector
        org.springframework.boot.orm.jpa.JpaDependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器，检测指定类型的Bean：
# spring.jpa.defer-datasource-initialization=true时：不进行检测。
# spring.jpa.defer-datasource-initialization=false或不存在时：检测EntityManagerFactory、AbstractEntityManagerFactoryBean。
org.springframework.boot.orm.jpa.JpaDependsOnDatabaseInitializationDetector

```

### SpringImplicitNamingStrategy

```

# Spring的Hibernate ImplicitNamingStrategy：遵循Spring推荐的命名约定。
# 除了连接表的名称为：{owning_physical_table_name}_{association_owning_property_name}，SpringImplicitNamingStrategy实现的命名约定与ImplicitNamingStrategyJpaCompliantImpl相同。
# determineJoinTableName：没有显式给定名称时，根据给定的ImplicitJoinTableNameSource，确定连接表的名称。
org.springframework.boot.orm.jpa.hibernate.SpringImplicitNamingStrategy

```

### SpringJtaPlatform

```

# Spring的Hibernate JtaPlatform：从Spring配置的JtaTransactionManager中解析JTA UserTransaction和TransactionManager。
# transactionManager：      JTA事务管理器（JtaTransactionManager）。
# locateTransactionManager：从Spring配置的JtaTransactionManager中获取事务管理器（TransactionManager）。
# locateUserTransaction：   从Spring配置的JtaTransactionManager中获取用户事务（UserTransaction）。
org.springframework.boot.orm.jpa.hibernate.SpringJtaPlatform

```

## JPA仓库

### JpaRepositoriesAutoConfiguration

```

# Spring Data的JpaRepository自动配置等同于使用@EnableJpaRepositories注解启用JpaRepository。
#
# @AutoConfiguration：自动配置类，在HibernateJpaAutoConfiguration、TaskExecutionAutoConfiguration配置之后配置Spring Data的JpaRepository。
# @Import：引入配置类：JpaRepositoriesImportSelector。
# @ConditionalOnClass：前提条件，类路径中存在类：JpaRepository。
# @ConditionalOnBean：前提条件，BeanFactory中存在Bean：DataSource。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：JpaRepositoryFactoryBean、JpaRepositoryConfigExtension。
# @ConditionalOnProperty：前提条件：spring.data.jpa.repositories.enabled=true或spring.data.jpa.repositories.enabled不存在。
#
# entityManagerFactoryBootstrapExecutorCustomizer：
# @Bean：创建Bean：EntityManagerFactoryBuilderCustomizer，依赖Bean：AsyncTaskExecutor。
# @Conditional：前提条件：满足BootstrapExecutorCondition，即spring.data.jpa.repositories.bootstrap-mode=deferred或lazy。
org.springframework.boot.autoconfigure.data.jpa.JpaRepositoriesAutoConfiguration

```

### JpaRepositoriesImportSelector

```

# JpaRepository的ImportBeanDefinitionRegistrar选择器。
# selectImports：类路径中存在org.springframework.data.envers.repository.config.EnableEnversRepositories类时，选择EnversRevisionRepositoriesRegistrar，否则选择JpaRepositoriesRegistrar。
org.springframework.boot.autoconfigure.data.jpa.JpaRepositoriesAutoConfiguration.JpaRepositoriesImportSelector

```

### BootstrapExecutorCondition

```

# JpaRepository自动配置的启动执行器条件。
org.springframework.boot.autoconfigure.condition.SpringBootCondition
    org.springframework.boot.autoconfigure.condition.AbstractNestedCondition
        org.springframework.boot.autoconfigure.condition.AnyNestedCondition
            org.springframework.boot.autoconfigure.data.jpa.JpaRepositoriesAutoConfiguration.BootstrapExecutorCondition

# JpaRepository自动配置的启动执行器条件。
# AnyNestedCondition：任何嵌套的条件类匹配时，则满足条件。
# 满足条件的情况：spring.data.jpa.repositories.bootstrap-mode=deferred或lazy。
# 测试条件的阶段：REGISTER_BEAN（注册Bean时）。
# 嵌套的条件类：DeferredBootstrapMode、LazyBootstrapMode。
org.springframework.boot.autoconfigure.data.jpa.JpaRepositoriesAutoConfiguration.BootstrapExecutorCondition

# @ConditionalOnProperty：前提条件：spring.data.jpa.repositories.bootstrap-mode=deferred
org.springframework.boot.autoconfigure.data.jpa.JpaRepositoriesAutoConfiguration.BootstrapExecutorCondition.DeferredBootstrapMode

# @ConditionalOnProperty：前提条件：spring.data.jpa.repositories.bootstrap-mode=lazy
org.springframework.boot.autoconfigure.data.jpa.JpaRepositoriesAutoConfiguration.BootstrapExecutorCondition.LazyBootstrapMode

```

### JpaRepositoriesRegistrar

```

# JPA仓库注册器。
org.springframework.boot.autoconfigure.data.AbstractRepositoryConfigurationSourceSupport
    org.springframework.boot.autoconfigure.data.jpa.JpaRepositoriesRegistrar
        org.springframework.boot.autoconfigure.data.jpa.EnversRevisionRepositoriesRegistrar

# JPA仓库注册器：自动配置Spring Data JPA的JpaRepository的ImportBeanDefinitionRegistrar。
# bootstrapMode：                      启动模式（BootstrapMode）。
# getAnnotation：                      获取EnableJpaRepositories注解。
# getConfiguration：                   获取EnableJpaRepositoriesConfiguration配置。
# getRepositoryConfigurationExtension：获取JpaRepositoryConfigExtension仓库配置扩展。
# getBootstrapMode：                   获取BootstrapMode，默认值：DEFAULT。
# setEnvironment：                     设置Environment，从spring.data.jpa.repositories.bootstrap-mode属性获取启动模式，配置启动模式。
org.springframework.boot.autoconfigure.data.jpa.JpaRepositoriesRegistrar

# JPA仓库注册器：自动配置Spring Data Envers的EnversRevisionRepository的ImportBeanDefinitionRegistrar。
# getConfiguration：                   获取EnableJpaRepositoriesConfiguration配置。
org.springframework.boot.autoconfigure.data.jpa.EnversRevisionRepositoriesRegistrar

```

### EnableJpaRepositoriesConfiguration

```

# @EnableJpaRepositories：启用JpaRepository。
org.springframework.boot.autoconfigure.data.jpa.JpaRepositoriesRegistrar.EnableJpaRepositoriesConfiguration

# @EnableJpaRepositories：启用EnversRevisionRepository。
# repositoryFactoryBeanClass：EnversRevisionRepositoryFactoryBean。
org.springframework.boot.autoconfigure.data.jpa.EnversRevisionRepositoriesRegistrar.EnableJpaRepositoriesConfiguration

```

## JPA测试

```

# @AutoConfiguration：自动配置类：在HibernateJpaAutoConfiguration配置之后配置TestEntityManager。
# @ConditionalOnClass：前提条件，类路径中存在类：EntityManagerFactory。
#
# testEntityManager：
# @Bean：创建Bean：TestEntityManager，依赖Bean：EntityManagerFactory。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：TestEntityManager。
org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManagerAutoConfiguration

org.springframework.boot.test.autoconfigure.orm.jpa.AutoConfigureDataJpa
org.springframework.boot.test.autoconfigure.orm.jpa.AutoConfigureTestEntityManager
org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTest
org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTestContextBootstrapper
org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTypeExcludeFilter
org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManager

```
