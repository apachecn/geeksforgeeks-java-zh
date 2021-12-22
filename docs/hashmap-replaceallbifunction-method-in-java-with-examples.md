# Java 中 HashMap replaceAll(BiFunction)方法示例

> 原文:[https://www . geeksforgeeks . org/hashmap-replaceallbifunction-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashmap-replaceallbifunction-method-in-java-with-examples/)

**[HashMap 类](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)** 的 **replaceAll(BiFunction)** 方法将每个值替换为对相应值应用给定函数(执行特定操作)的结果。这个过程以同样的方式继续，直到所有条目都被处理完，或者直到函数抛出一个异常。它会重新引发替换函数引发的异常。

**语法:**

```java
default void replaceAll(BiFunction<K, V> function)

```

**参数:**

*   **双功能:**功能对每个条目的值进行操作。

**返回值:**就地替换计算值，该方法不返回任何内容

**异常:**

*   **ClassCastException:** 抛出，表示替换类试图将一个对象强制转换为该映射不可接受类型的子类。
    **示例:**当试图将整数转换为字符串时，字符串不是整数的子类，将引发 ClassCastException。
*   **ConcurrentModificationException:**当对象迭代时试图同时修改或移除该对象时发生。
    **示例:**当其他线程正在迭代集合时，线程(程序内独立的执行路径)不允许修改集合。发生这种情况的原因是上述操作的结果变得未定义。
*   **IllegalArgumentException** (可选) **:** 当替换值的某个属性被传递了非法或不适当的参数，从而阻止它存储在此地图中时。
    **示例:**如果一个方法需要一个非空字符串作为参数，并且输入字符串等于 null，则会引发 IllegalArgumentException。
*   **空指针异常**(可选) **:** 当给定函数指向空值或新值尚未初始化，因此引用空值时，它会抛出一个空指针异常。
    **示例:**调用空对象的实例方法。
*   **取消支持操作异常**(可选) **:** 抛出，表示此映射不支持请求的操作。
    **例:**在 ArraysList 类中如果我们使用 add 或者 remove 方法就会抛出 UnsupportedOperationException。

以下程序说明了合并(键、值、双功能)方法:

**程序 1:**

```java
// Java program to demonstrate
// replaceAll(BiFunction) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a HashMap having some entries
        HashMap<String, Integer>
            map1 = new HashMap<>();
        map1.put("key1", 1);
        map1.put("key2", 2);
        map1.put("key3", 3);
        map1.put("key4", 4);

        // print map details
        System.out.println("HashMap1: "
                           + map1.toString());

        // replace oldValue with square of oldValue
        // using replaceAll method
        map1.replaceAll((key, oldValue)
                            -> oldValue * oldValue);

        // print new mapping
        System.out.println("New HashMap: "
                           + map1);
    }
}
```

**Output:**

```java
HashMap1: {key1=1, key2=2, key3=3, key4=4}
New HashMap: {key1=1, key2=4, key3=9, key4=16}

```

**程序 2:**

```java
// Java program to demonstrate
// replaceAll(BiFunction) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a HashMap having
        // record of the year of birth
        HashMap<String, Integer>
            map1 = new HashMap<>();
        map1.put("Tushar", 2000);
        map1.put("Anushka", 2001);
        map1.put("Sanskriti", 2003);
        map1.put("Anuj", 2002);

        // print map details
        System.out.println("HashMap1: "
                           + map1.toString());

        // replace yearOfBirth with current age
        // using replaceAll method
        map1.replaceAll((key, yearOfBirth)
                            -> 2019 - yearOfBirth);

        // print new mapping
        System.out.println("New HashMap: "
                           + map1);
    }
}
```

**Output:**

```java
HashMap1: {Sanskriti=2003, Anushka=2001, Tushar=2000, Anuj=2002}
New HashMap: {Sanskriti=16, Anushka=18, Tushar=19, Anuj=17}

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/map . html # replace all(Java . util . function . bifunction)](https://docs.oracle.com/javase/10/docs/api/java/util/Map.html#replaceAll(java.util.function.BiFunction))