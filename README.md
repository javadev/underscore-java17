underscore-java11
=================

[![Maven Central](https://img.shields.io/maven-central/v/com.github.javadev/underscore11.svg)](http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22com.github.javadev%22%20AND%20a%3A%22underscore11%22)
[![MIT License](http://img.shields.io/badge/license-MIT-green.svg) ](https://github.com/javadev/underscore-java11/blob/master/LICENSE.txt)
[![Build Status](https://travis-ci.com/javadev/underscore-java11.svg?branch=main)](https://travis-ci.com/javadev/underscore-java11)
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
    <version>1.24</version>
  </dependency>
  ...
</dependencies>
```

Gradle:

```groovy
compile 'com.github.javadev:underscore11:1.24'
```

Underscore-java is a java port of [Underscore.js](http://underscorejs.org/).

### Usage

```java
U.of(/* array | list | set | map | anything based on Iterable interface */)
    .filter(..)
    .map(..)
    ...
    .sortWith()
    .forEach(..);
U.of(value1, value2, value3)...
U.range(0, 10)...

U.of(1, 2, 3) // or java.util.Arrays.asList(1, 2, 3) or new Integer[] {1, 2, 3}
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

U.xmlToJson("<a attr=\"c\"><b>data</b></a>");
    // {
    //   "a": {
    //     "-attr": "c",
    //     "b": "data"
    //   },
    //   "#omit-xml-declaration": "yes"
    // }

U.jsonToXml("{\"a\":{\"-attr\":\"c\",\"b\":\"data\"}}");
    // <?xml version="1.0" encoding="UTF-8"?>
    // <a attr="c">
    //   <b>data</b>
    // </a>

U.Builder builder = U.objectBuilder()
    .add("firstName", "John")
    .add("lastName", "Smith")
    .add("age", 25)
    .add("address", U.arrayBuilder()
        .add(U.objectBuilder()
            .add("streetAddress", "21 2nd Street")
            .add("city", "New York")
            .add("state", "NY")
            .add("postalCode", "10021")))
    .add("phoneNumber", U.arrayBuilder()
        .add(U.objectBuilder()
            .add("type", "home")
            .add("number", "212 555-1234"))
        .add(U.objectBuilder()
            .add("type", "fax")
            .add("number", "646 555-4567")));
System.out.println(builder.toJson());
System.out.println(builder.toXml());
```
```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25,
  "address": [
    {
      "streetAddress": "21 2nd Street",
      "city": "New York",
      "state": "NY",
      "postalCode": "10021"
    }
  ],
  "phoneNumber": [
    {
      "type": "home",
      "number": "212 555-1234"
    },
    {
      "type": "fax",
      "number": "646 555-4567"
    }
  ]
}
```
```xml
<?xml version="1.0" encoding="UTF-8"?>
<root>
  <firstName>John</firstName>
  <lastName>Smith</lastName>
  <age number="true">25</age>
  <address array="true">
    <streetAddress>21 2nd Street</streetAddress>
    <city>New York</city>
    <state>NY</state>
    <postalCode>10021</postalCode>
  </address>
  <phoneNumber>
    <type>home</type>
    <number>212 555-1234</number>
  </phoneNumber>
  <phoneNumber>
    <type>fax</type>
    <number>646 555-4567</number>
  </phoneNumber>
</root>
```

In addition to porting Underscore's functionality, Underscore-java includes matching unit tests.

For docs, license, tests, and downloads, see:
https://javadev.github.io/underscore-java

Thanks to Jeremy Ashkenas and all contributors to Underscore.js.
