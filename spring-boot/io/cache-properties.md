
## 2. Cache Properties

```
spring.cache.cache-names

Comma-separated list of cache names to create if supported by the underlying cache manager. Usually, this disables the ability to create additional caches on-the-fly.

spring.cache.caffeine.spec

The spec to use to create caches. See CaffeineSpec for more details on the spec format.

spring.cache.couchbase.expiration

Entry expiration. By default the entries never expire. Note that this value is ultimately converted to seconds.

spring.cache.infinispan.config

The location of the configuration file to use to initialize Infinispan.

spring.cache.jcache.config

The location of the configuration file to use to initialize the cache manager. The configuration file is dependent of the underlying cache implementation.

spring.cache.jcache.provider

Fully qualified name of the CachingProvider implementation to use to retrieve the JSR-107 compliant cache manager. Needed only if more than one JSR-107 implementation is available on the classpath.

spring.cache.redis.cache-null-values

Allow caching null values.

true

spring.cache.redis.enable-statistics

Whether to enable cache statistics.

false

spring.cache.redis.key-prefix

Key prefix.

spring.cache.redis.time-to-live

Entry expiration. By default the entries never expire.

spring.cache.redis.use-key-prefix

Whether to use the key prefix when writing to Redis.

true

spring.cache.type

Cache type. By default, auto-detected according to the environment.


```
