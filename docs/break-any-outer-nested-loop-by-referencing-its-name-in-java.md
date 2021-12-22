# 通过在 Java 中引用其名称来中断任何外部嵌套循环

> 原文:[https://www . geesforgeks . org/break-any-outer-nested-loop-by-reference-it-name-in-Java/](https://www.geeksforgeeks.org/break-any-outer-nested-loop-by-referencing-its-name-in-java/)

A [***嵌套循环***](https://www.geeksforgeeks.org/java-nested-loops-with-examples/)**是一个循环内的循环，一个内循环体内的一个外循环。**

****工作:****

***   The first pass of the outer loop triggers the inner loop, which is executed until completion.*   Then the outer ring triggers the inner ring again for the second time.*   Repeat this process until the outer ring ends.*   A [***Breaking the inner or outer loop in***](https://www.geeksforgeeks.org/break-statement-in-java/) will interrupt this process.**

****嵌套循环的功能:****

## **Java**

```java
// Nested for loop

import java.io.*;
class GFG {

    public static void main(String[] args)
    {

        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                System.out.print("GFG! ");
            }
            System.out.println();
        }
    }
}
```

****输出****

```java
GFG! GFG! GFG! 
GFG! GFG! GFG! 
GFG! GFG! GFG! 
```