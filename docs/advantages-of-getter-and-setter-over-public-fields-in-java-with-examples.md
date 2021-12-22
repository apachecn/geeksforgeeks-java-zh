# Java 中 getter 和 setter 相对于公共字段的优势举例

> 原文:[https://www . geeksforgeeks . org/getter-and-setter-over-public-field-in-Java-with-examples/](https://www.geeksforgeeks.org/advantages-of-getter-and-setter-over-public-fields-in-java-with-examples/)

提供 getter 和 setter 方法来访问 Java 中的任何类字段起初看起来毫无意义，这仅仅是因为您可以将该字段公开，并且它在任何地方的 Java 程序中都是可用的。实际上，很多程序员在早期都是这样做的，但是一旦你开始从企业应用程序或生产代码的角度考虑，你就可以开始看到它会带来多少维护麻烦。

根据软件开发生命周期流程，由于软件在维护上花费的时间比开发时间多，因此将易于维护作为开发目标之一是值得的。Java 编码的最佳实践之一就是在 Java 中简单地使用 getter 和 setter 方法。

**下面是 getter 和 setter 相对于公共领域的一些优势**

1.getter 和 setter 方法让您可以集中控制如何初始化某个字段并将其提供给客户端，这使得验证和调试变得更加容易。要查看哪个线程正在访问以及哪些值将被输出，您可以轻松地放置断点或打印语句。

2.通过包含 getter 和 setter 并遵循 java bean 命名约定，使字段成为私有字段，可以使用许多开源库和模块(如显示标签)来访问该类。它结合使用反射和 Java bean 命名约定来动态加载和访问字段。

3.您给了子类一个用 getter 和 setter 重写这个方法的机会，并返回在子类的上下文中更有意义的内容。

4.通过使用替代表示公开属性来隐藏属性的内部表示。

5.允许继承方通过重写 getter/setter 方法来更改属性的行为和公开方式的语义。

## 爪哇

```java
class Person {
    // private = restricted access
    private String name;

    // Getter
    public String getName() { return name; }

    // Setter
    public void setName(String newName)
    {
        this.name = newName;
    }
}

class Main {
    public static void main(String[] args)
    {
        Person person = new Person();
        // Set the value of the name variable to "kapil"
        person.setName("kapil");
        System.out.println(person.getName());
    }
}
```

**输出**

```java
kapil

```