# YAML(。yml)和。Java 中的属性文件

> 原文:[https://www . geesforgeks . org/difference-YAML-yml-and-properties-file-in-Java-spring boot/](https://www.geeksforgeeks.org/difference-between-yaml-yml-and-properties-file-in-java-springboot/)

这些文件具有启动和运行应用程序所需的不同配置属性，例如与数据库连接、凭据是什么、应用程序将在哪个端口上运行等。

**<u>YAML(。yml)文件:</u>T3】YAML 是配置语言。像 Python、Ruby、Java 这样的语言在开发应用程序时大量使用它来配置各种属性。**

如果您曾经使用过弹性搜索实例和 MongoDB 数据库，这两个应用程序都使用 YAML()。yml)作为它们的默认配置格式。

**示例:**

```java
#.yml file

some_key:value
some_number:9
some_bool:true
```

**筑巢:**对于筑巢来说。yml 文件支持使用空格的层次结构。

```java
# .yml file

somemap:
  key:value #use space not tab
  number:9

#inline format                         
  map2: {bool=true, date=2016-01-01}
```

**让我们在这样的文件中定义一个列表:**作为其规范的一部分，YAML 支持该列表。

```java
#.properties file

# A List
numbers[0] = one
numbers[1] = two

# Inline List
numbers = one, two
```

**<u>。属性文件:</u>** 此文件扩展名用于配置应用程序。这些在像 Java 等技术中被用作属性资源包文件。

**示例:**

```java
#.properties file

some_key = value
some_number = 9
some_bool = true
```

**筑巢:**对于筑巢来说。属性文件支持点(。)符号。中的内联格式。yml 文件与 JSON 非常相似

```java
#.properties file

somemap.key = value 
somemap.number = 9

map2.bool = true
map2.date = 2016-01-01
```

**我们在这样的文件中定义一个列表:**。属性文件不支持列表，但是 spring 使用数组作为约定来定义。属性文件。

```java
#.yml file

numbers:
  - one # use a dash followed by space
  - two

# Inline List
numbers:[one, two]
```

**<u>差异表:</u>**

<figure class="table">

| YAML(..(yml) | 。性能 |
| --- | --- |
| 规格可以在[这里](https://yaml.org/spec/)找到 | 它实际上没有规格。它最接近规范的东西实际上是 javadoc。 |
| 人类可读的(两者在人类可读性方面都做得很好) | 人类可读的 |
| 支持键/值，基本上是映射、列表和标量类型(int、string 等)。) | 支持键/值，但不支持超出字符串的值 |
| 它的用法在很多语言中都很普遍，比如 Python、Ruby 和 Java | 它主要用于 java |
| 分级结构 | 非等级结构 |
| Spring Framework 不支持带有的@PropertySources。yml 文件 | 支持带有的@PropertySources。属性文件 |
| 如果您使用的是弹簧轮廓，则可以在一个轮廓中包含多个轮廓。yml 文件 | 每个配置文件需要一个单独的。属性文件 |
| 从检索值时。yml 文件我们得到的值是相应的类型(int、string 等)。)处于配置中 | 而在。不管配置中的实际值类型是什么，我们都会得到字符串 |

</figure>

**该用什么。属性或。yml 文件？**

严格来说，。yml 文件比。属性文件，因为它具有类型安全性、层次结构和支持列表，但是如果您正在使用 spring，spring 有许多约定和类型转换，允许您有效地获得 YAML 为您提供的所有这些相同的功能。

使用 YAML 的一个好处是。yml)文件是如果您正在使用多个读取相同配置文件的应用程序。您可能会看到其他语言对 YAML 的更好支持。yml)与. properties 相反。