# JavaTuples equal()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-equal-method/](https://www.geeksforgeeks.org/java-tuples-equal-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的**等于()**方法用于检查一个类是否等于作为参数给出的类。这个方法可以用于 javatuples 库的任何元组类对象。它返回一个布尔值，根据该类与现有类的等价性，该值为真或假。

**方法申报:**

```
public final boolean equals(Object obj)
```

**语法:**

```
boolean result = TupleClassObject.equals(TupleClass2Object)
```

**参数:**该方法以*图普勒类 2 对象*为参数，其中:

*   **TupleClassObject**–表示像单位、五进制、十进制等使用的 JavaTuple 类对象。
*   **tupleclass2 object**–表示传递给 JavaTuple Class 对象的参数，如 Unit、Quintet、Decade 等。

**返回值:**如果 TupleClassObject 等于 TupleClass2Object，则该方法返回 true。否则返回假

下面的程序说明了使用 equals()方法的各种方法:

**程序 1:** 使用等号()与单位类:

```
// Below is a Java program to use equals() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Unit with one value
        Unit<String> unit = Unit.with("GeeksforGeeks");

        // Creating another Unit with one value
        Unit<String> unit1 = Unit.with("GeeksNotforGeeks");

        // Using equals() method
        boolean res = unit.equals(unit1);

        System.out.println("Is " + unit + " equal to "
                           + unit1 + " : " + res);
    }
}
```

**输出:**

```
Is [GeeksforGeeks] equal to [GeeksNotforGeeks] : false
```

**程序二:**使用等于()与四方类:

```
// Below is a Java program to use equals() method

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        // Creating Quartet from List
        List<String> list = new ArrayList<String>();
        list.add("GeeksforGeeks");
        list.add("A computer portal");
        list.add("for geeks");
        list.add("by Sandeep Jain");

        Quartet<String, String, String, String> quartet
            = Quartet.fromCollection(list);

        // Creating Quartet from Array
        String[] arr = { "GeeksforGeeks",
                         "A computer portal",
                         "for geeks",
                         "by Sandeep Jain" };

        Quartet<String, String, String, String> otherQuartet
            = Quartet.fromArray(arr);

        // Using equals() method
        boolean res = quartet.equals(otherQuartet);

        System.out.println("Is \n" + quartet + "\n equal to \n"
                           + otherQuartet + "\n : " + res);
    }
}
```

**输出:**

```
Is 
[GeeksforGeeks, A computer portal, for geeks, by Sandeep Jain]
 equal to 
[GeeksforGeeks, A computer portal, for geeks, by Sandeep Jain]
 : true
```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。