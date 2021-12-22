# 如何在 Java 中使用反射访问私有字段和方法？

> 原文:[https://www . geesforgeks . org/如何使用 java 中的反射访问私有字段和方法/](https://www.geeksforgeeks.org/how-to-access-private-field-and-method-using-reflection-in-java/)

如果我们想要使用反射访问私有字段和方法，我们只需要在您想要访问的字段或方法对象上调用 *setAccessible(true)* 。*class . getdeclaredfields(字符串字段名称*)或*class . getdeclaredfields()*可用于获取私有字段。鉴于类. getDeclaredMethod(字符串方法名，类<？> … parameterTypes)或者 Class.getDeclaredMethods()都可以用来获取私有方法。

下面的程序可能无法在在线 IDEs 上运行，比如，只在离线 IDEs 上编译和运行下面的程序。

**1。访问私有字段**

## Java

```java
// Access Private Field Using Reflection in Java
import java.lang.reflect.Field;

// Student class declaration
class Student {

    // private fields
    private String name;
    private int age;

    // Constructor
    public Student(String name, int age)
    {
        this.name = name;
        this.age = age;
    }

    // Getters and setters
    public String getName() { return name; }

    public void setName(String name) { this.name = name; }

    private int getAge() { return age; }

    public void setAge(int age) { this.age = age; }

    // Override toString method to get required
    // output at terminal
    @Override public String toString()
    {
        return "Employee [name=" + name + ", age=" + age
            + "]";
    }
}

// Program will throw an exception on online IDE
// Compile and run the program on offline IDE
class GFG {

    public static void main(String[] args)
    {
        try {

            // Student object created
            Student e = new Student("Kapil", 23);

            // Create Field object
            Field privateField
                = Student.class.getDeclaredField("name");

            // Set the accessibility as true
            privateField.setAccessible(true);

            // Store the value of private field in variable
            String name = (String)privateField.get(e);

            // Print the value
            System.out.println("Name of Student:" + name);
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```