# Groovy 和 Java 的区别

> 原文:[https://www . geesforgeks . org/groovy 和 java 的区别/](https://www.geeksforgeeks.org/difference-between-groovy-and-java/)

**Groovy** 是一种强大的、可选类型的动态语言，用于在 **Java** 平台上开发应用程序，其语法类似于 **Java** 。它的打字规则是强有力的，静态的，动态的。Groovy 最棒的地方在于它扩展了 JDK，接受了 Java 代码。 **Groovy** 既可以作为编程语言，也可以作为脚本语言。 **Groovy** 是 **Java** 的超集，这意味着 **Java** 程序将在 **Groovy** 环境中运行，但反过来可能会也可能不会。而 **Java** 是强静态类型的编程语言。

**1。默认导入:**

*   在 **Groovy** 中，默认导入一些通用包和类:
    *   java.io.*
    *   java.lang.*
    *   java.math.BigDecimal
    *   java.math.BigInteger
    *   java.net.*
    *   java.util.*
    *   groovy.lang.*
    *   groovy.util.*
*   其中在 **Java** 中默认只导入 java.lang.*包。

**2。额外关键词:**

*   **作为**，**定义**，**特质**这些都是 **Groovy** 中多余的关键词。
*   您不能将此关键字用作变量名。

**3。默认访问修饰符:**

*   在 **Java** 中，默认的访问修饰符是**包**，也就是说，如果你没有为字段、方法或类指定访问修饰符，它就变成了包私有。
*   在 **Groovy** 中，默认为**公共**。

**4。吸气剂和沉降剂:**

*   在 **Java** 中，你需要为字段提供 getters 和 setters 方法，特别是如果你遵循 Java Beans 命名约定，使用工具和库，使用 Reflection 动态访问和变异 bean 属性。
*   在 **Groovy** 中，会自动为类成员生成 getters 和 setters。

**5。点分隔符:**

*   在 **Java** 中，我们使用点运算符(。)来访问类的属性
*   **Groovy** 也支持点运算符，但与**不同的是，Java** 调用实际上要经过 getters 和 setters，这是在 **Groovy** 中自动生成的

**6。**在 **Groovy** 分号**(；)**是可选的，只有喜欢或者想一行写多条语句的时候才使用。

**7。对于循环:**

*   正如我们在大多数任务中使用 for 循环一样，在 **Groovy** 中声明 for 循环要容易得多，我们可以将 for 循环声明为

```java
for(j in 0..4){ print j } 
0.upto(3) { print "$it" } 
4.times{ print "$it" }    
```

*   其中 **Java**

```java
 for(int i=0;i<=5;i++){
  System.out.println(i);
 }
```

**8。安全导航操作员:**

*   在 **Java** 中我们要执行一些操作来检查空对象，避免空指针异常。

```java
String str = null;
if(str != null){
    System.out.println(str.reverse());
}
```

*   但是在 **Groovy** 中我们可以直接做如下

```java
println  str.reverse()
```

**9。主要()方法:**

*   在 **Java** 中，需要主方法来使一个类可执行
*   在 **Groovy** 中，你不需要这个。由于 **Groovy** 是一种脚本语言，所以每个程序都自动有一个名为 Script 的包装类。
*   **10。布尔求值:**
    **Groovy** 自动将表达式求值为布尔。

```java
def str = “test”
if(str){ println str }
```

**11 时。数组声明:**

*   如果你想在 **Java** 中创建字符串数组，那么你必须使用花括号“{}”。
    在**爪哇**:

```java
String[] testArray = {"A", "B", "C"};
```

*   而在 **Groovy** 中，我们可以使用方括号。"[]".
    在**常规**中:

```java
String[] testArray = ["A", "B", "C"]
```

**总结 Java 和 Groovy 的区别**

<figure class="table">

| Java 语言(一种计算机语言，尤用于创建网站) | 绝妙的 |
| --- | --- |
| 它是在 JDK 开发的，在 JVM 上运行 | 编译成 JVM 字节码，兼容 **Java** 平台 |
| 它被用作编程和面向对象语言 | 它被用作编程和脚本语言 |
| 在 **Java** 默认访问修饰符**包** | 在 **Groovy** 默认访问修饰符**公共** |
| 在 **Java** 中，您需要为字段提供 getters 和 setters 方法，尤其是如果您遵循**Java**bean 命名约定的话 | 在 **Groovy** 中，为类成员自动生成获取器和设置器 |
| 在 **Java 中**分号是强制的 | 在 **Groovy** 中，分号是可选的 |
| 在 **Java** 中，默认只导入 **Java** .lang.*包 | 在 **Groovy** 中，默认导入常用包 |
| **Java** 有原语数据类型和包装类来隐式或显式地执行装箱和取消装箱 | 在 **Groovy** 中，一切都是对象，并且只使用对象，因此没有自动装箱或取消装箱的概念 |
| **Java** 要求类内部的主方法运行程序 | **Groovy** 不需要任何主方法或方法的入口点来运行类或任何程序 |

</figure>