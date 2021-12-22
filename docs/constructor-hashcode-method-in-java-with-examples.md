# Java 中的构造函数 hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/constructor-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-hashcode-method-in-java-with-examples/)

**Java . lang . reflect . Constructor 类**的 **hashCode()** 方法用于返回此 Constructor 对象的 hashCode。如果构造的对象没有改变，hashcode 总是相同的。Hashcode 是 JVM 在创建类对象时生成的唯一代码。我们可以使用 hashcode 对 hash 相关算法进行一些操作，比如 hashtable、hashmap 等。我们可以搜索一个具有唯一代码的对象。

**语法:**

```
public int hashCode()

```

**参数:**此方法不接受任何内容。

**返回**:该方法返回该对象的哈希码**整数值**。

下面的程序说明了 hashCode()方法:
**程序 1:**

```
// Java program to illustrate hashCode() method

import java.lang.reflect.Constructor;
import java.util.ArrayList;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = ArrayList.class;

        // get Constructor object
        // array from class object
        Constructor[] cons = classObj.getConstructors();

        // get hash code of this constructor class
        int code = cons[0].hashCode();

        // print result
        System.out.println(
            "Hash Code count = " + code);
    }
}
```

**Output:**

```
Hash Code count = -1114099497

```

**程序 2:**

```
// Java program to illustrate hashCode() method

import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = String.class;

        // get Constructor object
        // array from class object
        Constructor[] cons = classObj.getConstructors();

        // get hash code of this constructor class
        int code = cons[0].hashCode();

        // print result
        System.out.println(
            "Hash Code count for string class"
            + " constructor = " + code);
    }
}
```

**Output:**

```
Hash Code count for string class constructor = 1195259493

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#hashCode())