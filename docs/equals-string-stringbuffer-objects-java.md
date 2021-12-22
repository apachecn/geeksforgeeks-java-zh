# 在 Java 的 String 和 StringBuffer 对象上

# 等于()

> 原文:[https://www . geesforgeks . org/equals-string-stringbuffer-objects-Java/](https://www.geeksforgeeks.org/equals-string-stringbuffer-objects-java/)

考虑以下 java 代码:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// This program prints false
class GFG {

  public static void main(String[] args) {
    StringBuffer sb1 = new StringBuffer("GFG");
    StringBuffer sb2 = new StringBuffer("GFG");
    System.out.println(sb1.equals(sb2));
  }
}
```

**Output:** 

```java
false
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// This program prints true
class GFG {

  public static void main(String[] args) {
    String s1 = "GFG";
    String s2 = "GFG";
    System.out.println(s1.equals(s2));
  }
}
```

**Output:** 

```java
true
```

第一个示例的输出为假，第二个示例为真。在第二个例子中，等于()的参数属于[字符串类](https://www.geeksforgeeks.org/string-class-in-java/)，而在第一个例子中，它属于[字符串类](https://www.geeksforgeeks.org/stringbuffer-class-in-java/)。当字符串对象被传递时，字符串被比较。但是当传递 StringBuffer 的对象时，会比较引用，因为 StringBuffer 不会[覆盖 object 类的 equals 方法](https://www.geeksforgeeks.org/overriding-equals-method-in-java/)。
例如，以下第一个程序打印假，第二个打印真。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// This program prints false
class GFG {

  public static void main(String[] args) {
    String s1 = "GFG";
    StringBuffer sb1 = new StringBuffer("GFG");
    System.out.println(s1.equals(sb1));
  }
}
```

**Output:** 

```java
false
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// This program prints true
class GFG {

  public static void main(String[] args) {
    String s1 = "GFG";
    StringBuffer sb1 = new StringBuffer("GFG");
    String s2 = sb1.toString();
    System.out.println(s1.equals(s2));
  }
}
```

**Output:** 

```java
true
```