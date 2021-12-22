# Java 中的 equals()和 hashCode()方法

> 原文:[https://www.geeksforgeeks.org/equals-hashcode-methods-java/](https://www.geeksforgeeks.org/equals-hashcode-methods-java/)

Java.lang.object 定义了两个非常重要的方法:public boolean equals(Object obj)和 public int hashCode()。

**等于()方法**

在 java 中，equals()方法用于比较两个对象的相等性。可以用两种方式比较这种相等性:

*   **浅比较:**equals 方法的默认实现是在 Java.lang.Object 类中定义的，它只是检查两个 Object 引用(比如 x 和 y)是否引用同一个 Object。即它检查 x == y。由于 Object 类没有定义其状态的数据成员，因此也称为浅层比较。
*   **深度比较:**假设一个类提供了它自己的 equals()方法的实现，以便比较该类的对象和对象的状态。这意味着对象的数据成员(即字段)要相互比较。这种基于数据成员的比较称为深度比较。

**语法:**

```java
public boolean equals  (Object obj)

// This method checks if some other Object
// passed to it as an argument is equal to 
// the Object on which it is invoked.

```

**Object 类的 equals()方法的一些原理:**如果某个其他对象等于某个给定对象，那么它遵循以下规则:

*   **反身:**对于任何参考值 a，a.equals(a)应该返回 true。
*   **对称:**对于任何参考值 a 和 b，如果 a.equals(b)应该返回真，那么 b.equals(a)必须返回真。
*   **传递:**对于任何引用值 a、b 和 c，如果 a.equals(b)返回 true，b.equals(c)返回 true，那么 a.equals(c)应该返回 true。
*   **Consistent :** for any reference values a and b, multiple invocations of a.equals(b) consistently return true or consistently return false, provided no information used in equals comparisons on the object is modified.

    **注意:**对于任何非空引用值 a，a.equals(null)应该返回 false。

```java
// Java program to illustrate 
// how hashCode() and equals() methods work
import java.io.*;

class Geek 
{

    public String name;
    public int id;

    Geek(String name, int id) 
    {

        this.name = name;
        this.id = id;
    }

    @Override
    public boolean equals(Object obj)
    {

    // checking if both the object references are 
    // referring to the same object.
    if(this == obj)
            return true;

        // it checks if the argument is of the 
        // type Geek by comparing the classes 
        // of the passed argument and this object.
        // if(!(obj instanceof Geek)) return false; ---> avoid.
        if(obj == null || obj.getClass()!= this.getClass())
            return false;

        // type casting of the argument. 
        Geek geek = (Geek) obj;

        // comparing the state of argument with 
        // the state of 'this' Object.
        return (geek.name == this.name && geek.id == this.id);
    }

    @Override
    public int hashCode()
    {

        // We are returning the Geek_id 
        // as a hashcode value.
        // we can also return some 
        // other calculated value or may
        // be memory address of the 
        // Object on which it is invoked. 
        // it depends on how you implement 
        // hashCode() method.
        return this.id;
    }

}

//Driver code
class GFG
{

    public static void main (String[] args)
    {

        // creating the Objects of Geek class.
        Geek g1 = new Geek("aa", 1);
        Geek g2 = new Geek("aa", 1);

        // comparing above created Objects.
        if(g1.hashCode() == g2.hashCode())
        {

            if(g1.equals(g2))
                System.out.println("Both Objects are equal. ");
            else
                System.out.println("Both Objects are not equal. ");

        }
        else
        System.out.println("Both Objects are not equal. "); 
    } 
}
```

输出:

```java
Both Objects are equal.

```

在上面的示例中，请参见行:

```java
// if(!(obj instanceof Geek)) return false;--> avoid.-->(a)
```

我们用这条线代替了上面的线:

```java
if(obj == null || obj.getClass()!= this.getClass()) return false; --->(y)
```

这里，首先我们比较两个对象(即 g1 和 g2)上的 hashcode，如果两个对象生成了相同的 hashcode，这并不意味着它们相等，因为 hashCode 对于不同的对象也可以相同，如果它们具有相同的 id(在这种情况下)。因此，如果生成的 hashcode 值对于两个对象都是相等的，那么我们将比较这两个对象的状态，因为我们在类中重写了 equals(Object)方法。如果根据 equals(Object)方法，两个对象具有相同的状态，则它们相等，否则不相等。如果不同的对象生成不同的 hashcode 值，会有更好的读写性能。

**原因:**参考 **obj** 也可以参考极客子类的对象。行(b)确保如果传递的参数是 Geek 类子类的对象，它将返回 false。但是运算符条件的**实例如果发现传递的参数是 Geek 类的子类，则不会返回 false。读取运算符的[实例。](https://www.geeksforgeeks.org/java-instanceof-and-its-applications/)**

**hashCode()方法**

它以整数形式返回哈希值。Hashcode 值主要用于基于哈希的集合，如 HashMap、HashSet、HashTable…等。这个方法必须在每个重写 equals()方法的类中被重写。
语法:

```java
public int hashCode()

// This method returns the hash code value 
// for the object on which this method is invoked.

```

**hashCode 的总合同为:**

*   在应用程序执行期间，如果在同一对象上多次调用 hashCode()，那么它必须一致地返回相同的整数值，前提是在对象上的**等于(对象)**比较中使用的信息没有被修改。从应用程序的一次执行到同一应用程序的另一次执行，该整数值不必保持不变。
*   如果两个对象相等，根据**等于(对象)**方法，那么 hashCode()方法必须在两个对象的每一个上产生相同的整数。
*   如果两个对象不相等，根据**等于(对象)**的方法，hashCode()方法在两个对象上产生的整数值没有必要是不同的。它可以是相同的，但是在两个对象中的每一个上产生不同的整数对于提高基于散列的集合的性能更好，比如散列映射、散列表等等。

注意:只要相等，相等的对象必须产生相同的哈希代码，但是不相等的对象不需要产生不同的哈希代码。

**相关链接:** [在 Java 中覆盖等号](https://www.geeksforgeeks.org/overriding-equals-method-in-java/)
T5【参考: [JavaRanch](http://www.javaranch.com/journal/2002/10/equalhash.html)

本文由 **Nitsdheerendra** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。