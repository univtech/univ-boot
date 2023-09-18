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


org.springframework.boot.orm.jpa.EntityManagerFactoryBuilder
org.springframework.boot.orm.jpa.EntityManagerFactoryBuilder.Builder

org.springframework.boot.orm.jpa.hibernate.SpringImplicitNamingStrategy
org.springframework.boot.orm.jpa.hibernate.SpringJtaPlatform

org.springframework.boot.autoconfigure.orm.jpa.EntityManagerFactoryBuilderCustomizer
org.springframework.boot.autoconfigure.orm.jpa.EntityManagerFactoryDependsOnPostProcessor
org.springframework.boot.autoconfigure.orm.jpa.HibernateDefaultDdlAutoProvider
org.springframework.boot.autoconfigure.orm.jpa.HibernateSettings


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
