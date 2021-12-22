# Java 中的 CopyOnWriteArrayList removeAll()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-removeall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearraylist-removeall-method-in-java-with-examples/)

[copy onwriterarraylist 类](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)中的 **removeAll()** 方法，用于从调用的 CopyOnArrayList 对象中移除指定集合中包含的所有元素。

**语法:**

```java
public boolean removeAll(Collection collection)

```

**参数:**该方法只接受单个参数**集合**，该集合将从调用对象中移除。

**返回值:**该方法返回一个**布尔值**。如果删除操作成功，则返回 true。

**异常:**该方法抛出以下异常:

*   **ClassCastException:** 如果此列表的某个元素的类与指定的集合不兼容。
*   **NullPointRexception:**如果指定的集合为空，或者如果此列表包含空元素，并且指定的集合不允许空元素。

以下示例说明了 removeAll()方法:

**例 1:**

```java
// Java program to demonstrate removeAll() method

import java.util.ArrayList;
import java.util.concurrent.CopyOnWriteArrayList;

public class Demo {

    public static void main(String args[])
    {

        // Get the CopyOnWriteArrayList
        CopyOnWriteArrayList<String> wishlist
            = new CopyOnWriteArrayList<>();

        // Add the elements in the CopyOnWriteArrayList
        wishlist.add("TV");
        wishlist.add("computer");
        wishlist.add("play station");
        wishlist.add("mobile");
        wishlist.add("smart watch");

        // Print the CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: \n"
                           + wishlist);

        // Get the collection to be removed
        ArrayList<String> checkList
            = new ArrayList<>();

        checkList.add("play station");
        checkList.add("TV");
        checkList.add("mobile");

        System.out.println("\nCollection to be removed:\n"
                           + checkList);

        // Remove the collection from CopyOnWriteArrayList
        // using removeAll() method
        wishlist.removeAll(checkList);

        // Print the CopyOnWriteArrayList after removal
        System.out.println("\nAfter removal of collection"
                           + " from CopyOnWriteArrayList:\n"
                           + wishlist);
    }
}
```

**Output:**

```java
CopyOnWriteArrayList: 
[TV, computer, play station, mobile, smart watch]

Collection to be removed:
[play station, TV, mobile]

After removal of collection from CopyOnWriteArrayList:
[computer, smart watch]

```

**示例 2:** 显示空指针异常

```java
// Java program to demonstrate removeAll() method

import java.util.ArrayList;
import java.util.concurrent.CopyOnWriteArrayList;

public class Demo {

    public static void main(String args[])
    {

        // Get the CopyOnWriteArrayList
        CopyOnWriteArrayList<String> wishlist
            = new CopyOnWriteArrayList<>();

        // Add the elements in the CopyOnWriteArrayList
        wishlist.add("TV");
        wishlist.add("computer");
        wishlist.add("play station");
        wishlist.add("mobile");
        wishlist.add("smart watch");

        // Print the CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: \n"
                           + wishlist);

        // Get the collection to be removed
        ArrayList<String> checkList
            = null;
        System.out.println("\nCollection to be removed: "
                           + checkList);

        try {

            // Remove the collection from CopyOnWriteArrayList
            // using removeAll() method
            wishlist.removeAll(checkList);
        }
        catch (Exception e) {

            // Print the Exception
            System.out.println("\nException thrown"
                               + " while removing null "
                               + "from the CopyOnWriteArrayList: \n"
                               + e);
        }
    }
}
```

**Output:**

```java
CopyOnWriteArrayList: 
[TV, computer, play station, mobile, smart watch]

Collection to be removed: null

Exception thrown while removing null from the CopyOnWriteArrayList: 
java.lang.NullPointerException

```