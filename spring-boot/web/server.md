# server

## 层次结构

```
# Web服务器工厂
org.springframework.boot.web.server.WebServerFactory
    + org.springframework.boot.web.server.ConfigurableWebServerFactory
        + org.springframework.boot.web.server.AbstractConfigurableWebServerFactory

# 错误页面注册表
org.springframework.boot.web.server.ErrorPageRegistry
    + org.springframework.boot.web.server.ConfigurableWebServerFactory
        + org.springframework.boot.web.server.AbstractConfigurableWebServerFactory

## SSL存储库提供者
org.springframework.boot.web.server.SslStoreProvider
    + org.springframework.boot.web.server.CertificateFileSslStoreProvider

# Web服务器的SSL包
org.springframework.boot.ssl.SslBundle
    + org.springframework.boot.web.server.WebServerSslBundle

# SSL存储库提供者的SSL存储库包适配器
org.springframework.boot.ssl.SslStoreBundle
    + org.springframework.boot.web.server.WebServerSslBundle.SslStoreProviderBundleAdapter
```

## Web服务器

```
# Web服务器，例如：Tomcat、Jetty、Netty、Undertow。
# getPort            获取端口
# start              启动Web服务器
# stop               关闭Web服务器
# shutDownGracefully 优雅关闭Web服务器
org.springframework.boot.web.server.WebServer

# Web服务器（WebServer）工厂。
org.springframework.boot.web.server.WebServerFactory

# 可配置的Web服务器工厂（WebServerFactory）。
# setPort             设置Web服务器监听的端口，默认值：8080，-1：禁用自动启动，即只启动Web应用程序上下文，但是不监听任何端口
# setAddress          设置Web服务器绑定的网络地址
# setErrorPages       Sets the error pages that will be used when handling exceptions.
# setSsl              Sets the SSL configuration that will be applied to the server's default connector.
# setSslStoreProvider Sets a provider that will be used to obtain SSL stores.已废弃，请使用：setSslBundles
# setSslBundles       Sets the SSL bundles that can be used to configure SSL connections.
# setHttp2            Sets the HTTP/2 configuration that will be applied to the server.
# setCompression      Sets the compression configuration that will be applied to the server's default connector.
# setServerHeader     Sets the server header value.
# setShutdown         Sets the shutdown configuration that will be applied to the server.
org.springframework.boot.web.server.ConfigurableWebServerFactory

org.springframework.boot.web.server.AbstractConfigurableWebServerFactory

org.springframework.boot.web.server.WebServerFactoryCustomizer
org.springframework.boot.web.server.WebServerFactoryCustomizerBeanPostProcessor

org.springframework.boot.web.server.WebServerException
org.springframework.boot.web.server.PortInUseException
```

## 错误页面

```
org.springframework.boot.web.server.ErrorPage
org.springframework.boot.web.server.ErrorPageRegistrar
org.springframework.boot.web.server.ErrorPageRegistry
org.springframework.boot.web.server.ErrorPageRegistrarBeanPostProcessor
```

```
org.springframework.boot.web.server.Cookie
org.springframework.boot.web.server.Cookie.SameSite

org.springframework.boot.web.server.MimeMappings
org.springframework.boot.web.server.MimeMappings.DefaultMimeMappings
org.springframework.boot.web.server.MimeMappings.LazyMimeMappingsCopy
org.springframework.boot.web.server.MimeMappings.Mapping
org.springframework.boot.web.server.MimeMappings.MimeMappingsRuntimeHints
```

```
org.springframework.boot.web.server.Http2
org.springframework.boot.web.server.Compression
```

## SSL证书

