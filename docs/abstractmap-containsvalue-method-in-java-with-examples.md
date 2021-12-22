# 抽象映射包含 Java 中的 Value()方法，示例

> 原文:[https://www . geesforgeks . org/abstract map-contains value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-containsvalue-method-in-java-with-examples/)

**抽象映射**的 **containsValue()** 方法用于检查抽象映射中的单个或多个键是否映射了特定的值。它将值作为参数，如果该值由映射中的任何键映射，则返回真。

**语法:**

```
AbstractMap.containsValue(*Object Value*)
```

**参数:**该方法只取一个对象类型的参数*值*，并引用其映射应该由映射内任何键检查的值。

**返回值:**如果检测到值的映射，则该方法返回布尔值 true，否则返回 false。

下面的程序用来说明 AbstractMap.containsValue()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate
// the containsValue() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<Integer, String>
            abs_map = new HashMap<Integer, String>();

        // Mapping string values to int keys
        abs_map.put(10, "Geeks");
        abs_map.put(15, "4");
        abs_map.put(20, "Geeks");
        abs_map.put(25, "Welcomes");
        abs_map.put(30, "You");

        // Displaying the AbstractMap
        System.out.println("Initial Mappings are: "
                           + abs_map);

        // Checking for the Value 'Geeks'
        System.out.println("Is the value"
                           + " 'Geeks' present? "
                           + abs_map.containsValue("Geeks"));

        // Checking for the Value 'World'
        System.out.println("Is the value"
                           + " 'World' present? "
                           + abs_map.containsValue("World"));
    }
}
```

**输出:**

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Is the value 'Geeks' present? true
Is the value 'World' present? false

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate
// the containsValue() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<String, Integer>
            abs_map = new HashMap<String, Integer>();

        // Mapping int values to string keys
        abs_map.put("Geeks", 10);
        abs_map.put("4", 15);
        abs_map.put("Geeks", 20);
        abs_map.put("Welcomes", 25);
        abs_map.put("You", 30);

        // Displaying the AbstractMap
        System.out.println("Initial Mappings are: "
                           + abs_map);

        // Checking for the Value '10'
        System.out.println("Is the value"
                           + " '10' present? "
                           + abs_map.containsValue(10));

        // Checking for the Value '30'
        System.out.println("Is the value"
                           + " '30' present? "
                           + abs_map.containsValue(30));

        // Checking for the Value '40'
        System.out.println("Is the value"
                           + " '40' present? "
                           + abs_map.containsValue(40));
    }
}
```

**输出:**

```
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
Is the value '10' present? false
Is the value '30' present? true
Is the value '40' present? false

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。