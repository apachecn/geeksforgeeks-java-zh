# 如何在 Java 中从列表中移除子列表

> 原文:[https://www . geesforgeks . org/如何从 java 列表中删除子列表/](https://www.geeksforgeeks.org/how-to-remove-a-sublist-from-a-list-in-java/)

给定一个 Java 中的列表，任务是移除[子列表](https://www.geeksforgeeks.org/arraylist-sublist-method-in-java-with-examples/)中的所有元素，这些元素的索引介于 fromIndex(包含)和 toIndex(排除)之间。索引的范围由用户定义。

**示例:**

> **输入**列表= [1，2，3，4，5，6，7，8]，fromIndex = 2，endIndex = 4
> **输出**【1，2，5，6，7，8】
> 
> **输入**列表= ['G '，' E '，' E '，' G '，' K '，' S']，fromIndex = 3，endIndex = 5
> **输出** ['G '，' E '，' E '，' K '，' S']

*   ### 方法 1:使用 subList()和 clear()方法

    **语法:**

    ```
    List.subList(int fromIndex, int toIndex).clear()

    ```

    **示例:**

    ```
    // Java code to remove a subList using
    // subList(a, b).clear() method

    import java.util.*;

    public class AbstractListDemo {
        public static void main(String args[])
        {

            // Creating an empty AbstractList
            AbstractList<String>
                list = new LinkedList<String>();

            // Using add() method
            // to add elements in the list
            list.add("GFG");
            list.add("for");
            list.add("Geeks");
            list.add("computer");
            list.add("portal");

            // Output the list
            System.out.println("Original List: "
                               + list);

            // subList and clear method
            // to remove elements
            // specified in the range
            list.subList(1, 3).clear();

            // Print the final list
            System.out.println("Final List: "
                               + list);
        }
    }
    ```

    **Output:**

    ```
    Original List: [GFG, for, Geeks, computer, portal]
    Final List: [GFG, computer, portal]

    ```

    **注意:**可以继承抽象列表的类:

    *   [阵列列表](https://www.geeksforgeeks.org/arraylist-in-java/)
    *   [矢量](https://www.geeksforgeeks.org/java-util-vector-class-java/)
    *   链接列表
    *   [堆叠](https://www.geeksforgeeks.org/stack-class-in-java/)
*   ### 方法 2:使用 removeRange()方法

    **语法:**

    ```
    List.removeRange(int fromIndex, int toIndex)

    ```

    **示例:**

    ```
    // Java code to remove a subList
    // using removeRange() method

    import java.util.*;

    // since removeRange() is a protected method
    // ArrayList has to be extend the class
    public class GFG extends ArrayList<Integer> {

        public static void main(String[] args)
        {

            // create an empty array list

            GFG arr = new GFG();

            // use add() method
            // to add values in the list
            arr.add(1);
            arr.add(2);
            arr.add(3);
            arr.add(4);
            arr.add(5);
            arr.add(6);
            arr.add(7);
            arr.add(8);

            // prints the list before removing
            System.out.println("Original List: "
                               + arr);

            // removing elements in the list
            // from index 2 to 4
            arr.removeRange(2, 4);
            System.out.println("Final List: "
                               + arr);
        }
    }
    ```

    **Output:**

    ```
    Original List: [1, 2, 3, 4, 5, 6, 7, 8]
    Final List: [1, 2, 5, 6, 7, 8]

    ```