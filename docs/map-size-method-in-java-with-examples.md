# Java 中的地图大小()方法示例

> 原文:[https://www . geesforgeks . org/map-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-size-method-in-java-with-examples/)

**使用 Java 中的 Map size()方法**获取条目总数，即键值对。因此，当您想要在地图上显示所有条目时，这种方法非常有用。如果地图包含多个 [*整数。MAX _ VALUE*](https://www.geeksforgeeks.org/integer-max_value-and-integer-min_value-in-java-with-examples/)*元素返回  [*整数。MAX_VALUE*](https://www.geeksforgeeks.org/integer-max_value-and-integer-min_value-in-java-with-examples/) 。*

***语法:***

> *int size()；*

***参数:**该方法不取任何参数。*

***返回值:**该方法返回该映射中键值映射的数。*

***示例 1:** 对于非通用输入*

## *Java 语言(一种计算机语言，尤用于创建网站)*

```java
*// Java program to illustrate
// the Map size() Method
import java.util.*;

public class MapSizeExample {

      // Main Method
    public static void main(String[] args)
    {
        Map map = new HashMap();

          // Adding key-values
        map.put(1, "Amit");
        map.put(5, "Rahul");
        map.put(2, "Jai");
        map.put(6, "Amit");

          // using the method
        System.out.println("Size of the map is : "
                           + map.size());
    }
}*
```

***输出:***

```java
*Size of the map is : 4*
```

***示例 2:** 用于通用输入*

## *Java 语言(一种计算机语言，尤用于创建网站)*

```java
*// Java program to illustrate
// the Map size() Method
import java.util.*;

class MapSizeExample {

    // Main Method
    public static void main(String[] args)
    {

        Map<Integer, String> map
            = new HashMap<Integer, String>();

        map.put(1, "one");
        map.put(2, "two");
        map.put(3, "three");
        map.put(4, "four");

        // using the method
        System.out.println("Size of map is :"
                           + map.size());
    }
}*
```

***输出:***

```java
*Size of the map is : 4*
```