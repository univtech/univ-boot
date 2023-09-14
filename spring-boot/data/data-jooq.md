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
```



