# 简要概述&面向对象编程从 C 到 Java 的比较

> 原文:[https://www . geesforgeks . org/brief-overview-object-oriented-programming-从 c 到 java/](https://www.geeksforgeeks.org/brief-overview-comparison-of-object-oriented-programming-from-c-to-java/)

在本文中，您将通过 [C](https://www.geeksforgeeks.org/c-programming-language/) 获得思考 [Java](https://www.geeksforgeeks.org/java/) 中 [OOP](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/&sa=U&ved=2ahUKEwiw9Krz0ontAhWKyjgGHY1vBewQFjAAegQIABAC&usg=AOvVaw0itC_iDk_3Kt_Truah8XgY) 真正如何工作的能力。

通过 [C](https://www.geeksforgeeks.org/c-programming-language/) ，你会了解到**多态**、**继承**、**封装**、**类**、**对象**等概念。正如你也知道的，C 语言不支持面向对象，但是我们可以通过将一个精细的结构定义为类并将其标识创建为对象来理解它背后的概念。

并行地，通过 Java，我们可以理解它如何真正与实际的类和对象一起工作。

从这个比较中，我们获得了思考面向对象编程背后的逻辑的能力。

#### 理解比较背后的概念

<figure class="table">

| 

Java 语言(一种计算机语言，尤用于创建网站)

 | 

C

 |
| --- | --- |
| java 类(客户示例) | 在 C 语言中创建的结构(示例客户) |
| 类的字段(例如整型标识、字符串名称) | 结构中存在的变量(例如整数标识、字符*名称) |
| 类中存在的构造函数 | 函数创建并返回一个指针，该指针将数据存储在堆内存中(示例 cust* createCustomer) |
| 类的方法(示例打印客户) | 创建的函数(打印客户示例) |
| 用 Java 从类中创建对象 | 创建结构客户的实例 |

</figure>

## C

```
// Adding the necessary header files
#include <stdio.h>
#include <stdlib.h>

// customer structure
typedef struct customer {
    int id;
    char* name;

    // cust is an alias used for struct customer by using
    // typedef
} cust;

cust* createCustomer(int id, char* name)
{
    // Memory allocation in the Heap
    cust* this = (cust*)malloc(sizeof(cust));

    // Similar to 'this' in Java
    this->id = id;
    this->name = name;
    return this;
}
void printCustomer(cust* c)
{
    printf("The Id is %d\n", c->id);
    printf("The name is %s\n", c->name);
}

int main()
{
    // Create an instance of struct customer Similar
    // to creation of Object form the Class in Java
    cust* c1;

    // Adding the Arguments in the function
    // is similar to adding arguments in methods of the Java
    // Class
    c1 = createCustomer(25, "Siddharth");

    // Calling the function printCustomer
    printCustomer(c1);

    // Free the allocated memory
    free(c1);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// import the required classes

import java.io.*;

class Cust {
    int id;
    String name;

    // constructor
    Cust(int id, String name)
    {
        this.id = id;
        this.name = name;
    }
    public void printCustomer()
    {
        System.out.println("The Id is " + id);
        System.out.println("The name is " + name);
    }
}

class GFG {
    public static void main(String[] args)
    {
        // Object declaration
        Cust c1;

        // object Initialisation
        c1 = new Cust(25, "Siddharth");

        // Calling the method of cust
        // class
        c1.printCustomer();
    }
}
```

**Output**

```
The Id is 25
The name is Siddharth
```