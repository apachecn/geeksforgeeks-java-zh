# 在 Java 中给方法和函数添加标签

> 原文:[https://www . geesforgeks . org/add-labels-to-method-and-functions-in-Java/](https://www.geeksforgeeks.org/adding-labels-to-method-and-functions-in-java/)

Java 中标签的概念来自汇编语言。在 Java 中，中断和继续是控制程序流程的控制语句。标签也可以被认为是控制语句，但是有一个强制条件，即在循环中，标签只能与 break 和 continue 关键字一起使用。

**标签的用法:**

break 语句有助于在某些条件出现后从内部循环中出来，标签用于在内部循环中使用 break 语句从外部循环中出来。

标签是用冒号(:)定义的，位于标签名称之后，循环之前。

下面是使用标签和不使用标签的代码的演示语法。

**不使用标签**

```java
while (condition)  
{
 if (specific condition )
 { 
       break;
    // when control will reach to this break 
        // statement,the control will come out of while loop.
  } 
 else
     {
        // code that needs to be executed
    // if condition in if block is false.
     }
}

```

**带标签**

```java
// labelName is the name of the label
labelName:

while (condition)  
{
 if (specific condition )
     {  
       break labelName;
    // it will work same as if break is used here.
     }
 else
     {
        // code that needs to be executed 
    // if condition in if block is false.
     } 
}

```

下面是一些使用 main 函数的程序，这将有助于理解 label 语句是如何工作的，以及它们可以在哪里使用。

**在单个 For 循环中使用标签**

## Java

```java
// Java program to demonstrate 
// the use of label in for loop

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
    label1:
        for (int i = 0; i < 5; i++) {
            if (i == 3)
                break label1;
            System.out.print(i + " ");
        }
    }
}
```

**输出**

```java
0 1 2 

```

#### 嵌套循环中标签的使用

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the use 
// of label in nested for loop
import java.io.*;

class GFG {

    public static void main(String[] args)
    {
    outerLoop:
        for (int i = 0; i < 5; i++) {
        innerLoop:
            for (int j = 0; j < 5; j++) {
                if (i != j) {
                    System.out.println("If block values "
                                       + i);
                    break outerLoop;
                }
                else {
                    System.out.println("Else block values "
                                       + i);
                    continue innerLoop;
                }
            }
        }
    }
}
```

**Output**

```java
Else block values 0
If block values 0
```