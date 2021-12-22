# java 中的 java.lang.reflect.Method 类

> 原文:[https://www . geesforgeks . org/Java-lang-reflect-method-class-in-Java/](https://www.geeksforgeeks.org/java-lang-reflect-method-class-in-java/)

**java.lang.reflect.Method** 类提供关于某个类别或接口上的一个方法的必要细节，并提供对该方法的访问。反射方法也可以是类别方法或实例方法(包括抽象方法)。

当匹配实际参数来调用基础方法的形式参数时，这个类允许进行扩展转换，但是如果进行了扩展转换，它会抛出一个 IllegalArgumentException。

> java.lang.Object
> 
> Java . lang . reflect . access ible object
> 
> java.lang.reflect.Executable
> 
> java.lang.reflect.Method

**方法:**

<figure class="table">

| **Method** | **Description** |
| --- | --- |
| 等于(对象对象) | This method compares this method with the specified object. |
| getannotatedreturnttype() | This method returns an annotated Type object, which indicates that a type is used to specify the return type of the method/constructor represented by this executable file. |
| getAnnotation(类<t>注释类)</t> | If there is a comment of the specified type, the method returns the comment of the element; otherwise, it is null. |
| getDeclaredAnnotations() | This method returns comments that exist directly on this element. |
| getDeclaringClass() | This method returns a Class object, which represents the class or interface that declares the executable file represented by this object. |
| getDefaultValue() | This method returns the default value of the annotation member represented by this method instance. |
| getexceptinotypes _) | This method returns an array of Class objects, which represents the types of exceptions declared by the underlying executable file represented by this object. |
| getgenericexceptinotypes_) | This method returns an array of Type objects, which represents the exception that this executable object declares to throw. |
| getGenericParameterTypes() | This method returns an array of Type objects that represent the formal parameter types of the executable file represented by this object in the order of declaration. |
| getGenericReturnType() | This method returns a Type object that represents the formal return type of the method represented by this method object. |
| getModifiers() | This method returns the Java language modifier of the executable file represented by this object. |
| 获取名（） | This method returns the name of the method represented by this method object as a String. |
| getparameter Annotations() | This method returns an Annotations array that represents the annotations on the formal parameters (in order of declaration) of the executable file represented by this object. |
| getParameterCount() | This method returns the number of formal parameters of the executable file represented by this object (whether explicitly declared or implicitly declared or neither). |
| getParameterTypes() | This method returns an array of Class objects that represent the formal parameter types of the executable file represented by this object in the order of declaration. |

</figure>

**getDefaultValue（） 方法：**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to show the
// Implementation of getDefaultvalue()

import java.lang.reflect.Method;

public class getDefaultValueExample {

    public static void main(String[] args)
    {

        Method[] methods = Demo.class.getMethods();

        // calling method getDefaultValue()
        System.out.println(methods[0].getDefaultValue());
    }
}

class Demo {
    private String str;

    // member function returning string str
    public String getSampleField() { return str; }

    public void setSampleField(String str)
    {
        this.str = str;
    }
}
```

**Output**

```java
null
```

**toString()方法:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to show the
// Implementation of toString()

import java.lang.reflect.Method;

public class MethodDemo {
    public static void main(String[] args)
    {

        Method[] methods = SampleClass.class.getMethods();

        // calling method toString()
        System.out.println(methods[1].toString());
    }
}

class SampleClass {
    private String str;

    public String getSampleField() { return str; }

    public void setSampleField(String str)
    {
        this.str = str;
    }
}
```

**Output**

```java
public void SampleClass.setSampleField(java.lang.String)
```