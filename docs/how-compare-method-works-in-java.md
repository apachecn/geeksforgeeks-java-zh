# 【compare()方法在 Java 中是如何工作的

> 原文:[https://www . geesforgeks . org/how-compare-method-in-works-Java/](https://www.geeksforgeeks.org/how-compare-method-works-in-java/)

**先决条件:**[Java 中的比较器接口](https://www.geeksforgeeks.org/comparator-interface-java/)[Java 中的 TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)
Java 中的 compare()方法比较作为参数给出的两个类特定对象(x，y)。它返回以下值:

*   **0:** if (x==y)
*   **-1:** if (x < y)
*   **1:** if (x > y)

**语法:**

```
public int compare(Object obj1, Object obj2)
```

其中 obj1 和 obj2 是要使用 compare()方法进行比较的两个对象。

### 示例:

显示使用整数类的 compare()方法的工作原理。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working
// of compare() method using Integer Class

import java.lang.Integer;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        int a = 10;
        int b = 20;

        // as 10 less than 20,
        // Output will be a value less than zero
        System.out.println(Integer.compare(a, b));

        int x = 30;
        int y = 30;

        // as 30 equals 30,
        // Output will be zero
        System.out.println(Integer.compare(x, y));

        int w = 15;
        int z = 8;

        // as 15 is greater than 8,
        // Output will be a value greater than zero
        System.out.println(Integer.compare(w, z));
    }
}
```

**Output:** 

```
-1
0
1
```

### 如何评估返回值:

compare()方法的内部工作可以在下面伪代码的帮助下可视化:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Converting the two objects to integer
// for comparison
int intObj1 = (int)obj1;
int intObj2 = (int)obj2;

// Get the difference
int difference = intObj1 - intObj2;

if (difference == 0) {

    // Both are equal
    return 0;
}
else if (difference < 0) {

    // obj1 < obj2
    return -1;
}
else {

    // obj1 > obj2
    return 1;
}
```

### 使用这种方法可视化 compare()方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working
// of compare() method

import java.lang.Integer;

class Gfg {

    // Function to compare both objects
    public static int compare(Object obj1, Object obj2)
    {

        // Converting the two objects to integer
        // for comparison
        int intObj1 = (int)obj1;
        int intObj2 = (int)obj2;

        // Get the difference
        int difference = intObj1 - intObj2;

        if (difference == 0) {

            // Both are equal
            return 0;
        }
        else if (difference < 0) {

            // obj1 < obj2
            return -1;
        }
        else {

            // obj1 > obj2
            return 1;
        }
    }

    // driver code
    public static void main(String args[])
    {
        int a = 10;
        int b = 20;

        // as 10 less than 20,
        // Output will be a value less than zero
        System.out.println(compare(a, b));

        int x = 30;
        int y = 30;

        // as 30 equals 30,
        // Output will be zero
        System.out.println(compare(x, y));

        int w = 15;
        int z = 8;

        // as 15 is greater than 8,
        // Output will be a value greater than zero
        System.out.println(compare(w, z));
    }
}
```

**Output:** 

```
-1
0
1
```

### compare()方法的各种可能实现

> ```
> public int compare(Object obj1, Object obj2)
> {
>     Integer I1 = (Integer)obj1; // typecasting object type into integer type
>     Integer I2 = (Integer)obj2; // same as above ..
>     // 1.
>     return I1.compareTo(I2); // ascending order [0, 5, 10, 15, 20]
>     // 2.
>     return -I1.compareTo(I2); // descending order [20, 15, 10, 5, 0]
>     // 3.
>     return I2.compareTo(I1); // descending order [20, 15, 10, 5, 0]
>     // 4.
>     return -I2.compareTo(I1); // ascending order [0, 5, 10, 15, 20]
>     // 5.
>     return +1; // insertion order [10, 0, 15, 5, 20, 20]
>     // 6.
>     return -1; // reverse of insertion order [20, 20, 5, 15, 0, 10]
>     // 7.
>     return 0; // only first element [10]
> }
> ```