# Java 中早绑定和晚绑定的区别

> 原文:[https://www . geesforgeks . org/Java 中早期绑定和晚期绑定的区别/](https://www.geeksforgeeks.org/difference-between-early-and-late-binding-in-java/)

**早期绑定:**编译器在编译时可以解析的绑定称为静态或早期绑定。所有静态、私有和最终方法的绑定都是在编译时完成的。

**示例:**

```java
public class NewClass {
    public static class superclass {
        static void print()
        {
            System.out.println("print in superclass.");
        }
    }
    public static class subclass extends superclass {
        static void print()
        {
            System.out.println("print in subclass.");
        }
    }

    public static void main(String[] args)
    {
        superclass A = new superclass();
        superclass B = new subclass();
        A.print();
        B.print();
    }
}
```

**Output:**

```java
print in superclass.
print in superclass.

```

**后期绑定:**在后期绑定或动态绑定中，编译器不决定要调用的方法。重写是动态绑定的一个完美例子。在重写时，父类和子类都有相同的方法。

**示例:**

```java
public class NewClass {
    public static class superclass {
        void print()
        {
            System.out.println("print in superclass.");
        }
    }

    public static class subclass extends superclass {
        @Override
        void print()
        {
            System.out.println("print in subclass.");
        }
    }

    public static void main(String[] args)
    {
        superclass A = new superclass();
        superclass B = new subclass();
        A.print();
        B.print();
    }
}
```

**Output:**

```java
print in superclass.
print in subclass.

```

**早、晚绑定差异表:**

| 早期绑定 | 后期绑定 |
| --- | --- |
| 这是一个编译时过程 | 这是一个运行时过程 |
| 方法定义和方法调用在编译时是链接的。 | 方法定义和方法调用在运行时被链接。 |
| 实际对象不用于绑定。 | 实际对象用于绑定。 |
| 例如:方法重载 | 例如:方法重写 |
| 程序执行更快 | 程序执行较慢 |