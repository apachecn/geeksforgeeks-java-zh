# 数组的 Java 数组列表

> 原文:[https://www.geeksforgeeks.org/java-arraylist-of-arrays/](https://www.geeksforgeeks.org/java-arraylist-of-arrays/)

数组的数组列表可以像任何其他对象一样使用数组列表构造函数来创建。在 2D 数组中，数组中的大部分可能是空的。为了优化空间复杂度，可以使用数组的数组列表。

> 数组列表<string>极客=新数组列表<string>()；</string></string>

**示例:**

```
Input :int array1[] = {1, 2, 3},
       int array2[] = {31, 22},
       int array3[] = {51, 12, 23}
Output: ArrayList of Arrays = {{1, 2, 3},{31, 22},{51, 12, 23}}
```

**进场:**

*   创建字符串[]类型的数组列表对象，比如列表。
*   将字符串数组，比如姓名[]、年龄[]和地址[]存储到列表对象中。
*   打印数组的数组列表。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java ArrayList of Arrays
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // create an ArrayList of String Array type
        ArrayList<String[]> list = new ArrayList<String[]>();

        // create a string array called Names
        String names[] = { "Rohan", "Ritik", "Prerit" };

        // create a string array called Age
        String age[] = { "23", "20" };

        // create a string array called address
        String address[] = { "Lucknow", "Delhi", "Jaipur" };

        // add the above arrays to ArrayList Object
        list.add(names);
        list.add(age);
        list.add(address);

        // print arrays from ArrayList
        for (String i[] : list) {
            System.out.println(Arrays.toString(i));
        }
    }
}
```

**Output**

```
[Rohan, Ritik, Prerit]
[23, 20]
[Lucknow, Delhi, Jaipur]
```