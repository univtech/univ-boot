# spring-boot-starter-jetty

```xml

# 构件
org.springframework.boot:spring-boot-starter-jetty:3.1.3

  <name>spring-boot-starter-jetty</name>
  <description>Starter for using Jetty as the embedded servlet container. An alternative to spring-boot-starter-tomcat</description>

# 地址
https://spring.io
https://spring.io/projects/spring-boot

https://github.com/spring-projects/spring-boot
https://github.com/spring-projects/spring-boot/issues

git://github.com/spring-projects/spring-boot.git
ssh://git@github.com/spring-projects/spring-boot.git

# 依赖：
jakarta.servlet:jakarta.servlet-api:6.0.0:compile
jakarta.websocket:jakarta.websocket-api:2.1.1:compile
jakarta.websocket:jakarta.websocket-client-api:2.1.1:compile
org.apache.tomcat.embed:tomcat-embed-el:10.1.12:compile
org.eclipse.jetty:jetty-servlets:11.0.15:compile
org.eclipse.jetty:jetty-webapp:11.0.15:compile</scope>
      <exclusions>
        <exclusion>
          <artifactId>jetty-jakarta-servlet-api</artifactId>
          <groupId>org.eclipse.jetty.toolchain</groupId>
        </exclusion>
      </exclusions>
org.eclipse.jetty.websocket:websocket-jakarta-server:11.0.15:compile</scope>
      <exclusions>
        <exclusion>
          <artifactId>jetty-jakarta-servlet-api</artifactId>
          <groupId>org.eclipse.jetty.toolchain</groupId>
        </exclusion>
        <exclusion>
          <artifactId>jetty-jakarta-websocket-api</artifactId>
          <groupId>org.eclipse.jetty.toolchain</groupId>
        </exclusion>
      </exclusions>
org.eclipse.jetty.websocket:websocket-jetty-server:11.0.15:compile</scope>
      <exclusions>
        <exclusion>
          <artifactId>jetty-jakarta-servlet-api</artifactId>
          <groupId>org.eclipse.jetty.toolchain</groupId>
        </exclusion>
        <exclusion>
          <artifactId>jetty-jndi</artifactId>
          <groupId>org.eclipse.jetty</groupId>
        </exclusion>
      </exclusions>
```
