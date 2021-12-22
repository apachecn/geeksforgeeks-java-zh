# 如何在 Java 中使用多线程查找质数和回文数？

> 原文:[https://www . geesforgeks . org/如何使用 java 多线程找到质数和回文数/](https://www.geeksforgeeks.org/how-to-find-prime-and-palindrome-numbers-using-multi-threading-in-java/)

**Java 中的多线程**是同时执行两个或两个以上线程以最大化 CPU 利用率的过程。多线程应用程序执行两个或多个并发运行的线程。因此，它在 Java 中也被称为并发。每个线程彼此平行运行。多线程不会分配单独的内存区域，因此可以节省内存。

**问题陈述:**编写一个双线程程序，其中一个线程找到所有素数(在 0 到 100 之间)，另一个线程找到所有回文数(在 10 到 1000 之间)。以顺序的方式调度这些线程以获得结果。现在将它们重新安排为并行线程。

**解决方案:**

> 1.启动了两个线程，一个线程打印质数，另一个线程打印回文数
> 
> 2.打印素数的算法:
> 
> 开始
> 
> 步骤 1 →取整数变量 A
> 
> 步骤 2 →用(A-1 到 2)除变量 A
> 
> 步骤 3 →如果 A 能被任何值整除(A-1 到 2)，它就不是质数
> 
> 步骤 4 →否则是质数
> 
> 停止
> 
> 3.打印回文编号的算法
> 
> 开始
> 
> 步骤 1 →从用户处获取号码
> 
> 步骤 2 →将数字保存在临时变量中
> 
> 步骤 3 →反转数字
> 
> 步骤 4 →比较临时号码和反向号码
> 
> 步骤 5 →如果两个数字相同，打印。
> 
> 停止

同步块如何工作:

```java
thread 1, thread 2, thread 3 ---> synchronization ---> thread 1
          thread 2,thread 3  ---> synchronization ---> thread 2
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.util.Scanner;

// thread to print prime numbers
class part1 extends Thread {
    public synchronized void run()
    {
        int i = 0;
        int num = 0;
        String primeNumbers = "";

        for (i = 1; i <= 100; i++) {
            int counter = 0;
            for (num = i; num >= 1; num--) {

                // condition to check if the number is prime
                if (i % num == 0) {

                    // increment counter
                    counter = counter + 1;
                }
            }

            if (counter == 2) {
                primeNumbers = primeNumbers + i + " ";
            }
        }

        System.out.println("\nPrime numbers from 0 to 100 : \n"
            + primeNumbers);

        System.out.println();
    }
}

// thread to print palindrome numbers
class part2 extends Thread {
    public synchronized void run()
    {
        int n, b, rev = 0;
        int N = 1000;

        System.out.println("Palindrome numbers from 10 to 1000 : ");

        for (int i = 10; i <= N; i++) {
            n = i;
            while (n > 0) {

                // Find reverse of n
                b = n % 10;
                rev = rev * 10 + b;
                n = n / 10;
            }

            // If n and rev are same, n is palindrome number
            if (rev == i) {
                System.out.print(i + " ");
            }
            rev = 0;
        }
    }
}
public class Main {
    public static void main(String args[])
    {
        part1 t1 = new part1();
        part2 t2 = new part2();

        Thread m1 = new Thread(t1);
        Thread m3 = new Thread(t2);
        Scanner sc = new Scanner(System.in);

        // start() method starts the execution of thread.
        m1.start();
        m3.start();

        try {

            // join() method waits for the thread to die
            m1.join();
            m3.join();
        }
        catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```

**Output**

```java
Palindrome numbers from 10 to 1000 : 
11 22 33 44 55 66 77 88 99 101 111 121 131 141 151 161 171 181 191 202 212 222 232 242 252 262 272 282 292 303 313 323 333 343 353 363 373 383 393 404 414 424 434 444 454 464 474 484 494 505 515 525 535 545 555 565 575 585 595 606 616 626 636 646 656 666 676 686 696 707 717 727 737 747 757 767 777 787 797 808 818 828 838 848 858 868 878 888 898 909 919 929 939 949 959 969 979 989 999 
Prime numbers from 0 to 100 : 
2 3 5 7 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97 
```