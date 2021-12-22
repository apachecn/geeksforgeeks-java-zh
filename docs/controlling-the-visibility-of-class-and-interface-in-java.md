# 控制 Java 中类和接口的可见性

> 原文:[https://www . geesforgeks . org/控制 java 中类和接口的可见性/](https://www.geeksforgeeks.org/controlling-the-visibility-of-class-and-interface-in-java/)

维护是软件开发的重要方面之一，经验表明，维护组件可见性低的软件比暴露组件更多的软件更容易维护。你不会提前知道它，但是当重新设计应用程序时，你会非常想念它。

您最终会修补并重复同样的错误，因为维护向后兼容性是许多应用程序的必备要求。您不会做太多，因为类和接口与许多其他应用程序紧密集成。Java 总是优先考虑封装，从一开始就提供支持的访问修饰符。通过将它们公开，包私有或私有提供了监视某种类型(如类或接口)的可见性的方法。

**下面是一些控制能见度的规则:**

1.  顶级类(名称与包含它的 Java 源文件相同的类)也可以是公共包或私有包(没有访问修饰符)，不能是私有包。私有、公共或包私有只能是嵌套类。
2.  一个公共类对所有人都是可访问的，也是最可见的，尽量只公开关键接口，在你相信它是完整的和成熟的之前，不要让实现公开。
3.  另一方面，私有类型不太可见，在 Java 中，只有嵌套类或接口可以是私有的。你可以完全控制这个类，用经验、新技术、工具和重新设计来改变它的行为，因为它是最不可见的。
4.  Package-private 可见性是一个聪明的中途，也是默认可见性，没有 package-private 这样的关键字，相反，如果你没有任何访问修饰符，因为 Java 认为它是 package-private，然后使它只在同一个包上可见。
5.  如果类和接口只在同一个包中在其他类之间共享，那么将它们设为包私有。由于客户无法联系到他们，因此更换他们是合理安全的。

**如何控制 Java 中** [**类**](https://www.geeksforgeeks.org/classes-objects-java/) **或** [**接口**](https://www.geeksforgeeks.org/interfaces-in-java/) **的可见性？**

除了使用访问修饰符降低类或接口的可见性之外，根据您的运行时环境，还有许多其他方法可以做到这一点。在组件级别，如 Websphere、Weblogic 或应用服务器中的 JBoss，接口类可能被代理或包装以减少外部可见性。

不管你做什么，仍然会有某些类型需要暴露给外部世界，但是你总是可以用代理或者包装器来处理它们。尽管客户端程序会加载代理实现类，但通常会获得不可变的代理或包装。

例如，Java Servlet API(javax . Servlet)getservlet context()返回 javax.servlet.ServletContext 的一个实现，它通常是一个不可变的代理来满足 ServletContext 框架的承诺。javax.servlet.ServletContext 规范的单独版本很可能在应用服务器上运行。

在其他外部可访问接口的实现中也可以使用类似的模式，例如 Javax.ejb.EJBContext、Javax.ejb.TimerService、ServletRequest、ServletResponse 等。为了支持这些全局接口，各种应用服务器可以使用各种应用。

**控制 Java 类可见性的 JDK 示例**

[EnumSet 类](https://www.geeksforgeeks.org/enumset-class-java/)是管理可见性的另一个引人入胜的例子。为了防止实例化，Java 设计者创建了抽象类，并提供了工厂方法作为创建该类实例的唯一方法，例如 EnumSet.of()或 EnumSet.noneOf()中的方法。

在内部，以 RegularEnumSet 和 JumboEnumSet 的形式，它们有两个独立的实现，通过静态工厂方法根据主宇宙的大小自动选择。

例如，如果枚举中的值的数量小于 64，则使用正则枚举集，否则，返回 JumboEnumSet 实例。这种设计的美妙之处在于，包私有意味着消费者对这些实现一无所知。

<figure class="table">

| 修饰语 | 描述 |
| --- | --- |
| 默认 | 声明仅在包中可见(包私有) |
| 私人的 | 声明仅在类中可见 |
| 保护 | 声明在包或所有子类中都是可见的 |
| 公众 | 宣言随处可见 |

</figure>

**私有访问修饰符**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for showcasing the behaviour
// of Private Access Modifier

class Data {

   // private variable
   private String name;
}
public class Main {
   public static void main(String[] main){

       // create an object of Data
       Data d = new Data();

       // access private variable and field from another class
       d.name = "Kapil";
   }
}
```

**输出:**

```java
Main.java:18: error: name has private access in Data
     d.name = "Programiz";
      ^
```

在上面的例子中，我们已经声明了一个名为 name 的私有变量和一个名为 display()的私有方法。当我们运行程序时，我们会得到上面的错误:

**受保护访问修饰符**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for showcasing the behaviour
// of Protected Access Modifier

class Animal {

    // protected method
    protected void display() {
        System.out.println("I am an animal");
    }
}

class Dog extends Animal {

    public static void main(String[] args) {

        // create an object of Dog class
        Dog dog = new Dog();

        // access protected method
        dog.display();
    }
}
```

**Output**

```java
I am an animal
```

**公共访问修饰符:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for showcasing the behaviour
// of Public Access Modifier

// Animal.java file
// public class

class Animal {

    // public variable
    public int legCount;

    // public method
    public void display() {
        System.out.println("I am an animal.");
        System.out.println("I have " + legCount + " legs.");
    }
}

// Main.java
public class Main {
    public static void main( String[] args ) {
        // accessing the public class
        Animal animal = new Animal();

        // accessing the public variable
        animal.legCount = 4;
        // accessing the public method
        animal.display();
    }
}
```

**Output**

```java
I am an animal.
I have 4 legs.
```