# java

```

# 日志系统
org.springframework.boot.logging.LoggingSystem
    org.springframework.boot.logging.AbstractLoggingSystem
        org.springframework.boot.logging.java.JavaLoggingSystem

# 日志系统工厂
# 类路径中存在java.util.logging.LogManager类时，创建Java日志系统
org.springframework.boot.logging.LoggingSystemFactory
    org.springframework.boot.logging.java.JavaLoggingSystem.Factory

org.springframework.boot.logging.java.JavaLoggingSystem
org.springframework.boot.logging.java.JavaLoggingSystem.Factory
org.springframework.boot.logging.java.JavaLoggingSystemRuntimeHints
org.springframework.boot.logging.java.SimpleFormatter

```
