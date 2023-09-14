# jOOQ数据库

## 层次结构

```
# 依赖于数据库初始化的Bean检测器
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector
    + org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDependsOnDatabaseInitializationDetector
        + org.springframework.boot.jooq.JooqDependsOnDatabaseInitializationDetector

# 失败分析器
org.springframework.boot.diagnostics.FailureAnalyzer
    + org.springframework.boot.diagnostics.AbstractFailureAnalyzer
        + org.springframework.boot.autoconfigure.jooq.NoDslContextBeanFailureAnalyzer

```

## 自动配置

```

# @AutoConfiguration：jOOQ数据库自动配置，      (after = { DataSourceAutoConfiguration.class, TransactionAutoConfiguration.class })
# @ConditionalOnClass：类路径中必须存在DSLContext类。
# @ConditionalOnBean：BeanFactory中必须存在DataSource Bean。
# @Bean dataSourceConnectionProvider：BeanFactory中不存在ConnectionProvider Bean时，创建DataSourceConnectionProvider Bean，依赖于DataSource Bean。
# @Bean transactionProvider：BeanFactory中存在PlatformTransactionManager Bean，且不存在TransactionProvider Bean时，创建SpringTransactionProvider Bean。
# @Bean jooqExceptionTranslatorExecuteListenerProvider：创建DefaultExecuteListenerProvider Bean，顺序为0，优先级最高。
org.springframework.boot.autoconfigure.jooq.JooqAutoConfiguration

# @Configuration：DSLContext配置类。
# @EnableConfigurationProperties：启用JooqProperties配置属性。
# @ConditionalOnMissingBean：BeanFactory中不存在DSLContext Bean。
# @Bean dslContext 创建DefaultDSLContext Bean，依赖Configuration Bean。
# @Bean jooqConfiguration BeanFactory中不存在Configuration Bean时，创建DefaultConfiguration Bean，依赖Bean：JooqProperties、ConnectionProvider、DataSource、TransactionProvider、ExecuteListenerProvider、DefaultConfigurationCustomizer。
org.springframework.boot.autoconfigure.jooq.JooqAutoConfiguration.DslContextConfiguration

# @ConfigurationProperties：前缀为spring.jooq的jOOQ数据库配置属性。
# sqlDialect          SQL方言，默认自动检测
# determineSqlDialect 根据DataSource查找SQL方言，调用SqlDialectLookup.getDialect方法
# getXXX              获取XXX
# setXXX              设置XXX
org.springframework.boot.autoconfigure.jooq.JooqProperties

# SQL方言查找器。
# getDialect 根据DataSource查找SQL方言
org.springframework.boot.autoconfigure.jooq.SqlDialectLookup

# 需要自定义jOOQ配置，又想保留默认的自动配置的Bean实现的回调接口。
# customize 自定义jOOQ配置（DefaultConfiguration）
org.springframework.boot.autoconfigure.jooq.DefaultConfigurationCustomizer

# jOOQ事务的Spring事务适配器。
# transactionStatus 事务状态（TransactionStatus）
# getXXX            获取XXX
org.springframework.boot.autoconfigure.jooq.SpringTransaction

# jOOQ事务提供者的Spring事务提供者适配器
# transactionManager 平台事务管理器（PlatformTransactionManager）
# begin    开启事务，事务传播行为为PROPAGATION_NESTED（如果存在当前事务，则在嵌套事务中执行，否则事务传播行为类似于PROPAGATION_REQUIRED）
# commit   提交事务，调用PlatformTransactionManager.commit方法
# rollback 回滚事务，调用PlatformTransactionManager.rollback方法
org.springframework.boot.autoconfigure.jooq.SpringTransactionProvider

# 不存在DSLContext Bean的失败分析器（FailureAnalyzer）。
# 存在R2dbcAutoConfiguration时，R2DBC自动配置为支持JDBC。
# 因为jOOQ自动配置不支持R2DBC，因此无法自动配置jOOQ，所以DSLContext Bean不存在。
# 要同时使用jOOQ和JDBC，需要排除R2dbcAutoConfiguration。
# 要同时使用jOOQ和R2DBC，需要自定义jOOQ配置。
# analyze  分析NoSuchBeanDefinitionException异常
# getOrder 获取顺序
org.springframework.boot.autoconfigure.jooq.NoDslContextBeanFailureAnalyzer

# jOOQ异常转换器：把SQLException转换为Spring的DataAccessException。
org.springframework.boot.autoconfigure.jooq.JooqExceptionTranslator

```

## 数据库初始化依赖

```

# 依赖于数据库初始化的Bean检测器：检测DSLContext类型的Bean。
org.springframework.boot.jooq.JooqDependsOnDatabaseInitializationDetector

```

## 测试

```

org.springframework.boot.test.autoconfigure.jooq.AutoConfigureJooq
org.springframework.boot.test.autoconfigure.jooq.JooqTest
org.springframework.boot.test.autoconfigure.jooq.JooqTestContextBootstrapper
org.springframework.boot.test.autoconfigure.jooq.JooqTypeExcludeFilter

```
