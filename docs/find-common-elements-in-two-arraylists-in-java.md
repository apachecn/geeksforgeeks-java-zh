# 在 Java 中的两个数组列表中查找公共元素

> 原文:[https://www . geesforgeks . org/find-common-elements-in-two-ArrayList-in-Java/](https://www.geeksforgeeks.org/find-common-elements-in-two-arraylists-in-java/)

**先决条件:**[Java 中的数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)

给定两个数组列表，任务是在 Java 中打印两个数组列表中的所有公共元素。

**示例:**

```java
Input: List1 = ["Hii", "Geeks", "for", "Geeks"], 
       List2 = ["Hii", "Geeks", "Gaurav"]
Output: [Hii, Geeks, Geeks]

Input: List1 = ["a", "b", "c", "d", "e", "f"], 
       List2 = ["b", "d", "e", "h", "g", "c"]
Output:[b, c, d, e]

```

1.  **Using Collections.retainAll() method**

    **语法:**

    ```java
    Collections1.retainAll(Collections2)

    This method keeps only the common elements
    of both Collection in Collection1.

    ```

    **进场:**

    1.  获取两个数组列表。
    2.  使用 Collection.retainAll()方法查找两个列表中的公共元素。此方法只保留集合 1 中两个集合的公共元素。
    3.  列表 1 现在只包含公共元素。

    下面是上述方法的实现:
    **程序:**通过修改列表 1 的内容。

    ```java
    // Java Program to find common elements
    // in two ArrayLists
    // Using retainAll() method

    // import ArrayList package
    import java.util.ArrayList;

    public class GFG {

        // main method
        public static void main(String[] args)
        {

            // create ArrayList list1
            ArrayList<String>
                list1 = new ArrayList<String>();

            // Add values in ArrayList
            list1.add("Hii");
            list1.add("Geeks");
            list1.add("for");
            list1.add("Geeks");

            // print list 1
            System.out.println("List1: "
                               + list1);

            // Create ArrayList list2
            ArrayList<String>
                list2 = new ArrayList<String>();

            // Add values in ArrayList
            list2.add("Hii");
            list2.add("Geeks");
            list2.add("Gaurav");

            // print list 2
            System.out.println("List2: "
                               + list2);

            // Find the common elements
            list1.retainAll(list2);

            // print list 1
            System.out.println("Common elements: "
                               + list1);
        }
    }
    ```

    **Output:**

    ```java
    List1: [Hii, Geeks, for, Geeks]
    List2: [Hii, Geeks, Gaurav]
    Common elements: [Hii, Geeks, Geeks]

    ```

    **程序 2:** 通过保留列表 1 的内容。

    ```java
    // Java Program to find common elements
    // in two ArrayLists
    // Using retainAll() method

    // import ArrayList package
    import java.util.ArrayList;

    public class GFG {

        // main method
        public static void main(String[] args)
        {

            // create ArrayList list1
            ArrayList<String>
                list1 = new ArrayList<String>();

            // Add values in ArrayList
            list1.add("Hii");
            list1.add("Geeks");
            list1.add("for");
            list1.add("Geeks");

            // print list 1
            System.out.println("List1: "
                               + list1);

            // Create ArrayList list2
            ArrayList<String>
                list2 = new ArrayList<String>();

            // Add values in ArrayList
            list2.add("Hii");
            list2.add("Geeks");
            list2.add("Gaurav");

            // print list 2
            System.out.println("List2: "
                               + list2);

            // Create ArrayList list3
            ArrayList<String>
                list3 = new ArrayList<String>(list1);

            // Store the comparison output
            // in ArrayList list3
            list3.retainAll(list2);

            // print list 3
            System.out.println("Common elements: "
                               + list3);
        }
    }
    ```

    **Output:**

    ```java
    List1: [Hii, Geeks, for, Geeks]
    List2: [Hii, Geeks, Gaurav]
    Common elements: [Hii, Geeks, Geeks]

    ```

2.  **Using Stream filter**

    **语法:**

    ```java
    list1.stream()
        .filter(list2::contains)
        .collect(Collectors
        .toList()));

    This method returns element if found in second list.

    ```

    **进场:**

    1.  首先创建两个数组列表，并添加列表的值。
    2.  使用 Stream()方法将数组列表转换为流。
    3.  使用 contains()方法将筛选条件设置为 distinct。
    4.  使用 Collect()方法将筛选值收集为列表。该列表将返回两个列表中公共元素。
    5.  打印列表 3

    下面是上述方法的实现:

    **程序:**

    ```java
    // Java Program to find common elements
    // in two ArrayLists
    // Using  Stream filter method

    // import ArrayList package
    import java.util.*;
    import java.util.stream.*;

    public class GFG {

        // main method
        public static void main(String[] args)
        {

            // create ArrayList list1
            ArrayList<String>
                list1 = new ArrayList<String>();

            // Add values in ArrayList
            list1.add("Hii");
            list1.add("Geeks");
            list1.add("for");
            list1.add("Geeks");

            // print list 1
            System.out.println("List1: "
                               + list1);

            // Create ArrayList list2
            ArrayList<String>
                list2 = new ArrayList<String>();

            // Add values in ArrayList
            list2.add("Hii");
            list2.add("Geeks");
            list2.add("Gaurav");

            // print list 2
            System.out.println("List2: "
                               + list2);

            // Find common elements
            System.out.print("Common elements: ");
            System.out.println(list1.stream()
                                   .filter(list2::contains)
                                   .collect(Collectors
                                                .toList()));
        }
    }
    ```

    **Output:**

    ```java
    List1: [Hii, Geeks, for, Geeks]
    List2: [Hii, Geeks, Gaurav]
    Common elements: [Hii, Geeks, Geeks]

    ```

3.  **Naive approach:**
    1.  首先创建两个数组列表，并添加列表的值。
    2.  创建一个包含公共元素的临时数组列表。
    3.  使用 ArrayList.contains()方法遍历列表 1 并检查列表 2 中是否存在该元素。
    4.  如果找到，将其添加到列表中 3
    5.  打印列表 3 中的公共元素

    下面是上述方法的实现:

    ```java
    // Java Program to find common elements
    // in two ArrayLists
    // Using  Stream filter method

    // import ArrayList package
    import java.util.ArrayList;

    public class GFG {

        // main method
        public static void main(String[] args)
        {

            // create ArrayList list1
            ArrayList<String>
                list1 = new ArrayList<String>();

            // Add values in ArrayList
            list1.add("Hii");
            list1.add("Geeks");
            list1.add("for");
            list1.add("Geeks");

            // print list 1
            System.out.println("List1: "
                               + list1);

            // Create ArrayList list2
            ArrayList<String>
                list2 = new ArrayList<String>();

            // Add values in ArrayList
            list2.add("Hii");
            list2.add("Geeks");
            list2.add("Gaurav");

            // print list 2
            System.out.println("List2: "
                               + list2);

            // Create ArrayList list3
            ArrayList<String>
                list3 = new ArrayList<String>();

            // Find common elements
            // while iterating through list1
            for (String temp : list1) {

                // Check if theis element is
                // present in list2 or not
                if (list2.contains(temp)) {

                    // Since present, add it to list3
                    list3.add(temp);
                }
            }

            // print common elements from list 3
            System.out.println("Common elements: "
                               + list3);
        }
    }
    ```

    **Output:**

    ```java
    List1: [Hii, Geeks, for, Geeks]
    List2: [Hii, Geeks, Gaurav]
    Common elements: [Hii, Geeks, Geeks]

    ```