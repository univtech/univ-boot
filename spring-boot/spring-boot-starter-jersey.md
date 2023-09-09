# spring-boot-starter-jersey

```xml

  <modelVersion>4.0.0</modelVersion>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-jersey</artifactId>
  <version>3.1.3</version>
  <name>spring-boot-starter-jersey</name>
  <description>Starter for building RESTful web applications using JAX-RS and Jersey. An alternative to spring-boot-starter-web</description>
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
org.springframework.boot:spring-boot-starter-json:3.1.3:compile
org.springframework.boot:spring-boot-starter-tomcat:3.1.3:compile
org.springframework.boot:spring-boot-starter-validation:3.1.3:compile
org.springframework:spring-web:6.0.11:compile
org.glassfish.jersey.containers:jersey-container-servlet-core:3.1.3:compile
org.glassfish.jersey.containers:jersey-container-servlet:3.1.3:compile
org.glassfish.jersey.core:jersey-server:3.1.3:compile
org.glassfish.jersey.ext:jersey-bean-validation:3.1.3:compile</scope>
      <exclusions>
        <exclusion>
          <artifactId>jakarta.el</artifactId>
          <groupId>org.glassfish</groupId>
        </exclusion>
        <exclusion>
          <artifactId>jakarta.el-api</artifactId>
          <groupId>jakarta.el</groupId>
        </exclusion>
      </exclusions>
org.glassfish.jersey.ext:jersey-spring6:3.1.3:compile
org.glassfish.jersey.media:jersey-media-json-jackson:3.1.3:compile
```
