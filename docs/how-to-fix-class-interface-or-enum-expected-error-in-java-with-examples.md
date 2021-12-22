# 如何用示例修复 Java 中的“类、接口或枚举预期”错误？

> 原文:[https://www . geesforgeks . org/how-fix-class-interface-or-enum-预期错误-in-java-with-examples/](https://www.geeksforgeeks.org/how-to-fix-class-interface-or-enum-expected-error-in-java-with-examples/)

在 Java 中，类接口或枚举预期错误是编译时错误。我们在 Java 中得到“类、接口或预期枚举”错误可能有以下原因之一:

**案例 1:额外卷曲括号**

## Java

```
class Hello {

    public static void main(String[] args)
    {
        System.out.println("Helloworld");
    }
}
} // extra bracket.
```

在这种情况下，只需移除额外的括号即可消除错误。

## 爪哇

```
class Hello {

    public static void main(String[] args)
    {
        System.out.println("Helloworld");
    }
}
```

**案例二:类外功能**

## Java

```
class Hello {
    public static void main(String args[])
    {
        System.out.println("HI");
    }
}
public static void func() { System.out.println("Hello"); }
```

在前面的例子中，我们得到一个错误，因为 func()方法在 Hello 类之外。可以通过将右花括号“}”移动到文件末尾来删除它。换句话说，在 Hello 内部移动 func()方法。

## 爪哇

T5

```
class Hello {
    public static void main(String args[])
    {
        System.out.println("HI");
    }
    public static void func()
    {
        System.out.println("Hello");
    }
}
```