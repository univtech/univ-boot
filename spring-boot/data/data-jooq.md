# jooq

## 层次结构

```
# 依赖于数据库初始化的Bean检测器
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector
    + org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDependsOnDatabaseInitializationDetector
        + org.springframework.boot.jooq.JooqDependsOnDatabaseInitializationDetector
```

## Bean检测器

```
# 依赖于数据库初始化的Bean检测器：检测DSLContext类型的Bean。
org.springframework.boot.jooq.JooqDependsOnDatabaseInitializationDetector
























org.springframework.boot.autoconfigure.jooq.DefaultConfigurationCustomizer
org.springframework.boot.autoconfigure.jooq.JooqAutoConfiguration.DslContextConfiguration
org.springframework.boot.autoconfigure.jooq.JooqAutoConfiguration
org.springframework.boot.autoconfigure.jooq.JooqExceptionTranslator
org.springframework.boot.autoconfigure.jooq.JooqProperties
org.springframework.boot.autoconfigure.jooq.NoDslContextBeanFailureAnalyzer
org.springframework.boot.autoconfigure.jooq.SpringTransaction
org.springframework.boot.autoconfigure.jooq.SpringTransactionProvider
org.springframework.boot.autoconfigure.jooq.SqlDialectLookup

org.springframework.boot.test.autoconfigure.jooq.AutoConfigureJooq
org.springframework.boot.test.autoconfigure.jooq.JooqTest
org.springframework.boot.test.autoconfigure.jooq.JooqTestContextBootstrapper
org.springframework.boot.test.autoconfigure.jooq.JooqTypeExcludeFilter
```



