# Java 中的 Float hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/float-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/float-hashcode-method-in-java-with-examples/)

**[Float 类](https://www.geeksforgeeks.org/java-lang-float-class-in-java/)** 中的 **hashCode()** 方法方法是 Java 中的一个内置方法，返回这个 Float 对象的 hashCode 值。

**语法:**

```
public int hashCode()
```

**参数:**不取参数。

**返回:**函数返回该对象的哈希码值。

下面是 hashCode()方法的实现:

**例 1:**

```
// Java code to demonstrate
// Float hashCode() Method

class GFG {
    public static void main(String[] args)
    {

        float d = 118.698f;

        // creating Float object.
        Float value = new Float(d);

        // hashCode() method Float class
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
Hashcode Value of 118.698 : 1122854240

```

**例 2:**

```
// Java code to demonstrate
// Float hashCode() Method

class GFG {
    public static void main(String[] args)
    {

        int i = -30;

        // creating Float object.
        Float value = new Float(i);

        // hashCode() method Float class
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
Hashcode Value of -30.0 : -1041235968

```