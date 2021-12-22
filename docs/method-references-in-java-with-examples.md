# Java 中的方法引用，带示例

> 原文:[https://www . geesforgeks . org/method-references-in-Java-with-examples/](https://www.geeksforgeeks.org/method-references-in-java-with-examples/)

[Java 中的函数接口](https://www.geeksforgeeks.org/functional-interfaces-java/)和 [Lambda 函数](https://www.geeksforgeeks.org/lambda-expressions-java-8/)是掌握 Java 中方法引用的先决条件。众所周知，[方法](https://www.geeksforgeeks.org/methods-in-java/)是执行某个特定任务并将结果返回给调用者的语句的集合。一个方法可以执行一些特定的任务而不返回任何东西。方法允许我们在不重新键入代码的情况下重用代码。在本文中，我们将看到如何将方法用作值。

在 Java 8 中，我们可以像使用对象或基元值一样使用方法，并且可以将它们视为变量。该示例将函数显示为 java 中的变量:

```
// This square function is a variable getSquare. 
Function<Integer, Integer> getSquare = i -> i * i; 
```

```
SomeFunction(a, b, getSquare); 
// Pass function as a argument to other function easily 
```

有时，lambda 表达式只调用现有的方法。在这些情况下，通过名称来引用现有方法看起来很清楚。方法引用可以做到这一点，与 lambda 表达式相比，它们紧凑、易于阅读。方法引用是仅包含一个方法调用的 lambda 表达式的简写语法。下面是

**泛型语法:**方法引用

**A.** 指对象中的方法

```
Object :: methodName 
```

**B.** 打印列表中的所有元素

下面是一个 lambda 表达式的示例，该表达式在整个执行过程中只调用一个方法:

```
list.forEach(s -> System.out.println(s));  
```

**C.** 简写打印列表中所有元素

为了使代码清晰紧凑，在上面的示例中，可以将 lambda 表达式转换为方法引用:

```
list.forEach(System.out::println);  
```

方法引用只能用于替换 lambda 表达式的单个方法。如果使用 lambda 表达式而不是匿名类，并且可以使用方法引用而不是使用单个函数 lambda 表达式来实现同样的效果，那么代码会更加清晰和简短。一般来说，不必将参数传递给方法引用。

以下示例是关于对列表中的元素执行一些操作并添加它们。要对元素执行的操作是一个函数参数，调用方可以相应地传递。

插图:

```
public int transformAndAdd(List<Integer> l,
                           Function<Integer, Integer> ops) {
    int result = 0;
    for (Integer s : l)
        result += f.apply(s);

    return results;
}

// Operations utility class
class OpsUtil {

    // Method 1
    // To half the variable
    public static Integer doHalf(Integer x) {
        return x / 2;
    }

    // Method 2
    // Square up the integer number
    public static Integer doSquare(Integer x) {

        return x * x;
    }

    ... many more operations...
}
```

下面是调用上述方法的方法，如下所示:

```
List<Integer> list = new ArrayList<>();
// Add some element to list
...
// Using an anonymous class
transformAndAdd(list, new Function<Integer, Integer>() {
    public Integer apply(Integer i) {
        // The method
        return OpsUtil.doHalf(i);
    }
});

// Using a lambda expression
tranformAndAdd(list, i -> OpsUtil.doHalf(i));

// Using a method reference
tranformAndAdd(list, OpsUtil::doHalf);
```

## 方法引用的类型

有以下四种类型方法引用:

1.  静态方法引用。
2.  特定对象的实例方法引用。
3.  特定类型的任意对象的实例方法引用。
4.  构造函数引用。

为了研究所有这些类型，我们将考虑使用比较器排序的一个常见示例，如下所示:

### 类型 1:对静态方法的引用

如果 Lambda 表达式类似于:

> //如果一个 lambda 表达式只调用一个类的静态方法
> (args)->class . static method(args)

那么方法参考就像:

> //速记如果一个 lambda 表达式只是调用一个类的静态方法
> Class::staticMethod

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate How One can use
// Static method reference
// To Sort with Custom Comparator

// Importing required classes
import java.io.*;
import java.util.*;

// Class 1
// Helper class
// Object need to be sorted
class Person {

    private String name;
    private Integer age;

    // Constructor
    public Person(String name, int age)
    {
        // This keyword refers to current instance itself
        this.name = name;
        this.age = age;
    }

    // Getter-setters
    public Integer getAge() { return age; }
    public String getName() { return name; }
}

// Class 2
// Main class
public class GFG {

    // Method 1
    // Static method to compare with name
    public static int compareByName(Person a, Person b)
    {
        return a.getName().compareTo(b.getName());
    }

    // Method 2
    // Static method to compare with age
    public static int compareByAge(Person a, Person b)
    {
        return a.getAge().compareTo(b.getAge());
    }

    // Method 3
    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty ArrayList of user-defined type
        // List of person
        List<Person> personList = new ArrayList<>();

        // Adding elements to above List
        // using add() method
        personList.add(new Person("vicky", 24));
        personList.add(new Person("poonam", 25));
        personList.add(new Person("sachin", 19));

        // Using static method reference to
        // sort array by name
        Collections.sort(personList, GFG::compareByName);

        // Display message only
        System.out.println("Sort by name :");

        // Using streams over above object of Person type
        personList.stream()
            .map(x -> x.getName())
            .forEach(System.out::println);

        // Now using static method reference
        // to sort array by age
        Collections.sort(personList, GFG::compareByAge);

        // Display message only
        System.out.println("Sort by age :");

        // Using streams over above object of Person type
        personList.stream()
            .map(x -> x.getName())
            .forEach(System.out::println);
    }
}
```

**Output:** 

```
Sort by name :
poonam
sachin
vicky
Sort by age :
sachin
vicky
poonam
```

### **类型 2:** 引用特定对象的实例方法

如果 Lambda 表达式类似于:

> //如果 lambda 表达式只调用对象的默认方法
> 
> args-> obj . instance method(args)

那么方法参考就像:

> //速记如果 lambda 表达式只调用对象的默认方法
> 
> obj::instanceMethod

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate How One can use
// Static method reference
// To Sort with Custom Comparator
// But using object method reference

// Importing required classes
import java.io.*;
import java.util.*;

// Class 1
// Helper class
// Object need to be sorted
class Person {

    // Attributes of a person
    private String name;
    private Integer age;

    // Constructor
    public Person(String name, int age)
    {
        // This keyword refers to current object itself
        this.name = name;
        this.age = age;
    }

    // Getter-setter methods
    public Integer getAge() { return age; }
    public String getName() { return name; }
}

// Class 2
// Helper class
// Comparator class
class ComparisonProvider {

    // Method 1
    // To compare with name
    public int compareByName(Person a, Person b)
    {
        return a.getName().compareTo(b.getName());
    }

    // Method 2
    // To compare with age
    public int compareByAge(Person a, Person b)
    {
        return a.getAge().compareTo(b.getAge());
    }
}

// Class 3
// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty ArrayList of user-defined type
        // List of person
        List<Person> personList = new ArrayList<>();

        // Adding elements to above object
        // using add() method
        personList.add(new Person("vicky", 24));
        personList.add(new Person("poonam", 25));
        personList.add(new Person("sachin", 19));

        // A comparator class with multiple
        // comaparator methods
        ComparisonProvider comparator
            = new ComparisonProvider();

        // Now using instance method reference
        // to sort array by name
        Collections.sort(personList,
                         comparator::compareByName);

        // Display message only
        System.out.println("Sort by name :");

        // Using streams
        personList.stream()
            .map(x -> x.getName())
            .forEach(System.out::println);

        // Using instance method reference
        // to sort array by age
        Collections.sort(personList,
                         comparator::compareByAge);

        // Display message only
        System.out.println("Sort by age :");

        personList.stream()
            .map(x -> x.getName())
            .forEach(System.out::println);
    }
}
```

**Output:** 

```
Sort by name :
poonam
sachin
vicky
Sort by age :
sachin
vicky
poonam
```

### **类型 3:** 对特定类型的任意对象的实例方法的引用

如果 Lambda 表达式类似于:

> //如果 lambda 表达式只调用 ObjectType 的实例方法
> 
> (obj、args)-(obj . instance method)(args)

那么方法参考就像:

> //如果 lambda 表达式只调用 ObjectType 的实例方法，则速记
> 
> ObjectType::instanceMethod

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate how One can use
// Instance type method reference to
// sort with custom comparator

// Importing required classes
import java.io.*;
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty ArrayList of user defined type
        // List of person
        List<String> personList = new ArrayList<>();

        // Adding elements to above object of List
        // using add() method
        personList.add("vicky");
        personList.add("poonam");
        personList.add("sachin");

        // Method reference to String type
        Collections.sort(personList,
                         String::compareToIgnoreCase);

        // Printing the elements(names) on console
        personList.forEach(System.out::println);
    }
}
```

**Output:** 

```
poonam
sachin
vicky
```

### **类型 4:** 构造函数方法引用

如果 Lambda 表达式类似于:

> //如果一个 lambda 表达式只是创建一个对象
> (args) - >新的类名(args)

那么方法参考就像:

> //速记如果一个 lambda 表达式只是创建一个对象
> ClassName::new

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate How We can Use
// constructor method reference

// Importing required classes
import java.io.*;
import java.nio.charset.Charset;
import java.util.*;
import java.util.function.*;

// Object need to be sorted
class Person {
    private String name;
    private Integer age;

    // Constructor
    public Person()
    {
        Random ran = new Random();

        // Assigning a random value
        // to name
        this.name
            = ran
                  .ints(97, 122 + 1)
                  .limit(7)
                  .collect(StringBuilder::new,
                           StringBuilder::appendCodePoint,
                           StringBuilder::append)
                  .toString();
    }

    public Integer getAge()
    {
        return age;
    }
    public String getName()
    {
        return name;
    }
}

public class GFG {

    // Get List of objects of given
    // length and Supplier
    public static <T> List<T>
    getObjectList(int length,
                  Supplier<T> objectSupply)
    {
        List<T> list = new ArrayList<>();

        for (int i = 0; i < length; i++)
            list.add(objectSupply.get());
        return list;
    }

    public static void main(String[] args)
    {

        // Get 10 person by supplying
        // person supplier, Supplier is
        // created by person constructor
        // reference
        List<Person> personList
            = getObjectList(5, Person::new);

        // Print names of personList
        personList.stream()
            .map(x -> x.getName())
            .forEach(System.out::println);
    }
}
```

**Output:** 

```
vzskgmu
iupltfx
kocsipj
lyvhxsp
hbdphyv
```

> **结论:**如上所述，如果一个 lambda 表达式只调用一个现有的方法，那么使用方法引用可以使代码更加易读和清晰。在使用 Java 流时，我们可以用 Java8 Lambda 和方法引用做更多的事情。