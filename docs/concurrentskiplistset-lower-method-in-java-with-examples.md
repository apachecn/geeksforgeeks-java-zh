# Java 中的 ConcurrentSkipListSet lower()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-lower-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistset-lower-method-in-java-with-examples/)

[ConcurrentSkipListSet](https://www.geeksforgeeks.org/concurrentskiplistset-in-java-with-examples/) 的 **lower()** 方法用于返回该集合中存在的最大元素，该元素严格来说是小于指定元素的**。如果集合中没有这样的元素，那么这个函数将返回 null。**

****语法:****

```
public E lower (E e)
```

****参数:**该方法只取一个参数， **e** ，即指定要匹配的值。**

****返回值:**该方法返回**一个值**，该值是集合中存在的最大元素，严格来说小于指定元素。如果不存在这样的元素，那么它将返回空值。**

****异常:**该方法抛出以下异常:**

*   ****ClassCastException** :如果这个集合的某个元素的类与指定的集合不兼容，就会抛出这个。**
*   ****NullPointRexception**:如果指定的集合为空，则抛出。**

**下面的程序说明了 ConcurrentSkipListSet 类的下()函数:**

****程序 1:** 在下面的程序中，指定的元素是 67，我们的集合也包含了元素 67，但是没有返回，因为 lower()方法返回的值严格来说比较少。**

```
// Java program to demonstrate
// ConcurrentSkipListSet lower() method.

import java.util.concurrent.ConcurrentSkipListSet;

class GfgCSLS {
    public static void main(String[] args)
    {

        // Initializing the set
        // using ConcurrentSkipListSet()
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        // using add() method
        set.add(17);
        set.add(24);
        set.add(35);
        set.add(67);
        set.add(98);

        // Printing the ConcurrentSkipListSet
        System.out.println("ConcurrentSkipListSet: "
                           + set);

        // Invoking lower() method
        // to find the largest element
        // less than the specified element
        System.out.println("Largest element: "
                           + set.lower(67));
    }
}
```

****输出:****

```
ConcurrentSkipListSet: [17, 24, 35, 67, 98]
Largest element: 35
```

****程序 2:** 显示空指针异常**

```
// Java program to demonstrate
// ConcurrentSkipListSet lower() method.

import java.util.concurrent.ConcurrentSkipListSet;

class GfgCSLS {
    public static void main(String[] args)
    {

        // Initializing the set
        // using ConcurrentSkipListSet()
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        // using add() method
        set.add(17);
        set.add(24);
        set.add(35);
        set.add(67);
        set.add(98);

        // Printing the ConcurrentSkipListSet
        System.out.println("ConcurrentSkipListSet: "
                           + set);

        try {
            // Invoking lower() method
            // to find the largest element
            // less than the specified element
            System.out.println("Largest element: "
                               + set.lower(null));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

****输出:****

```
ConcurrentSkipListSet: [17, 24, 35, 67, 98]
java.lang.NullPointerException
```