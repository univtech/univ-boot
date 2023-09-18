# jOOQ

## jOOQ启动器

### spring-boot-starter-jooq

```

# 启动器构件：使用jOOQ，通过JDBC来访问SQL数据库，用于替换：spring-boot-starter-jdbc或spring-boot-starter-data-jpa。
org.springframework.boot:spring-boot-starter-jooq:3.1.3

# 依赖：compile
org.springframework.boot:spring-boot-starter-jdbc:3.1.3
org.springframework:spring-tx:6.0.11
org.jooq:jooq:3.18.6

```

## jOOQ属性

### spring.jooq.*

```

# 配置属性类：JooqProperties

spring.jooq.sql-dialect SQL方言，默认自动检测

```

### JooqProperties

```

# @ConfigurationProperties：配置属性，jOOQ配置属性前缀：spring.jooq。
# sqlDialect：         SQL方言，默认自动检测
# determineSqlDialect：根据DataSource确定SQL方言（SQLDialect），调用SqlDialectLookup.getDialect方法。
# getXXX：             获取XXX
# setXXX：             设置XXX
org.springframework.boot.autoconfigure.jooq.JooqProperties

```

### SqlDialectLookup

```

# SQL方言查找器。
# getDialect：根据DataSource查找SQL方言（SQLDialect）。
org.springframework.boot.autoconfigure.jooq.SqlDialectLookup

```

## jOOQ配置

### JooqAutoConfiguration

```

# @AutoConfiguration：自动配置类，在DataSourceAutoConfiguration和TransactionAutoConfiguration配置之后配置jOOQ。
# @ConditionalOnClass：前提条件，类路径中存在类：DSLContext。
# @ConditionalOnBean：前提条件，BeanFactory中存在Bean：DataSource。
#
# dataSourceConnectionProvider：
# @Bean：创建Bean：DataSourceConnectionProvider，依赖Bean：DataSource。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：ConnectionProvider。
#
# transactionProvider：
# @Bean：创建Bean：SpringTransactionProvider，依赖Bean：PlatformTransactionManager。
# @ConditionalOnBean：前提条件，BeanFactory中存在Bean：PlatformTransactionManager。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：TransactionProvider。
#
# jooqExceptionTranslatorExecuteListenerProvider
# @Bean：创建Bean：DefaultExecuteListenerProvider。
# @Order：优先级顺序：0，优先级最高。
org.springframework.boot.autoconfigure.jooq.JooqAutoConfiguration

```

### DslContextConfiguration

```

# @Configuration：配置类，配置：DSLContext。
# @EnableConfigurationProperties：启用配置属性：JooqProperties。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：DSLContext。
#
# dslContext：
# @Bean：创建Bean：DefaultDSLContext，依赖Bean：Configuration。
#
# jooqConfiguration：
# @Bean：创建Bean：DefaultConfiguration，依赖Bean：JooqProperties、ConnectionProvider、DataSource、TransactionProvider、ExecuteListenerProvider、DefaultConfigurationCustomizer。
# @ConditionalOnMissingBean：前提条件，BeanFactory中不存在Bean：Configuration。
org.springframework.boot.autoconfigure.jooq.JooqAutoConfiguration.DslContextConfiguration

```

### DefaultConfigurationCustomizer

```

# DefaultConfiguration定制器。
# 既想自定义jOOQ配置，又想保留默认的自动配置的Bean实现的回调接口。
# customize：自定义jOOQ配置（DefaultConfiguration）。
org.springframework.boot.autoconfigure.jooq.DefaultConfigurationCustomizer

```

## jOOQ检测器

### JooqDependsOnDatabaseInitializationDetector

```

# 依赖于数据库初始化的Bean检测器。
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector
    org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDependsOnDatabaseInitializationDetector
        org.springframework.boot.jooq.JooqDependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器，检测指定类型的Bean：DSLContext。
org.springframework.boot.jooq.JooqDependsOnDatabaseInitializationDetector

```

## jOOQ事务

### SpringTransaction

```

# jOOQ事务的Spring事务适配器。
# transactionStatus：事务状态（TransactionStatus）。
# getXXX：           获取XXX
org.springframework.boot.autoconfigure.jooq.SpringTransaction

```

### SpringTransactionProvider

```

# jOOQ事务提供者的Spring事务提供者适配器。
# transactionManager：平台事务管理器（PlatformTransactionManager）。
# begin：   开启事务，事务传播行为：PROPAGATION_NESTED（如果存在当前事务，则在嵌套事务中执行，否则事务传播行为类似于PROPAGATION_REQUIRED）。
# commit：  提交事务，调用PlatformTransactionManager.commit方法。
# rollback：回滚事务，调用PlatformTransactionManager.rollback方法。
org.springframework.boot.autoconfigure.jooq.SpringTransactionProvider

```

