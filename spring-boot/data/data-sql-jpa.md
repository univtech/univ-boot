# JPA

org.springframework.boot.autoconfigure.orm.jpa
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

## HibernateJpa

```

org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaAutoConfiguration

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

## HibernateMetrics

### HibernateMetricsAutoConfiguration

```

# @Configuration：配置类。
# @AutoConfigureAfter：自动配置类，在MetricsAutoConfiguration、HibernateJpaAutoConfiguration和SimpleMetricsExportAutoConfiguration配置之后配置Hibernate指标。
# @ConditionalOnClass：前提条件，类路径中存在类：EntityManagerFactory、SessionFactory、HibernateMetrics、MeterRegistry。
# @ConditionalOnBean：前提条件，BeanFactory中存在Bean：EntityManagerFactory、MeterRegistry。
#
# ENTITY_MANAGER_FACTORY_SUFFIX：       实体管理器工厂后缀："entityManagerFactory"。
# entityManagerFactories：              实体管理器工厂映射。
# meterRegistry：                       指标注册表。
# afterSingletonsInstantiated：         在单例实例化之后，把实体管理器工厂绑定到指标注册表中。
# bindEntityManagerFactoriesToRegistry：把实体管理器工厂绑定到指标注册表中。
# bindEntityManagerFactoryToRegistry：  把实体管理器工厂绑定到指标注册表中。
# getEntityManagerFactoryName：         根据Bean名称，获取实体管理器工厂的名称。
org.springframework.boot.actuate.autoconfigure.metrics.orm.jpa.HibernateMetricsAutoConfiguration

```

## JpaRepository

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

## JpaTest

### TestEntityManagerAutoConfiguration

```

# @AutoConfiguration：自动配置类：在HibernateJpaAutoConfiguration配置之后配置TestEntityManager。
# @ConditionalOnClass：前提条件，类路径中存在类：EntityManagerFactory。
#
# testEntityManager：
# @Bean：创建Bean：TestEntityManager，依赖Bean：EntityManagerFactory。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：TestEntityManager。
org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManagerAutoConfiguration

```

### DataJpaTest

```

# 只关注JPA组件的JPA测试注解。
# 这个组件会禁用完整的自动配置，只使用JPA测试相关的配置。
# 默认情况下，@DataJpaTest注解的测试是事务性的，测试结束时会进行回滚。
# 如果要使用嵌入式内存数据库替换显式的或自动配置的DataSource，可以使用@AutoConfigureTestDatabase覆盖这些配置。
# 如果既要加载完整的应用程序配置，又要使用嵌入式数据库，应该使用@SpringBootTest和@AutoConfigureTestDatabase，而不是使用@DataJpaTest。
# 使用JUnit 4时，@DataJpaTest注解应该与@RunWith(SpringRunner.class)一起使用。
#
# @Target：类（TYPE）。
# @Inherited：可继承。
# @BootstrapWith：TestContext启动器类：DataJpaTestContextBootstrapper。
# @ExtendWith：注册扩展：SpringExtension。
# @OverrideAutoConfiguration：覆盖自动配置：false。
# @TypeExcludeFilters：类型排除过滤器：DataJpaTypeExcludeFilter。
# @Transactional：开启事务。
# @AutoConfigureCache：自动配置缓存。
# @AutoConfigureDataJpa：自动配置Spring Data JPA。
# @AutoConfigureTestDatabase：自动配置测试数据库。
# @AutoConfigureTestEntityManager：自动配置TestEntityManager。
# @ImportAutoConfiguration：引入自动配置。
#
# properties：              key=value属性（String[]），在运行测试之前添加到Spring Environment。
# showSql：                 是否输出SQL，默认值：true，属性映射：spring.jpa.show-sql。
# bootstrapMode：           测试仓库支持的BootstrapMode，默认值：DEFAULT，属性映射：spring.data.jpa.repositories.bootstrap-mode。
# useDefaultFilters：       默认过滤器是否应该与@SpringBootApplication一起使用，默认情况下不包含任何Bean，默认值：true。
# includeFilters：          包含过滤器（Filter[]），把过滤后的Bean添加到应用程序上下文。
# excludeFilters：          排除过滤器（Filter[]），过滤掉要添加到应用程序上下文的Bean。
# excludeAutoConfiguration：排除自动配置类（Class<?>[]），排除应用于@DataJpaTest的自动配置类，@ImportAutoConfiguration.exclude的别名。
org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTest

```

### AutoConfigureDataJpa

```

# @AutoConfigureDataJpa：为Spring Data JPA测试引入自动配置。
# 应该使用@DataJpaTest，而不是直接使用@AutoConfigureDataJpa。
# @Target：类（TYPE）。
# @Inherited：可继承。
# @ImportAutoConfiguration：引入自动配置。
org.springframework.boot.test.autoconfigure.orm.jpa.AutoConfigureDataJpa

```

### AutoConfigureTestEntityManager

```

# @AutoConfigureTestEntityManager：为测试类自动配置TestEntityManager。
# @Target：类（TYPE）、方法（METHOD）。
# @Inherited：可继承。
# @ImportAutoConfiguration：引入自动配置。
org.springframework.boot.test.autoconfigure.orm.jpa.AutoConfigureTestEntityManager

```

### DataJpaTestContextBootstrapper

```

# 支持@DataJpaTest的测试上下文启动器。
org.springframework.boot.test.context.SpringBootTestContextBootstrapper
    org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTestContextBootstrapper

# 支持@DataJpaTest的测试上下文启动器（TestContextBootstrapper）。
# getProperties：获取@DataJpaTest.properties。
org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTestContextBootstrapper

```

### DataJpaTypeExcludeFilter

```

# @DataJpaTest注解的类型排除过滤器。
org.springframework.boot.context.TypeExcludeFilter
    org.springframework.boot.test.autoconfigure.filter.AnnotationCustomizableTypeExcludeFilter
        org.springframework.boot.test.autoconfigure.filter.StandardAnnotationCustomizableTypeExcludeFilter
            org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTypeExcludeFilter

# @DataJpaTest注解的类型排除过滤器（TypeExcludeFilter）。
org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTypeExcludeFilter

```

### TestEntityManager

```

# JPA测试中使用的EntityManager。
# 提供了EntityManager方法的子集，以及persist/flush/find等的辅助方法。
# entityManagerFactory：实体管理器工厂。
# persistAndGetId： 持久化实体并返回ID。
# persist：         持久化实体。
# persistFlushFind：持久化实体，把持久化上下文同步到数据库，并根据ID进行查找。
# persistAndFlush： 持久化实体，把持久化上下文同步到数据库。
# merge：           合并实体状态。
# remove：          删除实体。
# find：            查找实体。
# flush：           把持久化上下文同步到数据库。
# refresh：         刷新实体状态。
# clear：           清理持久化上下文，使所有实体游离。
# detach：          从持久化上下文删除实体，使实体游离。
# getId：           获取ID。
# getEntityManager：获取EntityManager。
org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManager

```
