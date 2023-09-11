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
debug

Enable debug logs.

false

info.*

Arbitrary properties to add to the info endpoint.

logging.charset.console

Charset to use for console output.

logging.charset.file

Charset to use for file output.

logging.config

Location of the logging configuration file. For instance, `classpath:logback.xml` for Logback.

logging.exception-conversion-word

Conversion word used when logging exceptions.

%wEx

logging.file.name

Log file name (for instance, `myapp.log`). Names can be an exact location or relative to the current directory.

logging.file.path

Location of the log file. For instance, `/var/log`.

logging.group.*

Log groups to quickly change multiple loggers at the same time. For instance, `logging.group.db=org.hibernate,org.springframework.jdbc`.

logging.level.*

Log levels severity mapping. For instance, `logging.level.org.springframework=DEBUG`.

logging.log4j2.config.override

Overriding configuration files used to create a composite configuration.

logging.logback.rollingpolicy.clean-history-on-start

Whether to clean the archive log files on startup.

false

logging.logback.rollingpolicy.file-name-pattern

Pattern for rolled-over log file names.

${LOG_FILE}.%d{yyyy-MM-dd}.%i.gz

logging.logback.rollingpolicy.max-file-size

Maximum log file size.

10MB

logging.logback.rollingpolicy.max-history

Maximum number of archive log files to keep.

7

logging.logback.rollingpolicy.total-size-cap

Total size of log backups to be kept.

0B

logging.pattern.console

Appender pattern for output to the console. Supported only with the default Logback setup.

%clr(%d{${LOG_DATEFORMAT_PATTERN:-yyyy-MM-dd'T'HH:mm:ss.SSSXXX}}){faint} %clr(${LOG_LEVEL_PATTERN:-%5p}) %clr(${PID:- }){magenta} %clr(---){faint} %clr([%15.15t]){faint} %clr(%-40.40logger{39}){cyan} %clr(:){faint} %m%n${LOG_EXCEPTION_CONVERSION_WORD:-%wEx}

logging.pattern.dateformat

Appender pattern for log date format. Supported only with the default Logback setup.

yyyy-MM-dd'T'HH:mm:ss.SSSXXX

logging.pattern.file

Appender pattern for output to a file. Supported only with the default Logback setup.

%d{${LOG_DATEFORMAT_PATTERN:-yyyy-MM-dd'T'HH:mm:ss.SSSXXX}} ${LOG_LEVEL_PATTERN:-%5p} ${PID:- } --- [%t] %-40.40logger{39} : %m%n${LOG_EXCEPTION_CONVERSION_WORD:-%wEx}

logging.pattern.level

Appender pattern for log level. Supported only with the default Logback setup.

%5p

logging.register-shutdown-hook

Register a shutdown hook for the logging system when it is initialized. Disabled automatically when deployed as a war file.

true

logging.threshold.console

Log level threshold for console output.

TRACE

logging.threshold.file

Log level threshold for file output.

TRACE
```




















