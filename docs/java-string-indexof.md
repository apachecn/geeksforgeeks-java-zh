# Java String IndexOf（）

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-string-index of/

indexOf()方法有四个**变体。本文对它们进行了描述，如下所示:
**1.int 索引 Of()** :此方法**返回****索引**中指定字符的第一个出现的字符串，如果该字符没有出现，则返回-1。** 

```java
**Syntax:**
**int indexOf(char ch )**
**Parameters:**
**ch :** a character.
```

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java code to demonstrate the working
// of String indexOf()
public class Index1 {
public static void main(String args[])
    {

        // Initialising String
        String gfg = new String("Welcome to geeksforgeeks");

        System.out.print("Found g first at position : ");

        // Initial index of 'g' will print
        // prints 11
        System.out.println(gfg.indexOf('g'));
    }
}
```

****Output**

```java
Found g first at position : 11
```** 

****2。int indexOf(char ch，int strt ) :** 此方法**返回**的第一个**出现的字符串内的索引，在指定的索引处开始搜索，如果该字符没有出现，则返回-1。**** 

```java
**Syntax:**
**int indexOf(char ch, int strt)**
**Parameters:**
**ch** :a character.
**strt** : the index to start the search from.
```

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java code to demonstrate the working
// of String indexOf(char ch, int strt)
public class Index2 {
public static void main(String args[])
    {

        // Initialising String
        String gfg = new String("Welcome to geeksforgeeks");

        System.out.print("Found g after 13th index at position : ");

        // 2nd index of 'g' will print
        // prints 19
        System.out.println(gfg.indexOf('g', 13));
    }
}
```

****Output****

```java
Found g after 13th index at position : 19
```