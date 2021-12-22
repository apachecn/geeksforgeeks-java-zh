# Java 中的抽象顺序列表索引()方法，示例

> 原文:[https://www . geeksforgeeks . org/abstractsequentialist-indexof-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-indexof-method-in-java-with-example/)

**Java . util . abstractsequentialist**类的 **indexOf()** 方法用于返回该列表中指定元素第一次出现的索引，如果该列表不包含该元素，则返回-1。更正式地说，返回最低的索引 I，这样(o==null？get(i)==null : o.equals(get(i))，如果没有这样的索引，则为-1。

**语法:**

```
public int indexOf(Object o)
```

**参数:**该方法以的**对象为参数，该参数是要搜索的元素。**

**返回值:**该方法返回该列表中指定元素第一次出现的**索引**，如果该列表不包含该元素，则返回-1。

**异常:**此方法抛出:

*   **ClassCastException** :如果指定元素的类型与本列表不兼容。
*   **NullPointRexception**:如果指定的元素为空，并且该列表不允许空元素。

下面是举例说明方法的**索引。**

**例 1:**

```
// Java program to demonstrate indexOf()
// method for AbstractSequentialList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Creating object of AbstractSequentialList
        AbstractSequentialList<Integer>
            arrlist1 = new LinkedList<Integer>();

        // Populating arrlist1
        arrlist1.add(10);
        arrlist1.add(20);
        arrlist1.add(30);
        arrlist1.add(40);
        arrlist1.add(50);

        // print arrlist1
        System.out.println("AbstractSequentialList: "
                           + arrlist1);

        // getting the index of element 30
        // using indexOf() method
        int index = arrlist1.indexOf(30);

        // print the index
        System.out.println("Index of 30: "
                           + index);
    }
}
```

**Output:**

```
AbstractSequentialList: [10, 20, 30, 40, 50]
Index of 30: 2

```

**例 2:**

```
// Java program to demonstrate indexOf()
// method for AbstractSequentialList

import java.util.*;

public class GFG1 {
    public static void main(String[] args)
    {
        // Creating object of AbstractSequentialList
        AbstractSequentialList<Integer>
            arrlist1 = new LinkedList<Integer>();

        // Populating arrlist1
        arrlist1.add(10);
        arrlist1.add(20);
        arrlist1.add(30);
        arrlist1.add(40);
        arrlist1.add(50);

        // print arrlist1
        System.out.println("LinkedListlist: "
                           + arrlist1);

        // getting the index of element 100
        // using indexOf() method
        int index = arrlist1.indexOf(null);

        // print the index
        System.out.println("Index of 100: "
                           + index);
    }
}
```

**Output:**

```
LinkedListlist: [10, 20, 30, 40, 50]
Index of 100: -1

```