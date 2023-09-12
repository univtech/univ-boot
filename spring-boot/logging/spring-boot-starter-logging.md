# spring-boot-starter-logging

## 构建信息

```
# 地址
https://spring.io
https://spring.io/projects/spring-boot

https://github.com/spring-projects/spring-boot
https://github.com/spring-projects/spring-boot/issues

git://github.com/spring-projects/spring-boot.git
ssh://git@github.com/spring-projects/spring-boot.git

# 构件
org.springframework.boot:spring-boot-starter-logging:3.1.3

# 依赖：compile
ch.qos.logback:logback-classic:1.4.11
org.apache.logging.log4j:log4j-to-slf4j:2.20.0
org.slf4j:jul-to-slf4j:2.0.7
```

## 配置属性

```
debug                                                启用debug日志，默认值：false
info.*                                               添加到info端点的任意属性

# 参考：LoggingApplicationListener
logging.config                                       日志配置文件的位置，例如：Logback的classpath:logback.xml
logging.group.*                                      可以同时快速修改多个日志记录器（Logger）的日志组，例如：logging.group.db=org.hibernate,org.springframework.jdbc
logging.level.*                                      日志级别的严重性映射，例如：logging.level.org.springframework=DEBUG
logging.register-shutdown-hook                       日志系统初始化后，为日志系统注册一个关闭钩子，使用war文件部署时自动禁用，默认值：true

# 参考：LoggingSystemProperties
PID                                                  应用程序的进程ID，系统属性：PID=xxx
logging.exception-conversion-word                    记录异常时使用的转换词，系统属性：LOG_EXCEPTION_CONVERSION_WORD，默认值：%wEx
logging.pattern.dateformat                           日志日期格式的输出器（Appender）格式，只支持默认的Logback设置，系统属性：LOG_DATEFORMAT_PATTERN，默认值：yyyy-MM-dd'T'HH:mm:ss.SSSXXX
logging.pattern.level                                日志级别的输出器（Appender）格式，只支持默认的Logback设置，系统属性：LOG_LEVEL_PATTERN，默认值：%5p

logging.charset.console                              控制台日志的字符集，系统属性：CONSOLE_LOG_CHARSET，默认值：UTF-8
logging.threshold.console                            控制台日志的日志级别阈值，系统属性：CONSOLE_LOG_THRESHOLD，默认值：TRACE
logging.pattern.console                              控制台日志的输出器（Appender）格式，只支持默认的Logback设置，系统属性：CONSOLE_LOG_PATTERN，默认值：%clr(%d{${LOG_DATEFORMAT_PATTERN:-yyyy-MM-dd'T'HH:mm:ss.SSSXXX}}){faint} %clr(${LOG_LEVEL_PATTERN:-%5p}) %clr(${PID:- }){magenta} %clr(---){faint} %clr([%15.15t]){faint} %clr(%-40.40logger{39}){cyan} %clr(:){faint} %m%n${LOG_EXCEPTION_CONVERSION_WORD:-%wEx}

logging.charset.file                                 日志文件的字符集，系统属性：FILE_LOG_CHARSET，默认值：UTF-8
logging.threshold.file                               日志文件的日志级别阈值，系统属性：FILE_LOG_THRESHOLD，默认值：TRACE
logging.pattern.file                                 日志文件的输出器（Appender）格式，只支持默认的Logback设置，系统属性：FILE_LOG_PATTERN，默认值：%d{${LOG_DATEFORMAT_PATTERN:-yyyy-MM-dd'T'HH:mm:ss.SSSXXX}} ${LOG_LEVEL_PATTERN:-%5p} ${PID:- } --- [%t] %-40.40logger{39} : %m%n${LOG_EXCEPTION_CONVERSION_WORD:-%wEx}

# 参考：LogFile
logging.file.name                                    日志文件的名称，系统属性：LOG_FILE，例如：myapp.log，名称可以是精确位置或当前目录的相对位置
logging.file.path                                    日志文件的位置，系统属性：LOG_PATH，例如：/var/log

# 参考：Log4J2LoggingSystem
logging.log4j2.config.override                       创建组合配置时使用的覆盖配置文件
```

## java文件

```
# 日志应用程序监听器
org.springframework.boot.context.logging.LoggingApplicationListener

# 日志系统属性
org.springframework.boot.logging.LoggingSystemProperties
    + org.springframework.boot.logging.logback.LogbackLoggingSystemProperties

# 日志文件属性
org.springframework.boot.logging.LogFile

# 日志级别映射
org.springframework.boot.logging.AbstractLoggingSystem.LogLevels

# 日志级别枚举
org.springframework.boot.logging.LogLevel
    + TRACE
    + DEBUG
    + INFO
    + WARN
    + ERROR
    + FATAL
    + OFF

# 日志系统工厂
# 类路径中存在java.util.logging.LogManager类时，创建Java日志系统
# 类路径中存在org.apache.logging.log4j.core.impl.Log4jContextFactory类时，创建Log4J2日志系统
org.springframework.boot.logging.LoggingSystemFactory
    + org.springframework.boot.logging.DelegatingLoggingSystemFactory
    + org.springframework.boot.logging.java.JavaLoggingSystem.Factory
    + org.springframework.boot.logging.logback.LogbackLoggingSystem.Factory
    + org.springframework.boot.logging.log4j2.Log4J2LoggingSystem.Factory

# 日志记录器分组
org.springframework.boot.logging.LoggerGroup
org.springframework.boot.logging.LoggerGroups

# 延迟日志记录器
org.springframework.boot.logging.DeferredLog
org.springframework.boot.logging.DeferredLog.Line
org.springframework.boot.logging.DeferredLog.Lines

# 延迟日志记录器工厂
org.springframework.boot.logging.DeferredLogFactory
    + org.springframework.boot.logging.DeferredLogs

# 日志记录器配置
org.springframework.boot.logging.LoggerConfiguration
org.springframework.boot.logging.LoggerConfiguration.LevelConfiguration
org.springframework.boot.logging.LoggerConfiguration.ConfigurationScope
    + DIRECT
    + INHERITED






# 日志系统
org.springframework.boot.logging.LoggingSystem
    + org.springframework.boot.logging.LoggingSystem.NoOpLoggingSystem
    + org.springframework.boot.logging.AbstractLoggingSystem
        + org.springframework.boot.logging.java.JavaLoggingSystem
        + org.springframework.boot.logging.logback.LogbackLoggingSystem
        + org.springframework.boot.logging.log4j2.Log4J2LoggingSystem

# Log4J2日志系统的日志记录器配置
org.springframework.boot.logging.log4j2.Log4J2LoggingSystem.LevelSetLoggerConfig

# 日志初始化上下文
org.springframework.boot.logging.LoggingInitializationContext

# 日志记录器配置的比较器
org.springframework.boot.logging.LoggerConfigurationComparator
```

