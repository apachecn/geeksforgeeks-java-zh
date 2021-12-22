# 如何在 Java 中检查 LinkedHashMap 是否包含值？

> 原文:[https://www . geesforgeks . org/如何检查 if-link edhashmap-contains-a-value-in-Java/](https://www.geeksforgeeks.org/how-to-check-if-linkedhashmap-contains-a-value-in-java/)

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是 Java 中的预定义类，类似于 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) ，包含键及其各自的值与 HashMap 不同，在 LinkedHashMap 中插入顺序被保留。任务是检查 LinkedHashMap 在 java 中是否包含任何值。为了检查，我们必须迭代我们的 LinkedHashMap，如果我们得到任何值，我们返回 true。

**例** :

```
Input : Key- 2 : Value-6
    Key- 4 : Value-1
    Key- 5 : Value-10
    value to check - 2

Output : False

Input : Key- 1 : Value-15
    Key- 3 : Value-12
    Key- 5 : Value-9
    Key- 6 : Value-11
    Value to check - 11

Output : True
```

**方法 1:(使用 entrySet()方法)**

使用 For-each 循环遍历 LinkedHashMap。create check()函数检查 LinkedHasMap 或 nor 中是否存在任何值。如果我们得到任何返回值 true，则迭代 LinkedHashMap，否则返回 false。

**伪代码:**

```
for (Map.Entry<Integer, Integer> it : lhm.entrySet()) {
       if (it.getValue() != null)
                return true;
}
```

**语法:**

```
linked_hash_map.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个集合，该集合具有与 LinkedHashMap 相同的元素。

**示例:**

## Java

```
// Java program to check if LinkedHashMap contains a
// particular value

import java.util.*;
import java.io.*;

class GFG {

    public static boolean
    check(LinkedHashMap<Integer, Integer> lhm, int value)
    {
        // iterate the map and find
        for (Map.Entry<Integer, Integer> it :
             lhm.entrySet()) {
            if (it.getValue() == value)
                return true;
        }

        return false;
    }
    public static void main(String[] args)
    {
        // create a linked Hashmap
        LinkedHashMap<Integer, Integer> LHM
            = new LinkedHashMap<>();

        // add elements
        LHM.put(2, 6);
        LHM.put(4, 1);
        LHM.put(5, 10);
        int value = 2;

        // check if has a value 2
        if (check(LHM, value))
            System.out.println("True");
        else
            System.out.println("False");
    }
}
```

**输出**

```
False
```

**时间复杂度** : O(n)。

**方法 2:(使用 containsValue()方法)**

这个方法是解决我们问题的最佳方法。在上面的方法中，我们遍历我们的 LinkedHashMap。在这种方法中，我们直接使用预定义的函数来检查我们的值。

**算法**

> 使用函数 containValue()来查找我们的值是否存在于我们的 LinkedHashMap 中。
> 
> Psuedo 代码:
> 
> LHM . Contains VaLue(Val)
> 
> 这里，
> 
> Val 是要检查的值。
> 
> LHM 是我们 LinkedHashMap 的名字。

**语法:**

```
Linked_Hash_Map.containsValue(*Object Value*)
```

**参数:**该方法只取一个对象类型的参数*值*，并引用其映射应该由映射内任何键检查的值。

**返回值:**如果检测到值的映射，则该方法返回布尔值 true，否则返回 false。

**示例:**

## Java

```
// Java program to check if LinkedHashMap contains a
// particular value

import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
          // create a linked hashmap
        LinkedHashMap<Integer, Integer> LHM
            = new LinkedHashMap<>();

          // add mappings
        LHM.put(2, 6);
        LHM.put(4, 1);
        LHM.put(5, 10);
        int value = 2;

          // check if it has a value
        if (LHM.containsValue(value))
            System.out.println("True");
        else
            System.out.println("False");
    }
}
```

**输出**

```
False
```

**时间复杂度:** O(1)。