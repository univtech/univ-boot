# 5. Data Properties

```
spring.cassandra.compression

Compression supported by the Cassandra binary protocol.

none

spring.cassandra.config

Location of the configuration file to use.

spring.cassandra.connection.connect-timeout

Timeout to use when establishing driver connections.

5s

spring.cassandra.connection.init-query-timeout

Timeout to use for internal queries that run as part of the initialization process, just after a connection is opened.

5s

spring.cassandra.contact-points

Cluster node addresses in the form 'host:port', or a simple 'host' to use the configured port.

[127.0.0.1:9042]

spring.cassandra.controlconnection.timeout

Timeout to use for control queries.

5s

spring.cassandra.keyspace-name

Keyspace name to use.

spring.cassandra.local-datacenter

Datacenter that is considered "local". Contact points should be from this datacenter.

spring.cassandra.password

Login password of the server.

spring.cassandra.pool.heartbeat-interval

Heartbeat interval after which a message is sent on an idle connection to make sure it's still alive.

30s

spring.cassandra.pool.idle-timeout

Idle timeout before an idle connection is removed.

5s

spring.cassandra.port

Port to use if a contact point does not specify one.

9042

spring.cassandra.request.consistency

Queries consistency level.

spring.cassandra.request.page-size

How many rows will be retrieved simultaneously in a single network round-trip.

5000

spring.cassandra.request.serial-consistency

Queries serial consistency level.

spring.cassandra.request.throttler.drain-interval

How often the throttler attempts to dequeue requests. Set this high enough that each attempt will process multiple entries in the queue, but not delay requests too much.

spring.cassandra.request.throttler.max-concurrent-requests

Maximum number of requests that are allowed to execute in parallel.

spring.cassandra.request.throttler.max-queue-size

Maximum number of requests that can be enqueued when the throttling threshold is exceeded.

spring.cassandra.request.throttler.max-requests-per-second

Maximum allowed request rate.

spring.cassandra.request.throttler.type

Request throttling type.

none

spring.cassandra.request.timeout

How long the driver waits for a request to complete.

2s

spring.cassandra.schema-action

Schema action to take at startup.

none

spring.cassandra.session-name

Name of the Cassandra session.

spring.cassandra.ssl.bundle

SSL bundle name.

spring.cassandra.ssl.enabled

Whether to enable SSL support.

spring.cassandra.username

Login user of the server.

spring.couchbase.connection-string

Connection string used to locate the Couchbase cluster.

spring.couchbase.env.io.idle-http-connection-timeout

Length of time an HTTP connection may remain idle before it is closed and removed from the pool.

4500ms

spring.couchbase.env.io.max-endpoints

Maximum number of sockets per node.

12

spring.couchbase.env.io.min-endpoints

Minimum number of sockets per node.

1

spring.couchbase.env.ssl.bundle

SSL bundle name.

spring.couchbase.env.ssl.enabled

Whether to enable SSL support. Enabled automatically if a "keyStore" or "bundle" is provided unless specified otherwise.

spring.couchbase.env.timeouts.analytics

Timeout for the analytics service.

75s

spring.couchbase.env.timeouts.connect

Bucket connect timeout.

10s

spring.couchbase.env.timeouts.disconnect

Bucket disconnect timeout.

10s

spring.couchbase.env.timeouts.key-value

Timeout for operations on a specific key-value.

2500ms

spring.couchbase.env.timeouts.key-value-durable

Timeout for operations on a specific key-value with a durability level.

10s

spring.couchbase.env.timeouts.management

Timeout for the management operations.

75s

spring.couchbase.env.timeouts.query

N1QL query operations timeout.

75s

spring.couchbase.env.timeouts.search

Timeout for the search service.

75s

spring.couchbase.env.timeouts.view

Regular and geospatial view operations timeout.

75s

spring.couchbase.password

Cluster password.

spring.couchbase.username

Cluster username.

spring.dao.exceptiontranslation.enabled

Whether to enable the PersistenceExceptionTranslationPostProcessor.

true

spring.data.cassandra.repositories.type

Type of Cassandra repositories to enable.

auto

spring.data.couchbase.auto-index

Automatically create views and indexes. Use the meta-data provided by "@ViewIndexed", "@N1qlPrimaryIndexed" and "@N1qlSecondaryIndexed".

false

spring.data.couchbase.bucket-name

Name of the bucket to connect to.

spring.data.couchbase.field-naming-strategy

Fully qualified name of the FieldNamingStrategy to use.

spring.data.couchbase.repositories.type

Type of Couchbase repositories to enable.

auto

spring.data.couchbase.scope-name

Name of the scope used for all collection access.

spring.data.couchbase.type-key

Name of the field that stores the type information for complex types when using "MappingCouchbaseConverter".

_class

spring.data.elasticsearch.repositories.enabled

Whether to enable Elasticsearch repositories.

true

spring.data.jdbc.repositories.enabled

Whether to enable JDBC repositories.

true

spring.data.jpa.repositories.bootstrap-mode

Bootstrap mode for JPA repositories.

default

spring.data.jpa.repositories.enabled

Whether to enable JPA repositories.

true

spring.data.ldap.repositories.enabled

Whether to enable LDAP repositories.

true

spring.data.mongodb.additional-hosts

Additional server hosts. Cannot be set with URI or if 'host' is not specified. Additional hosts will use the default mongo port of 27017. If you want to use a different port you can use the "host:port" syntax.

spring.data.mongodb.authentication-database

Authentication database name.

spring.data.mongodb.auto-index-creation

Whether to enable auto-index creation.

spring.data.mongodb.database

Database name. Overrides database in URI.

spring.data.mongodb.field-naming-strategy

Fully qualified name of the FieldNamingStrategy to use.

spring.data.mongodb.gridfs.bucket

GridFS bucket name.

spring.data.mongodb.gridfs.database

GridFS database name.

spring.data.mongodb.host

Mongo server host. Cannot be set with URI.

spring.data.mongodb.password

Login password of the mongo server. Cannot be set with URI.

spring.data.mongodb.port

Mongo server port. Cannot be set with URI.

spring.data.mongodb.replica-set-name

Required replica set name for the cluster. Cannot be set with URI.

spring.data.mongodb.repositories.type

Type of Mongo repositories to enable.

auto

spring.data.mongodb.ssl.bundle

SSL bundle name.

spring.data.mongodb.ssl.enabled

Whether to enable SSL support. Enabled automatically if "bundle" is provided unless specified otherwise.

spring.data.mongodb.uri

Mongo database URI. Overrides host, port, username, and password.

mongodb://localhost/test

spring.data.mongodb.username

Login user of the mongo server. Cannot be set with URI.

spring.data.mongodb.uuid-representation

Representation to use when converting a UUID to a BSON binary value.

java-legacy

spring.data.neo4j.database

Database name to use. By default, the server decides the default database to use.

spring.data.neo4j.repositories.type

Type of Neo4j repositories to enable.

auto

spring.data.r2dbc.repositories.enabled

Whether to enable R2DBC repositories.

true

spring.data.redis.client-name

Client name to be set on connections with CLIENT SETNAME.

spring.data.redis.client-type

Type of client to use. By default, auto-detected according to the classpath.

spring.data.redis.cluster.max-redirects

Maximum number of redirects to follow when executing commands across the cluster.

spring.data.redis.cluster.nodes

Comma-separated list of "host:port" pairs to bootstrap from. This represents an "initial" list of cluster nodes and is required to have at least one entry.

spring.data.redis.connect-timeout

Connection timeout.

spring.data.redis.database

Database index used by the connection factory.

0

spring.data.redis.host

Redis server host.

localhost

spring.data.redis.jedis.pool.enabled

Whether to enable the pool. Enabled automatically if "commons-pool2" is available. With Jedis, pooling is implicitly enabled in sentinel mode and this setting only applies to single node setup.

spring.data.redis.jedis.pool.max-active

Maximum number of connections that can be allocated by the pool at a given time. Use a negative value for no limit.

8

spring.data.redis.jedis.pool.max-idle

Maximum number of "idle" connections in the pool. Use a negative value to indicate an unlimited number of idle connections.

8

spring.data.redis.jedis.pool.max-wait

Maximum amount of time a connection allocation should block before throwing an exception when the pool is exhausted. Use a negative value to block indefinitely.

-1ms

spring.data.redis.jedis.pool.min-idle

Target for the minimum number of idle connections to maintain in the pool. This setting only has an effect if both it and time between eviction runs are positive.

0

spring.data.redis.jedis.pool.time-between-eviction-runs

Time between runs of the idle object evictor thread. When positive, the idle object evictor thread starts, otherwise no idle object eviction is performed.

spring.data.redis.lettuce.cluster.refresh.adaptive

Whether adaptive topology refreshing using all available refresh triggers should be used.

false

spring.data.redis.lettuce.cluster.refresh.dynamic-refresh-sources

Whether to discover and query all cluster nodes for obtaining the cluster topology. When set to false, only the initial seed nodes are used as sources for topology discovery.

true

spring.data.redis.lettuce.cluster.refresh.period

Cluster topology refresh period.

spring.data.redis.lettuce.pool.enabled

Whether to enable the pool. Enabled automatically if "commons-pool2" is available. With Jedis, pooling is implicitly enabled in sentinel mode and this setting only applies to single node setup.

spring.data.redis.lettuce.pool.max-active

Maximum number of connections that can be allocated by the pool at a given time. Use a negative value for no limit.

8

spring.data.redis.lettuce.pool.max-idle

Maximum number of "idle" connections in the pool. Use a negative value to indicate an unlimited number of idle connections.

8

spring.data.redis.lettuce.pool.max-wait

Maximum amount of time a connection allocation should block before throwing an exception when the pool is exhausted. Use a negative value to block indefinitely.

-1ms

spring.data.redis.lettuce.pool.min-idle

Target for the minimum number of idle connections to maintain in the pool. This setting only has an effect if both it and time between eviction runs are positive.

0

spring.data.redis.lettuce.pool.time-between-eviction-runs

Time between runs of the idle object evictor thread. When positive, the idle object evictor thread starts, otherwise no idle object eviction is performed.

spring.data.redis.lettuce.shutdown-timeout

Shutdown timeout.

100ms

spring.data.redis.password

Login password of the redis server.

spring.data.redis.port

Redis server port.

6379

spring.data.redis.repositories.enabled

Whether to enable Redis repositories.

true

spring.data.redis.sentinel.master

Name of the Redis server.

spring.data.redis.sentinel.nodes

Comma-separated list of "host:port" pairs.

spring.data.redis.sentinel.password

Password for authenticating with sentinel(s).

spring.data.redis.sentinel.username

Login username for authenticating with sentinel(s).

spring.data.redis.ssl.bundle

SSL bundle name.

spring.data.redis.ssl.enabled

Whether to enable SSL support. Enabled automatically if "bundle" is provided unless specified otherwise.

spring.data.redis.timeout

Read timeout.

spring.data.redis.url

Connection URL. Overrides host, port, username, and password. Example: redis://user:password@example.com:6379

spring.data.redis.username

Login username of the redis server.

spring.data.rest.base-path

Base path to be used by Spring Data REST to expose repository resources.

spring.data.rest.default-media-type

Content type to use as a default when none is specified.

spring.data.rest.default-page-size

Default size of pages.

spring.data.rest.detection-strategy

Strategy to use to determine which repositories get exposed.

default

spring.data.rest.enable-enum-translation

Whether to enable enum value translation through the Spring Data REST default resource bundle.

spring.data.rest.limit-param-name

Name of the URL query string parameter that indicates how many results to return at once.

spring.data.rest.max-page-size

Maximum size of pages.

spring.data.rest.page-param-name

Name of the URL query string parameter that indicates what page to return.

spring.data.rest.return-body-on-create

Whether to return a response body after creating an entity.

spring.data.rest.return-body-on-update

Whether to return a response body after updating an entity.

spring.data.rest.sort-param-name

Name of the URL query string parameter that indicates what direction to sort results.

spring.data.web.pageable.default-page-size

Default page size.

20

spring.data.web.pageable.max-page-size

Maximum page size to be accepted.

2000

spring.data.web.pageable.one-indexed-parameters

Whether to expose and assume 1-based page number indexes. Defaults to "false", meaning a page number of 0 in the request equals the first page.

false

spring.data.web.pageable.page-parameter

Page index parameter name.

page

spring.data.web.pageable.prefix

General prefix to be prepended to the page number and page size parameters.

spring.data.web.pageable.qualifier-delimiter

Delimiter to be used between the qualifier and the actual page number and size properties.

_

spring.data.web.pageable.size-parameter

Page size parameter name.

size

spring.data.web.sort.sort-parameter

Sort parameter name.

sort

spring.datasource.dbcp2.abandoned-usage-tracking
spring.datasource.dbcp2.access-to-underlying-connection-allowed
spring.datasource.dbcp2.auto-commit-on-return
spring.datasource.dbcp2.cache-state
spring.datasource.dbcp2.clear-statement-pool-on-return
spring.datasource.dbcp2.connection-factory-class-name
spring.datasource.dbcp2.connection-init-sqls
spring.datasource.dbcp2.default-auto-commit
spring.datasource.dbcp2.default-catalog
spring.datasource.dbcp2.default-query-timeout
spring.datasource.dbcp2.default-read-only
spring.datasource.dbcp2.default-schema
spring.datasource.dbcp2.default-transaction-isolation
spring.datasource.dbcp2.disconnection-sql-codes
spring.datasource.dbcp2.driver
spring.datasource.dbcp2.driver-class-name
spring.datasource.dbcp2.eviction-policy-class-name
spring.datasource.dbcp2.fast-fail-validation
spring.datasource.dbcp2.initial-size
spring.datasource.dbcp2.jmx-name
spring.datasource.dbcp2.lifo
spring.datasource.dbcp2.log-abandoned
spring.datasource.dbcp2.log-expired-connections
spring.datasource.dbcp2.login-timeout
spring.datasource.dbcp2.max-conn-lifetime-millis
spring.datasource.dbcp2.max-idle
spring.datasource.dbcp2.max-open-prepared-statements
spring.datasource.dbcp2.max-total
spring.datasource.dbcp2.max-wait-millis
spring.datasource.dbcp2.min-evictable-idle-time-millis
spring.datasource.dbcp2.min-idle
spring.datasource.dbcp2.num-tests-per-eviction-run
spring.datasource.dbcp2.password
spring.datasource.dbcp2.pool-prepared-statements
spring.datasource.dbcp2.remove-abandoned-on-borrow
spring.datasource.dbcp2.remove-abandoned-on-maintenance
spring.datasource.dbcp2.remove-abandoned-timeout
spring.datasource.dbcp2.rollback-on-return
spring.datasource.dbcp2.soft-min-evictable-idle-time-millis
spring.datasource.dbcp2.test-on-borrow
spring.datasource.dbcp2.test-on-create
spring.datasource.dbcp2.test-on-return
spring.datasource.dbcp2.test-while-idle
spring.datasource.dbcp2.time-between-eviction-runs-millis
spring.datasource.dbcp2.url
spring.datasource.dbcp2.username
spring.datasource.dbcp2.validation-query
spring.datasource.dbcp2.validation-query-timeout

Commons DBCP2 specific settings bound to an instance of DBCP2's BasicDataSource

spring.datasource.driver-class-name

Fully qualified name of the JDBC driver. Auto-detected based on the URL by default.

spring.datasource.embedded-database-connection

Connection details for an embedded database. Defaults to the most suitable embedded database that is available on the classpath.

spring.datasource.generate-unique-name

Whether to generate a random datasource name.

true

spring.datasource.hikari.allow-pool-suspension
spring.datasource.hikari.auto-commit
spring.datasource.hikari.catalog
spring.datasource.hikari.connection-init-sql
spring.datasource.hikari.connection-test-query
spring.datasource.hikari.connection-timeout
spring.datasource.hikari.data-source-class-name
spring.datasource.hikari.data-source-j-n-d-i
spring.datasource.hikari.data-source-properties
spring.datasource.hikari.driver-class-name
spring.datasource.hikari.exception-override-class-name
spring.datasource.hikari.health-check-properties
spring.datasource.hikari.idle-timeout
spring.datasource.hikari.initialization-fail-timeout
spring.datasource.hikari.isolate-internal-queries
spring.datasource.hikari.jdbc-url
spring.datasource.hikari.keepalive-time
spring.datasource.hikari.leak-detection-threshold
spring.datasource.hikari.login-timeout
spring.datasource.hikari.max-lifetime
spring.datasource.hikari.maximum-pool-size
spring.datasource.hikari.metrics-tracker-factory
spring.datasource.hikari.minimum-idle
spring.datasource.hikari.password
spring.datasource.hikari.pool-name
spring.datasource.hikari.read-only
spring.datasource.hikari.register-mbeans
spring.datasource.hikari.scheduled-executor
spring.datasource.hikari.schema
spring.datasource.hikari.transaction-isolation
spring.datasource.hikari.username
spring.datasource.hikari.validation-timeout

Hikari specific settings bound to an instance of Hikari's HikariDataSource

spring.datasource.jndi-name

JNDI location of the datasource. Class, url, username and password are ignored when set.

spring.datasource.name

Datasource name to use if "generate-unique-name" is false. Defaults to "testdb" when using an embedded database, otherwise null.

spring.datasource.oracleucp.abandoned-connection-timeout
spring.datasource.oracleucp.connection-factory-class-name
spring.datasource.oracleucp.connection-factory-properties
spring.datasource.oracleucp.connection-harvest-max-count
spring.datasource.oracleucp.connection-harvest-trigger-count
spring.datasource.oracleucp.connection-labeling-high-cost
spring.datasource.oracleucp.connection-pool-name
spring.datasource.oracleucp.connection-properties
spring.datasource.oracleucp.connection-repurpose-threshold
spring.datasource.oracleucp.connection-validation-timeout
spring.datasource.oracleucp.connection-wait-timeout
spring.datasource.oracleucp.data-source-name
spring.datasource.oracleucp.database-name
spring.datasource.oracleucp.description
spring.datasource.oracleucp.fast-connection-failover-enabled
spring.datasource.oracleucp.high-cost-connection-reuse-threshold
spring.datasource.oracleucp.inactive-connection-timeout
spring.datasource.oracleucp.initial-pool-size
spring.datasource.oracleucp.login-timeout
spring.datasource.oracleucp.max-connection-reuse-count
spring.datasource.oracleucp.max-connection-reuse-time
spring.datasource.oracleucp.max-connections-per-shard
spring.datasource.oracleucp.max-idle-time
spring.datasource.oracleucp.max-pool-size
spring.datasource.oracleucp.max-statements
spring.datasource.oracleucp.min-pool-size
spring.datasource.oracleucp.network-protocol
spring.datasource.oracleucp.o-n-s-configuration
spring.datasource.oracleucp.pdb-roles
spring.datasource.oracleucp.port-number
spring.datasource.oracleucp.property-cycle
spring.datasource.oracleucp.query-timeout
spring.datasource.oracleucp.read-only-instance-allowed
spring.datasource.oracleucp.role-name
spring.datasource.oracleucp.s-q-l-for-validate-connection
spring.datasource.oracleucp.seconds-to-trust-idle-connection
spring.datasource.oracleucp.server-name
spring.datasource.oracleucp.sharding-mode
spring.datasource.oracleucp.time-to-live-connection-timeout
spring.datasource.oracleucp.timeout-check-interval
spring.datasource.oracleucp.u-r-l
spring.datasource.oracleucp.user
spring.datasource.oracleucp.validate-connection-on-borrow

Oracle UCP specific settings bound to an instance of Oracle UCP's PoolDataSource

spring.datasource.password

Login password of the database.

spring.datasource.tomcat.abandon-when-percentage-full
spring.datasource.tomcat.access-to-underlying-connection-allowed
spring.datasource.tomcat.alternate-username-allowed
spring.datasource.tomcat.commit-on-return
spring.datasource.tomcat.connection-properties
spring.datasource.tomcat.data-source-j-n-d-i
spring.datasource.tomcat.db-properties
spring.datasource.tomcat.default-auto-commit
spring.datasource.tomcat.default-catalog
spring.datasource.tomcat.default-read-only
spring.datasource.tomcat.default-transaction-isolation
spring.datasource.tomcat.driver-class-name
spring.datasource.tomcat.fair-queue
spring.datasource.tomcat.ignore-exception-on-pre-load
spring.datasource.tomcat.init-s-q-l
spring.datasource.tomcat.initial-size
spring.datasource.tomcat.jdbc-interceptors
spring.datasource.tomcat.jmx-enabled
spring.datasource.tomcat.log-abandoned
spring.datasource.tomcat.log-validation-errors
spring.datasource.tomcat.login-timeout
spring.datasource.tomcat.max-active
spring.datasource.tomcat.max-age
spring.datasource.tomcat.max-idle
spring.datasource.tomcat.max-wait
spring.datasource.tomcat.min-evictable-idle-time-millis
spring.datasource.tomcat.min-idle
spring.datasource.tomcat.name
spring.datasource.tomcat.num-tests-per-eviction-run
spring.datasource.tomcat.password
spring.datasource.tomcat.propagate-interrupt-state
spring.datasource.tomcat.remove-abandoned
spring.datasource.tomcat.remove-abandoned-timeout
spring.datasource.tomcat.rollback-on-return
spring.datasource.tomcat.suspect-timeout
spring.datasource.tomcat.test-on-borrow
spring.datasource.tomcat.test-on-connect
spring.datasource.tomcat.test-on-return
spring.datasource.tomcat.test-while-idle
spring.datasource.tomcat.time-between-eviction-runs-millis
spring.datasource.tomcat.url
spring.datasource.tomcat.use-disposable-connection-facade
spring.datasource.tomcat.use-equals
spring.datasource.tomcat.use-lock
spring.datasource.tomcat.use-statement-facade
spring.datasource.tomcat.username
spring.datasource.tomcat.validation-interval
spring.datasource.tomcat.validation-query
spring.datasource.tomcat.validation-query-timeout
spring.datasource.tomcat.validator-class-name

Tomcat datasource specific settings bound to an instance of Tomcat JDBC's DataSource

spring.datasource.type

Fully qualified name of the connection pool implementation to use. By default, it is auto-detected from the classpath.

spring.datasource.url

JDBC URL of the database.

spring.datasource.username

Login username of the database.

spring.datasource.xa.data-source-class-name

XA datasource fully qualified name.

spring.datasource.xa.properties.*

Properties to pass to the XA data source.

spring.elasticsearch.connection-timeout

Connection timeout used when communicating with Elasticsearch.

1s

spring.elasticsearch.password

Password for authentication with Elasticsearch.

spring.elasticsearch.path-prefix

Prefix added to the path of every request sent to Elasticsearch.

spring.elasticsearch.restclient.sniffer.delay-after-failure

Delay of a sniff execution scheduled after a failure.

1m

spring.elasticsearch.restclient.sniffer.interval

Interval between consecutive ordinary sniff executions.

5m

spring.elasticsearch.restclient.ssl.bundle

SSL bundle name.

spring.elasticsearch.socket-keep-alive

Whether to enable socket keep alive between client and Elasticsearch.

false

spring.elasticsearch.socket-timeout

Socket timeout used when communicating with Elasticsearch.

30s

spring.elasticsearch.uris

Comma-separated list of the Elasticsearch instances to use.

[http://localhost:9200]

spring.elasticsearch.username

Username for authentication with Elasticsearch.

spring.h2.console.enabled

Whether to enable the console.

false

spring.h2.console.path

Path at which the console is available.

/h2-console

spring.h2.console.settings.trace

Whether to enable trace output.

false

spring.h2.console.settings.web-admin-password

Password to access preferences and tools of H2 Console.

spring.h2.console.settings.web-allow-others

Whether to enable remote access.

false

spring.influx.password

Login password.

spring.influx.url

URL of the InfluxDB instance to which to connect.

spring.influx.user

Login user.

spring.jdbc.template.fetch-size

Number of rows that should be fetched from the database when more rows are needed. Use -1 to use the JDBC driver's default configuration.

-1

spring.jdbc.template.max-rows

Maximum number of rows. Use -1 to use the JDBC driver's default configuration.

-1

spring.jdbc.template.query-timeout

Query timeout. Default is to use the JDBC driver's default configuration. If a duration suffix is not specified, seconds will be used.

spring.jooq.sql-dialect

SQL dialect to use. Auto-detected by default.

spring.jpa.database

Target database to operate on, auto-detected by default. Can be alternatively set using the "databasePlatform" property.

spring.jpa.database-platform

Name of the target database to operate on, auto-detected by default. Can be alternatively set using the "Database" enum.

spring.jpa.defer-datasource-initialization

Whether to defer DataSource initialization until after any EntityManagerFactory beans have been created and initialized.

false

spring.jpa.generate-ddl

Whether to initialize the schema on startup.

false

spring.jpa.hibernate.ddl-auto

DDL mode. This is actually a shortcut for the "hibernate.hbm2ddl.auto" property. Defaults to "create-drop" when using an embedded database and no schema manager was detected. Otherwise, defaults to "none".

spring.jpa.hibernate.naming.implicit-strategy

Fully qualified name of the implicit naming strategy.

spring.jpa.hibernate.naming.physical-strategy

Fully qualified name of the physical naming strategy.

spring.jpa.mapping-resources

Mapping resources (equivalent to "mapping-file" entries in persistence.xml).

spring.jpa.open-in-view

Register OpenEntityManagerInViewInterceptor. Binds a JPA EntityManager to the thread for the entire processing of the request.

true

spring.jpa.properties.*

Additional native properties to set on the JPA provider.

spring.jpa.show-sql

Whether to enable logging of SQL statements.

false

spring.ldap.anonymous-read-only

Whether read-only operations should use an anonymous environment. Disabled by default unless a username is set.

spring.ldap.base

Base suffix from which all operations should originate.

spring.ldap.base-environment.*

LDAP specification settings.

spring.ldap.embedded.base-dn

List of base DNs.

spring.ldap.embedded.credential.password

Embedded LDAP password.

spring.ldap.embedded.credential.username

Embedded LDAP username.

spring.ldap.embedded.ldif

Schema (LDIF) script resource reference.

classpath:schema.ldif

spring.ldap.embedded.port

Embedded LDAP port.

0

spring.ldap.embedded.validation.enabled

Whether to enable LDAP schema validation.

true

spring.ldap.embedded.validation.schema

Path to the custom schema.

spring.ldap.password

Login password of the server.

spring.ldap.template.ignore-name-not-found-exception

Whether NameNotFoundException should be ignored in searches through the LdapTemplate.

false

spring.ldap.template.ignore-partial-result-exception

Whether PartialResultException should be ignored in searches through the LdapTemplate.

false

spring.ldap.template.ignore-size-limit-exceeded-exception

Whether SizeLimitExceededException should be ignored in searches through the LdapTemplate.

true

spring.ldap.urls

LDAP URLs of the server.

spring.ldap.username

Login username of the server.

spring.neo4j.authentication.kerberos-ticket

Kerberos ticket for connecting to the database. Mutual exclusive with a given username.

spring.neo4j.authentication.password

Login password of the server.

spring.neo4j.authentication.realm

Realm to connect to.

spring.neo4j.authentication.username

Login user of the server.

spring.neo4j.connection-timeout

Timeout for borrowing connections from the pool.

30s

spring.neo4j.max-transaction-retry-time

Maximum time transactions are allowed to retry.

30s

spring.neo4j.pool.connection-acquisition-timeout

Acquisition of new connections will be attempted for at most configured timeout.

60s

spring.neo4j.pool.idle-time-before-connection-test

Pooled connections that have been idle in the pool for longer than this threshold will be tested before they are used again.

spring.neo4j.pool.log-leaked-sessions

Whether to log leaked sessions.

false

spring.neo4j.pool.max-connection-lifetime

Pooled connections older than this threshold will be closed and removed from the pool.

1h

spring.neo4j.pool.max-connection-pool-size

Maximum amount of connections in the connection pool towards a single database.

100

spring.neo4j.pool.metrics-enabled

Whether to enable metrics.

false

spring.neo4j.security.cert-file

Path to the file that holds the trusted certificates.

spring.neo4j.security.encrypted

Whether the driver should use encrypted traffic.

false

spring.neo4j.security.hostname-verification-enabled

Whether hostname verification is required.

true

spring.neo4j.security.trust-strategy

Trust strategy to use.

trust-system-ca-signed-certificates

spring.neo4j.uri

URI used by the driver.

bolt://localhost:7687

spring.r2dbc.generate-unique-name

Whether to generate a random database name. Ignore any configured name when enabled.

false

spring.r2dbc.name

Database name. Set if no name is specified in the url. Default to "testdb" when using an embedded database.

spring.r2dbc.password

Login password of the database. Set if no password is specified in the url.

spring.r2dbc.pool.enabled

Whether pooling is enabled. Requires r2dbc-pool.

true

spring.r2dbc.pool.initial-size

Initial connection pool size.

10

spring.r2dbc.pool.max-acquire-time

Maximum time to acquire a connection from the pool. By default, wait indefinitely.

spring.r2dbc.pool.max-create-connection-time

Maximum time to wait to create a new connection. By default, wait indefinitely.

spring.r2dbc.pool.max-idle-time

Maximum amount of time that a connection is allowed to sit idle in the pool.

30m

spring.r2dbc.pool.max-life-time

Maximum lifetime of a connection in the pool. By default, connections have an infinite lifetime.

spring.r2dbc.pool.max-size

Maximal connection pool size.

10

spring.r2dbc.pool.max-validation-time

Maximum time to validate a connection from the pool. By default, wait indefinitely.

spring.r2dbc.pool.min-idle

Minimal number of idle connections.

0

spring.r2dbc.pool.validation-depth

Validation depth.

local

spring.r2dbc.pool.validation-query

Validation query.

spring.r2dbc.properties.*

Additional R2DBC options.

spring.r2dbc.url

R2DBC URL of the database. database name, username, password and pooling options specified in the url take precedence over individual options.

spring.r2dbc.username

Login username of the database. Set if no username is specified in the url.


```

