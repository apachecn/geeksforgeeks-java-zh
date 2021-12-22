# Java 中通过引用实现传递的不同方式

> 原文:[https://www . geeksforgeeks . org/Java 中通过引用实现传递的不同方法/](https://www.geeksforgeeks.org/different-ways-to-achieve-pass-by-reference-in-java/)

参数有两种，一种是**形式参数**，另一种是**实际参数**。形式参数是在函数定义过程中定义的参数，实际参数是在其他函数的函数调用过程中传递的参数。

**通过代码展示形式参数和实际参数:**

## Java

```
// Java program to show the difference
// between formal and actual parameters

import java.io.*;

class GFG {
  static int sum(int a,int b) // Formal parameters
  { 
   return a+b;
  }
    public static void main (String[] args) {
       int a=5;
       int b=10;

      System.out.println(sum(a,b));  //This is actual parameters
    }
}
```

**输出**

```
15
```

*   [**Functions**](https://www.geeksforgeeks.org/methods-in-java/) can be distinguished according to parameters.
*   There are two ways to transfer parameters in a function: **Call** and **by value by reference to** .
*   C/C++ supports reference call, because in reference call, we use **pointer to pass the address of actual parameter at formal parameter.**
*   Moreover, Java does not support pointers, which is why Java does not support calling by reference, but c/c++ supports pointers, so these languages support calling by reference.

```
Swapping of Two numbers in C/C++ language is done by the call by Reference approach
```

**下面是 C** 中引用调用的实现

## C

```
// C program o show the call by reference support

#include <stdio.h>

// formal parameters
void swap(int* x, int* y)
{

    int temp;

    // save the value at address x
    temp = *x;

    // put y into x
    *x = *y;

    // put temp into y
    *y = temp;

    return;
}
int main()
{
    int a = 15;
    int b = 5;
    printf("Value of a %d\n", a);
    printf("Value of b %d\n", b);

    // swapping the value using call by reference
    swap(&a,&b);

    printf("Value of a %d\n", a);

    printf("Value of b %d", b);

    return 0;
}
```

**Output**

```
Value of a 15
Value of b 5
Value of a 5
Value of b 15
```

在 java 中，如果我们试图在 java 中交换数字，这两个数字的状态变化只在特定的交换方法中有效

**用 java 交换两个数字:**

## Java

```
// Java program to swap two numbers

import java.io.*;

class GFG {
    static void swap(int a, int b)
    {
        int temp = a;

        a = b;

        b = temp;

        System.out.println("Value of a in swap function "
                           + a);

        System.out.println("Value of b in swap function "
                           + b);
        return;
    }

    public static void main(String[] args)
    {
        int a = 5;
        int b = 10;

        // original value of a
        System.out.println("Value of the a "
                           + a);

        // original value of b
        System.out.println("Value of the b "
                           + b);

        // swap the numbers
        swap(a, b);

        System.out.println("Value of the a " + a);

        System.out.println("Value of the b " + b);
    }
}
```

**输出**

```
Value of the a 5
Value of the b 10
Value of a in swap function 10
Value of b in swap function 5
Value of the a 5
Value of the b 10
```

**在 java 中有一些方法可以实现引用传递，代替引用调用:**

**1。将特定数据类型的特定变量作为类成员**

*   Class members can be accessed in the whole class definition. When there are local variables with the same name as class members in a specific function body or function definition, we can use the keyword **this** to access members to avoid confusion.
*   In order to pass the reference, the object of the class we pass has the same reference with the object type of the formal parameter of a class where the actual parameter is located, which is why any change of the object with the formal parameter of the class will be reflected in both the form of the object and the actual object.

## Java

```
// Java program to make a particular variable
// of a particular datatype as a class member

import java.io.*;

class GFG {
    int Number;
    void GFG() { Number = 0; }

    static void update(GFG ob) { ob.Number++; }

    public static void main(String[] args)
    {
        GFG ob = new GFG();

        System.out.println("Number value " + (ob.Number));

        update(ob);

        System.out.println("Updated Number value "
                           + (ob.Number));
    }
}
```

**输出**

```
Number value 0
Updated Number value 1
```

**2。传递集合或单元素数组作为参数:**

*   We can pass arrays, stacks and other collections or single element arrays as actual parameters, and the actual parameters and formal parameters of the function have the same references to memory addresses.

## Java

```
// Java program to passing collections
// as parameters

import java.io.*;
import java.util.*;

class GFG {
    static void update(int a[])
    {
        // formal parameter
        a[0]++;
    }

    static void update2(ArrayList<Integer> A)
    {
        for (int i = 0; i < A.size(); ++i) {

            // update the item of
            // the arraylist
            A.set(i, A.get(i) + 1);
        }
    }
    public static void main(String[] args)
    {
        // using single array of element
        int a[] = new int[1];

        System.out.println("Number Value " + a[0]);

        // actual parameter
        update(a);

        System.out.println("Number Value " + a[0]);

        // using Arraylist collection
        ArrayList<Integer> A = new ArrayList<>();

        A.add(1);
        A.add(2);

        System.out.println("List " + A);

        // actual parameter
        update2(A);

        System.out.println("Updated List " + A);
    }
}
```

**输出**

```
Number Value 0
Number Value 1
List [1, 2]
Updated List [2, 3]
```

**3。更新返回值:**

*   【 Naive Method 】 The reference is performed by simply updating the return value with the previous value.

## Java

```
// Java program to show the return
// value getting updated

import java.io.*;

class GFG {
    static int update(int number)
    {
        // update the number
        return ++number;
    }

    public static void main(String[] args)
    {
        int number = 3;

        // printing the number
        System.out.println("Number " + number);

        int returnnumber = update(number);

        // update the number
        number = returnnumber;

        // printing the updated number;
        System.out.println("Updated number " + number);
    }
}
```

**输出**

```
Number 3
Updated number 4
```