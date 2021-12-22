# Java 中的映射值()方法示例

> 原文:[https://www . geesforgeks . org/map-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-values-method-in-java-with-examples/)

Map Values()方法返回此地图中包含的值的集合视图。收藏以地图为后盾，因此地图的变化会反映在收藏中，反之亦然。

**语法:**

> map.values()

**参数:**该方法不取任何参数。

**返回值:**返回地图中所有值的集合视图。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// use of Map.Values() Method
import java.util.*;

public class GfG {

      // Main Method
    public static void main(String[] args)
    {
        // Initializing a Map of type HashMap 
        Map<Integer, String> map
            = new HashMap<Integer, String>();

        map.put(12345, "student 1");
        map.put(22345, "student 2");
        map.put(323456, "student 3");
        map.put(32496, "student 4");
        map.put(32446, "student 5");
        map.put(32456, "student 6");

        System.out.println(map.values());
    }
}
```

**输出:**

```java
[student 4, student 3, student 6, student 1, student 2, student 5]
```

如您所见，上面示例的输出是返回一个值的集合视图。因此，地图中的任何更改都会自动反映在集合视图中。因此，始终将集合的泛型与映射的值的泛型相同，否则会产生错误。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// use of Map.Values() Method
import java.util.*;

public class GfG {

      // Main Method
    public static void main(String[] args)
    {
        // Initializing a Map of type HashMap 
        Map<Integer, String> map
            = new HashMap<Integer, String>();

        map.put(12345, "student 1");
        map.put(22345, "student 2");
        map.put(323456, "student 3");
        map.put(32496, "student 4");
        map.put(32446, "student 5");
        map.put(32456, "student 6");
        Collection<String> collectionValues = map.values();

        System.out.println("<------OutPut before modification------>\n");
        for(String s: collectionValues){
            System.out.println(s);
        }

        map.put(3245596, "student 7");
        System.out.println("\n<------OutPut after modification------>\n");
        for(String s: collectionValues){
            System.out.println(s);
        }
    }
}
```

**输出:**

```java
<------OutPut before modification------>

student 4
student 3
student 6
student 1
student 2
student 5

<------OutPut after modification------>

student 4
student 3
student 6
student 1
student 2
student 7
student 5
```