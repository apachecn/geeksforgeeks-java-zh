# Java 中的 BinaryOperator 接口

> 原文:[https://www . geesforgeks . org/binaryoperator-interface-in-Java/](https://www.geeksforgeeks.org/binaryoperator-interface-in-java/)

**BinaryOperator 接口< T >** 是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程。](https://www.geeksforgeeks.org/functional-programming-paradigm/)它代表一个二进制运算符，该运算符接受两个操作数并对其进行运算以产生一个结果。然而，它与普通 BiFunciton 的区别在于它的参数和返回类型都是相同的。

该功能界面采用一个通用名称，即:-

*   **: indicates the type of input parameter and the return value of operation.**

**双功能操作器<t>扩展了双功能<t t="">类型。所以它从双功能界面继承了以下方法:</t></t>**

***   [应用(T t，T u)](https://www.geeksforgeeks.org/java-bifunction-interface-methods-apply-and-addthen/)*   [和然后(功能<？超级 r，？延伸五>后)](https://www.geeksforgeeks.org/java-bifunction-interface-methods-apply-and-addthen/)**

**分配给 BiaryOperator 类型的对象的 lambda 表达式用于定义其 **apply()** ，该表达式最终对其参数应用给定的操作。**

### **二进制运算符接口中的函数**

**BinaryOperator 接口由以下功能组成:**

### **1.maxBy()**

**这些方法返回一个 BinaryOperator，它根据给定的比较器返回两个元素中较大的一个**

****语法:****

```java
static <T> BinaryOperator<T> 
    maxBy(Comparator<? super T> comparator)
```

****参数:**它只接受一个参数，即**比较器**，它是比较器类的一个对象。**

****返回:**这个方法返回一个 BinaryOperator，它返回两个对象的**最大值，当基于给定的比较器调用它的时候。****

**下面是演示 maxBy()方法的代码:**

****程序:****

## **Java**

```java
import java.util.function.BinaryOperator;

public class GFG {
    public static void main(String args[])
    {
        BinaryOperator<Integer>
            op = BinaryOperator
                     .maxBy(
                         (a, b) -> (a > b) ? 1 : ((a == b) ? 0 : -1));

        System.out.println(op.apply(98, 11));
    }
}
```

****输出:****

```java
98
```