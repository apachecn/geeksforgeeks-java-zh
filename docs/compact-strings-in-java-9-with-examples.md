# 用示例压缩 Java 9 中的字符串

> 原文:[https://www . geesforgeks . org/compact-strings-in-Java-9-with-examples/](https://www.geeksforgeeks.org/compact-strings-in-java-9-with-examples/)

**先决条件** : [弦](https://www.geeksforgeeks.org/strings-in-java/)

**紧凑字符串**是作为 [JDK 9](https://www.geeksforgeeks.org/java-9-features-with-examples/) 的一部分在 [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 中引入的性能增强之一。直到 JDK 8，每当我们创建一个[字符串对象](https://www.geeksforgeeks.org/string-initialization-java-string-literal-vs-string-object/)时，它在内部被表示为 char[]，由字符串对象的字符组成。

**紧凑弦的需求是什么？**

*   直到 JDK 8，java 将 String 对象表示为 char[]，因为 Java 中的每个字符都是 2 字节，因为 Java 内部使用 UTF-16。
*   如果任何字符串在英语中包含一个单词，那么这个字符只能用一个字节来表示，我们不需要每个字符 2 个字节。许多字符需要 2 个字节来表示，但大多数字符只需要 1 个字节，属于 LATIN-1 字符集。因此，内存消耗和性能还有提高的空间。
*   [Java 9](https://www.geeksforgeeks.org/java-9-features-with-examples/) 引入了紧凑字符串的概念。紧凑字符串的主要目的是，每当我们创建一个字符串对象，并且对象内部的字符可以用 1 字节表示，这只是 LATIN-1 表示，那么在内部 java 将创建一个字节[]。在其他情况下，如果任何字符需要 1 个以上的字节来表示，那么每个字符使用 2 个字节来存储，即 UTF-16 表示。
*   这就是 Java 开发人员如何改变字符串的内部实现，即所谓的紧凑字符串，这将提高字符串的内存消耗和性能。

【Java 9 之前的字符串类内部实现 :

## Java 8 或更早版本

```java
import java.io.Serializable;

public final class String
    implements Serializable,
               Comparable<String>,
               CharSequence {

    // The value is used
    // for character storage.
    private final char value[];
}
```