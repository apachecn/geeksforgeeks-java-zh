# 统计在 Java 中创建的一个类对象的数量

> 原文:[https://www . geesforgeks . org/count-a-class-number-objects-created-in-Java/](https://www.geeksforgeeks.org/count-number-of-a-class-objects-created-in-java/)

想法是使用类中的[静态](https://www.geeksforgeeks.org/static-keyword-java/)成员来计数对象。静态成员由类的所有对象共享，如果不存在其他初始化，则在创建第一个对象时，所有静态数据都被初始化为零，并且构造函数和静态成员函数只能从类外部访问静态数据成员、其他静态成员函数和任何其他函数。

我们创建了一个静态 int 类型的变量，并把它放在一个带有增量操作符的静态变量中，这样它在构造函数中就增加了 1。

```java
// Java program Find Out the Number of Objects Created
// of a Class
class Test {

    static int noOfObjects = 0;

    // Instead of performing increment in the constructor
    // instance block is preferred to make this program generic.
    {
        noOfObjects += 1;
    }

    // various types of constructors
    // that can create objects
    public Test()
    {
    }
    public Test(int n)
    {
    }
    public Test(String s)
    {
    }

    public static void main(String args[])
    {
        Test t1 = new Test();
        Test t2 = new Test(5);
        Test t3 = new Test("GFG");

        // We can also write t1.noOfObjects or
        // t2.noOfObjects or t3.noOfObjects
        System.out.println(Test.noOfObjects);
    }
}
```

**输出:**

```java
3

```