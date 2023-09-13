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

```
org.springframework.boot.web.server.Cookie
org.springframework.boot.web.server.Cookie.SameSite
org.springframework.boot.web.server.MimeMappings
org.springframework.boot.web.server.MimeMappings.DefaultMimeMappings
org.springframework.boot.web.server.MimeMappings.LazyMimeMappingsCopy
org.springframework.boot.web.server.MimeMappings.Mapping
org.springframework.boot.web.server.MimeMappings.MimeMappingsRuntimeHints
org.springframework.boot.web.server.PortInUseException
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
```

## 错误页面

```
org.springframework.boot.web.server.ErrorPage
org.springframework.boot.web.server.ErrorPageRegistrar
org.springframework.boot.web.server.ErrorPageRegistry
org.springframework.boot.web.server.ErrorPageRegistrarBeanPostProcessor
```

```
org.springframework.boot.web.server.Http2

org.springframework.boot.web.server.Compression
```

## 

```
# SSL配置验证器，已废弃。
# validateKeyAlias 验证密钥的别名
org.springframework.boot.web.server.SslConfigurationValidator

# SSL配置。
# boolean    enabled                    是否启用SSL，默认值：true 
# String     bundle                     the name of the SSL bundle to use.
# ClientAuth clientAuth                 Return Whether client authentication is not wanted ("none"), wanted ("want") or needed ("need"). Requires a trust store.
# String[]   ciphers                    Return the supported SSL ciphers.
# String[]   enabledProtocols           Return the enabled SSL protocols.
# String     keyAlias                   Return the alias that identifies the key in the key store.
# String     keyPassword                Return the password used to access the key in the key store.
# String     keyStore                   Return the path to the key store that holds the SSL certificate (typically a jks file).
# String     keyStorePassword           Return the password used to access the key store.
# String     keyStoreType               Return the type of the key store.
# String     keyStoreProvider           Return the provider for the key store.
# String     trustStore                 Return the trust store that holds SSL certificates.
# String     trustStorePassword         Return the password used to access the trust store.
# String     trustStoreType             Return the type of the trust store.
# String     trustStoreProvider         Return the provider for the trust store.
# String     certificate                Return the location of the certificate in PEM format.
# String     certificatePrivateKey      Return the location of the private key for the certificate in PEM format.
# String     trustCertificate           Return the location of the trust certificate authority chain in PEM format.
# String     trustCertificatePrivateKey Return the location of the private key for the trust certificate in PEM format.
# String     protocol                   SSL协议，默认值：TLS
# forBundle
# isEnabled
# getXXX
# isXXX
# setXXX
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
# getKeyPassword 获取密钥存储库（KeyStore）中私钥的密码
org.springframework.boot.web.server.SslStoreProvider
 
# 根据证书和PEM私钥文件创建密钥和受信存储库的SSL存储库提供者（SslStoreProvider），已废弃。
# delegate       SslBundle
# from           创建SslStoreProvider
# getTrustStore  获取受信的密钥存储库（KeyStore）
# getKeyStore    获取密钥存储库（KeyStore）
# getKeyPassword 获取密钥存储库（KeyStore）中私钥的密码
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


## 关闭Web服务器

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
