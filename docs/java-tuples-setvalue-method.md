# JavaTuples setValue()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-setvalue-method/](https://www.geeksforgeeks.org/java-tuples-setvalue-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的**设置值()**方法用于设置标签值类对象或键值类对象中的值。此方法只能用于 javatuples 库的 LabelValue 类或 KeyValue 类。它返回另一个类对象，该类对象的值作为作为参数传递的元素，以及来自前一个类对象的键或标签。

### LabelValue.setValue()

**方法声明:**

```
public <X> LabelValue<A, X> setValue(X value)
```

**语法:**

```
LabelValue<A, B> LabelValueClassObject = LabelValue.setValue(X value)
```

**返回值:**这个方法返回另一个 LabelValueClassObject，值作为作为参数传递的元素，标签来自上一个 LabelValueClassObject。

下面的程序将说明在标签值类中使用 setValue()方法的各种方法:

**例**:

```
// Below is a Java program to set
// Value in a LabelValue pair

import java.util.*;
import org.javatuples.LabelValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating a LabelValue object
        LabelValue<Integer, String> lv
            = LabelValue.with(Integer.valueOf(1),
                              "A computer science portal");

        // Using setValue() method
        LabelValue<Integer, Integer> lv1 = lv.setValue(Integer.valueOf(2));

        // Printing the returned LabelValue
        System.out.println(lv1);
    }
}
```

输出:

```
[1, 2]

```

### KeyValue.setValue（）

**方法声明:**

```
public <X> KeyValue<A, X> setValue(X value)
```

**语法:**

```
KeyValue<A, B> KeyValueClassObject = KeyValue.setValue(X value)
```

**返回值:**这个方法返回另一个 KeyValueClassObject，这个 KeyValueClassObject 的值是作为参数传递的元素，这个 key 来自之前的 key Value classobject。

下面的程序将说明在键值类中使用 setValue()方法的各种方法:

**例**:

```
// Below is a Java program to set
// Value in a KeyValue pair

import java.util.*;
import org.javatuples.KeyValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating a KeyValue object
        KeyValue<Integer, String> kv
            = KeyValue.with(Integer.valueOf(1),
                            "A computer science portal");

        // Using setValue() method
        KeyValue<Integer, String> kv1 = kv.setValue("GeeksforGeeks");

        // Printing the returned KeyValue
        System.out.println(kv1);
    }
}
```

输出:

```
[1, GeeksforGeeks]

```