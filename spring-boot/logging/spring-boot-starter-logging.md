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

# 参考：LogbackLoggingSystemProperties
org.jboss.logging.provider                           jboss日志提供者，类路径中包含org.jboss.logging.Logger类时，设置系统属性：org.jboss.logging.provider=slf4j
logging.logback.rollingpolicy.file-name-pattern      滚动存储的日志文件名称格式，系统属性：LOGBACK_ROLLINGPOLICY_FILE_NAME_PATTERN，废弃属性：logging.pattern.rolling-file-name，默认值：${LOG_FILE}.%d{yyyy-MM-dd}.%i.gz
logging.logback.rollingpolicy.clean-history-on-start 启动时是否清理归档日志文件，系统属性：LOGBACK_ROLLINGPOLICY_CLEAN_HISTORY_ON_START，废弃属性：logging.file.clean-history-on-start，默认值：false
logging.logback.rollingpolicy.max-file-size          日志文件的最大大小，系统属性：LOGBACK_ROLLINGPOLICY_MAX_FILE_SIZE，废弃属性：logging.file.max-size，默认值：10MB
logging.logback.rollingpolicy.total-size-cap         日志备份保留的总大小，系统属性：LOGBACK_ROLLINGPOLICY_TOTAL_SIZE_CAP，废弃属性：logging.file.total-size-cap，默认值：0B
logging.logback.rollingpolicy.max-history            归档日志文件保留的最大数量，系统属性：LOGBACK_ROLLINGPOLICY_MAX_HISTORY，废弃属性：logging.file.max-history，默认值：7

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
# 类路径中存在ch.qos.logback.classic.LoggerContext类时，创建Logback日志系统
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

org.springframework.boot.logging.logback.ColorConverter
org.springframework.boot.logging.logback.DebugLogbackConfigurator
org.springframework.boot.logging.logback.DefaultLogbackConfiguration
org.springframework.boot.logging.logback.ExtendedWhitespaceThrowableProxyConverter
org.springframework.boot.logging.logback.LogbackConfigurator
org.springframework.boot.logging.logback.LogbackRuntimeHints
org.springframework.boot.logging.logback.RootLogLevelConfigurator
org.springframework.boot.logging.logback.SpringBootJoranConfigurator
org.springframework.boot.logging.logback.SpringProfileAction
org.springframework.boot.logging.logback.SpringProfileIfNestedWithinSecondPhaseElementSanityChecker
org.springframework.boot.logging.logback.SpringProfileModel
org.springframework.boot.logging.logback.SpringProfileModelHandler
org.springframework.boot.logging.logback.SpringPropertyAction
org.springframework.boot.logging.logback.SpringPropertyModel
org.springframework.boot.logging.logback.SpringPropertyModelHandler
org.springframework.boot.logging.logback.WhitespaceThrowableProxyConverter

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










