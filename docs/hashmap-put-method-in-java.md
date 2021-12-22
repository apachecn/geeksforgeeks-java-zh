# HashMap 把()方法放到 Java 中

> 原文:[https://www.geeksforgeeks.org/hashmap-put-method-in-java/](https://www.geeksforgeeks.org/hashmap-put-method-in-java/)

HashMap 的 java.util.HashMap.put()方法用于将映射插入到映射中。这意味着我们可以将特定的键及其映射到的值插入到特定的映射中。如果传递了一个现有的键，那么前一个值将被新值替换。如果传递了一个新的对，那么该对将作为一个整体被插入。
**语法:**

```
Hash_Map.put(*key, value*)
```

**参数:**该方法采用两个参数，都是 HashMap 的对象类型。

*   *关键:*这是指需要插入到 Map 中进行映射的关键元素。
*   *值:*这是指上述键将映射到的值。

**返回值:**如果传递了一个现有的键，则返回前一个值。如果传递了新的对，则返回空值。
以下程序用于说明 java.util.HashMap.put()方法:
**程序 1:** 在传递现有密钥时的工作情况。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate the put() method
import java.util.*;

public class Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty HashMap
        HashMap<Integer, String> hash_map = new HashMap<Integer, String>();

        // Mapping string values to int keys
        hash_map.put(10, "Geeks");
        hash_map.put(15, "4");
        hash_map.put(20, "Geeks");
        hash_map.put(25, "Welcomes");
        hash_map.put(30, "You");

        // Displaying the HashMap
        System.out.println("Initial Mappings are: " + hash_map);

        // Inserting existing key along with new value
        String returned_value = (String)hash_map.put(20, "All");

        // Verifying the returned value
        System.out.println("Returned value is: " + returned_value);

        // Displaying the new map
        System.out.println("New map is: " + hash_map);
    }
}
```

**Output:** 

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Returned value is: Geeks
New map is: {20=All, 25=Welcomes, 10=Geeks, 30=You, 15=4}
```