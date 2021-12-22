# 检查 Java HashMap 中是否存在特殊值

> 原文:[https://www . geesforgeks . org/check-if-special-value-exists-in-Java-hashmap/](https://www.geeksforgeeks.org/check-if-particular-value-exists-in-java-hashmap/)

Java **HashMap** 是映射接口的一个实现，它将一个值映射到一个键，这个键本质上形成了一个关联对，在这个关联对中，我们可以基于这个键调用一个值。Java HashMap 提供了很多优势，比如允许 Key 和 Value 有不同的数据类型，这使得这种数据结构更具包容性和通用性。它还允许键和值为空，前提是形成对的两者之一不为空。

**检查 Java HashMap 中特定值存在的不同方法是:**

1.  使用 HashMap 类的内置 containsValue()方法
2.  从哈希表的条目创建一个映射，然后遍历值
3.  从哈希表的值创建一个数组列表，然后遍历这个列表

**方法 1 :**

这种方法提供了一种相当简单有效的方法，使用返回布尔值的 [**containsValue()**](https://www.geeksforgeeks.org/hashmap-containsvalue-method-in-java/) 预定义方法来检查哈希表中是否存在值。

**语法:**

```
Hash_Map.containsValue(*Object Value*)
```

**参数:**该方法只取一个对象类型的参数*值*，并引用其映射应该由映射内任何键检查的值。

**返回值:**如果检测到值的映射，则该方法返回布尔值 true，否则返回 false。

**算法:**

1.  声明一个返回类型为布尔值的方法，以检查该值的存在性。
2.  初始化一个描述键和值的数据类型的散列表。
3.  使用 HashMap 类的内置 put()方法用键值对填充这个 HashMap。
4.  声明一个布尔变量来存储 containsValue()方法的结果。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java program to check if a particular
// value exists in a HashMap

import java.util.*;

class GFG {

    // declaring the method to return
    // if the value is present or not
    // the parameter valueToBeChecked
    // represents the value to be checked
    boolean checkForValue(int valueToBeChecked)
    {

        // initializing the HashMap
        HashMap<String, Integer> hashMap = new HashMap<>();

        // filling the HashMap with
        // key value pairs
        hashMap.put("key1", 1);
        hashMap.put("key2", 2);
        hashMap.put("key3", 3);
        hashMap.put("key4", 4);

        // declaring the variable to store
        // the result
        // calling the containsValue() method
        boolean result
            = hashMap.containsValue(valueToBeChecked);

        // returning the result
        return result;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        // displaying and calling the
        // checkForValue() method
        System.out.println(ob.checkForValue(10));
    }
}
```

**Output**

```
false
```

**方法 2 :**

使用这种方法，我们从包含的哈希表、键和值的所有条目中创建一个映射，然后只迭代值来检查特定的一个。

**算法:**

1.  重复第一种方法中描述的步骤 1 到 3，创建一个 HashMap。
2.  然后使用每个循环的和预先定义的哈希表的[**【entrySet()】**](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/)**方法创建一个地图。**
3.  **使用地图类的预定义 [**getValue()**](https://www.geeksforgeeks.org/java-tuples-getvalue-method/) 方法迭代地图中的值。**
4.  **在每次迭代中，将该值与指定的值进行比较，并返回相应的结果。**

****代码:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// java program to check if a particular
// value exists in HashMap

import java.util.*;

class GFG {

    // declaring the method
    // the parameter is the variable which
    // stores the value to be checked
    boolean checkForValue(int valueToBeChecked)
    {

        // initializing the HashMap
        HashMap<String, Integer> hashMap = new HashMap<>();

        // filling up the HashMap with
        // Key-Value pairs
        hashMap.put("key1", 1);
        hashMap.put("key2", 2);
        hashMap.put("key3", 3);
        hashMap.put("key4", 4);

        // for each loop
        // all the entries in the HashMap are
        // stored in the Map
        for (Map.Entry<String, Integer> mapEntries :
             hashMap.entrySet()) {

            // fetching the values of the HashMap
            // one at a time and comparing with
            // the value to be checked
            if (mapEntries.getValue() == valueToBeChecked)
                return true;
        }
        return false;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        // displaying and calling the
        // checkForValue() method
        System.out.println(ob.checkForValue(2));
    }
}
```

****Output**

```
true
```** 

****进场 3 :****

**在第三种方法中，我们从 HashMap 的值创建一个 ArrayList，并遍历整个列表来检查提到的特定值。**

****算法:****

1.  **重复步骤 1 到 3 创建一个 HashMap。**
2.  **接下来，创建一个与哈希表中的值具有相同数据类型的数组列表。**
3.  **在下一步中，我们声明一个迭代器来遍历整个数组列表，直到找到特定的值。**
4.  **使用 while 循环遍历数组列表中存储的值，并在每次迭代中使用指定的值进行检查。**
5.  **将相应的结果作为布尔值返回。**

****代码:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// java program to check if a particular
// key exists in a HashMap

import java.util.*;

class GFG {

    // declaring the method
    // the parameter specifies the value to
    // be checked
    boolean checkForValue(int valueToBeChecked)
    {

        // initializing the HashMap
        HashMap<String, Integer> hashMap = new HashMap<>();

        // filling up the HashMap with
        // Key-Value pairs
        hashMap.put("key1", 1);
        hashMap.put("key2", 2);
        hashMap.put("key3", 3);
        hashMap.put("key4", 4);

        // declaring an ArrayList of type
        // Integer from the values of the
        // HashMap using the predefined
        // values() method of the HashMap class
        ArrayList<Integer> listOfValues
            = new ArrayList<>(hashMap.values());

        // declaring the iterator
        Iterator<Integer> itr = listOfValues.iterator();

        // iterating through the list
        while (itr.hasNext()) {

            // comparing each value with the
            // one specified
            if (itr.next() == valueToBeChecked)
                return true;
        }
        return false;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        // displaying and calling the
        // checkForValue() method
        System.out.println(ob.checkForValue(0));
    }
}
```

****Output**

```
false
```**