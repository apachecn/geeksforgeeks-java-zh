# 如何在 Java 中删除数组列表中的重复项

> 原文:[https://www . geesforgeks . org/如何从 java 数组列表中删除重复项/](https://www.geeksforgeeks.org/how-to-remove-duplicates-from-arraylist-in-java/)

给定一个具有重复值的数组列表，任务是在 Java 中从这个数组列表中移除重复值。

**示例:**

```
Input: List = [1, 10, 2, 2, 10, 3, 3, 3, 4, 5, 5]
Output: List = [1, 10, 2, 3, 4, 5]

Input: List = ["G", "e", "e", "k", "s"]
Output: List = ["G", "e", "k", "s"]

```

1.  ### 使用迭代器

    **进场:**

    1.  获取具有重复值的数组列表。
    2.  创建另一个数组列表。
    3.  遍历第一个数组列表，并使用 contains()方法将每个元素的第一个外观存储到第二个数组列表中。
    4.  第二个数组列表包含删除了重复项的元素。

    下面是上述方法的实现:

    ```
    // Java program to remove duplicates from ArrayList

    import java.util.*;

    public class GFG {

        // Function to remove duplicates from an ArrayList
        public static <T> ArrayList<T> removeDuplicates(ArrayList<T> list)
        {

            // Create a new ArrayList
            ArrayList<T> newList = new ArrayList<T>();

            // Traverse through the first list
            for (T element : list) {

                // If this element is not present in newList
                // then add it
                if (!newList.contains(element)) {

                    newList.add(element);
                }
            }

            // return the new list
            return newList;
        }

        // Driver code
        public static void main(String args[])
        {

            // Get the ArrayList with duplicate values
            ArrayList<Integer>
                list = new ArrayList<>(
                    Arrays
                        .asList(1, 10, 1, 2, 2, 3, 3, 10, 3, 4, 5, 5));

            // Print the Arraylist
            System.out.println("ArrayList with duplicates: "
                               + list);

            // Remove duplicates
            ArrayList<Integer>
                newList = removeDuplicates(list);

            // Print the ArrayList with duplicates removed
            System.out.println("ArrayList with duplicates removed: "
                               + newList);
        }
    }
    ```

    **Output:**

    ```
    ArrayList with duplicates: [1, 10, 1, 2, 2, 3, 3, 10, 3, 4, 5, 5]
    ArrayList with duplicates removed: [1, 10, 2, 3, 4, 5]

    ```

2.  ### 使用 LinkedHashSet

    一个更好的方法(时间复杂度和容易实现)是从数组列表中移除重复项，即将其转换为不允许重复项的集合。因此，LinkedHashSet 是最好的选择，因为它不允许重复，也保留了插入顺序。

    **进场:**

    1.  获取具有重复值的数组列表。
    2.  从这个数组列表中创建一个链接表。这将删除重复项
    3.  将此链接哈希集转换回数组列表。
    4.  第二个数组列表包含删除了重复项的元素。

    下面是上述方法的实现:

    ```
    // Java program to remove duplicates from ArrayList

    import java.util.*;

    public class GFG {

        // Function to remove duplicates from an ArrayList
        public static <T> ArrayList<T> removeDuplicates(ArrayList<T> list)
        {

            // Create a new LinkedHashSet
            Set<T> set = new LinkedHashSet<>();

            // Add the elements to set
            set.addAll(list);

            // Clear the list
            list.clear();

            // add the elements of set
            // with no duplicates to the list
            list.addAll(set);

            // return the list
            return list;
        }

        // Driver code
        public static void main(String args[])
        {

            // Get the ArrayList with duplicate values
            ArrayList<Integer>
                list = new ArrayList<>(
                    Arrays
                        .asList(1, 10, 1, 2, 2, 3, 10, 3, 3, 4, 5, 5));

            // Print the Arraylist
            System.out.println("ArrayList with duplicates: "
                               + list);

            // Remove duplicates
            ArrayList<Integer>
                newList = removeDuplicates(list);

            // Print the ArrayList with duplicates removed
            System.out.println("ArrayList with duplicates removed: "
                               + newList);
        }
    }
    ```

    **Output:**

    ```
    ArrayList with duplicates: [1, 10, 1, 2, 2, 3, 10, 3, 3, 4, 5, 5]
    ArrayList with duplicates removed: [1, 10, 2, 3, 4, 5]

    ```

3.  ### 使用 Java 8 Stream.distinct()

    您可以使用流应用编程接口中的 distinct()方法。distinct()方法根据 equals()方法返回的结果返回一个没有重复元素的新流，该结果可用于进一步处理。Stream 管道的实际处理只有在调用像 forEach()或 collect()这样的终端方法之后才开始。

    **进场:**

    1.  获取具有重复值的数组列表。
    2.  从此数组列表创建一个新列表。
    3.  使用流()。返回不同对象流的 distinct()方法。
    4.  将此对象流转换为列表

    下面是上述方法的实现:

    ```
    // Java program to remove duplicates from ArrayList

    import java.util.ArrayList;
    import java.util.Arrays;
    import java.util.List;
    import java.util.stream.Collectors;

    // Program to remove duplicates from a List in Java 8
    class GFG
    {
        public static void main(String[] args)
        {
            // input list with duplicates
            List<Integer> list = new ArrayList<>(
                Arrays.asList(1, 10, 1, 2, 2, 3, 10, 3, 3, 4, 5, 5));
                // Print the Arraylist
            System.out.println("ArrayList with duplicates: "
                               + list);

            // Construct a new list from the set constucted from elements
            // of the original list
            List<Integer> newList = list.stream()
                                          .distinct()
                                          .collect(Collectors.toList());

            // Print the ArrayList with duplicates removed
            System.out.println("ArrayList with duplicates removed: "
                               + newList);
        }
    }
    ```

    **Output:**

    ```
    ArrayList with duplicates: [1, 10, 1, 2, 2, 3, 10, 3, 3, 4, 5, 5]
    ArrayList with duplicates removed: [1, 10, 2, 3, 4, 5]

    ```