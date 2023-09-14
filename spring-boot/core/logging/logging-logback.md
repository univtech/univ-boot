# logback

## 层次结构

```
# Logback的日志系统
org.springframework.boot.logging.LoggingSystem
    + org.springframework.boot.logging.AbstractLoggingSystem
        + org.springframework.boot.logging.logback.LogbackLoggingSystem

# Logback的日志系统工厂
org.springframework.boot.logging.LoggingSystemFactory
    + org.springframework.boot.logging.logback.LogbackLoggingSystem.Factory

# Logback的日志系统属性
org.springframework.boot.logging.LoggingSystemProperties
    + org.springframework.boot.logging.logback.LogbackLoggingSystemProperties

# Logback的编程式配置器
org.springframework.boot.logging.logback.LogbackConfigurator
    + org.springframework.boot.logging.logback.DebugLogbackConfigurator
```

## 日志系统

```
# Logback的日志系统（LoggingSystem）。
# https://logback.qos.ch
# 1、日志级别映射：
# Spring Boot    Logback
# LogLevel.TRACE Level.TRACE
# LogLevel.TRACE Level.ALL
# LogLevel.DEBUG Level.DEBUG
# LogLevel.INFO  Level.INFO
# LogLevel.WARN  Level.WARN
# LogLevel.ERROR Level.ERROR
# LogLevel.FATAL Level.ERROR
# LogLevel.OFF   Level.OFF
# 2、标准配置位置：
# logback-test.groovy
# logback-test.xml
# logback.groovy
# logback.xml
# 3、Logback日志系统初始化之前：
# 如果类路径中存在org.slf4j.bridge.SLF4JBridgeHandler类，并且JUL只使用了一个ConsoleHandler时，移除ConsoleHandler，并配置JDK日志的SLF4J桥接处理器（SLF4JBridgeHandler）。
# 添加FilterReply.DENY决策的TurboFilter过滤器。
# 4、初始化Logback日志系统：
# 启用AOT（系统属性spring.aot.enabled=true）时，应用系统属性，使用AOT生成的构件进行配置，并报告存在的配置错误。
# 禁用AOT（系统属性spring.aot.enabled=false）或使用AOT生成的构件配置失败时，调用父类的初始化方法。
# 移除FilterReply.DENY决策的TurboFilter过滤器。
# 标记正在初始化Logback日志系统。
# 系统属性中存在logback.configurationFile时，打印警告日志，替代配置属性为logging.config。
# 5、加载Logback默认配置：
# 启用debug（系统属性logback.debug=true）时，添加控制台状态监听器（OnConsoleStatusListener），使用DebugLogbackConfigurator配置器。
# 禁用debug（系统属性logback.debug=false）时，使用LogbackConfigurator配置器。
# 应用配置属性：Logback日志系统属性（LogbackLoggingSystemProperties）、Logback默认配置（DefaultLogbackConfiguration）。
# 6、从标准配置位置加载Logback配置，目前只支持xml配置文件，并报告存在的配置错误。
# 7、配置SLF4J桥接处理器（SLF4JBridgeHandler）时，添加日志级别变更传播者（LevelChangePropagator）
org.springframework.boot.logging.logback.LogbackLoggingSystem

# Logback的日志系统工厂（LoggingSystemFactory）。
# 类路径中存在ch.qos.logback.classic.LoggerContext类时，创建Logback的日志系统（LogbackLoggingSystem）。
org.springframework.boot.logging.logback.LogbackLoggingSystem.Factory

# Logback的日志系统属性（LoggingSystemProperties）。
# 从属性解析器（PropertyResolver）获取属性值，并设置为系统属性。
# 类路径中存在org.jboss.logging.Logger类时，设置系统属性：org.jboss.logging.provider=slf4j。
# logging.logback.rollingpolicy.file-name-pattern      废弃属性：logging.pattern.rolling-file-name，  系统属性：LOGBACK_ROLLINGPOLICY_FILE_NAME_PATTERN，     日志归档的文件名称格式，默认值：${LOG_FILE}.%d{yyyy-MM-dd}.%i.gz}
# logging.logback.rollingpolicy.clean-history-on-start 废弃属性：logging.file.clean-history-on-start，系统属性：LOGBACK_ROLLINGPOLICY_CLEAN_HISTORY_ON_START，启动时是否清理日志归档，默认值：false
# logging.logback.rollingpolicy.max-file-size          废弃属性：logging.file.max-size，              系统属性：LOGBACK_ROLLINGPOLICY_MAX_FILE_SIZE，         归档前日志文件的最大大小，默认值：10MB
# logging.logback.rollingpolicy.total-size-cap         废弃属性：logging.file.total-size-cap，        系统属性：LOGBACK_ROLLINGPOLICY_TOTAL_SIZE_CAP，        删除前日志归档的最大容量，默认值：0
# logging.logback.rollingpolicy.max-history            废弃属性：logging.file.max-history，           系统属性：LOGBACK_ROLLINGPOLICY_MAX_HISTORY，           删除前日志归档的最大数量，默认值：7
org.springframework.boot.logging.logback.LogbackLoggingSystemProperties
```

