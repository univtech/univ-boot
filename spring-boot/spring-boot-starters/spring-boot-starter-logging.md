# spring-boot-starter-logging

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



```
debug                                                启用debug日志，默认：false
info.*                                               添加到info端点的任意属性

logging.charset.console                              控制台输出使用的字符集
logging.charset.file                                 文件输出使用的字符集
logging.config                                       日志配置文件的位置，例如：Logback的classpath:logback.xml
logging.exception-conversion-word                    记录异常时使用的转换词，默认：%wEx
logging.file.name                                    日志文件的名称，例如：myapp.log，名称可以是精确位置或当前目录的相对位置
logging.file.path                                    日志文件的位置，例如：/var/log
logging.group.*                                      可以同时快速修改多个日志记录器（Logger）的日志组，例如：logging.group.db=org.hibernate,org.springframework.jdbc
logging.level.*                                      日志级别的严重性映射，例如：logging.level.org.springframework=DEBUG
logging.log4j2.config.override                       创建组合配置时使用的覆盖配置文件

logging.logback.rollingpolicy.clean-history-on-start 启动时是否清理归档日志文件，默认：false
logging.logback.rollingpolicy.file-name-pattern      滚动存储的日志文件名称格式，默认：${LOG_FILE}.%d{yyyy-MM-dd}.%i.gz
logging.logback.rollingpolicy.max-file-size          日志文件的最大大小，默认：10MB
logging.logback.rollingpolicy.max-history            归档日志文件保留的最大数量，默认：7
logging.logback.rollingpolicy.total-size-cap         日志备份保留的总大小，默认：0B

logging.pattern.console                              输出到控制台时使用的输出器（Appender）格式，只支持默认的Logback设置，默认：%clr(%d{${LOG_DATEFORMAT_PATTERN:-yyyy-MM-dd'T'HH:mm:ss.SSSXXX}}){faint} %clr(${LOG_LEVEL_PATTERN:-%5p}) %clr(${PID:- }){magenta} %clr(---){faint} %clr([%15.15t]){faint} %clr(%-40.40logger{39}){cyan} %clr(:){faint} %m%n${LOG_EXCEPTION_CONVERSION_WORD:-%wEx}
logging.pattern.dateformat                           日志日期格式使用的输出器（Appender）格式，只支持默认的Logback设置，默认：yyyy-MM-dd'T'HH:mm:ss.SSSXXX
logging.pattern.file                                 输出到文件时使用的输出器（Appender）格式，只支持默认的Logback设置，默认：%d{${LOG_DATEFORMAT_PATTERN:-yyyy-MM-dd'T'HH:mm:ss.SSSXXX}} ${LOG_LEVEL_PATTERN:-%5p} ${PID:- } --- [%t] %-40.40logger{39} : %m%n${LOG_EXCEPTION_CONVERSION_WORD:-%wEx}
logging.pattern.level                                日志级别使用的输出器（Appender）格式，只支持默认的Logback设置，默认：%5p

logging.register-shutdown-hook                       日志系统初始化后，为日志系统注册一个关闭钩子，使用war文件部署时自动禁用，默认：true
logging.threshold.console                            控制台输出的日志级别阈值，默认：TRACE
logging.threshold.file                               文件输出的日志级别阈值，默认：TRACE
```


```

org.springframework.boot.logging.AbstractLoggingSystem.java
org.springframework.boot.logging.DeferredLog.java
org.springframework.boot.logging.DeferredLogFactory.java
org.springframework.boot.logging.DeferredLogs.java
org.springframework.boot.logging.DelegatingLoggingSystemFactory.java
org.springframework.boot.logging.java.JavaLoggingSystem.java
org.springframework.boot.logging.java.JavaLoggingSystemRuntimeHints.java

org.springframework.boot.logging.java.SimpleFormatter.java
org.springframework.boot.logging.log4j2.ColorConverter.java
org.springframework.boot.logging.log4j2.ExtendedWhitespaceThrowablePatternConverter.java
org.springframework.boot.logging.log4j2.Log4J2LoggingSystem.java

org.springframework.boot.logging.log4j2.SpringBootConfigurationFactory.java
org.springframework.boot.logging.log4j2.SpringBootPropertySource.java
org.springframework.boot.logging.log4j2.SpringEnvironmentLookup.java
org.springframework.boot.logging.log4j2.SpringEnvironmentPropertySource.java
org.springframework.boot.logging.log4j2.SpringProfileArbiter.java
org.springframework.boot.logging.log4j2.WhitespaceThrowablePatternConverter.java
org.springframework.boot.logging.logback.ColorConverter.java
org.springframework.boot.logging.logback.DebugLogbackConfigurator.java
org.springframework.boot.logging.logback.DefaultLogbackConfiguration.java
org.springframework.boot.logging.logback.ExtendedWhitespaceThrowableProxyConverter.java
org.springframework.boot.logging.logback.LogbackConfigurator.java
org.springframework.boot.logging.logback.LogbackLoggingSystem.java
org.springframework.boot.logging.logback.LogbackLoggingSystemProperties.java
org.springframework.boot.logging.logback.LogbackRuntimeHints.java

org.springframework.boot.logging.logback.RootLogLevelConfigurator.java
org.springframework.boot.logging.logback.SpringBootJoranConfigurator.java
org.springframework.boot.logging.logback.SpringProfileAction.java
org.springframework.boot.logging.logback.SpringProfileIfNestedWithinSecondPhaseElementSanityChecker.java
org.springframework.boot.logging.logback.SpringProfileModel.java
org.springframework.boot.logging.logback.SpringProfileModelHandler.java
org.springframework.boot.logging.logback.SpringPropertyAction.java
org.springframework.boot.logging.logback.SpringPropertyModel.java
org.springframework.boot.logging.logback.SpringPropertyModelHandler.java
org.springframework.boot.logging.logback.WhitespaceThrowableProxyConverter.java
org.springframework.boot.logging.LogFile.java
org.springframework.boot.logging.LoggerConfiguration.java
org.springframework.boot.logging.LoggerConfigurationComparator.java
org.springframework.boot.logging.LoggerGroup.java
org.springframework.boot.logging.LoggerGroups.java
org.springframework.boot.logging.LoggingInitializationContext.java
org.springframework.boot.logging.LoggingSystem.java
org.springframework.boot.logging.LoggingSystemFactory.java
org.springframework.boot.logging.LoggingSystemProperties.java
org.springframework.boot.logging.LogLevel.java

org.springframework.boot.autoconfigure.logging.ConditionEvaluationReportLogger.java
org.springframework.boot.autoconfigure.logging.ConditionEvaluationReportLoggingListener.java
org.springframework.boot.autoconfigure.logging.ConditionEvaluationReportLoggingProcessor.java
org.springframework.boot.autoconfigure.logging.ConditionEvaluationReportMessage.java

org.springframework.boot.actuate.logging.LogFileWebEndpoint.java
org.springframework.boot.actuate.logging.LoggersEndpoint.java

org.springframework.boot.actuate.autoconfigure.logging.LogFileWebEndpointAutoConfiguration.java
org.springframework.boot.actuate.autoconfigure.logging.LogFileWebEndpointProperties.java
org.springframework.boot.actuate.autoconfigure.logging.LoggersEndpointAutoConfiguration.java

```










