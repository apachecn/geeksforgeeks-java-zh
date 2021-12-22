# 角括号<Java 中的>带示例

> 原文:[https://www . geesforgeks . org/angle-中括号-Java-带示例/](https://www.geeksforgeeks.org/angle-bracket-in-java-with-examples/)

Java 中的**尖括号**用来定义[泛型](https://www.geeksforgeeks.org/generics-in-java/)。这意味着在调用过程中，尖括号将定义中的泛型类型(比如 T)和任何类作为参数。其思想是允许类型(整数、字符串、…等和用户定义的类型)成为方法、类和接口的参数。例如，像 HashSet、ArrayList、HashMap 等类很好地使用了泛型。我们可以将它们用于任何类型。

**示例:**

```java
<T> // of type T
<Integer> // of type Integer
<String> // of type String
<MyClass> // of type MyClass
.
.

```

**如何与 Class 一起使用尖括号？:**

我们使用尖括号“<>”来指定泛型类创建中的参数类型。要创建泛型类的对象，我们使用以下语法:

```java
// To create an instance of generic class 
BaseType  obj = new BaseType ()

Note: In Parameter type,
      we can not use primitives like 
      'int', 'char' or 'double'.

```

```java
// A Simple Java program
// to show working of user defined
// Generic classes

// We use < > to specify Parameter type
class Test<T> {

    // An object of type T is declared
    T obj;

    // constructor
    Test(T obj)
    {
        this.obj = obj;
    }

    public T getObject()
    {
        return this.obj;
    }
}

// Driver class to test above
class Main {
    public static void main(String[] args)
    {
        // instance of Integer type
        Test<Integer> iObj
            = new Test<Integer>(15);
        System.out.println(iObj.getObject());

        // instance of String type
        Test<String> sObj
            = new Test<String>("GeeksForGeeks");
        System.out.println(sObj.getObject());
    }
}
```

**Output:**

```java
15
GeeksForGeeks

```

**如何使用带功能的角括号？:**

我们使用尖括号”来指定泛型函数定义中的参数类型。然后为了调用这个函数，我们只需要传递 expecter 类型作为参数。我们还可以根据传递给泛型方法的参数类型，编写可以用不同类型的参数调用的泛型函数，编译器处理每个方法。

```java
// To create a generic function
public static  void func(T a, T b){}

Note: In Parameter type,
      we can not use primitives like 
      'int', 'char' or 'double'.

```

```java
// A Simple Java program
// to show working of user defined
// Generic functions

class Test {
    // A Generic method example
    static <T> void genericDisplay(T element)
    {
        System.out.println(
            element
                .getClass()
                .getName()
            + " = " + element);
    }

    // Driver method
    public static void main(String[] args)
    {
        // Calling generic method
        // with Integer argument
        genericDisplay(11);

        // Calling generic method
        // with String argument
        genericDisplay("GeeksForGeeks");

        // Calling generic method
        // with double argument
        genericDisplay(1.0);
    }
}
```

**Output:**

```java
java.lang.Integer = 11
java.lang.String = GeeksForGeeks
java.lang.Double = 1.0

```