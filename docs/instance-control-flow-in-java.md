# Java 中的实例控制流

> 原文:[https://www . geesforgeks . org/instance-control-flow-in-Java/](https://www.geeksforgeeks.org/instance-control-flow-in-java/)

本文将解释每当创建对象时实例控制流是如何发生的。

### 普通类中的实例控制流

每当我们执行 java 时。类文件，将执行第一个[静态控制流](https://www.geeksforgeeks.org/static-control-flow-in-java/)。在静态控制流中，如果我们正在创建一个对象，以下步骤序列将作为实例控制流的一部分执行:

1.  Identify instance members from top to bottom.
2.  Execute instance variable assignment and instance block from top to bottom.
3.  Execute the constructor.

**例:**

## 爪哇

```java
// InstanceControlFlow class
class InstanceControlFlow {

    // initializing instance integer i = 10
    int i = 10;

    // first instance block
    {
        // call instance method (methodeOne())
        methodOne();
        System.out.println("First Instance Block");
    }

    // constructor
    InstanceControlFlow()
    {
        System.out.println("Constructor");
    }

    // main method
    public static void main(String[] args)
    {
        // create InstanceControlFlow class object
        InstanceControlFlow f = new InstanceControlFlow();
        System.out.println("Main method");
    }

    // instance method (methodOne())
    public void methodOne() { System.out.println(j); }

    // second instance block
    {
        System.out.println("Second Instance Block");
    }

    // initializing instance integer j = 20
    int j = 20;
}
```

**输出**

```java
0
First Instance Block
Second Instance Block
Constructor
Main method
```