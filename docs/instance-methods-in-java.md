# Java 中的实例方法

> 原文:[https://www.geeksforgeeks.org/instance-methods-in-java/](https://www.geeksforgeeks.org/instance-methods-in-java/)

实例方法是执行特定任务的一组代码。有时程序的大小会增加，我们希望将主方法的逻辑与其他方法分开。方法是在类内部编写的函数。由于 java 是一种面向对象的编程语言，我们需要在一些类中编写一个方法。

关于实例变量的要点是:

1.  实例方法可以直接、不依赖地访问实例变量和实例方法。
2.  实例方法可以直接访问静态变量和静态方法。

## **无参数实例方法**

**语法:**

```java
modifier return_type method_name( )
{
        method body ;
}
```

*   **修饰符:**定义方法的访问类型，可选使用。
*   **return_type:** 方法可能返回值。例如:- int、void、String、char、float 等。
*   **method_name:** 这是您在编写变量名时可以编写任何内容的方法名。
*   **方法体:**方法体描述方法用语句做什么。

**示例:**

```java
public void disp( )
{
       int a= 10;
    System.out.println(a);
}
```

### **调用实例方法:**

您不能直接调用静态方法中的实例方法，因此可以使用类的对象调用实例方法。我们知道 java 程序的执行是从 main 方法开始的，main 方法是静态的，所以不能直接调用 instance 方法。我们必须创建类对象；然后，我们可以在 main 方法中调用 instance 方法。

让我们看看如何调用实例方法:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to see how can we call
// an instance method without parameter

import java.io.*;

class GFG {
      // static method
    public static void main (String[] args) {  

          // Creating object of the class
        GFG obj = new GFG();          

          // Calling instance method
        obj.disp();  

        System.out.println("GFG!");
    }

      // Instance method
    void disp()                                  
    {
          // Local variable
        int a = 20;                              
        System.out.println(a);
    }
}
```

**Output**

```java
20
GFG!
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to see how can we call
// an instance method without parameter

import java.io.*;

// Different class
class class1 {      

      // Instance method in different class 
    void add()                
    { 
      int a= 2;
      int b= 3;
      System.out.println("The sum of 2 and 3 is :" + (a+b));
    }
}
class GFG {
      // Static method
    public static void main (String[] args) {        

          // creating object of the class
        class1 obj = new class1();           

          // calling instance method
        obj.add();  

        System.out.println("GFG!");
    }
}
```

**Output**

```java
The sum of 2 and 3 is :5
GFG!
```

## 带参数的实例方法

当在主方法中调用带有参数的实例方法时，该方法接受参数。现在让我们看看例子，以便更好地理解。

**语法:**

```java
modifier return_type method_name( parameter list)
{
    method body ;
}
```

*   **参数列表:**用逗号分隔的参数列表。这些是可选的；该方法可以包含零个参数。

**示例:**

```java
public void disp(int a, int b)
{
      int x=a ;
      int y=b;
      int z = x+y;
     System.out.println(z);
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to see how can we call
// an instance method with parameter

import java.io.*;

class GFG {
      // static method
    public static void main (String[] args) { 

          // creating object
        GFG obj = new GFG();            

          // calling instance method by passing value
        obj.add(2,3);    

        System.out.println("GFG!");
    }

  // Instance method with parameter
  void add(int a, int b)          
  { 
    // local variables
    int x= a;                    
    int y= b;                    
    int z= x + y;             

    System.out.println("Sum : " + z);
  }
}
```

**Output**

```java
Sum : 5
GFG!
```

## 实例方法的类型:

Java 中有两种类型的实例方法:

1.  **存取方法**(获取器)
2.  **变异方法**(设定器)

**访问器方法**用于使代码更加安全并增加其保护级别，访问器也称为 getter。Getter 返回值(访问器)，它返回 int、String、double、float 等数据类型的值。为了程序的方便，getter 以单词“get”开头，后跟变量名。

**变异子法**也被称为 setter。它为类的程序中使用的任何变量设置值。并以单词“set”开头，后跟变量名。Getter 和 Setter 使程序员能够方便地设置和获取特定数据类型的值。在 getter 和 setter 中，变量的第一个字母都应该是大写。

存取子和变异子主要用于访问或设置主方法中类的私有成员的值。

让我们通过一些例子来理解:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the
// types of instance methods

import java.io.*;

class account {

      // private variable-balance
    private int balance = 50; 

      // accessor method (getter)
    public int getBalance()
    { 
        return balance;
    }

      // Mutator method (setter)
      public void setBalance(int a)
    { 
          // return balance + a;
        balance += a;
    }
}
class GFG {
    public static void main(String[] args)
    {
        account obj = new account();

          // setting new value for balance
        obj.setBalance(50); 

          // calling the Mutator (accessor)
        System.out.println("Your Balance : "+ obj.getBalance()); 

        System.out.println("GFG!");
    }
}
```

**Output**

```java
Your Balance : 100
GFG!
```