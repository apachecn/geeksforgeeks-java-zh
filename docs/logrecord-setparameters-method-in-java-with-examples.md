# Java 中的 LogRecord setParameters()方法，示例

> 原文:[https://www . geesforgeks . org/log record-set parameters-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setparameters-method-in-java-with-examples/)

**Java . util . logging . log record**的**设置参数()**方法用于设置日志消息的参数。这些参数是要插入到这个日志记录的消息中的参数。

**语法:**

```java
public void setParameters(Object[] parameters)

```

**参数:**该方法接受**参数**作为参数，参数为对象[]形式的日志消息参数。

**返回**:此方法不返回任何内容。

以下程序说明了设定参数()方法:
**程序 1:**

```java
// Java program to illustrate setParameters() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");

        // set empty object array
        logRecord.setParameters(new Object[] {});

        System.out.println(
            "Object Array length: "
            + logRecord.getParameters().length);
    }
}
```

**Output:**

```java
Object Array length: 0

```

**程序 2:**

```java
// Java program to illustrate setParameters() method

import java.lang.reflect.Method;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");

        // get parameter object array
        // from string class method
        Method method
            = String.class.getDeclaredMethods()[4];
        System.out.println("Method : "
                           + method.getName());
        Object[] objArr
            = method.getParameters();

        // set empty object array
        logRecord.setParameters(objArr);

        // get array
        Object[] array = logRecord.getParameters();
        for (int i = 0; i < array.length; i++) {
            System.out.println(array[i]);
        }
    }
}
```

**Output:**

```java
Method : compareTo
java.lang.Object arg0

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/logging/logrecord . html # setParameters-Java . lang . object:A-](https://docs.oracle.com/javase/8/docs/api/java/util/logging/LogRecord.html#setParameters-java.lang.Object:A-)