## 默认配置

```
# META-INF/services/ch.qos.logback.classic.spi.Configurator中注册的配置器（Configurator）。
# 把ROOT日志记录器的日志级别设置为INFO。
org.springframework.boot.logging.logback.RootLogLevelConfigurator

# Spring Boot的Joran配置器（JoranConfigurator），用于添加额外的Spring Boot规则。
# 1、对模型执行SpringProfileIfNestedWithinSecondPhaseElementSanityChecker检查。
# 2、添加模型处理器：
# SpringPropertyModel SpringPropertyModelHandler
# SpringProfileModel  SpringProfileModelHandler
# 3、添加元素选择器及其操作：
# configuration/springProperty SpringPropertyAction
# */springProfile              SpringProfileAction
# 4、添加透明路径部分：springProfile。
# 5、使用AOT生成的构件进行配置：
# 读取格式规则和模型。
# 处理模型，模型处理后，如果处于非Native镜像中，并且AOT处理正在进行（系统属性spring.aot.processing=true）时，存储LogbackConfigurationAotContribution对象。
# 注册安全配置。
org.springframework.boot.logging.logback.SpringBootJoranConfigurator

# Logback配置的AOT Contribution（BeanFactoryInitializationAotContribution）。
# 把模型写入META-INF/spring/logback-model文件。
# 把格式规则注册表中的属性写入META-INF/spring/logback-pattern-rules文件中。
org.springframework.boot.logging.logback.SpringBootJoranConfigurator.LogbackConfigurationAotContribution

# 模型读取器。
# 从META-INF/spring/logback-model文件读取模型。
org.springframework.boot.logging.logback.SpringBootJoranConfigurator.ModelReader

# 模型写入器。
# 把模型写入META-INF/spring/logback-model文件。
org.springframework.boot.logging.logback.SpringBootJoranConfigurator.ModelWriter

# 格式规则读写器。
# 从META-INF/spring/logback-pattern-rules文件读取属性，放入格式规则注册表中。
# 把格式规则注册表中的属性写入META-INF/spring/logback-pattern-rules文件中。
org.springframework.boot.logging.logback.SpringBootJoranConfigurator.PatternRules

# Logback的编程式配置器，比解析XML快。
org.springframework.boot.logging.logback.LogbackConfigurator

# 启用debug时，用于添加额外状态的Logback配置器（LogbackConfigurator）。
org.springframework.boot.logging.logback.DebugLogbackConfigurator

# Spring Boot中使用的Logback的默认配置。
# 使用Logback的编程式配置器（LogbackConfigurator）进行配置，以减少启动时间。
# 参考logback.xml使用的base.xml、defaults.xml、console-appender.xml和file-appender.xml文件：
# org/springframework/boot/logging/logback/base.xml
# org/springframework/boot/logging/logback/defaults.xml
# org/springframework/boot/logging/logback/console-appender.xml
# org/springframework/boot/logging/logback/file-appender.xml
org.springframework.boot.logging.logback.DefaultLogbackConfiguration
```

## 转换器

