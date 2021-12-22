# Java 中的泛型类

> 原文:[https://www.geeksforgeeks.org/generic-class-in-java/](https://www.geeksforgeeks.org/generic-class-in-java/)

引入 Java 泛型是为了处理类型安全的对象。它使代码 stable.Java 泛型方法和类，使程序员能够用一个单一的方法声明，一组相关的方法，一组相关的类型**。** **泛型**还提供**编译时类型安全**，允许程序员在编译时捕捉无效类型。 **通用**是指**参数化** 类型。使用泛型的想法是允许任何数据类型  到无论是**整数、字符串** 、 **还是任何** 用户定义的 **数据类型**，并且可以创建使用不同数据类型的类。

泛型类只是意味着该类中的**项或函数**可以用参数(例如**T**)**T5】来概括，以指定我们可以添加任何类型作为参数来代替 **T** ，如整数、字符、字符串、双精度或任何其他用户定义的类型。**

**例:**单一类型参数

```
class Solution<T>
{
   T data;
   public static T getData(){
       return data;
   }
}

```

**示例:**多个类型参数

```
public class Pair<K, V> {

    private K key;
    private V value;

    public Pair(K key, V value) {
    this.key = key;
    this.value = value;
    }

    public K getKey()    { return key; }
    public V getValue() { return value; }
}

```

在这个例子中，我们可以多次使用这个类的对象或实例，使用不同的参数作为 **T** 类型。如果我们希望数据是 **int** 类型， **T** 可以替换为整数，字符串、字符、浮点或任何用户定义的类型也是如此。a泛型类的声明几乎与a非泛型类的声明相同，只是类名后面有一个类型参数段。泛型类的类型参数部分可以有一个或多个用逗号分隔的类型参数。

我们可以编写一个可以用不同类型的参数调用的单一泛型方法声明。根据传递给泛型方法的参数类型，编译器会适当地处理每个方法调用。以下是定义泛型方法的规则:

*   All generic method declarations have a type parameter part, which is indicated by angle brackets **< >** and is located before the return type of the method.
*   Each type parameter segment can contain one or more type parameters **separated by commas.** Type parameter or type variable is an identifier that specifies the generic type name.
*   The type parameter can be used to declare that the return type is , which is called **and the actual type argument** .
*   The body of a generic method is declared to be similar to that of any non-generic method. It is important to note that is that type parameter can only represent **reference type, but not primitive type** (such as int, double , and char).

### Java 泛型的优势

**1。类型安全:**在泛型中只能持有一种类型的对象。

**2。** **不需要打型**:不需要打型。

**例:**

```
***Before Generics*** 
     List l= new ArrayList();
 l.add("India");
 String s = (String) list.get(0);     // typecasting

***After Generics, typecasting of the object is not required***
 List<String> l = new ArrayList<String>(); 
 l.add("hello"); 
 String s = list.get(0); 

```

**3。** **编译时检查**:它在编译时检查与泛型相关的数据类型的所有错误，因此在运行时不会出现 问题。

```
List<String> list = new ArrayList<String>(); 
list.add("hello"); 
list.add(32);   //Compile Time Error 

```

对于泛型类的实例

```
BaseType <Type> object = new BaseType <Type>();

```

**注意:**在参数类型中，我们不能使用 int、char、float 、等原语。

**示例:**

## Java

```
// Java program to show the
// instance of a generic class

// Generic Classes

// we use <> to specify parameter
// type and we can add any datatype
// like Integer, Double, String,
// Character or any user defined
// Datatype

// Every time when we need to make an
// object of another datatype of this
// generic class , we need not to make
// the whole class of that datatype again
// instead we can simply change the
// parameter/Datatype in braces <>

public class Area<T> {

    // T is the Datatype like String,
    // Integer of which Parameter type,
    // the class Area is of
    private T t;

    public void add(T t)
    {
        // this.t specify the t variable inside
        // the Area Class whereas the right hand
        // side t simply specify the value as the
        // parameter of the function add()
        this.t = t;
    }

    public T get() { return t; }

    public void getArea() {}

    public static void main(String[] args)
    {
        // Object of generic class Area with parameter Type
        // as Integer
        Area<Integer> rectangle = new Area<Integer>();
        // Object of generic class Area with parameter Type
        // as Double
        Area<Double> circle = new Area<Double>();
        rectangle.add(10);
        circle.add(2.5);
        System.out.println(rectangle.get());
        System.out.println(circle.get());
    }
}
```

**输出**

```
10
2.5

```