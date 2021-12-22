# 用 Java 编码时如何避免 TLE？

> 原文:[https://www . geeksforgeeks . org/如何避免在 java 中编码时出现小标题/](https://www.geeksforgeeks.org/how-to-avoid-tle-while-coding-in-java/)

避免超过[时间限制](https://www.geeksforgeeks.org/overcome-time-limit-exceedtle/) (TLE)是我们在进行竞争性编码以及在技术 PI 期间回答 DSA 问题时需要注意的最重要的方面之一。在这种情况下，所有编码平台中一个常见的问题是排序或涉及排序的问题。下面的代码是我在练习数据结构时设计的，它对从 1 开始的最少交换次数的连续数字列表进行线性排序，并返回交换次数的值。

下面代码背后的概念是，考虑到数组索引从 0 开始，排序数组中数字的正确位置比数字本身小 1。这是因为数组仅由从 1 开始的连续数字组成。

**图解:**考虑下面的例子:给定的未排序数组是:4 3 1 2 5。

**输入:**下面是数组元素及其在数组中的当前位置的表格(由第一行中的索引指示)。

<figure class="table">

| Zero | one | Two | three | four |
| four | three | one | Two | five |

</figure>

**输出:**排序后，数组将如下图所示。因此，元素的正确位置只不过是比数字本身小 1 的值的索引，因此我们所需要做的就是将各个元素放在它们的正确索引处，这些索引可以从元素值中确定。

<figure class="table">T18

3

T22

4

T26

| 0 | 1 | T15】2 |
| T29】1 | T33】2
T37 | 【T39】3【T40 |

</figure>

**进场:**

1.  我们首先将给定的数组元素插入到 HashMap 中，其中键是元素，值是指示当前位置的索引。
2.  然后我们运行一个 for 循环，从输入数组的初始索引值(即 0)开始，直到小于数组大小 1 的值。
3.  在每次迭代中，我们检查 arr[i]处的值是否比“I”多一个。
4.  如果是这样的话，这意味着该元素位于其正确的位置，否则它的位置需要与它实际所在位置的元素交换(该元素只不过是(i+1))。每次交换发生时，用于记录交换次数的变量都会增加 1。
5.  然后数组中由于交换而产生的相应变化也会在 HashMap 中更新。

**图示:**最初，散列表如下

<figure class="table">T33

| Element (key) | Current index (value) |
| --- | --- |
| 4 | 19【0】 |
| 3 | one |

</figure>

第一次迭代后，HashMap 会是这样的

<figure class="table">T14

2

T18T20

3

T24

1

T28T30

1

T31

| Element (Key) | Current index (Value) |
| 4 |

</figure>

而阵中则变成了

<figure class="table">T16

3

T19T25

| 0 | 1 | T13】2 | 4T 23 T21 |
| 【T27】1T29 | T313 | 【T35】4T37】 |

</figure>

**结论:**因此，在每次交换之后，一个元素被放置在其正确的位置，并且对 hashmap 进行相应的更改，以确保交换的数量最小。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate a Hack to Avoid TLE while
// coding

// Importing required libraries
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

// Main Class
class GFG {

    // Method 1
    // To find the minimum number of swaps required
    static int minimumSwaps(int[] arr)
    {

        // Declaring and initializing variables to 0
        // Swap and Index variable
        int swap = 0, index = 0;

        // Creating object of HashMap class for storing
        // array elements along with corresponding current
        // position in the input array

        // Declaring both the objects if Integer type
        HashMap<Integer, Integer> index_table
            = new HashMap<>();

        for (int i = 0; i < arr.length; i++) {

            index_table.put(arr[i], i);
        }

        // Loop variable beginning from 0 so the element
        // that should be present at index i after sorting
        // is, i+1 Hence we check if arr[i] is equal to i+1
        // or not
        for (int i = 0; i < arr.length; i++) {

            // Condition check for figuring out correct
            // element
            if (arr[i] != (i + 1))

            {

                // If the above condition is not fulfilled
                // i.e, if arr[i]!=i+1 that means the
                // correct element needs to be swapped with
                // the current one.

                // Find the index of the element i+1 from
                // the hashmap
                index = index_table.get(i + 1);

                // Swapping the element
                arr[index] = arr[i];
                arr[i] = i + 1;

                // Variable keeping a count of the number of
                // swaps
                swap++;

                // Updating the hashmap
                index_table.put(arr[i], i);

                index_table.put(arr[index], index);
            }
        }

        // Returning the swap counts
        return swap;
    }

    // Scnnere Class object to take unput from user
    private static final Scanner scanner
        = new Scanner(System.in);

    // Method 2
    // Main driver method
    public static void main(String[] args)
        throws IOException
    {

        // Creating an object of BufferedWriter to read
        // input fro te use
        BufferedWriter bufferedWriter = new BufferedWriter(
            new FileWriter(System.getenv("OUTPUT_PATH")));

        // Storing the non-primitive datatype
        // Here, Integer value
        int n = scanner.nextInt();

        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        // Creating arrays

        // Array 1
        // Creating an Integer array o size N
        int[] arr = new int[n];

        // Array 2
        // Creating an String array
        String[] arrItems = scanner.nextLine().split(" ");

        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        for (int i = 0; i < n; i++) {

            int arrItem = Integer.parseInt(arrItems[i]);

            arr[i] = arrItem;
        }

        int res = minimumSwaps(arr);

        bufferedWriter.write(String.valueOf(res));

        // Getting to new line
        bufferedWriter.newLine();

        // No further input will be accepted
        // isong the close()  method
        bufferedWriter.close();

        // Closing the inputs
        scanner.close();
    }
}
```

**输出:**

**输入:**

```java
4 3 1 2 5
```

**输出:**

```java
3
```