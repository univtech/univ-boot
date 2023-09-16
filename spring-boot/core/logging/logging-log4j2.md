# log4j2

```
# 日志系统
org.springframework.boot.logging.LoggingSystem
    org.springframework.boot.logging.AbstractLoggingSystem
        org.springframework.boot.logging.log4j2.Log4J2LoggingSystem

# 日志系统工厂
# 类路径中存在org.apache.logging.log4j.core.impl.Log4jContextFactory类时，创建Log4J2日志系统
org.springframework.boot.logging.LoggingSystemFactory
    org.springframework.boot.logging.log4j2.Log4J2LoggingSystem.Factory

# Log4J2日志系统的日志记录器配置
org.springframework.boot.logging.log4j2.Log4J2LoggingSystem.LevelSetLoggerConfig
```

```
# 参考：Log4J2LoggingSystem
logging.log4j2.config.override                       创建组合配置时使用的覆盖配置文件

org.springframework.boot.logging.log4j2.ColorConverter
org.springframework.boot.logging.log4j2.ExtendedWhitespaceThrowablePatternConverter
org.springframework.boot.logging.log4j2.Log4J2LoggingSystem
org.springframework.boot.logging.log4j2.Log4J2LoggingSystem.Factory
org.springframework.boot.logging.log4j2.Log4J2LoggingSystem.LevelSetLoggerConfig
org.springframework.boot.logging.log4j2.SpringBootConfigurationFactory
org.springframework.boot.logging.log4j2.SpringBootPropertySource
org.springframework.boot.logging.log4j2.SpringEnvironmentLookup
org.springframework.boot.logging.log4j2.SpringEnvironmentPropertySource
org.springframework.boot.logging.log4j2.SpringProfileArbiter
org.springframework.boot.logging.log4j2.SpringProfileArbiter.Builder
org.springframework.boot.logging.log4j2.WhitespaceThrowablePatternConverter
```

