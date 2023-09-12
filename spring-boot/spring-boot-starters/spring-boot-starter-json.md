# spring-boot-starter-json

```
# 构件
org.springframework.boot:spring-boot-starter-json:3.1.3

# 依赖：compile
org.springframework.boot:spring-boot-starter:3.1.3
org.springframework:spring-web:6.0.11
com.fasterxml.jackson.core:jackson-databind:2.15.2
com.fasterxml.jackson.datatype:jackson-datatype-jdk8:2.15.2
com.fasterxml.jackson.datatype:jackson-datatype-jsr310:2.15.2
com.fasterxml.jackson.module:jackson-module-parameter-names:2.15.2
```

## 4. JSON Properties

```
spring.gson.date-format

Format to use when serializing Date objects.

spring.gson.disable-html-escaping

Whether to disable the escaping of HTML characters such as '<', '>', etc.

spring.gson.disable-inner-class-serialization

Whether to exclude inner classes during serialization.

spring.gson.enable-complex-map-key-serialization

Whether to enable serialization of complex map keys (i.e. non-primitives).

spring.gson.exclude-fields-without-expose-annotation

Whether to exclude all fields from consideration for serialization or deserialization that do not have the "Expose" annotation.

spring.gson.field-naming-policy

Naming policy that should be applied to an object's field during serialization and deserialization.

spring.gson.generate-non-executable-json

Whether to generate non-executable JSON by prefixing the output with some special text.

spring.gson.lenient

Whether to be lenient about parsing JSON that doesn't conform to RFC 4627.

spring.gson.long-serialization-policy

Serialization policy for Long and long types.

spring.gson.pretty-printing

Whether to output serialized JSON that fits in a page for pretty printing.

spring.gson.serialize-nulls

Whether to serialize null fields.

spring.jackson.constructor-detector

Strategy to use to auto-detect constructor, and in particular behavior with single-argument constructors.

default

spring.jackson.date-format

Date format string or a fully-qualified date format class name. For instance, 'yyyy-MM-dd HH:mm:ss'.

spring.jackson.default-leniency

Global default setting (if any) for leniency.

spring.jackson.default-property-inclusion

Controls the inclusion of properties during serialization. Configured with one of the values in Jackson's JsonInclude.Include enumeration.

spring.jackson.deserialization.*

Jackson on/off features that affect the way Java objects are deserialized.

spring.jackson.generator.*

Jackson on/off features for generators.

spring.jackson.locale

Locale used for formatting.

spring.jackson.mapper.*

Jackson general purpose on/off features.

spring.jackson.parser.*

Jackson on/off features for parsers.

spring.jackson.property-naming-strategy

One of the constants on Jackson's PropertyNamingStrategies. Can also be a fully-qualified class name of a PropertyNamingStrategy implementation.

spring.jackson.serialization.*

Jackson on/off features that affect the way Java objects are serialized.

spring.jackson.time-zone

Time zone used when formatting dates. For instance, "America/Los_Angeles" or "GMT+10".

spring.jackson.visibility.*

Jackson visibility thresholds that can be used to limit which methods (and fields) are auto-detected.


```
