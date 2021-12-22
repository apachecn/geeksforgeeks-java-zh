# java 中的 java.lang.MethodType 类

> 原文:[https://www . geesforgeks . org/Java-lang-method type-class-in-Java/](https://www.geeksforgeeks.org/java-lang-methodtype-class-in-java/)

MethodType 是一个属于 java.lang 包的类。这个类由各种类型的方法组成，这些方法在大多数情况下有助于根据输入对象或方法的参数找到方法类型。

*   methodType 的所有实例都是不可变的。这意味着方法类型类的对象不能被任何其他对象数据覆盖。
*   在或多或少的情况下，方法类型对象是从字节码指令中派生出来的。
*   像所有其他类一样，方法类型类也可以单独向常量池表示常量 _ 方法类型。
*   类 MethodType 的大多数方法都是使用 Static 定义的，因为这些方法需要绑定到它们的 Methodtype 类，而不是对象。

**语法:**类声明

```java
public final class MethodType extends Object implements Serializable {

// MethodType extends Object Class which is root of class hierarchy
// The serialization interface has no methods or fields and serves only
// to identify the semantics of being serializable.

}
```

MethodType 类的方法:

<figure class="table">

| way | describe |
| --- | --- |
| Appendix parameter type (class [T0】 …ptypestorinsert) | This method finds or creates a method type with additional parameter types. |
| Appendix parameter type (list [T0】 >ptypestorinsert) | This method finds or creates a method type with additional parameter types. |
| changeParameterType() | This method finds or creates a method type with a single different parameter type. |
| changeReturnType() | This method finds or creates method types with different return types. |
| 【drop 参数类型()】 | This method finds or creates a method type, but omits some parameter types. |
| 等于() | This method compares whether the specified object is equal to this type. |
| 擦除() | This method erases all reference types to Object. |
| frommethodsdescriptorstring() | Given the spelling of the bytecode descriptor of a method, the method finds or creates an instance of the method type. |
| 通用() | This method converts all types (including references and primitives) into Object. |
| 泛型方法类型(int objectArgCount) | This method finds or creates a method type whose components are all Object. |
| 泛型方法类型(int objectArgCount，布尔 finalArray) | This method finds or creates a method type whose component is Object with an optional trailing Object[] array. |
| hashCode() | This method returns the hash code value of this method type. |
| hasPrimitives() | This method reports whether this type contains primitive parameters or return values. |
| 有包装() | This method reports whether this type contains wrapper parameters or return values. |
| Insert parameter type (int num, Class | This method finds or creates a method type with additional parameter types. |
| 诶哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟(int num，List < Class >ptypestorinsert) | This method finds or creates a method type with additional parameter types. |
| 方法类型(类 rtype) | This method uses the given component to find or create a method type. |
| 方法类型(类 rtype，Class ptype0) | This method uses the given component to find or create a method type. |
| 方法类型(类 rtype，Class [] ptypes) | This method finds or creates an instance of the given method type. |
| 方法类型(类 rtype，类 ptype0，类 …pt 类型) | This method uses the given component to find or create a method type. |
| Type of method (class rtype, list [T1】 >pt types) | This method finds or creates a method type with a given component. |
| 方法类型(类 rtype，方法类型 pt 类型) | This method finds or creates a method type with a given component. |
| 参数数组() | This method presents the parameter types as arrays (a convenient method). |
| 参数计数() | This method returns the number of parameter types in this method type. |
| 参数列表() | This method presents the parameter types as a list (a convenient method). |
| 参数类型(整数) | This method returns the parameter type at the specified index, within this method type. |
| 返回类型() | This method returns the return type of this method type. |
| Method descriptor string () | This method generates a bytecode descriptor representation of the method type. |
| ToString() | This method returns a string representation of the method type in the form "(PT0, **[pt1 …) RT".** |
| 展开() | This method converts all wrapper types into their corresponding primitive types. |
| 包装() | This method converts all primitive types into their corresponding wrap types. |

</figure>

**本类示例**方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate MethodType Class
// from java.lang.invoke package

// Importing required classes from java.lang package
import java.lang.invoke.MethodHandle;
import java.lang.invoke.MethodHandles;
import java.lang.invoke.MethodType;

// Main class
class GFG {

    // Method 1
    // Helper method
    static void hello()
    {

        // Print statement
        System.out.println("GeeksForGeeks");
    }

    // Method 2
    // Main driver method
    public static void main(String[] args) throws Throwable
    {

        // Creating an object MethodHandles class to
        // create an object lookup
        MethodHandles.Lookup lookup
            = MethodHandles.lookup();

        // Returning the type of method used using
        // methodType class

        // Now, we are also invoking the hello() method to
        // print the context present in it
        MethodHandle mh = lookup.findStatic(
            GFG.class, "hello",
            MethodType.methodType(void.class));

        // Lastly invoking invokeExact() method
        // using method handle
        mh.invokeExact();
    }
}
```

**Output**

```java
GeeksForGeeks
```