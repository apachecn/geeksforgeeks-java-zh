# Java String 包含()方法，示例

> 原文:[https://www . geesforgeks . org/Java-string-contains-method-example/](https://www.geeksforgeeks.org/java-string-contains-method-example/)

**Java . lang . string . contains()**方法搜索给定字符串中的字符序列。如果在该字符串中找到字符值序列，则返回 true，否则返回 false。
**执行本方法:**

```
public boolean contains(CharSequence sequence)
{
 return indexOf(sequence.toString()) > -1;
}
```

这里发生字符序列到字符串的转换，然后调用方法的 [**索引。方法**的**索引如果找到字符串则返回 **O** 或**更高的数字**，否则返回 **-1** 。所以，执行后，如果存在字符值序列，contains()方法返回 **true** ，否则返回 **false** 。
**语法:****](https://www.geeksforgeeks.org/java-string-indexof/) 

```
public boolean contains(CharSequence sequence)
Parameter : sequence : This is the sequence of 
characters to be searched.
Exception :
NullPointerException : If seq is null
```

**示例:**检查字符序列是否存在。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working
// contains() method
class Gfg {

    // Driver code
    public static void main(String args[])
    {
        String s1 = "My name is GFG";

        // prints true
        System.out.println(s1.contains("GFG"));

        // prints false
        System.out.println(s1.contains("geeks"));
    }
}
```

**Output:** 

```
true
false
```