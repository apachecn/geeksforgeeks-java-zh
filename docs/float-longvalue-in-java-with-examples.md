# Java 中的 Float longValue()，示例

> 原文:[https://www . geesforgeks . org/float-long value-in-Java-with-examples/](https://www.geeksforgeeks.org/float-longvalue-in-java-with-examples/)

中的**java . lang . Float . long value()**方法是 Java 中的一个内置方法，只要在类型转换之后，就会返回调用对象指定的值。

**语法:**

```
public long longValue()

```

**参数:**不取参数。

**返回类型:**它返回一个**长**值，即浮点对象的类型铸造值。

下面是上述方法的实现。

**程序 1:**

```
// Java Code to implement
// longValue() method of Float class

class GFG {

    // Driver method
    public static void main(String[] args)
    {

        // creating a Float object
        Float d = new Float(1022);

        // longValue() method of Float class
        // typecast the value
        long output = d.longValue();

        // printing the output
        System.out.println(output);
    }
}
```

**输出:**

```
1022

```

**程序二:**

```
// Java Code to implement
// longValue() method of Float class

class GFG {

    // Driver method
    public static void main(String[] args)
    {

        // creating a Float object
        Float d = new Float(-1023.23);

        // longValue() method of Float class
        // typecast the value
        long output = d.longValue();

        // printing the output
        System.out.println(output);
    }
}
```

**输出:**

```
-1023

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/float . html # long value()](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#longValue())