```
# Logback的RuntimeHints注册器（RuntimeHintsRegistrar），类路径中存在ch.qos.logback.classic.LoggerContext类时，注册：
# LoggerContext                             注册类
# SLF4JBridgeHandler                        类路径中存在org.slf4j.bridge.SLF4JBridgeHandler类时，注册构造器
# DateTokenConverter                        注册可调用的public构造函数
# IntegerTokenConverter                     注册可调用的public构造函数
# SyslogStartConverter                      注册可调用的public构造函数
# ColorConverter                            注册可调用的public构造函数
# WhitespaceThrowableProxyConverter         注册可调用的public构造函数
# ExtendedWhitespaceThrowableProxyConverter 注册可调用的public构造函数
org.springframework.boot.logging.logback.LogbackRuntimeHints

# 使用AnsiOutput类给输出内容添加颜色的组合转换器（CompositeConverter）。
# 先根据颜色（第一个选项）选择AnsiElement（AnsiColor或AnsiStyle）：
# black          AnsiColor.BLACK
# white          AnsiColor.WHITE
# faint          AnsiStyle.FAINT
# red            AnsiColor.RED
# green          AnsiColor.GREEN
# yellow         AnsiColor.YELLOW
# blue           AnsiColor.BLUE
# magenta        AnsiColor.MAGENTA
# cyan           AnsiColor.CYAN
# bright_black   AnsiColor.BRIGHT_BLACK
# bright_white   AnsiColor.BRIGHT_WHITE
# bright_red     AnsiColor.BRIGHT_RED
# bright_green   AnsiColor.BRIGHT_GREEN
# bright_yellow  AnsiColor.BRIGHT_YELLOW
# bright_blue    AnsiColor.BRIGHT_BLUE
# bright_magenta AnsiColor.BRIGHT_MAGENTA
# bright_cyan    AnsiColor.BRIGHT_CYAN
# 如果颜色不存在，则根据日志级别选择AnsiElement（AnsiColor）：
# 40000（ERROR）  AnsiColor.RED
# 30000（WARN）   AnsiColor.YELLOW
# 如果日志级别不存在，则默认为绿色（AnsiColor.GREEN）
org.springframework.boot.logging.logback.ColorConverter

# 在堆栈跟踪前后添加行分隔符的Throwable代理转换器（ThrowableProxyConverter）。
org.springframework.boot.logging.logback.WhitespaceThrowableProxyConverter

# 在堆栈跟踪前后添加行分隔符的扩展Throwable代理转换器（ExtendedThrowableProxyConverter）。
org.springframework.boot.logging.logback.ExtendedWhitespaceThrowableProxyConverter
```

## springProperty标签

```
# <springProperty>标签的模型（NamedModel），包括以下属性：
# name
# source
# scope
# defaultValue
# 可以从Spring的Environment中获取Logback属性。
org.springframework.boot.logging.logback.SpringPropertyModel

# <springProperty>标签的基本模型操作（BaseModelAction）。
# 获取<springProperty>标签的属性值，创建SpringPropertyModel，并设置属性值。
# 可以从Spring的Environment中获取Logback属性。
org.springframework.boot.logging.logback.SpringPropertyAction

# <springProperty>标签的基本模型处理器（ModelHandlerBase）。
# 可以从Spring的Environment中获取Logback属性。
org.springframework.boot.logging.logback.SpringPropertyModelHandler
```

## springProfile标签

```
# <springProfile>标签的模型（NamedModel），包括以下属性：
# name
# 启用特定profile时，可以只启用部分Logback配置。
org.springframework.boot.logging.logback.SpringProfileModel

# <springProfile>标签的基本模型操作（BaseModelAction）。
# 获取<springProfile>标签的属性值，创建SpringProfileModel，并设置属性值。
# 启用特定profile时，可以只启用部分Logback配置。
org.springframework.boot.logging.logback.SpringProfileAction

# <springProfile>标签的基本模型处理器（ModelHandlerBase）。
# 启用特定profile时，可以只启用部分Logback配置。
org.springframework.boot.logging.logback.SpringProfileModelHandler

# 第二相位元素（<appender>、<logger>和<root>）中是否嵌套<springProfile>元素的智能检查器（SanityChecker）。
# <root>     RootLoggerModel
# <logger>   LoggerModel
# <appender> AppenderModel
org.springframework.boot.logging.logback.SpringProfileIfNestedWithinSecondPhaseElementSanityChecker
```
