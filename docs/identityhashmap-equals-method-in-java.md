# Java 中的 IdentityHashMap 等于()方法

> 原文:[https://www . geesforgeks . org/identityhashmap-equals-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-equals-method-in-java/)

java 中的 Java . util . identity hashmap . equals()方法用于检查两个映射之间的相等性。它验证作为参数传递的一个映射的元素是否等于这个映射的元素。

**语法:**

```
ihashmap1.equals(*ihashmap2*)
```

**参数:**该方法接受一个身份哈希映射类型的参数 *ihashmap2* ，并引用要用该哈希映射检查其相等性的映射。

**返回值:**如果两个对象映射相等，则方法返回真，否则返回假。

下面的程序说明了 Java . util . identity hashmap . equals()方法的工作:
**程序 1:**

```
// Java code to illustrate the equals() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        IdentityHashMap<Integer, String> identity_hash1 = 
                   new IdentityHashMap<Integer, String>();
        IdentityHashMap<Integer, String> identity_hash2 = 
                   new IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        identity_hash1.put(10, "Geeks");
        identity_hash1.put(15, "4");
        identity_hash1.put(20, "Geeks");
        identity_hash1.put(25, "Welcomes");
        identity_hash1.put(30, "You");

        // Mapping string values to int keys
        identity_hash2.put(10, "Geeks");
        identity_hash2.put(15, "4");
        identity_hash2.put(20, "Geeks");
        identity_hash2.put(25, "Welcomes");
        identity_hash2.put(30, "You");

        // Displaying the IdentityHashMap
        System.out.println("First Map: "
                        + identity_hash1);

        // Displaying the final IdentityHashMap
        System.out.println("Second Map: "
                        + identity_hash2);

        // Displaying the equality
        System.out.println("Equality: "+
                  identity_hash1.equals(identity_hash2));
    }
}
```

**Output:**

```
First Map: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
Second Map: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
Equality: true

```

**程序 2:**

```
// Java code to illustrate the equals() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        IdentityHashMap<Integer, String> identity_hash1 = 
                   new IdentityHashMap<Integer, String>();
        IdentityHashMap<Integer, String> identity_hash2 = 
                   new IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        identity_hash1.put(10, "Geeks");
        identity_hash1.put(15, "4");
        identity_hash1.put(20, "Geeks");
        identity_hash1.put(25, "Welcomes");
        identity_hash1.put(30, "You");

        // Mapping string values to int keys
        identity_hash2.put(10, "Geeks");
        identity_hash2.put(15, "4");
        identity_hash2.put(20, "Geek");
        identity_hash2.put(25, "Welcomes");
        identity_hash2.put(30, "You");

        // Displaying the IdentityHashMap
        System.out.println("First Map: "
                        + identity_hash1);

        // Displaying the final IdentityHashMap
        System.out.println("Second Map: "
                        + identity_hash2);

        // Displaying the equality
        System.out.println("Equality: "+
                  identity_hash1.equals(identity_hash2));
    }
}
```

**Output:**

```
First Map: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
Second Map: {10=Geeks, 30=You, 20=Geek, 25=Welcomes, 15=4}
Equality: false

```