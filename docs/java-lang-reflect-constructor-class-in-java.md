# java 中的 java.lang.reflect.Constructor 类

> 原文:[https://www . geesforgeks . org/Java-lang-reflect-constructor-in-Java/](https://www.geeksforgeeks.org/java-lang-reflect-constructor-class-in-java/)

构造函数类用于管理构造函数元数据，如构造函数的名称、构造函数的参数类型和构造函数的访问修饰符。我们可以检查类的构造函数，并在运行时实例化对象。对于类中声明的每个公共构造函数，构造函数[]数组将有一个构造函数实例。

为了获得构造器对象，一个可以从类对象中获得构造器类对象。

**参数:** T-声明构造函数的类

实现的接口如下:

*   注释删除
*   泛型声明
*   成员

**插图:**

```
Class aClass = Employee.class;
Constructor[] constructors = aClass.getConstructors();
```

**先决条件:**

让我们讨论一些获取构造函数信息的方法

1.  [*[getconstructors ()*](https://www.geeksforgeeks.org/type-getconstructors-method-in-c-sharp-with-examples/) *:* One method can get all the public constructors in the corresponding class. It returns an array of constructors.
2.  [*getdeclared constructors ()*](https://www.geeksforgeeks.org/class-getdeclaredconstructors-method-in-java-with-examples/) *:* A can get all constructors in its own class, regardless of public keywords.
3.  *getname ():* You can get the *name of each constructor.*
4.  **getmodifiers ():* This returns that the Java language modifier of the constructor represented by this constructor object is an integer. The modifier class should be used to decode modifiers.*
5.  **getparametertypes ():* This returns the *parameter type of a specific constructor.**

**此外，该类的主要方法如下表所示:**

<figure class="table">**T103，则返回 true

| way | describe |
| --- | --- |
| [*is equal to (object object object* )](https://www.geeksforgeeks.org/equals-hashcode-methods-java/) | Compares the constructor with the specified object. |
| [getan note deerceivertype（）](https://www.geeksforgeeks.org/constructor-getannotatedreceivertype-method-in-java-with-examples/) | Returns an AnnotatedType object that represents the receiver type of the method/constructor represented by the executable object using a type. |
| [getannotedrettytttype()](https://www.geeksforgeeks.org/method-class-getannotatedreturntype-method-in-java/) | Returns an AnnotatedType object that represents the use of a type to specify the return type of the method/constructor represented by this Executable. |
| [getAnnotation(类< T >注释类)](https://www.geeksforgeeks.org/class-getannotation-method-in-java-with-examples/) | Returns the comment of this element of the specified type, or null if such comment exists. |
| [【get clear annotations()](https://www.geeksforgeeks.org/method-class-getdeclaredannotations-method-in-java/) | Returns the comment that appears directly on this element. |
| [get elangclass()](https://www.geeksforgeeks.org/method-class-getdeclaringclass-method-in-java/) | Returns a Class object that represents the Class or interface that declares the executable file represented by this object. |
| [获取异常类型（）](https://www.geeksforgeeks.org/method-class-getexceptiontypes-method-in-java/) | Returns an array of Class objects that represents the types of exceptions that the underlying executable file represented by this object declares to throw. |
| [get generic xceptonttypes()](https://www.geeksforgeeks.org/method-class-getgenericexceptiontypes-method-in-java/) | Returns an array of Type objects that represent the exceptions that the executable object declares to throw. |
| [get generic parameters types()](https://www.geeksforgeeks.org/constructor-getgenericparametertypes-method-in-java-with-examples/) | Returns an array of Type objects that represent the formal parameter types of the executable file represented by the object (in the order of declaration). |
| hashcode() | Returns the hashcode of this constructor |
| issynamic() | If this constructor is a composite constructor |
| isVarArgs() | If this constructor is declared to take a variable number of parameters |** </figure>

****示例:****

## **Java**

```
**// Java program to show uses of Constructor class
// present in java.lang.reflect package

// Importing package to that examine and
// introspect upon itself
import java.lang.reflect.*;

// Class 1
// Helper class
class Employee {

    // Member variables of this class
    int empno;
    String name;
    String address;

    // Constructor of this class

    // Constructor 1
    public Employee(int empno, String name, String address)
    {
        // 'this' keyword refers to the
        // current object itself
        this.empno = empno;
        this.name = name;
        this.address = address;
    }

    // Constructor 2
    public Employee(int empno, String name)
    {

        this.empno = empno;
        this.name = name;
    }

    // Constructor 3
    private Employee(String address)
    {
        this.address = address;
    }

    // Constructor 4
    protected Employee(int empno) { this.empno = empno; }
}

// Class 2
// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an object of above class
        // in the main() method
        Class c = Employee.class;

        // Display message
        System.out.println("All public constructor are :");

        Constructor[] cons = c.getConstructors();

        for (Constructor con : cons)

            // It will return all public constructor
            System.out.print(con.getName() + " ");

        // Display message for better readability
        System.out.println(
            "\n\nAll  constructor irrespective of access modifiers");

        // Getting constructors of this class
        // using getDeclaredConstructors() method
        cons = c.getDeclaredConstructors();

        // Iterating to print all constructors
        for (Constructor con : cons)
            System.out.print(con.getName() + " ");

        // Display message
        System.out.println(
            "\n\naccess modifiers of each constructor");

        // Iterating to get all the access modifiers
        for (Constructor con : cons)

            // Print all the access modifiers for all
            // constructors
            System.out.print(
                Modifier.toString(con.getModifiers())
                + " ");

        // Parameters types

        // Display message only
        System.out.println(
            "\n\ngetting parameters type of each constructor");

        // Iteerating to get parameter types of each
        // constructor using for-each loop
        for (Constructor con : cons) {
            Class[] parameratertypes
                = con.getParameterTypes();

            for (Class c1 : parameratertypes) {

                // Print and display parameter types of all
                // constructors
                System.out.print(c1.getName() + " ");
            }

            // Here we are done with inner loop
            // New line
            System.out.println();
        }
    }
}**
```

****输出**

```
All public constructor are :
Employee Employee 

All  constructor irrespective of access modifiers
Employee Employee Employee Employee 

access modifiers of each constructor
protected private public public 

getting parameters type of each constructor
int 
java.lang.String 
int java.lang.String 
int java.lang.String java.lang.String 
```**