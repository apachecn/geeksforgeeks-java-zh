# 在 Java 中创建包装类实例的不同方法

> 原文:[https://www . geeksforgeeks . org/创建 java 包装类实例的不同方法/](https://www.geeksforgeeks.org/different-ways-to-create-the-instances-of-wrapper-classes-in-java/)

[包装类](https://www.geeksforgeeks.org/wrapper-classes-java/)一个对象包装或包含原始数据类型的类。当我们为包装类创建一个对象时，它包含一个字段，在这个字段中，我们可以存储原始数据类型。换句话说，我们可以将一个基元值包装到包装器类对象中。

**方法:**

我们可以使用两种方法来构造包装类的实例

1.  Use the constructor of the wrapper class.
2.  Use the wrapper class
3.  The valueOf () method provided by uses the concept of automatic packaging

让我们分别详细讨论这两种方式

**方法 1** :使用包装类的构造函数

**语法:**

```java
ClassName object = new ClassName(argument);
```

**插图:**

```java
Integer number = new Integer(5);
```

**方法 2:** 使用 Wrapper 类提供的 valueOf()方法

**语法:**

```java
ClassName object = ClassName.valueOf(argument);
```

**插图:**

```java
Integer number = Integer.valueOf(5);
```

现在问题来了，在创建 Wrapper 类的实例时，这两种方法有什么不同，哪种方法更适合构造实例。让我们实现这两种方法，让它们公平竞争。

**实施:**

**例**

## 爪哇

```java
// Importing input output classes 
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main (String[] args) {

        // Creating and initializing two integer numbers
        // Value is passed as an argument to which it is initialized

        // Custom entries  
        // Number 1 where N = 5
        Integer num1 = new Integer(5);
        // Number 2 where N = 5
        Integer num2 = new Integer(5);

        // Creating objects of Integer class
        // using valueOf() method

        // Again, creating and initializing two integer numbers
        // Value is passed as an argument to which it is initialized
        Integer num3 = Integer.valueOf(5);
        Integer num4 = Integer.valueOf(5);

        // Now by far, all the objects contain the same value
        // N = 5

        // Boolean will return true if numbers are equal
        // else eturning false

        // Comparing two numbers  
        boolean value1 = (num1 == num2);
        boolean value2 = (num3 == num4);

        // Print and display the bool results 
        System.out.println(value1);
        System.out.println(value2);
    }
}
```

**输出:**

```java
false
true
```

**输出解释:**

请注意，类的实例指向堆中分配的内存位置，它们本身不保存该值。当我们在包装类的构造函数的帮助下创建对象时，每次在堆中分配一个新的内存，并且对象指向不同的内存位置。因此，在上面的例子中，在这种情况下，num1 和 num2 都指向不同的内存位置，因此在比较时，它们返回 false。

请注意，在 valueOf()方法的情况下，情况并非如此，因为 valueOf()方法会检查堆中是否有任何内存分配给该类的相同值。如果它找到了该值，那么它会将先前分配的内存位置提供给新实例，并且两者都开始指向堆中的同一个内存位置。因此，通过比较，它返回真。

因为包装类对象的值就像字符串一样是不可变的，因此一旦分配就不能更改，所以它不影响有多少实例指向同一个内存位置。因此，在上面的示例中，内存被分配给值 5，并且 num3 指向该内存位置，但是当我们再创建一个具有相同值的实例 num4 时，它也开始指向 num3 所指向的相同内存位置。

目前，不推荐使用使用构造函数创建实例的方法，因此最好始终使用 valueOf()方法。让我们继续讨论自动装箱的新概念。

**方法 3:** 使用自动装箱的概念

自动装箱是为了减少每次创建实例时编写 valueOf()方法的工作量，实现自动装箱。将原语类型自动转换为其对应包装类的对象被称为自动装箱。

到目前为止，我们一直在使用 *valueOf()* 方法创建包装类，但是当我们可以使用自动包装时，这似乎相当冗长。在自动装箱中，我们的工作是由编译器完成的，即后台的 Java 编译器将执行 valueOf()操作并创建它的实例。

使用自动装箱创建的实例在后台遵循 valueOf()的过程，因此在这种情况下，具有相同值的多个实例指向相同的内存位置。

**说明:**在上面的例子中，也可以写成 *Integer.valueOf(15)* )并把它的引用放在对象中(即一个数字)。

```java
Integer number = 15;
```

**语法:**

```java
ClassName object = value;                 
// of primitive data type associated with the wrapper class.
```

**示例:**

## Java

```java
// Importing input output classes
import java.io.*;

// Main class 
class GFG {

    // Main driver method 
    public static void main (String[] args) {

      // Creating Instances using AutoBoxing
      Integer num1 = 5;
      Integer num2 = 5;

      boolean bool = (num1 == num2);
      System.out.println(bool);
    }
}
```

**输出**

```java
true
```

**输出解释:**

num1 和 num2 都指向堆中的同一个内存位置，正如我们在 *valueOf()* 方法中讨论的那样。