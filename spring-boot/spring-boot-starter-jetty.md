# spring-boot-starter-jetty

```xml

  <modelVersion>4.0.0</modelVersion>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-jetty</artifactId>
  <version>3.1.3</version>
  <name>spring-boot-starter-jetty</name>
  <description>Starter for using Jetty as the embedded servlet container. An alternative to spring-boot-starter-tomcat</description>
  <url>https://spring.io/projects/spring-boot</url>
  <organization>
    <name>VMware, Inc.</name>
    <url>https://spring.io</url>
  </organization>
  <licenses>
    <license>
      <name>Apache License, Version 2.0</name>
      <url>https://www.apache.org/licenses/LICENSE-2.0</url>
    </license>
  </licenses>
  <developers>
    <developer>
      <name>Spring</name>
      <email>ask@spring.io</email>
      <organization>VMware, Inc.</organization>
      <organizationUrl>https://www.spring.io</organizationUrl>
    </developer>
  </developers>
  <scm>
    <connection>scm:git:git://github.com/spring-projects/spring-boot.git</connection>
    <developerConnection>scm:git:ssh://git@github.com/spring-projects/spring-boot.git</developerConnection>
    <url>https://github.com/spring-projects/spring-boot</url>
  </scm>
  <issueManagement>
    <system>GitHub</system>
    <url>https://github.com/spring-projects/spring-boot/issues</url>
  </issueManagement>
  <dependencies>
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