# 6. Transaction Properties

```

spring.jta.atomikos.connectionfactory.borrow-connection-timeout

Timeout, in seconds, for borrowing connections from the pool.

30

spring.jta.atomikos.connectionfactory.ignore-session-transacted-flag

Whether to ignore the transacted flag when creating session.

true

spring.jta.atomikos.connectionfactory.local-transaction-mode

Whether local transactions are desired.

false

spring.jta.atomikos.connectionfactory.maintenance-interval

Time, in seconds, between runs of the pool's maintenance thread.

60

spring.jta.atomikos.connectionfactory.max-idle-time

Time, in seconds, after which connections are cleaned up from the pool.

60

spring.jta.atomikos.connectionfactory.max-lifetime

Time, in seconds, that a connection can be pooled for before being destroyed. 0 denotes no limit.

0

spring.jta.atomikos.connectionfactory.max-pool-size

Maximum size of the pool.

1

spring.jta.atomikos.connectionfactory.min-pool-size

Minimum size of the pool.

1

spring.jta.atomikos.connectionfactory.reap-timeout

Reap timeout, in seconds, for borrowed connections. 0 denotes no limit.

0

spring.jta.atomikos.connectionfactory.unique-resource-name

Unique name used to identify the resource during recovery.

jmsConnectionFactory

spring.jta.atomikos.connectionfactory.xa-connection-factory-class-name

Vendor-specific implementation of XAConnectionFactory.

spring.jta.atomikos.connectionfactory.xa-properties

Vendor-specific XA properties.

spring.jta.atomikos.datasource.borrow-connection-timeout

Timeout, in seconds, for borrowing connections from the pool.

30

spring.jta.atomikos.datasource.concurrent-connection-validation

Whether to use concurrent connection validation.

true

spring.jta.atomikos.datasource.default-isolation-level

Default isolation level of connections provided by the pool.

spring.jta.atomikos.datasource.login-timeout

Timeout, in seconds, for establishing a database connection.

0

spring.jta.atomikos.datasource.maintenance-interval

Time, in seconds, between runs of the pool's maintenance thread.

60

spring.jta.atomikos.datasource.max-idle-time

Time, in seconds, after which connections are cleaned up from the pool.

60

spring.jta.atomikos.datasource.max-lifetime

Time, in seconds, that a connection can be pooled for before being destroyed. 0 denotes no limit.

0

spring.jta.atomikos.datasource.max-pool-size

Maximum size of the pool.

1

spring.jta.atomikos.datasource.min-pool-size

Minimum size of the pool.

1

spring.jta.atomikos.datasource.reap-timeout

Reap timeout, in seconds, for borrowed connections. 0 denotes no limit.

0

spring.jta.atomikos.datasource.test-query

SQL query or statement used to validate a connection before returning it.

spring.jta.atomikos.datasource.unique-resource-name

Unique name used to identify the resource during recovery.

dataSource

spring.jta.atomikos.datasource.xa-data-source-class-name

Vendor-specific implementation of XAConnectionFactory.

spring.jta.atomikos.datasource.xa-properties

Vendor-specific XA properties.

spring.jta.enabled

Whether to enable JTA support.

true

spring.transaction.default-timeout

Default transaction timeout. If a duration suffix is not specified, seconds will be used.

spring.transaction.rollback-on-commit-failure

Whether to roll back on commit failures.


```

