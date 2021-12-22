# java 中的 java.lang.reflect .修饰符类

> 原文:[https://www . geesforgeks . org/Java-lang-reflect-modifier-class-in-Java/](https://www.geeksforgeeks.org/java-lang-reflect-modifier-class-in-java/)

java.lang.reflect.Modifier 类包含用于获取类、成员和方法访问修饰符信息的方法。修饰符被表示为 int 值，设置位位于不同的位置。int 值代表不同的修饰符。这些值取自 JVM 规范第 4.1、4.4、4.5 和 4.7 节中的表格。

**类申报:**T0】

**字段:**

<figure class="table">

| **field** | **Description** |
| --- | --- |
| Abstract | represents the integer value of the abstract modifier. |
| Final | represents the integer value of the final modifier. |
| Interface | represents the integer value of the interface modifier. |
| NATIVE | represents the integer value of the native modifier. |
| PRIVATE | represents the integer value of the private modifier. |
| [Protected] | represents the integer value of the protected modifier. |
| PUBLIC | stands for the integer value of the public modifier. |
| Static | stands for the integer value of the static modifier. |
| Strict | represents the integer value of the strictfp modifier. |
| SYNCHRONIZED | stands for the integer value of the synchronized modifier. |
| Transient | represents the integer value of transient modifier. |
| VOLATILE | represents the integer value of volatile modifier. |

</figure>

**施工方:**

```java
public Modifier(): Default constructor
```

**方法:**

<figure class="table">

| **Method** | **Description** |
| --- | --- |
| Class modifier () | This method returns an int value OR-ing, which combines the source language modifiers that can be applied to the class. |
| Constructor Modifiers () | This method returns an int value, which combines the source language modifiers that can be applied to constructors. |
| Field modifiers () | This method returns an int value, which combines the source language modifiers that can be applied to fields. |
| Interface modifiers () | This method returns an int value OR- combines the source language modifiers that can be applied to the interface. |
| isabstract (int mod) | This method returns true if the integer parameter contains abstract modifiers, otherwise it returns false. |
| Isfinal (int mod) | This method returns true if the integer parameter contains the final modifier, otherwise it returns false. |
| IsInterface (int mod) | This method returns true if the integer parameter contains interface modifiers, otherwise it returns false. |
| is null (int mod) | This method returns true if the integer parameter contains native modifiers, otherwise it returns false. |
| Isprivate (int mod) | This method returns true if the integer parameter contains private modifiers, otherwise it returns false. |
| is Protected(int mod) | This method returns true if the integer parameter contains a protected modifier, otherwise it returns false. |
| IsPublic (int mod) | This method returns true if the integer parameter contains the public modifier, otherwise it returns false. |
| is static (int mod) | This method returns true if the integer parameter contains the staticfp modifier, otherwise it returns false. |
| is synchronized (int mod) | This method returns true if the integer parameter contains the synchronized modifier, otherwise it returns false. |
| Istransient (int mod) | This method returns true if the integer parameter contains transient modifiers, otherwise it returns false. |
| IsVolatile (int mod) | This method returns true if the integer parameter contains volatile modifier, otherwise it returns false. |
| Method modifiers () | This method returns an int value OR-ing, which is used together with the source language modifiers that can be applied to the method. |
| Parameter modifiers () | This method returns an int value OR-ing, which is used together with the source language modifiers that can be applied to parameters. |
| Tostring (int mod) | This method returns a string describing the access modifier flag in the specified modifier. |

</figure>

**1。静态 int classModifiers():**

此方法在对可应用于类的访问修饰符执行“或”操作后返回一个整数值。

```java
Return type: Integer
```

## 爪哇

```java
// Implementation of classModifiers() Method
import java.lang.reflect.Modifier;

public class GFG {
    public static void main(String[] args)
    {
        System.out.println(Modifier.classModifiers());
        System.out.println(
            Modifier.toString(Modifier.classModifiers()));
    }
}
```

**输出**

```java
3103
public protected private abstract static final strictfp
```

**2。static int constructor modifiers()；**对可应用于构造函数的访问修饰符执行“或”操作后，返回一个整数值。

```java
Return type: Integer
```

## Java

```java
// Implementation of constructorModifiers() Method
import java.lang.reflect.Modifier;

public class GFG {
    public static void main(String[] args)
    {
        System.out.println(Modifier.constructorModifiers());
        System.out.println(Modifier.toString(
            Modifier.constructorModifiers()));
    }
}
```

**输出**

```java
7
public protected private
```

**3。static int fieldModifiers():** 对可应用于字段的访问修饰符执行 OR 操作后返回一个 int 值。

```java
Return type: Integer
```

## Java

```java
// Implementation of fieldModifiers() Method
import java.lang.reflect.Modifier;

public class GFG {
    public static void main(String[] args)
    {
        System.out.println(Modifier.fieldModifiers());
        System.out.println(Modifier.toString(
            Modifier.fieldModifiers()));
    }
}
```

**输出**

```java
223
public protected private static final transient volatile
```