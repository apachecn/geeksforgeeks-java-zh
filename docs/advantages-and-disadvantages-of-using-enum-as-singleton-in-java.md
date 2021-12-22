# 在 Java 中使用 Enum 作为 Singleton 的优缺点

> 原文:[https://www . geeksforgeeks . org/使用枚举作为 java 中的单例的优缺点/](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-using-enum-as-singleton-in-java/)

[Enum](https://www.geeksforgeeks.org/enum-in-java/)Singleton 是一种使用 Enum 的新方法，只有一个实例来实现 Java 中的 [Singleton 模式](https://www.geeksforgeeks.org/singleton-design-pattern/)。虽然在 Java 中已经有了很长时间的 Singleton 模式，但是 Enum Singletons 是一个相对较新的术语，自从从 Java 5 开始实现 Enum 作为一个关键字和函数以来就一直在使用。

**将枚举用作 Singleton 的优势:**

**1。Enum Singletons 很容易编写:**如果您在 Java 5 之前就已经编写了 singleton，这是目前为止最大的好处，因为您意识到即使使用双重检查锁定，也可以拥有多个实例。虽然这个问题是通过改进 Java 内存模型和保证从 Java 5 开始的易失性变量来解决的，但是对于许多初学者来说仍然很难编写。

与同步的双重检查锁定相比，枚举单例非常容易。如果您不认为带有双重检查锁定的传统单例和枚举单例的以下代码是比较的:

在 Java 中单独使用枚举:默认情况下，创建枚举实例是线程安全的，但是任何其他枚举方法都是程序员的责任。

```
public enum EasySingleton{
  INSTANCE;
}
```

可以通过 EasySingleton 访问。实例，比在 Singleton 上调用 getInstance()函数简单得多。

**2。枚举单例自行处理序列化**

传统 Singleton 的另一个问题是，一旦实现了可序列化的接口，它们就不再是 Singleton 了，因为方法 readObject()总是返回一个新的实例，就像 Java 构造函数一样。通过使用 readResolve()方法并丢弃新创建的实例，可以通过替换 Singleton 来避免这种情况，如下例所示:

```
 private Object readResolve(){
      return INSTANCE;
  }
```

如果您的单例类保持状态，这可能会变得更加复杂，因为您需要使它们成为瞬态的，但是 JVM 保证了枚举单例的序列化。

**3。枚举实例的创建是线程安全的**

默认情况下，枚举实例是线程安全的，您不需要担心双重检查锁定。

总之，在 Java 5 世界中，考虑到序列化和线程安全得到保证，并且有一些代码行枚举，Singleton 模式是创建 Singleton 的最佳方式。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the example 
// of using Enum as Singleton

enum SingletonEnum {
    INSTANCE;
    int value;

    public int getValue() {
        return value;
    }

    public void setValue(int value) {
        this.value = value;
    }
}
 class Main {

    public static void main(String[] args) {
        SingletonEnum singleton = SingletonEnum.INSTANCE;

        System.out.println(singleton.getValue());
        singleton.setValue(2);
        System.out.println(singleton.getValue());
    }
}
```

**Output**

```
0
2

```

**将枚举作为单例使用的缺点:**

**1。编码约束**

在常规类中，有些事情可以实现，但在枚举类中是禁止的。例如，访问构造函数中的静态字段。因为他是在一个特殊的层次上工作，程序员需要更加小心。

**2。可串行化**

对于单例，有状态是非常常见的。一般来说，这些单例不应该是可序列化的。没有真实的例子表明将有状态的单例从一个虚拟机传输到另一个虚拟机是有意义的；单例意味着“在虚拟机中是唯一的”，而不是“在宇宙中是唯一的”

如果序列化对于有状态的单例真的有意义，那么单例应该明确而准确地指定在另一个虚拟机中反序列化可能已经有相同类型的单例意味着什么。

> 我们在 enum 上保存了一些代码行，但是价格太高，我们必须承担所有的包袱和 enum 限制，我们无意中继承了 enum 的“特性”，从而产生了意想不到的后果。一个缺点是唯一所谓的好处——自动可串行化。