# 检查 Java HashMap 中是否存在特定密钥

> 原文:[https://www . geesforgeks . org/check-if-special-key-exists-in-Java-hashmap/](https://www.geeksforgeeks.org/check-if-particular-key-exists-in-java-hashmap/)

[**HashMap**](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 在 Java 中是实现了 Hash Table 数据结构的排序。它由**键和值对**组成，符号表示为< K，V >，其中 K 代表键，V 代表值。它是映射接口的一个实现，并且在分别通过 put 和 get 方法分配和访问元素时提供了恒定的时间性能。它用于形成关联的对，并基于另一对访问或修改一个对。

**有多种方法可以检查特定的键是否存在，如下所述:**

*   Use the built-in **containskey ()** method of HashMap class.
*   Convert the keys of **hashmap into a list** , and then traverse them.
*   Create a map from all the entries of HashMap, and then traverse it.

**方法 1 :**

使用这种方法，我们使用了 HashMap 类的 [**containsKey()**](https://www.geeksforgeeks.org/hashmap-containskey-method-in-java/) 预定义方法，该方法返回一个布尔值。

**语法:**

```
Hash_Map.containsKey(*key_element*)
```

**参数:**该方法只取一个参数 *key_element* ，该参数是指映射应该在地图内部检查的键。

**返回值:**如果检测到键的存在，则该方法返回布尔真，否则返回假

**算法:**

1.  Create a function with a return type of Boolean.
2.  Inside the function, create a new HashMap, specifying the data types of the key and the value respectively.
3.  Use the put () method of HashMap class to populate HashMap with key-value pairs.
4.  Declare a Boolean variable to store the result.
5.  Call the containsKey () method of HashMap class, taking the key to check as the parameter.
6.  Returns a variable.

**代码:**

## Java

```
// java program to check if a particular
// key exists in HashMap

import java.util.*;

class GFG {

    // declaring the method
    // the parameter keyToBeChecked is the
    // key to be checked
    boolean checkForKey(String keyToBeChecked)
    {

        // initializing the hashmap
        HashMap<String, Integer> hashMap =
          new HashMap<>();

        // filling the key - value pairs in hashmap
        hashMap.put("first", 1);
        hashMap.put("second", 2);
        hashMap.put("third", 3);
        hashMap.put("fourth", 4);

        // variable to store the boolean value
        // for result
        boolean result
            = hashMap.containsKey(keyToBeChecked);

        // returning the result
        return result;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        // displaying and calling the checkForKey()
        // method
        System.out.println(ob.checkForKey("fourth"));
    }
}
```

**输出**

```
true
```

**方法 2 :**

我们从 HashMap 的键创建一个 ArrayList，然后遍历它们来检查指定的键是否存在。

**算法:**

1.  Repeat steps 1 to 3 mentioned in the first method.
2.  Next, we use the keySet () predefined method of HashMap class to initialize an ArrayList with the same data type as HashMap key.
3.  Next, we declare an iterator to iterate through the elements of ArrayList created above.
4.  Then, if the specific key matches any element in the array list created above, we will traverse the array list check in each iteration.
5.  Returns the corresponding output.

**代码:**

## Java

```
// java program to check if a particular
// key exists in the HashMap

import java.util.*;

class GFG {

    // declaring the method
    // the parameter keyToBeChecked is
    // the key to be checked
    boolean checkForKey(String keyToBeChecked)
    {

        // initializing the HashMap
        HashMap<String, Integer> hashMap =
          new HashMap<>();

        // filling the key-value pairs
        // in the HashMap
        hashMap.put("first", 1);
        hashMap.put("second", 2);
        hashMap.put("third", 3);
        hashMap.put("fourth", 4);

        // creating an ArrayList from the keys
        ArrayList<String> listOfKeys
            = new ArrayList<>(hashMap.keySet());

        // declaring the iterator
        Iterator<String> itr = listOfKeys.iterator();

        // loop to iterate through the
        // elements of the ArrayList
        while (itr.hasNext()) {

            // condition to check against
            // the specific key
            if (itr.next() == keyToBeChecked)
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
        // checkForKey method
        System.out.println(ob.checkForKey("second"));
    }
}
```

**输出**

```
true
```

**进场 3 :**

我们遍历这些键，检查指定的键是否存在。

**算法:**

1.  Repeat steps 1 to 3 in the first method to create a HashMap.
2.  Use a predefined method of HashMap class for each loop and entrySet () to create an identical Map.
3.  In each iteration of the for loop, use the built-in [getkey ()](https://www.geeksforgeeks.org/java-tuples-getkey-method/#:~:text=The%20getKey()%20method%20in,index%200%20of%20the%20KeyValueClassObject.) method of the Map class to get a key from the Map constructed above.
4.  Compare with the specified key.
5.  Returns true if the key matches any element of the key set, otherwise returns false.

**代码:**

## Java

```
// java program to check if a particular
// key exists in the HashMap

import java.util.*;

class GFG {

    // declaring the method
    // the parameter keyToBeChecked specifies
    // the particular key
    boolean checkForKey(String keyToBeChecked)
    {

        // initializing the HashMap
        HashMap<String, Integer> hashMap = new HashMap<>();

        // filling up the key-value
        // pairs in the HashMap
        hashMap.put("first", 1);
        hashMap.put("second", 2);
        hashMap.put("third", 3);
        hashMap.put("fourth", 4);

        // initializing the for each loop
        // using which the entries of the
        // HashMap are stored in a Set
        for (Map.Entry<String, Integer> mapEntries :
             hashMap.entrySet()) {

            // getting the keys and checking
            // against the specified key
            if (mapEntries.getKey() == keyToBeChecked)
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
        // checkForKey method
        System.out.println(ob.checkForKey("seventh"));
    }
}
```

**输出**

```
false
```