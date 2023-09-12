# spring-boot-starter-mail

```
# 构件
org.springframework.boot:spring-boot-starter-mail:3.1.3

# 依赖：compile
org.springframework.boot:spring-boot-starter:3.1.3
org.springframework:spring-context-support:6.0.11
org.eclipse.angus:jakarta.mail:1.1.0
```

## 3. Mail Properties

```
spring.mail.default-encoding

Default MimeMessage encoding.

UTF-8

spring.mail.host

SMTP server host. For instance, 'smtp.example.com'.

spring.mail.jndi-name

Session JNDI name. When set, takes precedence over other Session settings.

spring.mail.password

Login password of the SMTP server.

spring.mail.port

SMTP server port.

spring.mail.properties.*

Additional JavaMail Session properties.

spring.mail.protocol

Protocol used by the SMTP server.

smtp

spring.mail.test-connection

Whether to test that the mail server is available on startup.

false

spring.mail.username

Login user of the SMTP server.

spring.sendgrid.api-key

SendGrid API key.

spring.sendgrid.proxy.host

SendGrid proxy host.

spring.sendgrid.proxy.port

SendGrid proxy port.


```
