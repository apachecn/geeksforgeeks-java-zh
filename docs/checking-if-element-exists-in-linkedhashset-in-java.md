# 检查元素是否存在于 Java 的 LinkedHashSet 中

> 原文:[https://www . geesforgeks . org/checking-if-element-exists-in-link edhashset-in-Java/](https://www.geeksforgeeks.org/checking-if-element-exists-in-linkedhashset-in-java/)

***Java . util . LinkedHashset . contains()方法*** 用于检查特定元素是否存在于 [LinkedHashSet](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 中。所以它基本上是用来检查一个集合是否包含任何特定的元素。如果在 LinkedHashSet 对象中找到指定的元素，则包含 LinkedHashSet 类的方法返回 true。

**例:**

```java
Given List: [1, 2, 3, 4]

Input : FirstSearch = 1, SecondSearch = 6
Output: True False
```

**语法:**

```java
Hash_Set.contains(Object element)
```

**返回类型:**如果在中找到元素，则返回 true，否则返回 false。

**参数**:参数元素的类型为 LinkedHashSet。这是需要测试的元素，无论它是否存在于集合中。

**示例:**

## Java

```java
// Checking if element exists in LinkedHashSet in Java
import java.util.LinkedHashSet;
public class LinkedHashSetContainsExample {

    public static void main(String[] args)
    {

        LinkedHashSet<String> lhSetColors
            = new LinkedHashSet<String>();

        lhSetColors.add("red");
        lhSetColors.add("green");
        lhSetColors.add("blue");

        /*
         * To check if the LinkedHashSet contains the
         * element, use the contains method.
         */

        // this will return true as the "red" element exists
        System.out.println(lhSetColors.contains("red"));

        // this will return true as the "white" element does
        // not exists
        System.out.println(lhSetColors.contains("white"));
    }
}
```

**输出**

```java
true
false
```