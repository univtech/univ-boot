# sql

## 层次结构

```
# 数据库初始化器检测器
org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector
	+ org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDatabaseInitializerDetector

# 依赖于数据库初始化的Bean检测器
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector
    + org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDependsOnDatabaseInitializationDetector
    + org.springframework.boot.sql.init.dependency.AnnotationDependsOnDatabaseInitializationDetector
```






## 数据库初始化

```

# 数据库初始化器：通过schema脚本（DDL）或data脚本（DML）执行SQL数据库的初始化。
# OPTIONAL_LOCATION_PREFIX 可选位置前缀，默认值：optional:
# settings                 数据库初始化配置（DatabaseInitializationSettings）
# resourceLoader           资源加载器（ResourceLoader）
# setResourceLoader        设置资源加载器（ResourceLoaderAware）
# afterPropertiesSet       属性设置之后（InitializingBean），调用initializeDatabase
# initializeDatabase       初始化数据库
# runScripts               执行数据库初始化脚本
# isEmbeddedDatabase       是否嵌入式数据库
org.springframework.boot.sql.init.AbstractScriptDatabaseInitializer

# 数据库初始化脚本的位置解析器。
# resourcePatternResolver 资源模式解析器（ResourcePatternResolver）
org.springframework.boot.sql.init.AbstractScriptDatabaseInitializer.ScriptLocationResolver

# 数据库初始化脚本（Resource）。
# resources       数据库初始化脚本
# continueOnError 数据库初始化脚本发生错误时，是否继续，默认值：false
# separator       数据库初始化脚本的分隔符，默认值：";"
# encoding        读取数据库初始化脚本时使用的编码
org.springframework.boot.sql.init.AbstractScriptDatabaseInitializer.Scripts

# 数据库初始化配置。
# schemaLocations 数据库schema脚本（DDL）的位置，默认情况下，位置不存在时数据库初始化失败，在位置前面添加optional:前缀可以防止数据库初始化失败
# dataLocations   数据库data脚本（DML）的位置，默认情况下，位置不存在时数据库初始化失败，在位置前面添加optional:前缀可以防止数据库初始化失败
# continueOnError schema脚本（DDL）或data脚本（DML）发生错误时，是否继续，默认值：false
# separator       schema脚本（DDL）或data脚本（DML）的分隔符，默认值：";"
# encoding        读取schema脚本（DDL）或data脚本（DML）时使用的编码
# mode            数据库初始化模式，默认值：EMBEDDED
org.springframework.boot.sql.init.DatabaseInitializationSettings

# 数据库初始化模式。
# ALWAYS   总是初始化数据库
# EMBEDDED 只初始化嵌入式数据库
# NEVER    从不初始化数据库
org.springframework.boot.sql.init.DatabaseInitializationMode

```

## 数据库初始化依赖

```

# 数据库初始化依赖配置器（ImportBeanDefinitionRegistrar）。
# 把依赖于数据库初始化的Bean配置为依赖于执行数据库初始化的Bean。
# 在定义数据库初始化Bean或定义依赖于数据库初始化的Bean的配置类中引入这个配置器（@Import(DatabaseInitializationDependencyConfigurer.class)）。
# DatabaseInitializerDetector用于检测初始化数据库的Bean。
# DependsOnDatabaseInitializationDetector用于检测依赖于数据库初始化的Bean。
# 如果DependsOnDatabaseInitializationPostProcessor Bean未注册，则构造这个Bean，并注册到BeanDefinitionRegistry中。
org.springframework.boot.sql.init.dependency.DatabaseInitializationDependencyConfigurer

# 用于配置数据库初始化依赖关系的后置处理器（BeanFactoryPostProcessor）。
# 即调用BeanDefinition.setDependsOn方法，设置数据库初始化器和依赖于数据库初始化的Bean的依赖关系。
org.springframework.boot.sql.init.dependency.DatabaseInitializationDependencyConfigurer.DependsOnDatabaseInitializationPostProcessor

# 数据库初始化器的Bean名称。
# beanNames           所有数据库初始化器的Bean名称
# byDetectorBeanNames 数据库初始化器检测器与数据库初始化器的Bean名称之间的映射
org.springframework.boot.sql.init.dependency.DatabaseInitializationDependencyConfigurer.DependsOnDatabaseInitializationPostProcessor.InitializerBeanNames

----------------------------------------------------------------------------------------------------

# Bean检测器：检测指定类型的Bean。
# types  检测的Bean类型
# detect 检测ListableBeanFactory中types类型的Bean
org.springframework.boot.sql.init.dependency.BeansOfTypeDetector

----------------------------------------------------------------------------------------------------

# 数据库初始化器检测器。
# 实现类应该注册在META-INF/spring.factories的org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector下面。
# detect            检测ConfigurableListableBeanFactory中定义的初始化DataSource的Bean
# detectionComplete 所有数据库初始化器检测器都已调用，并且初始化DataSource的Bean都已检测完成的回调方法
# getOrder          获取顺序，默认值：0
org.springframework.boot.sql.init.dependency.DatabaseInitializerDetector

# 数据库初始化器检测器：检测指定类型的Bean。
# getDatabaseInitializerBeanTypes 获取数据库初始化器的Bean类型
org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDatabaseInitializerDetector

----------------------------------------------------------------------------------------------------

# 依赖于数据库初始化的Bean检测器。
# 实现类应该注册在META-INF/spring.factories的org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector下面。
# detect 检测ConfigurableListableBeanFactory中定义的依赖于数据库初始化的Bean
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器：检测指定类型的Bean。
# getDependsOnDatabaseInitializationBeanTypes 获取依赖于数据库初始化的Bean类型
org.springframework.boot.sql.init.dependency.AbstractBeansOfTypeDependsOnDatabaseInitializationDetector

# 依赖于数据库初始化的Bean检测器：检测@DependsOnDatabaseInitialization注解的Bean。
org.springframework.boot.sql.init.dependency.AnnotationDependsOnDatabaseInitializationDetector

# @DependsOnDatabaseInitialization注解：表示Bean的创建和初始化依赖于数据库初始化。
# 可用于Bean的class类或@Bean注解的方法。
org.springframework.boot.sql.init.dependency.DependsOnDatabaseInitialization

```












