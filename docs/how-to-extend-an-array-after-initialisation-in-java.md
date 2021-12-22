# 如何在 Java 中扩展初始化后的数组？

> 原文:[https://www . geesforgeks . org/如何在 java 中初始化后扩展数组/](https://www.geeksforgeeks.org/how-to-extend-an-array-after-initialisation-in-java/)

在 java 中，[](https://www.geeksforgeeks.org/arrays-in-java/)**数组是不可变的，也就是说，如果数组一旦被赋值或实例化，分配给数组的内存就不能减少或增加。但是有一种解决方案，我们可以扩展数组。**

****初始化后扩展数组:**由于我们不能在数组声明后修改数组大小，所以只能通过初始化一个新数组，并将旧数组的值复制到新数组中来扩展，然后我们可以根据声明的数组大小为数组分配新值。**

**下面是初始化后扩展数组的例子。**

****例 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// java program to demonstrate
// extending an array
import java.lang.*;

class ExtendingArray {

    public static void main(String[] args)
    {

        // initializing string array
        String[] words = new String[] { "G", "E", "E" };

        // allocating space for 5 strings
        // in the extended array
        String[] extendWords = new String[5];

        // adding new string
        // at index 3 and 4
        extendWords[3] = "K";
        extendWords[4] = "S";

        // copying the array elements
        // to new extended array
        System.arraycopy(words, 0, extendWords, 0,
                         words.length);

        // printing the extended array
        // elements
        for (String str : extendWords) {
            System.out.print(str);
        }
    }
}
```

****Output**

```
GEEKS
```** 

****例 2:****

## **Java**

```
// Java program to demonstrate
// extending an array

import java.lang.*;

class ExtendingArray {

    public static void extendedArray()
    {

        // initializing integers to array int
        int[] num = new int[] { 1, 2, 3, 4, 5, 6 };

        // allocating space for 10 integers
        int[] extendnum = new int[10];

        // adding new integers
        // at index 6,7,8,9
        extendnum[6] = 7;
        extendnum[7] = 8;
        extendnum[8] = 9;
        extendnum[9] = 10;

        // copying old array to new array
        System.arraycopy(num, 0, extendnum, 0, num.length);

        // print the elements of
        // extended array using for-each
        for (int str : extendnum)
            System.out.println(str);
    }
    public static void main(String[] args)
    {

        // create an instance
        ExtendingArray exarr = new ExtendingArray();

        // extend an array and print them
        exarr.extendedArray();
    }
}
```

****输出**

```
1
2
3
4
5
6
7
8
9
10
```**