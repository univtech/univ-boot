# sql

## 层次结构

```
# 数据库初始化器检测器
org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector
	+ org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDatabaseInitializerDetector

# 依赖于数据库初始化的Bean检测器
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector
    + org.springframework.boot.sql.init.dependency.AnnotationDependsOnDatabaseInitializationDetector
    + org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDependsOnDatabaseInitializationDetector
```

```
org.springframework.boot.sql.init.AbstractScriptDatabaseInitializer.ScriptLocationResolver
org.springframework.boot.sql.init.AbstractScriptDatabaseInitializer.Scripts
org.springframework.boot.sql.init.AbstractScriptDatabaseInitializer
org.springframework.boot.sql.init.DatabaseInitializationMode
org.springframework.boot.sql.init.DatabaseInitializationSettings

org.springframework.boot.sql.init.dependency.BeansOfTypeDetector
org.springframework.boot.sql.init.dependency.DatabaseInitializationDependencyConfigurer.DependsOnDatabaseInitializationPostProcessor.InitializerBeanNames
org.springframework.boot.sql.init.dependency.DatabaseInitializationDependencyConfigurer.DependsOnDatabaseInitializationPostProcessor
org.springframework.boot.sql.init.dependency.DatabaseInitializationDependencyConfigurer
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitialization
```



## 检测器

```
# 数据库初始化器检测器。
# 实现类应该注册在META-INF/spring.factories的org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector下面。
# detect            检测ConfigurableListableBeanFactory中定义的初始化DataSource的Bean
# detectionComplete 所有数据库初始化器检测器都已调用，并且初始化DataSource的Bean都已检测完成的回调方法
# getOrder          获取顺序，默认值：0
org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector

# 数据库初始化器检测器：检测指定类型的Bean。
# getDatabaseInitializerBeanTypes 获取数据库初始化器的Bean类型
org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDatabaseInitializerDetector

# 依赖于数据库初始化的Bean检测器。
# 实现类应该注册在META-INF/spring.factories的org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector下面。
# detect 检测ConfigurableListableBeanFactory中定义的依赖于数据库初始化的Bean
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器：检测@DependsOnDatabaseInitialization注解的Bean。
org.springframework.boot.sql.init.dependency.AnnotationDependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器：检测指定类型的Bean。
# getDependsOnDatabaseInitializationBeanTypes 获取依赖于数据库初始化的Bean类型
org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDependsOnDatabaseInitializationDetector
```












