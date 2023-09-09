# spring-boot-starter-test

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd" xmlns="http://maven.apache.org/POM/4.0.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <!-- This module was also published with a richer model, Gradle metadata,  -->
  <!-- which should be used instead. Do not delete the following line which  -->
  <!-- is to indicate to Gradle or any Gradle module metadata file consumer  -->
  <!-- that they should prefer consuming it instead. -->
  <!-- do_not_remove: published-with-gradle-metadata -->
  <modelVersion>4.0.0</modelVersion>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-test</artifactId>
  <version>3.1.3</version>
  <name>spring-boot-starter-test</name>
  <description>Starter for testing Spring Boot applications with libraries including JUnit Jupiter, Hamcrest and Mockito</description>
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
org.springframework.boot:spring-boot-starter:3.1.3:compile
org.springframework.boot:spring-boot-test:3.1.3:compile
org.springframework.boot:spring-boot-test-autoconfigure:3.1.3:compile
com.jayway.jsonpath:json-path:2.8.0:compile
jakarta.xml.bind:jakarta.xml.bind-api:4.0.0:compile
net.minidev:json-smart:2.4.11:compile
org.assertj:assertj-core:3.24.2:compile
org.hamcrest:hamcrest:2.2:compile
org.junit.jupiter:junit-jupiter:5.9.3:compile
org.mockito:mockito-core:5.3.1:compile
org.mockito:mockito-junit-jupiter:5.3.1:compile
org.skyscreamer:jsonassert:1.5.1:compile
org.springframework:spring-core:6.0.11:compile
org.springframework:spring-test:6.0.11:compile
org.xmlunit:xmlunit-core:2.9.1:compile</scope>
      <exclusions>
        <exclusion>
          <artifactId>jaxb-api</artifactId>
          <groupId>javax.xml.bind</groupId>
        </exclusion>
      </exclusions>
  </dependencies>
</project>

```
