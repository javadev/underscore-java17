underscore-java11
=================

[![Maven Central](https://img.shields.io/maven-central/v/com.github.javadev/underscore11.svg)](http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22com.github.javadev%22%20AND%20a%3A%22underscore11%22)
[![MIT License](http://img.shields.io/badge/license-MIT-green.svg) ](https://github.com/javadev/underscore-java11/blob/master/LICENSE.txt)
[![Build Status](https://secure.travis-ci.org/javadev/underscore-java11.svg)](https://travis-ci.org/javadev/underscore-java11)
[![codecov](https://codecov.io/gh/javadev/underscore-java11/branch/master/graph/badge.svg)](https://codecov.io/gh/javadev/underscore-java11)
[![Quality Gate](https://sonarcloud.io/api/project_badges/measure?project=javadev_underscore-java11&metric=alert_status)](https://sonarcloud.io/dashboard/index/javadev_underscore-java11)
[![Quality Gate](https://sonarcloud.io/api/project_badges/measure?project=javadev_underscore-java11&metric=sqale_rating)](https://sonarcloud.io/dashboard/index/javadev_underscore-java11)
[![](http://javadoc-badge.appspot.com/com.github.javadev/underscore11.svg?label=JavaDocs)](http://www.javadoc.io/doc/com.github.javadev/underscore11/)
[![Build Status](https://dev.azure.com/javadevazure/underscore-java/_apis/build/status/javadev.underscore-java11)](https://dev.azure.com/javadevazure/underscore-java/_build/latest?definitionId=5)
![Java Version](https://img.shields.io/badge/java-%3E%3D%2011-success)

Requirements
============

Java 11 and later.

## Installation

Include the following in your `pom.xml` for Maven:

```
<dependencies>
  <dependency>
    <groupId>com.github.javadev</groupId>
    <artifactId>underscore11</artifactId>
    <version>1.6</version>
  </dependency>
  ...
</dependencies>
```

Gradle:

```groovy
compile 'com.github.javadev:underscore11:1.6'
```

Underscore-java is a java port of [Underscore.js](http://underscorejs.org/).

### Usage

```java
U.chain(/* array | list | set | map | anything based on Iterable interface */)
    .filter(..)
    .map(..)
    ...
    .sortWith()
    .forEach(..);
U.chain(value1, value2, value3)...
U.range(0, 10)...

U.chain(1, 2, 3) // or java.util.Arrays.asList(1, 2, 3) or new Integer[] {1, 2, 3}
    .filter(v -> v > 1)
    // 2, 3
    .map(v -> v + 1)
    // 3, 4
    .sortWith((a, b) -> b.compareTo(a))
    // 4, 3
    .forEach(System.out::println);
    // 4, 3
    
U.formatXml("<a><b>data</b></a>");
    // <a>
    //    <b>data</b>
    // </a>

U.formatJson("{\"a\":{\"b\":\"data\"}}");
    // {
    //    "a": {
    //      "b": "data"
    //    }
    // }
```

In addition to porting Underscore's functionality, Underscore-java includes matching unit tests.

For docs, license, tests, and downloads, see:
http://javadev.github.io/underscore-java

Thanks to Jeremy Ashkenas and all contributors to Underscore.js.
