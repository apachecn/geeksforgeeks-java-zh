# Java 程序打印任意数字的乘法表

> 原文:[https://www . geesforgeks . org/Java-程序到打印-乘法-任意数字表/](https://www.geeksforgeeks.org/java-program-to-print-multiplication-table-for-any-number/)

给定一个数字 N 作为输入，我们需要打印它的表，其中 N>0。

**例**

```java
Input 1 :- N = 7
Output  :- 
     7 * 1 = 7
    7 * 2 = 14
    7 * 3 = 21
    7 * 4 = 28
    7 * 5 = 35
    7 * 6 = 42
    7 * 7 = 49
    7 * 8 = 56
    7 * 9 = 63
    7 * 10 = 70
```

**显示两种方式打印任意数字的乘法表:**

1.  用于循环打印 10 以内的乘法表。
2.  使用 while 循环打印给定范围内的乘法表。

**方法 1:生成乘法表，用于循环至 10**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to print the multiplication table of the
// number N.

class GFG {
    public static void main(String[] args)
    {
        // number n for which we have to print the
        // multiplication table.
        int N = 7;

        // looping from 1 to 10 to print the multiplication
        // table of the number.
        // using for loop
        for (int i = 1; i <= 10; i++) {
            // printing the N*i,ie ith multiple of N.
            System.out.println(N + " * " + i + " = "
                               + N * i);
        }
    }
}
```

**Output**

```java
7 * 1 = 7
7 * 2 = 14
7 * 3 = 21
7 * 4 = 28
7 * 5 = 35
7 * 6 = 42
7 * 7 = 49
7 * 8 = 56
7 * 9 = 63
7 * 10 = 70
```

**方法 2:-使用生成乘法表，同时循环到任意给定范围**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to print the multiplication table of
// number N using while loop

class GFG {
    public static void main(String[] args)
    {
        // number n for which we have to print the
        // multiplication table.
        int N = 7;

        int range = 18;

        // looping from 1 to range to print the
        // multiplication table of the number.
        int i = 1;

        // using while loop
        while (i <= range) {

            // printing the N*i,ie ith multiple of N.
            System.out.println(N + " * " + i + " = "
                               + N * i);
            i++;
        }
    }
}
```

**Output**

```java
7 * 1 = 7
7 * 2 = 14
7 * 3 = 21
7 * 4 = 28
7 * 5 = 35
7 * 6 = 42
7 * 7 = 49
7 * 8 = 56
7 * 9 = 63
7 * 10 = 70
7 * 11 = 77
7 * 12 = 84
7 * 13 = 91
7 * 14 = 98
7 * 15 = 105
7 * 16 = 112
7 * 17 = 119
7 * 18 = 126
```