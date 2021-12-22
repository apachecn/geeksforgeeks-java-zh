# Java 中的 Double hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/double-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/double-hashcode-method-in-java-with-examples/)

[Double 类](https://www.geeksforgeeks.org/java-lang-double-class-java/)的 **hashCode()** 方法是一个内置方法，用于返回这个 Double 对象的 hashCode 值。

**语法:**

```
DoubleObject.hashCode()
```

**参数:**不取参数。

**返回类型:**返回一个 **int** 值。返回的值是**(int)(v^(v>>>32))**，其中 v 是等于**double . double to longbits(this . double value())**的长变量。

下面是 hashCode()方法的实现:

**例 1:**

```
// Java code to demonstrate
// Double hashCode() Method

class GFG {
    public static void main(String[] args)
    {

        double d = 118.698;

        // creating Double object.
        Double value = new Double(d);

        // hashCode() method Double class
        int output = value.hashCode();

        // printing the output
        System.out.println("Hashcode Value of "
                           + value + " : "
                           + output);
    }
}
```

**Output:**

```
Hashcode Value of 118.698 : 1215072837

```

**例 2:**

```
// Java code to demonstrate
// Double hashCode() Method

class GFG {
    public static void main(String[] args)
    {

        int i = -30;

        // creating Double object.
        Double value = new Double(i);

        // hashCode() method Double class
        int output = value.hashCode();

        // printing the output
        System.out.println("Hashcode Value of "
                           + value + " : "
                           + output);
    }
}
```

**Output:**

```
Hashcode Value of -30.0 : -1069678592

```