```

org.springframework.boot.logging.java.JavaLoggingSystemRuntimeHints
org.springframework.boot.logging.java.SimpleFormatter

org.springframework.boot.logging.log4j2.ColorConverter
org.springframework.boot.logging.log4j2.ExtendedWhitespaceThrowablePatternConverter
org.springframework.boot.logging.log4j2.SpringBootConfigurationFactory
org.springframework.boot.logging.log4j2.SpringBootPropertySource
org.springframework.boot.logging.log4j2.SpringEnvironmentLookup
org.springframework.boot.logging.log4j2.SpringEnvironmentPropertySource
org.springframework.boot.logging.log4j2.SpringProfileArbiter
org.springframework.boot.logging.log4j2.WhitespaceThrowablePatternConverter

org.springframework.boot.autoconfigure.logging.ConditionEvaluationReportLogger
org.springframework.boot.autoconfigure.logging.ConditionEvaluationReportLoggingListener
org.springframework.boot.autoconfigure.logging.ConditionEvaluationReportLoggingProcessor
org.springframework.boot.autoconfigure.logging.ConditionEvaluationReportMessage

org.springframework.boot.actuate.logging.LogFileWebEndpoint
org.springframework.boot.actuate.logging.LoggersEndpoint

org.springframework.boot.actuate.autoconfigure.logging.LogFileWebEndpointAutoConfiguration
org.springframework.boot.actuate.autoconfigure.logging.LogFileWebEndpointProperties
org.springframework.boot.actuate.autoconfigure.logging.LoggersEndpointAutoConfiguration
```




## logback

```
# Logback的日志系统属性（LoggingSystemProperties）。
# 从属性解析器（PropertyResolver）获取属性值，并设置为系统属性。
# 类路径中存在org.jboss.logging.Logger类时，设置系统属性：org.jboss.logging.provider=slf4j。
# logging.logback.rollingpolicy.file-name-pattern      废弃属性：logging.pattern.rolling-file-name，  系统属性：LOGBACK_ROLLINGPOLICY_FILE_NAME_PATTERN，     日志归档的文件名称格式，默认值：${LOG_FILE}.%d{yyyy-MM-dd}.%i.gz
# logging.logback.rollingpolicy.clean-history-on-start 废弃属性：logging.file.clean-history-on-start，系统属性：LOGBACK_ROLLINGPOLICY_CLEAN_HISTORY_ON_START，启动时是否清理日志归档，默认值：false
# logging.logback.rollingpolicy.max-file-size          废弃属性：logging.file.max-size，              系统属性：LOGBACK_ROLLINGPOLICY_MAX_FILE_SIZE，         归档前日志文件的最大大小，默认值：10MB
# logging.logback.rollingpolicy.total-size-cap         废弃属性：logging.file.total-size-cap，        系统属性：LOGBACK_ROLLINGPOLICY_TOTAL_SIZE_CAP，        删除前日志归档的最大容量，默认值：0B
# logging.logback.rollingpolicy.max-history            废弃属性：logging.file.max-history，           系统属性：LOGBACK_ROLLINGPOLICY_MAX_HISTORY，           删除前日志归档的最大数量，默认值：7
org.springframework.boot.logging.logback.LogbackLoggingSystemProperties

# Logback的日志系统工厂（LoggingSystemFactory）。
# 类路径中存在ch.qos.logback.classic.LoggerContext类时，创建Logback的日志系统（LogbackLoggingSystem）。
org.springframework.boot.logging.logback.LogbackLoggingSystem.Factory

# META-INF/services/ch.qos.logback.classic.spi.Configurator中注册的配置器（Configurator）。
# 把ROOT日志记录器的日志级别设置为INFO。
org.springframework.boot.logging.logback.RootLogLevelConfigurator

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








# Logback的日志系统（LoggingSystem）
org.springframework.boot.logging.logback.LogbackLoggingSystem




----------------------------------------------------------------------------------------------------










org.springframework.boot.logging.logback.SpringBootJoranConfigurator
org.springframework.boot.logging.logback.LogbackConfigurator
org.springframework.boot.logging.logback.DebugLogbackConfigurator
org.springframework.boot.logging.logback.DefaultLogbackConfiguration












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

# 确保第二相位元素（<appender>、<logger>和<root>）中没有嵌套<springProfile>元素的智能检查器（SanityChecker）。
# <root>     RootLoggerModel
# <logger>   LoggerModel
# <appender> AppenderModel
org.springframework.boot.logging.logback.SpringProfileIfNestedWithinSecondPhaseElementSanityChecker
```
