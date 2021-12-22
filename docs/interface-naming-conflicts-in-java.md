# Java 中的接口命名冲突

> 原文:[https://www . geesforgeks . org/interface-naming-conflicts-in-Java/](https://www.geeksforgeeks.org/interface-naming-conflicts-in-java/)

Java 中的接口由抽象方法(不包含主体)和变量(公共静态 final)组成。接口方法的实现在实现该接口的类中定义。它帮助 Java 实现抽象。

当一个类实现两个具有同名方法和变量的接口时，就会发生命名冲突。

### 接口命名冲突

由于接口由变量和方法组成，因此**两种类型的**命名冲突可能会发生。

1.  Method naming conflict
2.  Variable naming conflict

### 1.方法命名冲突

这种方法命名冲突可能在各种情况下发生。

**Case-1:** 当我们有两个方法名相同、签名相同、返回类型相同的接口时，实现类可以实现其中的任意一个，不能说实现了其中的哪一个。

**代码**

## Java

```java
public interface Interface1 {

    // create a method
    public void show();
}
```

T15】JavaT1T21T23】JavaT2T28】

**输出**

```java
Geeks For Geeks
```

**说明:**在下面的代码中，我们无法确认哪一个显示 2 个接口的方法被执行。不会引发错误。

**Case-2:** 当两个接口由名称相同但签名不同的方法组成时，那么在实现类中，我们需要实现两种方法，并且根据我们调用的方法的种类来执行方法。

**代码**

## Java

```java
public interface Interface1 {

    // create a method
    public void show();
}
```

T15】JavaT1T21T23】JavaT2T28】

**输出**

```java
Geeks For Geeks
GFG
```

**说明:**这种情况下可以根据签名区分这些方法的执行，这种情况下忽略返回类型。

**Case-3:** 当两个接口包含一个名称相同、签名相同但返回类型不同的方法时，这种情况下两个接口不能在同一个类中实现。需要创建单独的类来实现该类型的每个接口。

**代码**

## Java

```java
public interface Interface1 {

    // create a method
    public void show();
}
```

## Java

```java
public interface Interface2 {
    // create method with same name & signature but
    // different return type
    public String show();
}
```