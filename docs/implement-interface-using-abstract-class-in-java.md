# 在 Java 中使用抽象类实现接口

> 原文:[https://www . geesforgeks . org/implement-interface-use-abstract-class-in-Java/](https://www.geeksforgeeks.org/implement-interface-using-abstract-class-in-java/)

[**接口**](https://www.geeksforgeeks.org/interfaces-in-java/) 只包含不能实例化的抽象方法，通过关键字**接口**声明。用**抽象**关键字声明的类在 Java 中称为[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)。这是一个通常包含至少一个不能被实例化的抽象方法的类，并且该类也可能根本没有方法。无法创建抽象类的实例。

由于接口中的所有方法都是抽象方法，因此我们可以使用抽象类来实现它。

**1。我们先创建一个界面:**

## 【Java】

```
// creating an interface named GFG
interface GFG {
    void learnCoding();
    void learnProgrammingLanguage();
    void contribute();
}
```