```
# SSL配置验证器，已废弃。
# validateKeyAlias 验证密钥的别名
org.springframework.boot.web.server.SslConfigurationValidator

# SSL配置。
# enabled                    是否启用SSL，默认值：true 
# bundle                     SSL包的名称
# clientAuth                 客户端认证类型
# ciphers                    支持的SSL密码
# enabledProtocols           启用的SSL协议
# keyAlias                   标识密钥存储库中的密钥的别名
# keyPassword                访问密钥存储库中的密钥的密码
# keyStore                   存储SSL证书（通常是jks文件）的密钥存储库的路径
# keyStorePassword           访问密钥存储库的密码
# keyStoreType               密钥存储库的类型
# keyStoreProvider           密钥存储库提供者
# trustStore                 受信的存储SSL证书的密钥存储库
# trustStorePassword         访问受信的密钥存储库的密码
# trustStoreType             受信的密钥存储库的类型
# trustStoreProvider         受信的密钥存储库提供者
# certificate                PEM证书的位置
# certificatePrivateKey      PEM证书的私钥位置
# trustCertificate           受信的PEM证书的位置
# trustCertificatePrivateKey 受信的PEM证书的私钥位置
# protocol                   SSL协议，默认值：TLS
# forBundle                  创建Ssl
# isEnabled                  SSL是否启用
# getXXX                     获取XXX
# isXXX                      是否XXX
# setXXX                     设置XXX
org.springframework.boot.web.server.Ssl

# 客户端认证类型。
# NONE 不想进行客户端认证
# WANT 想要但不强制进行客户端认证
# NEED 需要并强制进行客户端认证
# map  把ClientAuth映射为不同的类型
org.springframework.boot.web.server.Ssl.ClientAuth

# SSL存储库提供者，已废弃。
# getTrustStore  获取受信的密钥存储库（KeyStore）
# getKeyStore    获取密钥存储库（KeyStore）
# getKeyPassword 获取密钥存储库（KeyStore）中的密钥的密码
org.springframework.boot.web.server.SslStoreProvider
 
# 根据证书和PEM私钥文件创建密钥和受信存储库的SSL存储库提供者（SslStoreProvider），已废弃。
# delegate       SslBundle
# from           创建SslStoreProvider
# getTrustStore  获取受信的密钥存储库（KeyStore）
# getKeyStore    获取密钥存储库（KeyStore）
# getKeyPassword 获取密钥存储库（KeyStore）中的密钥的密码
org.springframework.boot.web.server.CertificateFileSslStoreProvider

# Web服务器的SSL包（SslBundle）。
# Ssl或SslStoreProvider支持的SslBundle。
# DEFAULT_PROTOCOL 默认协议：TLS
# stores           SslStoreBundle
# key              SslBundleKey
# options          SslOptions
# protocol         String
# managers         SslManagerBundle
# of               创建SslBundle
# createSslContext 创建SSLContext
# getStores        获取SslStoreBundle
# getKey           获取SslBundleKey
# getOptions       获取SslOptions
# getProtocol      获取协议
# getManagers      获取SslManagerBundle
# get              获取SslBundle
org.springframework.boot.web.server.WebServerSslBundle

# SSL存储库提供者（SslStoreProvider）的SSL存储库包（SslStoreBundle）适配器。
# 把SslStoreProvider适配成SslStoreBundle。
# NONE                空SslStoreBundle
# of                  创建SslStoreBundle
# getTrustStore       获取受信的密钥存储库（KeyStore）
# getKeyStore         获取密钥存储库（KeyStore）
# getKeyStorePassword 获取密钥存储库（KeyStore）中私钥的密码
org.springframework.boot.web.server.WebServerSslBundle.SslStoreProviderBundleAdapter
```

## 关闭服务器

```
# Web服务器的关闭配置。
# GRACEFUL  优雅关闭Web服务器
# IMMEDIATE 立即关闭Web服务器
org.springframework.boot.web.server.Shutdown

# Web服务器的优雅关闭结果。
# REQUESTS_ACTIVE 在最后的宽限期，激活请求仍然有效
# IDLE            在最后的宽限期，Web服务器空闲，没有激活请求
# IMMEDIATE       立即关闭Web服务器，忽略激活请求
org.springframework.boot.web.server.GracefulShutdownResult

# Web服务器的优雅关闭回调。
# shutdownComplete Web服务器优雅关闭完成后的处理
org.springframework.boot.web.server.GracefulShutdownCallback
```
