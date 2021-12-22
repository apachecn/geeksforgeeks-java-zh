# 常见 Java 编程面试问题|第二集

> 原文:[https://www . geesforgeks . org/common-question-Java-programming-interview-questions-set-2/](https://www.geeksforgeeks.org/commonly-asked-java-programming-interview-questions-set-2/)

在这篇文章中，讨论了一些最重要的 Java 面试问题和答案，让你在面试中处于领先地位。Java 是最流行、应用最广泛的编程语言和平台之一。Java 快速、可靠、安全。从桌面到网络应用，从科学超级计算机到游戏机，从手机到互联网，Java 被应用到每一个角落。这就是为什么你要想脱颖而出，就要掌握这些问题。

让我们先来看看一些最常被问到的 Java 面试问题，

*   [我们可以重载或者覆盖 Java 中的静态方法吗？](#Q1)
*   [为什么 java 中的主方法是静态的？](#Q2)
*   [如果从主方法中移除静态修改器会发生什么？](#Q3)
*   [在以下情况下，Java 中变量的作用域是什么？](#Q4)
*   [Java 中的“this”关键字是什么？](#Q5)
*   [什么是抽象类？Java 中的抽象类和 C++有什么相似或不同？](#Q6)
*   [每个类的超类是哪个类？](#Q7)
*   [我们可以重载 main()方法吗？](#Q8)
*   [什么是物体克隆？](#Q9)
*   [c++中的继承与 Java 有什么不同？](#Q10)
*   [为什么在 java 中通过改变返回类型无法实现方法重载？](#Q11)
*   [我们可以覆盖 Java 中的私有方法吗？](#Q12)
*   [什么是空白最终变量？](#Q13)
*   [Java 中的“super”关键字是什么？](#Q14)
*   [什么是 Java 中的静态变量？](#Q15)
*   [Java 中 HashMap 和 HashTable 的区别。](#Q16)
*   【Java 对象是如何存储在内存中的？
*   [Java 缺少哪些 C++特性？](#Q18)

![](img/fc2fde84664eb1a3e0545bd19c84467c.png)

让我们从 Java 面试问题集开始。

**Q1。我们可以在 java 中重载或覆盖静态方法吗？**

*   **覆盖:**覆盖与运行时多态性有关。子类(或派生类)在运行时提供超类(或基类)中方法的特定实现。
*   **重载:**重载与编译时(或静态)多态性有关。这个特性允许不同的方法有相同的名字，但是有不同的签名，特别是输入参数的数量和输入参数的类型。
*   **我们可以重载静态方法吗？**答案是**‘是’**。我们可以有两个或更多同名的静态方法，但是输入参数不同
*   **我们可以覆盖 java 中的静态方法吗？**我们可以在子类中声明具有相同签名的静态方法，但这不被认为是覆盖，因为不会有任何运行时多态性。因此答案是**‘不’**。静态方法不能被重写，因为方法重写只发生在方法的动态(即运行时)查找的上下文中。静态方法(按其名称)是静态查找的(即在编译时)。

更多阅读

**Q2。为什么 java 中的主方法是静态的？**
方法是静态的，因为否则会有歧义:应该调用哪个构造函数？尤其是你的班级长这样的话:

```java
public class JavaClass
{
  protected JavaClass(int x)
  {   }
   public void main(String[] args) 
   {

    }
}
```

JVM 应该调用新的 JavaClass(int)吗？它应该传递给 x 什么？如果没有，JVM 应该实例化 JavaClass 而不运行任何构造函数方法吗？因为这将特殊情况下你的整个类-有时你有一个实例还没有被初始化，你必须检查它在每一个可能被调用的方法。对于 JVM 来说，在调用入口点之前必须实例化一个类是没有意义的，因为有太多的边缘情况和歧义。这就是为什么 main 是静态的。

**Q3。如果从主方法中移除静态修饰符会发生什么？**
程序编译成功。但是在运行时抛出了一个错误“NoSuchMethodError”。

**Q4。下列情况下 Java 中** [**变量的范围是什么**](https://www.geeksforgeeks.org/variable-scope-in-java/) **？**

*   **成员变量**(类级范围) :成员变量必须在类内部(任何函数外部)声明。它们可以在课堂上的任何地方直接访问
*   **局部变量**(方法级作用域) :方法内部声明的变量具有方法级作用域，不能在方法外部访问。
*   **循环变量**(块作用域) :方法中一对括号“{”和“}”内声明的变量仅在括号内有作用域。

更多阅读

**Q5。什么是** [**爪哇**](https://www.geeksforgeeks.org/this-reference-in-java/) **中的“这个”关键词？**
在实例方法或构造函数中，这是对当前对象的引用，当前对象的方法或构造函数正在被调用。通过使用此，可以从实例方法或构造函数中引用当前对象的任何成员。
该关键词的用法

*   用于引用当前类实例变量。
*   调用当前类构造函数。
*   它可以在方法调用中作为参数传递。
*   它可以在构造函数调用中作为参数传递。
*   用于返回当前类实例。
*   用于调用当前类方法(隐式)

**Q6。什么是** [**抽象类**](https://www.geeksforgeeks.org/abstract-classes-in-java/) **？Java 中的抽象类和 C++有什么相似或不同？**
抽象类是包含一个或多个抽象方法的类。抽象方法是已声明但不包含实现的方法。抽象类不能被实例化，并且需要子类为抽象方法提供实现。

*   像 C++一样，在 Java 中，抽象类的实例不能被创建，但是我们可以有抽象类类型的引用。
*   像 C++一样，抽象类可以包含 Java 中的构造函数。并且在创建继承类的实例时调用抽象类的构造函数
*   在 Java 中，我们可以有一个抽象类，而不需要任何抽象方法。这允许我们创建不能被实例化，而只能被继承的类。
*   抽象类也可以有最终方法(不能被覆盖的方法)。例如，下面的程序编译并运行良好。

更多阅读

**Q7。哪个类是每个类的超类？**
对象类

**Q8。** [**我们能超载主()法吗？**](https://www.geeksforgeeks.org/gfact-48-overloading-main-in-java/)
爪哇的主要方法是无地法。除了 main()就像任何其他方法一样&可以以类似的方式重载之外，JVM 总是寻找方法签名来启动程序。

*   正常的主方法充当 JVM 开始执行程序的入口点。
*   我们可以在 Java 中重载主方法。但是当我们运行您的程序时，程序并不执行重载的 main 方法，我们只需要从实际的 main 方法中调用重载的 main 方法。

更多阅读

**Q9。什么是** [**物体克隆**](https://www.geeksforgeeks.org/cloning-in-java/) **？**
对象克隆是指创建原始对象的精确副本。如果一个类需要支持克隆，它必须实现 java.lang.Cloneable 接口，并从 Object 类重写 clone()方法。clone()方法的语法是:

```java
protected Object clone() throws CloneNotSupportedException
```

如果对象的类没有实现可克隆接口，那么它会抛出一个异常“CloneNotSupportedException”。

更多阅读

**Q10。C++中的** [**继承与 Java 有何不同？**](https://www.geeksforgeeks.org/comparison-of-inheritance-in-c-and-java/)

1.  在 Java 中，所有的类都直接或间接地继承自对象类。因此，Java 中总是有一个单一的类继承树，Object 类是树的根。
2.  在 Java 中，祖父母类的成员是不可直接访问的。详见[本 G-Fact](https://www.geeksforgeeks.org/accessing-grandparents-member-in-java-using-super/) 。
3.  在 Java 中，受保护成员访问说明符的含义有些不同。在 Java 中，类“A”的受保护成员在同一个包的其他类“B”中是可访问的，即使 B 不是从 A 继承的(它们都必须在同一个包中)。
4.  Java 使用*扩展*关键字进行继承。与 C++不同，Java 不提供像公共、受保护或私有这样的继承说明符。因此，我们不能在 Java 中更改基类成员的保护级别，如果某些数据成员在基类中是公共的或受保护的，那么它在派生类中仍然是公共的或受保护的。像 C++一样，基类的私有成员在派生类中是不可访问的。
    与 C++不同，在 Java 中，我们不需要记住那些继承规则，它们是基类访问说明符和继承说明符的组合。
5.  在 Java 中，默认情况下方法是虚拟的。在 C++中，我们显式地使用虚拟关键字。详见[本 G-Fact](https://www.geeksforgeeks.org/g-fact-43/) 。
6.  Java 使用单独的关键字*接口*作为接口，*抽象*关键字作为抽象类和抽象函数。
7.  与 C++不同，Java 不支持多重继承。一个类不能从多个类继承。一个类可以实现多个接口。
8.  在 C++中，父类的默认构造函数是自动调用的，但是如果我们要调用父类的参数化构造函数，就必须使用 [Initializer list](https://www.geeksforgeeks.org/when-do-we-use-initializer-list-in-c/) 。像 C++一样，父类的默认构造函数在 Java 中被自动调用，但是如果我们想调用参数化构造函数，那么我们必须使用 super 来调用父构造函数。

参见这里的例子

**Q11。为什么在 java 中改变返回类型不能实现方法重载？**
在 C++和 Java 中，如果函数只有返回类型不同，就不能重载。函数的返回类型不是由编译器生成的用于唯一标识每个函数的损坏名称的一部分。参数的数量，参数的类型&参数序列是用于为每个函数生成唯一的损坏名称的参数。正是基于这些独特的混乱名称，编译器可以理解调用哪个函数，即使名称相同(重载)。

**Q12。我们可以在 Java 中覆盖私有方法吗？**
不，私有方法不能被覆盖，因为它在任何其他类中都不可见。阅读[更多](https://www.geeksforgeeks.org/can-override-private-methods-java/)

**Q13。什么是** [**空白最终变量**](https://www.geeksforgeeks.org/blank-final-in-java/) **？**
Java 中的一个最终变量只能赋值一次，我们可以在声明中赋值，也可以稍后赋值。

```java
    final int i = 10;
    i = 30; // Error because i is final.
```

Java 中的一个**空白最终**变量是一个[最终](https://www.geeksforgeeks.org/g-fact-48/)变量，在声明过程中没有初始化。下面是一个简单的空白期末的例子。

```java
    // A simple blank final example 
    final int i;
    i = 30;
```

更多阅读

**Q14。** [**【超】在 java 中是什么关键词**](https://www.geeksforgeeks.org/super-keyword/) **？**
Java 中的 super 关键字是一个引用变量，用来引用父类对象。关键词“超级”带着继承的概念进入画面。无论何时创建子类的实例，都会隐式创建父类的实例，即由超级引用变量引用。
使用 java 超级关键词的各种场景:

*   super 用于引用直接父实例变量
*   super 用于调用父类方法
*   super()用于调用直接父构造函数

更多阅读

**Q15。什么是爪哇** **中的** [**静态变量？**
Java 中的 static 关键字主要用于内存管理。我们可以将 java static 关键字应用于变量、方法、块和嵌套类。static 关键字属于类，而不是类的实例。](https://www.geeksforgeeks.org/static-class-in-java/)

静态可以是:

*   变量(也称为类变量)
*   方法(也称为类方法)
*   街区
*   嵌套类

**Q16。** [**哈希表与 Java 中的哈希表**](https://www.geeksforgeeks.org/differences-between-hashmap-and-hashtable-in-java/) **的区别。**
1。HashMap 是非同步的。它不是线程安全的，没有适当的同步代码就不能在许多线程之间共享，而哈希表是同步的。它是线程安全的，可以与许多线程共享。
2。HashMap 允许一个空键和多个空值，而 Hashtable 不允许任何空键或空值。
3。如果不需要线程同步
[阅读更多](https://www.geeksforgeeks.org/differences-between-hashmap-and-hashtable-in-java/)，HashMap 通常比 HashTable 更受欢迎

**Q17。Java** [**对象如何存储在内存中**](https://www.geeksforgeeks.org/g-fact-46/) **？**
在 Java 中，所有对象都是在**堆**上动态分配的。这与 C++不同，在 c++中，对象可以在堆栈或堆上分配内存。在 C++中，当我们使用 new()分配对象时，对象是在 Heap 上分配的，否则在 Stack 上分配，如果不是全局或静态的话。
在 Java 中，当我们只声明一个类类型的变量时，只创建一个引用(不为对象分配内存)。要为对象分配内存，我们必须使用 new()。所以对象总是在堆上分配内存。更多阅读

**Q18。Java 中缺少哪些 C++特性？**
在看到答案之前，试着自己回答这个问题–[在这里](https://www.geeksforgeeks.org/c-features-missing-java/)。

另请参见:

*   【Java 面试常见问题|第 1 集
*   【Java 专业人士面试问题
*   [Java 选择题](https://www.geeksforgeeks.org/quiz-corner-gq/)
*   [练习编码题](https://practice.geeksforgeeks.org/)
*   [Java 文章](https://www.geeksforgeeks.org/java/)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。