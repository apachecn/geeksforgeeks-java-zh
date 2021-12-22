# Java 中的构造函数 getDeclaredAnnotations()方法，带示例

> 原文:[https://www . geesforgeks . org/constructor-getdeclaredannotations-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-getdeclaredannotations-method-in-java-with-examples/)

**Java . lang . reflect . Constructor 类**的 **getDeclaredAnnotations()** 方法用于将此 Constructor 元素上的注释作为注释类对象的数组返回。getDeclaredAnnotations()方法忽略此构造函数对象上的继承注释。返回的数组可以不包含注释，这意味着如果构造函数有 nop 注释，该数组的长度可以是 0。

**语法:**

```
public Annotation[] getDeclaredAnnotations()

```

**参数:**此方法不接受任何内容。

**返回**:这个方法返回直接出现在这个元素上的**注释数组**

下面的程序说明了 getDeclaredAnnotations()方法:
**程序 1:**

```
// Java program to illustrate
// getDeclaredAnnotations() method

import java.lang.annotation.Annotation;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = shape.class;

        // get Constructor object
        // array from class object
        Constructor[] cons
            = classObj.getConstructors();

        // get array of annotations
        Annotation[] annotations
            = cons[0].getDeclaredAnnotations();

        // print length of annotations array
        System.out.println("Annotation : "
                           + annotations);
    }

    @CustomAnnotation(createValues = "GFG")
    public class shape {

        @CustomAnnotation(createValues = "GFG")
        public shape()
        {
        }
    }

    // create a custom annotation
    public @interface CustomAnnotation {
        public String createValues();
    }
    }
```

**Output:**

```
Annotation : [Ljava.lang.annotation.Annotation;@4aa298b7

```

**程序 2:**

```
// Java program to illustrate
// getDeclaredAnnotations() method

import java.lang.annotation.Annotation;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = String.class;

        // get Constructor object
        // array from class object
        Constructor[] cons
            = classObj.getConstructors();

        // get array of annotations
        Annotation[] annotations
            = cons[0].getDeclaredAnnotations();

        // print length of annotations array
        System.out.println("Annotation length : "
                           + annotations.length);
    }
}
```

**Output:**

```
Annotation length : 0

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # getDeclaredAnnotations()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getDeclaredAnnotations())