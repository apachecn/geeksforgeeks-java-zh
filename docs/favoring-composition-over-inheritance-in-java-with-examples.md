# 在 Java 中支持合成而不是继承，示例

> 原文:[https://www . geesforgeks . org/favoring-composition-over-inheritation-in-Java-with-examples/](https://www.geeksforgeeks.org/favoring-composition-over-inheritance-in-java-with-examples/)

偏向[合成](https://www.geeksforgeeks.org/composition-in-java/)而不是[继承](https://www.geeksforgeeks.org/inheritance-in-java/)是[面向对象编程(OOP)的一个原则。](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/)类应该通过它们的组合实现多态行为和代码重用，而不是从基类或父类继承。为了获得更高的设计灵活性，设计原则说合成应该比继承更受青睐。

只有当子类“是”超类时，才应该使用继承。不要使用继承来获得代码重用。如果没有“is a”关系，则使用组合进行代码重用。

**Java 和 OOP 中偏向组合而非继承的原因:**

1.  The fact that Java does not support multiple inheritance is one reason why Java prefers combination to inheritance. Because you can only extend one class in Java, but if you need multiple functions, such as reading and writing character data into a file, you need Reader and Writer functions. Making them private members makes your job easier. This is the so-called combination.
2.  Provide better vocational test ability than inheritance. If a class consists of another class, for testing purposes, you can easily construct a mock object to represent a composite class. This privilege is not granted by inheritance.
3.  Although both composition and inheritance allow code reuse, one of the disadvantages of inheritance is that it destroys encapsulation. If a subclass relies on the actions of the superclass to realize its functions, it will suddenly become vulnerable. When the superclass behavior changes, the subclass function can be destroyed without any modification.
4.  Among the timeless classic design patterns, the Gang of Four listed several object-oriented design patterns: reusable elements of object-oriented software, recombination and light inheritance. The design pattern is a classic example, in which composition and delegation are used to modify the behavior of the context without involving the context code. Because Context uses combinations to carry policies, it is very simple to have a new policy implementation at runtime, instead of getting it through inheritance.
5.  Another reason why composition is superior to inheritance is flexibility. If you use Composition, you have enough flexibility to replace a better updated version of the Composed class implementation. One example is the use of the comparator class, which provides features for comparison.

**继承:**

继承是在面向对象编程中实现对象之间关系的设计策略。extends 关键字用于在 Java 中实现继承。

```
class Person {
 String title;
 String name;
 int age;
}

class Employee extends Person {
 int salary;
 String title;
}
```

在上面的例子中，雇员“是”人或从人继承。所有继承关系都是“是-a”关系。员工还隐藏了“人员”的标题属性，即“员工”。标题将返回员工的标题，而不是人员。

**成分:**

在面向对象编程中，组合是执行对象之间关系的架构策略。Java 合成是使用来自其他对象的实例变量完成的。

```
class Person {
 String title;
 String name;
 int age;

 public Person(String title, String name, String age) {
    this.title = title;
    this.name = name;
    this.age = age;
 }

}

class Employee {
 int salary;
 private Person person;

 public Employee(Person p, int salary) {
     this.person = p;
     this.salary = salary;
 }
}

Person p = new Person ("Mr.", "Kapil", 25);
Employee kapil = new Employee (p, 100000);
```

该组合物通常是“具有”或“使用”关系。这里，雇员类有一个人。它不从 Person 继承，而是将 Person 对象传递给它，这就是它“有”Person 的原因。

**合成重于继承**

现在假设您想要创建一个 Manager 类型，那么您最终会得到下面的语法，这在 java 中是不允许的(在 java 中不允许多重继承) :

//不允许多重继承

```
class Manager extends Person, Employee {
}
```

现在我们必须使用下面的语法来支持合成而不是继承:

```
Class Manager {
 public string title;
 public Manager(Person p, Employee e)
 {
    this.title = e.title;
 }
}
```