# 7. Data Migration Properties

```

spring.flyway.baseline-description

Description to tag an existing schema with when applying a baseline.

<< Flyway Baseline >>

spring.flyway.baseline-on-migrate

Whether to automatically call baseline when migrating a non-empty schema.

false

spring.flyway.baseline-version

Version to tag an existing schema with when executing baseline.

1

spring.flyway.batch

Whether to batch SQL statements when executing them. Requires Flyway Teams.

spring.flyway.cherry-pick

Migrations that Flyway should consider when migrating or undoing. When empty all available migrations are considered. Requires Flyway Teams.

spring.flyway.clean-disabled

Whether to disable cleaning of the database.

true

spring.flyway.clean-on-validation-error

Whether to automatically call clean when a validation error occurs.

false

spring.flyway.connect-retries

Maximum number of retries when attempting to connect to the database.

0

spring.flyway.connect-retries-interval

Maximum time between retries when attempting to connect to the database. If a duration suffix is not specified, seconds will be used.

120s

spring.flyway.create-schemas

Whether Flyway should attempt to create the schemas specified in the schemas property.

true

spring.flyway.default-schema

Default schema name managed by Flyway (case-sensitive).

spring.flyway.detect-encoding

Whether to attempt to automatically detect SQL migration file encoding. Requires Flyway Teams.

spring.flyway.driver-class-name

Fully qualified name of the JDBC driver. Auto-detected based on the URL by default.

spring.flyway.enabled

Whether to enable flyway.

true

spring.flyway.encoding

Encoding of SQL migrations.

UTF-8

spring.flyway.error-overrides

Rules for the built-in error handling to override specific SQL states and error codes. Requires Flyway Teams.

spring.flyway.execute-in-transaction

Whether Flyway should execute SQL within a transaction.

true

spring.flyway.fail-on-missing-locations

Whether to fail if a location of migration scripts doesn't exist.

false

spring.flyway.group

Whether to group all pending migrations together in the same transaction when applying them.

false

spring.flyway.ignore-migration-patterns

Ignore migrations that match this comma-separated list of patterns when validating migrations. Requires Flyway Teams.

spring.flyway.init-sqls

SQL statements to execute to initialize a connection immediately after obtaining it.

spring.flyway.installed-by

Username recorded in the schema history table as having applied the migration.

spring.flyway.jdbc-properties.*

Properties to pass to the JDBC driver. Requires Flyway Teams.

spring.flyway.kerberos-config-file

Path of the Kerberos config file. Requires Flyway Teams.

spring.flyway.license-key

Licence key for Flyway Teams.

spring.flyway.locations

Locations of migrations scripts. Can contain the special "{vendor}" placeholder to use vendor-specific locations.

[classpath:db/migration]

spring.flyway.lock-retry-count

Maximum number of retries when trying to obtain a lock.

50

spring.flyway.loggers

Loggers Flyway should use.

[slf4j]

spring.flyway.mixed

Whether to allow mixing transactional and non-transactional statements within the same migration.

false

spring.flyway.oracle-kerberos-cache-file

Path of the Oracle Kerberos cache file. Requires Flyway Teams.

spring.flyway.oracle-sqlplus

Whether to enable support for Oracle SQL*Plus commands. Requires Flyway Teams.

spring.flyway.oracle-sqlplus-warn

Whether to issue a warning rather than an error when a not-yet-supported Oracle SQL*Plus statement is encountered. Requires Flyway Teams.

spring.flyway.oracle-wallet-location

Location of the Oracle Wallet, used to sign in to the database automatically. Requires Flyway Teams.

spring.flyway.out-of-order

Whether to allow migrations to be run out of order.

false

spring.flyway.output-query-results

Whether Flyway should output a table with the results of queries when executing migrations. Requires Flyway Teams.

spring.flyway.password

Login password of the database to migrate.

spring.flyway.placeholder-prefix

Prefix of placeholders in migration scripts.

${

spring.flyway.placeholder-replacement

Perform placeholder replacement in migration scripts.

true

spring.flyway.placeholder-separator

Separator of default placeholders.

:

spring.flyway.placeholder-suffix

Suffix of placeholders in migration scripts.

}

spring.flyway.placeholders.*

Placeholders and their replacements to apply to sql migration scripts.

spring.flyway.repeatable-sql-migration-prefix

File name prefix for repeatable SQL migrations.

R

spring.flyway.schemas

Scheme names managed by Flyway (case-sensitive).

spring.flyway.script-placeholder-prefix

Prefix of placeholders in migration scripts.

FP__

spring.flyway.script-placeholder-suffix

Suffix of placeholders in migration scripts.

__

spring.flyway.skip-default-callbacks

Whether to skip default callbacks. If true, only custom callbacks are used.

false

spring.flyway.skip-default-resolvers

Whether to skip default resolvers. If true, only custom resolvers are used.

false

spring.flyway.skip-executing-migrations

Whether Flyway should skip executing the contents of the migrations and only update the schema history table. Requires Flyway teams.

spring.flyway.sql-migration-prefix

File name prefix for SQL migrations.

V

spring.flyway.sql-migration-separator

File name separator for SQL migrations.

__

spring.flyway.sql-migration-suffixes

File name suffix for SQL migrations.

[.sql]

spring.flyway.sql-server-kerberos-login-file

Path to the SQL Server Kerberos login file. Requires Flyway Teams.

spring.flyway.stream

Whether to stream SQL migrations when executing them. Requires Flyway Teams.

spring.flyway.table

Name of the schema history table that will be used by Flyway.

flyway_schema_history

spring.flyway.tablespace

Tablespace in which the schema history table is created. Ignored when using a database that does not support tablespaces. Defaults to the default tablespace of the connection used by Flyway.

spring.flyway.target

Target version up to which migrations should be considered.

latest

spring.flyway.url

JDBC url of the database to migrate. If not set, the primary configured data source is used.

spring.flyway.user

Login user of the database to migrate.

spring.flyway.validate-migration-naming

Whether to validate migrations and callbacks whose scripts do not obey the correct naming convention.

false

spring.flyway.validate-on-migrate

Whether to automatically call validate when performing a migration.

true

spring.liquibase.change-log

Change log configuration path.

classpath:/db/changelog/db.changelog-master.yaml

spring.liquibase.clear-checksums

Whether to clear all checksums in the current changelog, so they will be recalculated upon the next update.

false

spring.liquibase.contexts

Comma-separated list of runtime contexts to use.

spring.liquibase.database-change-log-lock-table

Name of table to use for tracking concurrent Liquibase usage.

DATABASECHANGELOGLOCK

spring.liquibase.database-change-log-table

Name of table to use for tracking change history.

DATABASECHANGELOG

spring.liquibase.default-schema

Default database schema.

spring.liquibase.driver-class-name

Fully qualified name of the JDBC driver. Auto-detected based on the URL by default.

spring.liquibase.drop-first

Whether to first drop the database schema.

false

spring.liquibase.enabled

Whether to enable Liquibase support.

true

spring.liquibase.label-filter

Comma-separated list of runtime labels to use.

spring.liquibase.liquibase-schema

Schema to use for Liquibase objects.

spring.liquibase.liquibase-tablespace

Tablespace to use for Liquibase objects.

spring.liquibase.parameters.*

Change log parameters.

spring.liquibase.password

Login password of the database to migrate.

spring.liquibase.rollback-file

File to which rollback SQL is written when an update is performed.

spring.liquibase.tag

Tag name to use when applying database changes. Can also be used with "rollbackFile" to generate a rollback script for all existing changes associated with that tag.

spring.liquibase.test-rollback-on-update

Whether rollback should be tested before update is performed.

false

spring.liquibase.url

JDBC URL of the database to migrate. If not set, the primary configured data source is used.

spring.liquibase.user

Login user of the database to migrate.

spring.sql.init.continue-on-error

Whether initialization should continue when an error occurs.

false

spring.sql.init.data-locations

Locations of the data (DML) scripts to apply to the database.

spring.sql.init.encoding

Encoding of the schema and data scripts.

spring.sql.init.mode

Mode to apply when determining whether initialization should be performed.

embedded

spring.sql.init.password

Password of the database to use when applying initialization scripts (if different).

spring.sql.init.platform

Platform to use in the default schema or data script locations, schema-${platform}.sql and data-${platform}.sql.

all

spring.sql.init.schema-locations

Locations of the schema (DDL) scripts to apply to the database.

spring.sql.init.separator

Statement separator in the schema and data scripts.

;

spring.sql.init.username

Username of the database to use when applying initialization scripts (if different).


```














