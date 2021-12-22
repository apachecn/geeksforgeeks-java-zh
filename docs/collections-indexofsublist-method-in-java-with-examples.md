# Java 中的 Collections indexOfSubList()方法，带示例

> 原文:[https://www . geesforgeks . org/collections-indexofpublist-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-indexofsublist-method-in-java-with-examples/)

**java.util.Collections** 类的**indexofpublist()**方法用于返回指定目标列表在指定源列表中第一次出现的起始位置，如果没有则返回-1。更正式地说，返回最低的索引 I，例如 source.subList(i，i+target.size())。等于(目标)，如果没有这样的索引，则为-1。(如果 target.size() > source.size()则返回-1。)

该实现使用“强力”技术扫描源列表，依次在每个位置寻找与目标的匹配。

**语法:**

```
public static int indexOfSubList(List source, List target)
```

**参数:**该方法以下列参数为参数

*   **来源–**要在其中搜索第一个目标的列表。
*   **target –** the list to search for as a subList of source.

    **返回值:**该方法返回指定源列表内指定目标列表第一次出现的**起始位置**，如果没有出现则返回-1。

    以下是示例，说明发布的*索引()*方法

    **例 1:**

    ```
    // Java program to demonstrate
    // indexOfSubList() method
    // for String value

    import java.util.*;

    public class GFG1 {
        public static void main(String[] argv)
            throws Exception
        {
            try {

                // creating object of List<String>
                List<String> arrlistsrc = new ArrayList<String>();
                List<String> arrlisttarget = new ArrayList<String>();

                // Adding element to arrlistsrc
                arrlistsrc.add("A");
                arrlistsrc.add("B");
                arrlistsrc.add("C");
                arrlistsrc.add("D");
                arrlistsrc.add("E");

                // Adding element to arrlisttarget
                arrlisttarget.add("C");
                arrlisttarget.add("D");
                arrlisttarget.add("E");

                // print the source list
                System.out.println("Source list: " + arrlistsrc);

                // print the target list
                System.out.println("Target list: " + arrlisttarget);

                // check target list in source list
                int index = Collections
                                .indexOfSubList(arrlistsrc,
                                                arrlisttarget);

                // print the index
                System.out.println("Target list starts at index: "
                                   + index);
            }

            catch (IllegalArgumentException e) {
                System.out.println("Exception thrown : " + e);
            }
        }
    }
    ```

    **Output:**

    ```
    Source list: [A, B, C, D, E]
    Target list: [C, D, E]
    Target list starts at index: 2

    ```

    **例 2:**

    ```
    // Java program to demonstrate
    // indexOfSubList() method
    // for Integer value

    import java.util.*;

    public class GFG1 {
        public static void main(String[] argv)
            throws Exception
        {
            try {

                // creating object of List<Integer>
                List<Integer> arrlistsrc = new ArrayList<Integer>();
                List<Integer> arrlisttarget = new ArrayList<Integer>();

                // Adding element to arrlistsrc
                arrlistsrc.add(20);
                arrlistsrc.add(30);
                arrlistsrc.add(40);
                arrlistsrc.add(50);
                arrlistsrc.add(60);

                // Adding element to arrlisttarget
                arrlisttarget.add(40);
                arrlisttarget.add(50);

                // print the source list
                System.out.println("Source list: " + arrlistsrc);

                // print the target list
                System.out.println("Target list: " + arrlisttarget);

                // check target list in source list
                int index = Collections
                                .indexOfSubList(arrlistsrc,
                                                arrlisttarget);

                // print the index
                System.out.println("Target list starts at index: "
                                   + index);
            }

            catch (IllegalArgumentException e) {
                System.out.println("Exception thrown : " + e);
            }
        }
    }
    ```

    **Output:**

    ```
    Source list: [20, 30, 40, 50, 60]
    Target list: [40, 50]
    Target list starts at index: 2

    ```