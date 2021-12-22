# Java 中的 Field equals()方法，示例

> 原文:[https://www . geesforgeks . org/field-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-equals-method-in-java-with-examples/)

**等于()**的**法的[法。场](https://www.geeksforgeeks.org/reflection-in-java/)**用于比较两个场对象。此方法比较两个字段对象，如果两个对象相等，则返回 true，否则返回 false。当且仅当这两个字段对象由同一类声明并且具有相同的名称和类型时，它们才被视为相等。这个方法在调试对象属性时非常有用，对象属性实际上是 Java 中一个类的字段。

**语法:**

```java
public boolean equals(Object obj)

```

**参数:**该方法接受一个参数**对象**，该参数是与该字段对象进行比较的参考对象。

**返回值:**如果两个对象相等，该方法返回真，否则返回假。

下面的程序说明了 equals()方法:
**程序 1:**

```java
// Java program to demonstrate the above method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get the array of Field objects
        Field[] fields
            = User.class.getDeclaredFields();
        Field fieldObj
            = User.class.getField("name");

        // print element of field array
        // and compare it with fieldObj
        for (int i = 0; i < fields.length; i++) {

            // compare the fields with each other
            boolean isEquals
                = fields[i].equals(fieldObj);
            if (isEquals) {
                System.out.println(
                    "Field -> ["
                    + fields[i] + "] and"
                    + " FieldObj -> ["
                    + fieldObj
                    + "] are equal.");
            }
            else {
                System.out.println(
                    "Field -> ["
                    + fields[i] + "] and"
                    + " FieldObj -> ["
                    + fieldObj
                    + "] are not equal.");
            }
        }
    }
}

// User class
class User {

    public String name;
    public int age;
}
```

**Output:**

> 字段->[public Java . lang . string user . name]
> 和
> field obj->[public Java . lang . string user . name]
> 相等。
> 
> 字段-> [public int User.age]
> 和
> field obj->【public Java . lang . string user . name】
> 不相等。

**程序 2:**

```java
// Java program to demonstrate the above method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get the array of Field objects
        Field[] fields1
            = Class.class.getDeclaredFields();
        Field[] fields2
            = Class.class.getDeclaredFields();

        // print element of field array 1 and compare
        // it with fields array 2
        for (int i = 0; i < fields1.length; i++) {

            for (int j = 0; j < fields2.length; j++) {

                // compare the fields with each other
                boolean isEquals
                    = fields1[i].equals(fields2[j]);
                if (isEquals) {
                    System.out.println(
                        "Field -> ["
                        + fields1[i] + "] and"
                        + " FieldObj -> ["
                        + fields2[j]
                        + "] are equal.");
                }
                else {
                    System.out.println(
                        "Field -> ["
                        + fields1[i] + "] and"
                        + " FieldObj -> ["
                        + fields2[j]
                        + "] are not equal.");
                }
            }
        }
    }
}

// Object of Class which contains
// noOfStudents and studentNames
class Class {

    public int noOfStudents;
    public String[] studentNames;
}
```

**Output:**

> field->[public int class . noofstudents]
> 和
> field obj->【public int class . noofstudents】
> 相等。
> 
> 字段->[public int class . noofstudents]
> 和
> field obj->[public Java . lang . string]【class . studentnames】
> 不相等。
> 
> 字段->[public Java . lang . string][class . studentnames]
> 和
> field obj->[public int class . noofstudents]
> 不相等。
> 
> field->[public Java . lang . string[]class . studentnames]
> 和
> field obj->[public Java . lang . string[]class . studentnames]
> 相等。

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/field . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Field.html#equals(java.lang.Object))