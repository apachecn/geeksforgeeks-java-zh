# JavaTuples 包含()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-contains-method/](https://www.geeksforgeeks.org/java-tuples-contains-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的**包含()**方法用于检查一个值是否存在于作为参数给出的 TupleClass 中。这个方法可以用于 javatuples 库的任何元组类对象。它返回一个布尔值，该值基于 TupleClass 中该值的存在与否。

**方法申报:**

```
public final boolean contains(Object value)
```

**语法:**

```
boolean result = TupleClassObject.contains(X value)
```

**参数:**该方法以*值*为参数，其中:

*   **X**–表示参数中值的数据类型。
*   **TupleClassObject**–表示像单位、五进制、十进制等使用的 JavaTuple 类对象。

**返回值:**如果元组中存在参数值，则该方法返回 true。否则返回假

下面的程序说明了使用 contains()方法的各种方法:

**程序 1:** 使用包含()的单位类:

```
// Below is a Java program to create
// a Unit tuple from contains() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Unit with one value
        Unit<String> unit = Unit.with("GeeksforGeeks");

        // Using contains() method

        boolean res;
        String check;

        // for True result
        check = "GeeksforGeeks";
        res = unit.contains(check);

        System.out.println("Is " + check + " present : " + res);

        // for False result
        check = "Geeks";
        res = unit.contains(check);

        System.out.println("Is " + check + " present : " + res);
    }
}
```

**输出:**

```
Is GeeksforGeeks present : true
Is Geeks present : false
```

**程序二:**使用包含()的带十年类:

```
// Below is a Java program to create
// a Unit tuple from contains() method

import java.util.*;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        // Creating a Decade with 10 value
        Decade<String, String, String, String, String,
               String, String, String, String, String>
            decade = Decade.with("Geeks",
                                 "for",
                                 "Geeks",
                                 "A",
                                 "Computer",
                                 "Science",
                                 "Portal",
                                 "for",
                                 "Geeks",
                                 "RishabhPrabhu");

        // Using contains() method

        boolean res;
        String check;

        // for True result
        check = "GeeksforGeeks";
        res = decade.contains(check);

        System.out.println("Is " + check + " present : " + res);

        // for False result
        check = "Geeks";
        res = decade.contains(check);

        System.out.println("Is " + check + " present : " + res);
    }
}
```

T4】

**输出:**

```
Is GeeksforGeeks present : true
Is Geeks present : false
```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。