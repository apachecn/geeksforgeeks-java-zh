# 检查给定数字是否为完全数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序检查给定数字是否是完美数字/](https://www.geeksforgeeks.org/java-program-to-check-if-a-given-number-is-perfect-number/)

如果一个数的适当除数之和(即不包括数本身的所有正除数)等于该数本身，则称该数为[](https://www.geeksforgeeks.org/perfect-number/)**。**等分总和**是一个数的除数之和，不包括数本身。因此，一个数只有等于它的等份和时才是完全数。所有已知的完全数都是**甚至**。**

```java
**Example 1:**

n = 9
Proper Divisors of 9 are 1 and 3.
Sum = 1+3 = 4 ≠ 9
⇒ 9 is not a perfect number.

**Example 2:**

n = 6
Proper Divisors of 6 are 1, 2 and 3.
Sum = 1+2+3 = 6 = 6
⇒ 6 is a perfect number.

**Example 3:**

n = 28
Proper Divisors of 28 are 1, 2, 4, 7 and 14.
Sum = 1+2+4+7+14 = 28 = 28
⇒ 28 is a perfect number.

**Example 4:**

n = 15
Proper Divisors of 15 are 1,3 and 5.
Sum = 1+3+5 = 9 ≠ 15
⇒ 15 is not a perfect number.
```

**所以，我们基本上要找到一个数的适当除数的和。**

****方法 1:****

**一个**简单的解决方法**就是把从 1 到 n-1 的每一个数都过一遍，检查它是不是除数，如果是，那么把它加到和变量中，最后检查和是否等于数本身，那么它就是一个完全数，否则不是。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to check if a given
// number is perfect or not

class GFG {

    // Returns true if n is perfect
    static boolean isPerfect(int n)
    {
        // 1 is not a perfect number
        if (n == 1)
            return false;

        // sum will store the sum of proper divisors
        // As 1 is a proper divisor for all numbers
        // initialised sum with 1
        int sum = 1;

        // Looping through the numbers to check if they are
        // divisors or not
        for (int i = 2; i < n; i++) {

            if (n % i == 0) {
                sum += i;
            }

        }

        // If sum of divisors is equal to
        // n, then n is a perfect number
        if (sum == n)
            return true;

        return false;
    }

    // Driver program
    public static void main(String[] args)
    {
        int n = 6;

        // Call isPerfect function to
        // check if the number is perfect or not.
        if (isPerfect(n))
            System.out.println(n + " is a perfect number");
        else
            System.out.println(
                n + " is not a perfect number");
    }
}
```

****Output**

```java
6 is a perfect number
```** 

*   ****时间复杂度:** O(n)**

****方法 2:****

**一个**有效的解决方案**是遍历数字直到 n 的**平方根****

> **如果 **i** 是除数，那么 **n/i** 也是除数。**

## **Java**

```java
// Java program to check if a given
// number is perfect or not

class GFG {

    // Returns true if n is perfect
    static boolean isPerfect(int n)
    {
        // 1 is not a perfect number
        if (n == 1)
            return false;

        // sum will store the sum of proper divisors
        // As 1 is a proper divisor for all numbers
        // initialised sum with 1
        int sum = 1;

        // Looping through the numbers to check if they are
        // divisors or not
        for (int i = 2; i * i <= n; i++) {

            if (n % i == 0) {

                // n is a perfect square
                // let's take 25
                // we need to add 5 only once
                // sum += i + n / i will add it twice

                if (i * i == n)
                    sum += i;
                else
                    sum += i + (n / i);
            }
        }

        // If sum of divisors is equal to
        // n, then n is a perfect number

        if (sum == n)

            return true;

        return false;
    }

    // Driver program
    public static void main(String[] args)
    {
        int n = 6;

        // Call isPerfect function to
        // check if the number is perfect or not.
        if (isPerfect(n))

            System.out.println(n + " is a perfect number");

        else
            System.out.println(
                n + " is not a perfect number");
    }
}
```

****输出**

```java
6 is a perfect number
```** 

****时间复杂度:** O(√n)**