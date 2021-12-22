# Java 中有趣又酷的小技巧

> 原文:[https://www . geesforgeks . org/有趣又酷的 java 技巧/](https://www.geeksforgeeks.org/interesting-and-cool-tricks-in-java/)

Java 是最好的面向对象编程语言之一，由詹姆斯·高斯林于 1991 年从太阳微系统公司开发，并于 1995 年公开发行。它是一种解释型编程语言，具有平台独立性，是所有编程语言中最好的一种。

在本文中，我们将看到 Java 中一些有趣且很酷的技巧。

1.  **Executing Comments:** Most of the developers think [comments](https://www.geeksforgeeks.org/comments-in-java/) are never executed in a program and are used for ease in understanding the code. But, they are executed. For example:

    ```
    public class GFG {
        public static void main(String[] args)
        {
            // \u000d System.out.println("GeeksForGeeks");
        }
    }
    ```

    **Output:**

    ```
    GeeksForGeeks

    ```

    **解释:**
    这个注释是因为 unicode 字符“\u000d”而执行的，java 编译器将这个 Unicode 字符解析为一个新行。Java 允许使用 [Unicode 字符](https://www.geeksforgeeks.org/understanding-character-encoding/)而不编码。

2.  **Underscore in Numeric Literals:** In Java SE 7 and above, underscores can be used in [numeric literals](https://www.geeksforgeeks.org/g-fact-45-using-underscore-in-numeric-literals/) without generating any warning or error in the output.

    **示例:**

    ```
    public class GFG {
        public static void main(String[] args)
        {
            int x = 123_34;
            System.out.println(x);
        }
    }
    ```

    **Output:**

    ```
    12334

    ```

3.  **Double Brace Initialization:** In Java, [collections](https://www.geeksforgeeks.org/collections-in-java-2/) such as [sets](https://www.geeksforgeeks.org/set-in-java/), lists, [maps](https://www.geeksforgeeks.org/map-interface-java-examples/), etc. does not have a simple and easy way to initialize the values during declaration. Developers either push values into the collection or creates a static block for the constant collection. Using [double brace initialization](https://www.geeksforgeeks.org/double-brace-initialization-java/), collections can be initialized during declaration with less efforts and time.

    **示例:**

    ```
    import java.util.HashSet;
    import java.util.Set;

    public class GFG {
        public static void main(String[] args)
        {
            Set<String> GFG = new HashSet<String>() {{
                add("DS");
                add("ALGORITHMS");
                add("BLOCKCHAIN");
                add("MACHINE LEARNING");
            } };
            System.out.println(GFG);
        }
    }
    ```

    **Output:**

    ```
    [MACHINE LEARNING, ALGORITHMS, DS, BLOCKCHAIN]

    ```

4.  **Finding a position to insert the numeric element in the array:** There is a small cool trick to find the position where the requested element can be inserted in the sorted array.

    **示例:**

    ```
    import java.util.Arrays;
    public class GFG {
        public static void main(String[] args)
        {
            int[] arr = new int[] { 1, 3, 4, 5, 6 };

            // 2 has to be inserted
            int pos = Arrays.binarySearch(arr, 2);
            System.out.print("Element has to be inserted at: "
                                                      + ~pos);
        }
    }
    ```

    **Output:**

    ```
    Element has to be inserted at: 1

    ```

5.  **包装类 vs 数据类型:**在下面的示例中，第二个 print 语句不会显示 true，因为包装类对象的引用正在被比较，而不是它们的值。

    ```
    import java.util.Arrays;
    public class GFG {
        public static void main(String[] args)
        {
            int num_1 = 10;

            int num_2 = 10;

            Integer wrapnum_1 = new Integer(10);

            Integer wrapnum_2 = new Integer(10);

            System.out.println(num_1 == num_2);

            // Compares reference
            System.out.println(wrapnum_1 == wrapnum_2);

            // Compares value of object
            System.out.println(wrapnum_1.equals(wrapnum_2));
        }
    }
    ```

    **输出:**

    ```
    true
    false
    true

    ```