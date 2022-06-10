# Demonstration of gradle bug [#20981](https://github.com/gradle/gradle/issues/20981)

pom.xml contains a single quote, which is not escaped using `gradle init`.

pom.xml contents:
```xml
<name>That's it</name>
```

build.gradle contents:

```
description = 'That's it'
```

To reproduce, run the following:

```sh
rm -rf .gradle gradle* *.gradle
gradle init
```


Gradle version:

```
------------------------------------------------------------
Gradle 7.4.2
------------------------------------------------------------

Build time:   2022-03-31 15:25:29 UTC
Revision:     540473b8118064efcc264694cbcaa4b677f61041

Kotlin:       1.5.31
Groovy:       3.0.9
Ant:          Apache Ant(TM) version 1.10.11 compiled on July 10 2021
JVM:          17.0.3 (Eclipse Adoptium 17.0.3+7)
OS:           Mac OS X 12.3.1 x86_64
```
