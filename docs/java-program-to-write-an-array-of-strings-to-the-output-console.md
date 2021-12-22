# 将字符串数组写入输出控制台的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序写字符串数组到输出控制台/](https://www.geeksforgeeks.org/java-program-to-write-an-array-of-strings-to-the-output-console/)

我们不能在 Java 中直接打印数组元素，需要使用 **Arrays.toString()** 或者 **Arrays.deepToString()** 来打印数组元素。如果要打印一维数组，请使用 **toString()** 方法；如果要打印二维或三维数组等，请使用 **deepToString()** 方法。

在 Java 中，数组不会覆盖 toString()。当我们尝试用 Java 将数组直接写到输出控制台时，我们得到了由 Object.toString()定义的数组的**类名+“@”+hash _ code**。为了更好的理解，请看下面的例子。

## Java

```
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        String gfg[] = { "Geeks", "for", "Geeks" };
        System.out.println(gfg);
    }
}
```

**输出**

```
[Ljava.lang.String;@3d075dc0

```

因此，要以有意义的方式打印 Java 数组，您不需要看得更远，因为您自己的 Collection 框架在 **java.util.Arrays** 类中提供了许多数组实用方法。这里我们有 toString()方法和 deepToString()方法来打印 Java 中的数组。

以下是将字符串数组写入输出控制台的方法。

**方法 1:使用 Arrays.toString()**

当您有一维数组时，使用此方法。

## 爪哇

```
import java.io.*;
import java.util.Arrays;

class GFG {
    public static void main(String[] args)
    {
        String gfg[] = { "Geeks", "for", "Geeks" };
        System.out.println(Arrays.toString(gfg));
    }
}
```

**输出**

```
[Geeks, for, Geeks]

```

上面，我们使用了 Arrays.toString()方法。只需在 Arrays.toString()中传递数组名作为参数，数组的所有元素都将被写入输出控制台。

**方法 2:使用 Arrays.deepToString()**

这种方法是在你必须二维数组的时候使用的。

## 爪哇

```
import java.io.*;
import java.util.Arrays;

class GFG {
    public static void main(String[] args)
    {
        String gfg[][]
            = { { "GeeksforGeeks", "Article Writing" },
                { "Google", "Search Engine" },
                { "Facebook", "Social Media" } };
        System.out.println(Arrays.deepToString(gfg));
    }
}
```

**输出**

```
[[GeeksforGeeks, Article Writing], [Google, Search Engine], [Facebook, Social Media]]

```

在上面的例子中，我们使用了 Arrays.deepToString()方法。此方法负责将二维数组的元素写入输出控制台。

**方法 3:用于循环**

在这个方法中，我们将访问数组的每个元素，并将它写入输出控制台。

## 爪哇

```
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        String gfg[] = new String[3];
        gfg[0] = "Geeks";
        gfg[1] = "for";
        gfg[2] = "Geeks";
        for (int i = 0; i <= 2; i++) {
            System.out.print(gfg[i] + " ");
        }
    }
}
```

**输出**

```
Geeks for Geeks 

```

在上面的方法中，我们使用 for 循环()方法来访问 gfg 数组的每个元素，并将其写入输出控制台。