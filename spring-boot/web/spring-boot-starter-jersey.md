# spring-boot-starter-jersey

```
# 地址
https://spring.io
https://spring.io/projects/spring-boot

https://github.com/spring-projects/spring-boot
https://github.com/spring-projects/spring-boot/issues

git://github.com/spring-projects/spring-boot.git
ssh://git@github.com/spring-projects/spring-boot.git

# 构件
org.springframework.boot:spring-boot-starter-jersey:3.1.3

# 依赖：compile
org.springframework.boot:spring-boot-starter-json:3.1.3
org.springframework.boot:spring-boot-starter-tomcat:3.1.3
org.springframework.boot:spring-boot-starter-validation:3.1.3
org.springframework:spring-web:6.0.11
org.glassfish.jersey.containers:jersey-container-servlet-core:3.1.3
org.glassfish.jersey.containers:jersey-container-servlet:3.1.3
org.glassfish.jersey.core:jersey-server:3.1.3
org.glassfish.jersey.ext:jersey-bean-validation:3.1.3
org.glassfish.jersey.ext:jersey-spring6:3.1.3
org.glassfish.jersey.media:jersey-media-json-jackson:3.1.3
```

## 配置属性

```
spring.jersey.application-path

Path that serves as the base URI for the application. If specified, overrides the value of "@ApplicationPath".

spring.jersey.filter.order

Jersey filter chain order.

0

spring.jersey.init.*

Init parameters to pass to Jersey through the servlet or filter.

spring.jersey.servlet.load-on-startup

Load on startup priority of the Jersey servlet.

-1

spring.jersey.type

Jersey integration type.

servlet
```
