# Java 中的 Float intValue()方法，带示例

> 原文:[https://www . geesforgeks . org/float-int value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/float-intvalue-method-in-java-with-examples/)

**[Float 类](https://www.geeksforgeeks.org/java-lang-float-class-in-java/)** 中的 **intValue()** 方法是 Java 中的内置方法，在类型转换后将调用对象指定的值作为 int 返回。

**语法:**

```
public int intValue()
```

**参数**:该功能不接受参数。

**返回值:**将浮点对象的值返回为 **int** 。

下面的程序用 Java 说明了 *intValue()* 方法:

**程序 1:**

```
// Java code to demonstrate
// Float intValue() method
class GFG {
    public static void main(String[] args)
    {

        // Float value
        Float a = 17.47f;

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(a);

        // intValue of the Float Object
        int output = b.intValue();

        // printing the output
        System.out.println("Int value of "
                           + b + " is : " + output);
    }
}
```

**输出:**

```
Int value of 17.47 is : 17

```

**程序二:**

```
// Java code to demonstrate
// Float intValue() method
// Not a number
class GFG {
    public static void main(String[] args)
    {

        // Float value
        Float a = Float.NaN;

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(a);

        // intValue of the Float Object
        int output = b.intValue();

        // printing the output
        System.out.println("Int value of "
                           + b + " is : " + output);
    }
}
```

**输出:**

```
Int value of NaN is : 0

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/float . html # intValue()](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#intValue())