## jOOQ异常

### NoDslContextBeanFailureAnalyzer

```

# 不存在DSLContext Bean的失败分析器。
org.springframework.boot.diagnostics.FailureAnalyzer
    org.springframework.boot.diagnostics.AbstractFailureAnalyzer
        org.springframework.boot.autoconfigure.jooq.NoDslContextBeanFailureAnalyzer

# 不存在DSLContext Bean的失败分析器（FailureAnalyzer）。
# 存在R2dbcAutoConfiguration时，R2DBC自动配置为支持JDBC。
# 因为jOOQ自动配置不支持R2DBC，因此无法自动配置jOOQ，所以DSLContext Bean不存在。
# 要同时使用jOOQ和JDBC，需要排除R2dbcAutoConfiguration。
# 要同时使用jOOQ和R2DBC，需要自定义jOOQ配置。
# analyze: 分析NoSuchBeanDefinitionException异常。
# getOrder：获取优先级顺序：0。
org.springframework.boot.autoconfigure.jooq.NoDslContextBeanFailureAnalyzer

```

### JooqExceptionTranslator

```

# jOOQ异常转换器。
# exception：把SQLException转换为Spring的DataAccessException。
org.springframework.boot.autoconfigure.jooq.JooqExceptionTranslator

```

## jOOQ测试

### JooqTest

```

# 只关注jOOQ组件的jOOQ测试注解。
# 这个组件会禁用完整的自动配置，只使用jOOQ测试相关的配置。
# 默认情况下，@JooqTest注解的测试会使用配置的数据库。
# 如果要使用嵌入式内存数据库替换显式的或自动配置的DataSource，可以使用@AutoConfigureTestDatabase覆盖这些配置。
# 使用JUnit 4时，@JooqTest注解应该与@RunWith(SpringRunner.class)一起使用。
#
# @Target：类（TYPE）。
# @Inherited：可继承。
# @BootstrapWith：TestContext启动器类：JooqTestContextBootstrapper。
# @ExtendWith：注册扩展：SpringExtension。
# @OverrideAutoConfiguration：覆盖自动配置：false。
# @TypeExcludeFilters：类型排除过滤器：JooqTypeExcludeFilter。
# @Transactional：开启事务。
# @AutoConfigureCache：自动配置缓存。
# @AutoConfigureJooq：自动配置jOOQ。
# @ImportAutoConfiguration：引入自动配置。
#
# properties：              key=value属性（String[]），在运行测试之前添加到Spring Environment。
# useDefaultFilters：       默认过滤器是否应该与@SpringBootApplication一起使用，默认情况下不包含任何Bean，默认值：true。
# includeFilters：          包含过滤器（Filter[]），把过滤后的Bean添加到应用程序上下文。
# excludeFilters：          排除过滤器（Filter[]），过滤掉要添加到应用程序上下文的Bean。
# excludeAutoConfiguration：排除自动配置类（Class<?>[]），排除应用于@JooqTest的自动配置类，@ImportAutoConfiguration.exclude的别名。
org.springframework.boot.test.autoconfigure.jooq.JooqTest

```

### AutoConfigureJooq

```

# 为jOOQ测试引入自动配置。
# 应该使用@JooqTest，而不是直接使用@AutoConfigureJooq。
# @Target：类（TYPE）。
# @Inherited：可继承。
# @ImportAutoConfiguration：引入自动配置。
org.springframework.boot.test.autoconfigure.jooq.AutoConfigureJooq

```

### JooqTestContextBootstrapper

```

# 支持@JooqTest的测试上下文启动器。
org.springframework.boot.test.context.SpringBootTestContextBootstrapper
    org.springframework.boot.test.autoconfigure.jooq.JooqTestContextBootstrapper

# 支持@JooqTest的测试上下文启动器（TestContextBootstrapper）。
# getProperties：获取@JooqTest.properties。
org.springframework.boot.test.autoconfigure.jooq.JooqTestContextBootstrapper

```

### JooqTypeExcludeFilter

```

# @JooqTest注解的类型排除过滤器。
org.springframework.boot.context.TypeExcludeFilter
    org.springframework.boot.test.autoconfigure.filter.AnnotationCustomizableTypeExcludeFilter
        org.springframework.boot.test.autoconfigure.filter.StandardAnnotationCustomizableTypeExcludeFilter
            org.springframework.boot.test.autoconfigure.jooq.JooqTypeExcludeFilter

# @JooqTest注解的类型排除过滤器（TypeExcludeFilter）。
org.springframework.boot.test.autoconfigure.jooq.JooqTypeExcludeFilter

```
