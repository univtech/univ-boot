# spring-boot-starter-webflux

```
# 构件
org.springframework.boot:spring-boot-starter-webflux:3.1.3

# 依赖：compile
org.springframework.boot:spring-boot-starter:3.1.3
org.springframework.boot:spring-boot-starter-json:3.1.3
org.springframework.boot:spring-boot-starter-reactor-netty:3.1.3
org.springframework:spring-web:6.0.11
org.springframework:spring-webflux:6.0.11
```

```
spring.webflux.base-path

Base path for all web handlers.

spring.webflux.format.date

Date format to use, for example 'dd/MM/yyyy'.

spring.webflux.format.date-time

Date-time format to use, for example 'yyyy-MM-dd HH:mm:ss'.

spring.webflux.format.time

Time format to use, for example 'HH:mm:ss'.

spring.webflux.hiddenmethod.filter.enabled

Whether to enable Spring's HiddenHttpMethodFilter.

false

spring.webflux.multipart.file-storage-directory

Directory used to store file parts larger than 'maxInMemorySize'. Default is a directory named 'spring-multipart' created under the system temporary directory. Ignored when streaming is enabled.

spring.webflux.multipart.headers-charset

Character set used to decode headers.

UTF-8

spring.webflux.multipart.max-disk-usage-per-part

Maximum amount of disk space allowed per part. Default is -1 which enforces no limits. Ignored when streaming is enabled.

-1B

spring.webflux.multipart.max-headers-size

Maximum amount of memory allowed per headers section of each part. Set to -1 to enforce no limits.

10KB

spring.webflux.multipart.max-in-memory-size

Maximum amount of memory allowed per part before it's written to disk. Set to -1 to store all contents in memory. Ignored when streaming is enabled.

256KB

spring.webflux.multipart.max-parts

Maximum number of parts allowed in a given multipart request. Default is -1 which enforces no limits.

-1

spring.webflux.problemdetails.enabled

Whether RFC 7807 Problem Details support should be enabled.

false

spring.webflux.static-path-pattern

Path pattern used for static resources.

/**

spring.webflux.webjars-path-pattern

Path pattern used for WebJar assets.

/webjars/**
```


