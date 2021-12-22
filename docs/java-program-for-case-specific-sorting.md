# 用于案例分类的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-针对特定案例的程序-排序/](https://www.geeksforgeeks.org/java-program-for-case-specific-sorting/)

给定一个由大写和小写字符组成的字符串。任务是分别对大写字母和小写字母进行排序，这样，如果原始字符串中的第 I 个位置有大写字符，则排序后它不应该有小写字符，反之亦然。如下图所示:

插图:

> **输入:** srbDKi
> **输出:**birds
> **处理:**排序后我们要把小写字符放到小写字符上，大写字符放到特定大写字符上

**进场:**

1.  我们将使用两个数组列表，一个存储小写值，*第二个存储大写值。*
2.  在列表中添加元素后，我们将使用 [*Collections.sort(list)方法*](https://www.geeksforgeeks.org/collections-sort-java-examples/) 对列表进行排序
3.  在排序之后，我们将遍历字符串并检查具体情况，并将元素存储在正确的位置

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program for Case Specific Sorting
// using Collections.sort(list) method

// Importing input output classes
// Importing utility classes
import java.io.*;
import java.util.*;

class GFG {

    // Method 1
    // To sort the string
    static String sortString(String str)
    {
        // Creating two Arraylist  class objects
        // Declaring object of character type
        ArrayList<Character> list = new ArrayList<>();
        ArrayList<Character> list2 = new ArrayList<>();

        // Initially the string is empty
        String res = "";

        // Iterating over the string
        for (int i = 0; i < str.length(); i++) {
            // Finding character at indexes
            // using charAt() method in List object
            if (str.charAt(i) >= 'a'
                && str.charAt(i) <= 'z')
                list.add(str.charAt(i));

            if (str.charAt(i) >= 'A'
                && str.charAt(i) <= 'Z')
                list2.add(str.charAt(i));
        }

        // Sorting the Collection interface
        // using sort() method
        Collections.sort(list);
        Collections.sort(list2);

        int i = 0;
        int j = 0;

        // iterating over string using length() method
        for (int k = 0; k < str.length(); k++) {

            // If lowercase character encountered
            if (str.charAt(k) >= 'a'
                && str.charAt(k) <= 'z') {

                // Appending them all in beginning of string
                res += list.get(i);
                ++i;
            }

            // If uppercase character encountered
            else if (str.charAt(k) >= 'A'
                     && str.charAt(k) <= 'Z') {

                // Appending them all together after
                // lowercase is finished in input string
                res += list2.get(j);
                ++j;
            }
        }
        return res;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Passing the custom string as input for which we
        // want case-specific sorting by calling the method
        // 1 as defined above
        System.out.println(sortString("defRTSersUXI"));
    }
}
```

**Output**

```java
deeIRSfrsTUX
```