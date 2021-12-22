# Java 中的 Java.lang.Class 类|第 2 集

> 原文:[https://www . geesforgeks . org/Java-lang-class-class-Java-set-2/](https://www.geeksforgeeks.org/java-lang-class-class-java-set-2/)

[Java 中的 Java.lang.Class 类|集合 1](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)

**更多方法:**

**1。int getModifiers()** :这个方法返回这个类或接口的 Java 语言修饰符，用整数编码。修饰符由 Java 虚拟机的公共、受保护、私有、最终、静态、抽象和接口常量组成。这些修饰符已经在 java.lang.Reflect 包中的[修饰符](https://docs.oracle.com/javase/7/docs/api/java/lang/reflect/Modifier.html)类中被解码。

```java
Syntax : 
public int getModifiers()
Parameters : 
NA
Returns :
the int representing the modifiers for this class
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getModifiers() method

import java.lang.reflect.Modifier;

public abstract class Test
{
    public static void main(String[] args)
    {
        // returns the Class object associated with Test class
        Class c = Test.class;

        // returns the Modifiers of the class Test
        // getModifiers method
        int i = c.getModifiers();

        System.out.println(i);

        System.out.print("Modifiers of " + c.getName() + " class are : ");

        // getting decoded i using toString() method
        // of Modifier class
        System.out.println(Modifier.toString(i));
    }
}
```

输出:

```java
1025
Modifiers of Test class are : public abstract
```

**2。t[]getenumconstats()**:这个方法返回这个枚举类的元素。如果此类对象不表示枚举类型，则返回空值。

```java
Syntax : 
public T[] getEnumConstants()
Parameters : 
NA
Returns :
an array containing the values comprising the enum class represented by this Class object
in the order they're declared,
or null if this Class object does not represent an enum type
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getEnumConstants() method

enum Color
{
    RED, GREEN, BLUE;
}

public class Test
{
    public static void main(String[] args)
    {  
        // returns the Class object associated with Color(an enum class)
        Class c1 = Color.class;

        // returns the Class object associated with Test class
        Class c2 = Test.class;

        // returns the elements of Color enum class in an array
        // getEnumConstants method
        Object[] obj1 = c1.getEnumConstants();

        System.out.println("Enum constants of " + c1.getName() + " class are :");

        // iterating through enum constants
        for (Object object : obj1)
        {
            System.out.println(object);
        }

        // returns null as Test Class object does not represent an enum type
        Object[] obj2 = c2.getEnumConstants();

        System.out.println("Test class does not contain any Enum constant.");
        System.out.println(obj2);

    }
}
```

输出:

```java
Enum constants of Color class are :
RED
GREEN
BLUE
Test class does not contain any Enum constant.
null
```

**3。String getCanonicalName()** :这个方法返回 Java 语言规范定义的底层类的规范名。
如果基础类没有规范名称(即，如果它是本地或匿名类或其组件类型没有规范名称的数组)，它将返回 null。

```java
Syntax : 
public String getCanonicalName()
Parameters : 
NA
Returns :
the Canonical name of the underlying class, if it exists
null, otherwise
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getCanonicalName() method
public class Test
{
    public static void main(String[] args)
            throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c1 = Class.forName("java.lang.String");

        System.out.print("Canonical name of class represented by c1 : ");

        // returns the Canonical name of the class
        // getCanonicalName method
        System.out.println(c1.getCanonicalName());
    }
}
```

输出:

```java
Canonical name of class represented by c1 : java.lang.String
```

**4。boolean desiredassertingstatus()**:这个方法返回断言状态，如果在调用这个方法的时候初始化这个类，这个断言状态将被分配给这个类。

```java
Syntax : 
public boolean desiredAssertionStatus()
Parameters : 
NA
Returns :
the desired assertion status of the specified class.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate desiredAssertionStatus() method
public class Test
{
    public static void main(String[] args)
                         throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c1 = Class.forName("java.lang.String");

        // checking for assertion status of String class

        System.out.print("desired assertion status of " + c1.getName() + "class: ");

        // desiredAssertionStatus() method
        System.out.println(c1.desiredAssertionStatus());

    }
}
```

输出:

```java
desired assertion status of java.lang.Stringclass : false
```

**5。类<？> getComponentType()** :这个方法返回代表数组的组件类型的 Class。如果此类不表示数组类，则此方法返回 null。

```java
Syntax : 
public Class<?> getComponentType()
Parameters : 
NA
Returns :
the Class representing the component type of this class if this class is an array
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getComponentType() method
public class Test
{
    public static void main(String[] args)
    {
        int a[] = new int[2];

        // returns the Class object for array class
        Class c = a.getClass();

        System.out.print("Component type of class represented by c : ");

        // getComponentType() method
        System.out.println(c.getComponentType());

    }
}
```

输出:

```java
Component type of class represented by c : int
```

**6。类<？> [] getDeclaredclasses()** :返回一个 Class 对象的数组，该数组反映了声明为此 Class 对象所表示的类的成员的所有类和接口。
此方法包括公共、受保护、默认(包)访问以及类声明的私有类和接口，但不包括继承的类和接口。如果类没有声明任何类或接口作为成员，或者如果此类对象表示基元类型、数组类或 void，则此方法返回长度为 0 的数组。

```java
Syntax : 
public Class<?>[] getDeclaredClasses()
Parameters : 
NA
Returns :
the array of Class objects representing all the declared members of this class
Throws :
SecurityException - If a security manager, s, is present 
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getDeclaredClasses() method

public class Test
{
    // base interface
    interface A
    {
        // methods and constant declarations
    }

    // derived class
    class B implements A
    {
        // methods implementations that were declared in A
    }

    public static void main(String[] args)
    {
        // returns the Class object associated with Test class
        Class myClass = Test.class;

        // getDeclaredClasses on myClass
        // it returns array of classes and interface declare in Test class
        Class c[] = myClass.getDeclaredClasses();

        System.out.println("Declared classes and interfaces present in " +
                                                  myClass.getName() + " class : ");

        // iterating through classes and interfaces declared in Test class
        for (Class class1 : c)
        {
            System.out.println(class1);
        }

    }
}
```

输出:

```java
Declared classes and interfaces present in Test class : 
interface Test$A
class Test$B
```

**7。Field getDeclaredField(String Field name)**:此方法返回一个 Field 对象，该对象反映了由该 class 对象表示的类或接口的指定声明字段。
name 参数是一个字符串，用于指定所需字段的简单名称。请注意，此方法不会反映数组类的长度字段。

```java
Syntax : 
public Field getDeclaredField(String fieldName) 
throws NoSuchFieldException,SecurityException
Parameters : 
fieldName -  the field name
Returns :
the Field object for the specified field in this class
Throws :
NoSuchFieldException - if a field with the specified name is not found.
NullPointerException - if fieldName is null
SecurityException - If a security manager, s, is present.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getDeclaredField() method

import java.lang.reflect.Field;

public class Test
{
    // any declared field
    int i;

    public static void main(String[] args)
            throws NoSuchFieldException, SecurityException
    {
        // returns the Class object associated with Test class
        Class myClass = Test.class;

        // getDeclaredField on myClass
        Field f = myClass.getDeclaredField("i");

        System.out.println("Declared field present in " +
                                     myClass.getName() +
                                     " class specified by \"i\" : ");

        System.out.println(f);
    }
}
```

输出:

```java
Declared field present in Test class specified by "i" : 
int Test.i
```

**8。Field[] getDeclaredFields()** :这个方法返回一个 Field 对象的数组，该数组反映了这个 class 对象所表示的类或接口所声明的所有字段。这包括公共、受保护、默认(包)访问和私有字段，但不包括继承字段。
如果类或接口没有声明字段，或者这个类对象表示一个基元类型、一个数组类或 void，这个方法返回一个长度为 0 的数组。

```java
Syntax : 
public Field[] getDeclaredFields()  throws SecurityException
Parameters : 
NA
Returns :
the array of Field objects representing all the declared fields of this class
Throws :
SecurityException - If a security manager, s, is present.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getDeclaredFields() method

import java.lang.reflect.Field;

public class Test
{
    // some declared fields
    int i;
    String str;
    boolean b;

    public static void main(String[] args)
    {
        // returns the Class object associated with Test class
        Class myClass = Test.class;

        // getDeclaredFields on myClass
        Field f[] = myClass.getDeclaredFields();

        System.out.println("Declared fields present in " +
                                            myClass.getName() + " class are : ");

        // iterating through declared fields of Test class
        for (Field field : f)
        {
            System.out.println(field);
        }
    }
}
```

输出:

```java
Declared fields present in Test class are : 
int Test.i
java.lang.String Test.str
boolean Test.b
```

**9。方法 getDeclaredMethod(String Method name，Class… parameterTypes)** :此方法返回一个 Method 对象，该对象反映了此 Class 对象表示的类或接口的指定声明方法。

```java
Syntax : 
public Method getDeclaredMethod(String methodName,Class... parameterTypes) 
throws NoSuchFieldException,SecurityException
Parameters : 
methodName -  the method name
parameterTypes - the list of parameters
Returns :
the Method object for the method of this class matching the specified name and parameters
Throws :
NoSuchMethodException - if a method with the specified name is not found.
NullPointerException - if methodName is null
SecurityException - If a security manager, s, is present.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getDeclaredMethod() method

import java.lang.reflect.Method;

public class Test
{
    // any declared method
    // with a String argument
    public void m1(String str)
    {
        System.out.println(str);
    }

    public static void main(String[] args)
            throws NoSuchMethodException, SecurityException, ClassNotFoundException
    {
        // returns the Class object associated with Test class
        Class myClass = Test.class;

        // returns the Class object for the class
        // with the specified name
        Class c = Class.forName("java.lang.String");

        // getDeclaredMethod on myClass
        Method m = myClass.getDeclaredMethod("m1",c);

        System.out.println("Declared method present in " +
                                myClass.getName() +
                                " class specified by argument : " + c.getName());

        System.out.println(m);
    }
}
```

输出:

```java
Declared method present in Test class specified by argument : java.lang.String
public void Test.m1(java.lang.String)
```

**10。方法[] getDeclaredMethods()** :此方法返回一个 Method 对象数组，该数组反映了由该 class 对象表示的类或接口声明的所有方法。这包括公共、受保护、默认(包)访问和私有方法，但不包括继承的方法。
如果类或接口没有声明任何方法，或者这个类对象表示一个基元类型、一个数组类或 void，那么这个方法返回一个长度为 0 的数组。

```java
Syntax : 
public Method[] getDeclaredMethods() throws SecurityException
Parameters : 
NA
Returns :
the array of Method objects representing all the declared methods of this class
Throws :
SecurityException - If a security manager, s, is present.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getDeclaredMethods() method

import java.lang.reflect.Method;

public class Test
{
    // some declared Methods
    public void m1()
    {
        System.out.println("Inside m1 method");
    }

    static void m2()
    {
        System.out.println("Inside m2 method");
    }

    // main method
    public static void main(String[] args)
    {
        // returns the Class object associated with Test class
        Class myClass = Test.class;

        // getDeclaredMethods on myClass
        Method m[] = myClass.getDeclaredMethods();

        System.out.println("Declared methods present in " +
                                            myClass.getName() + " class are : ");

        // iterating through declared Methods of Test class
        for (Method Method : m)
        {
            System.out.println(Method);
        }
    }
}
```

输出:

```java
Declared methods present in Test class are : 
public static void Test.main(java.lang.String[])
public void Test.m1()
static void Test.m2()
```

**11 时。建造师<？> getDeclaredConstructor(类<？> … parameterTypes)** :此方法返回一个 Constructor 对象，该对象反映了此 class 对象所表示的类或接口的指定构造函数。

```java
Syntax : 
public Constructor<?> getDeclaredConstructor(Class<?>... parameterTypes) 
throws NoSuchMethodException,SecurityException
Parameters : 
parameterTypes - the list of parameters
Returns :
The Constructor object for the constructor with the specified parameter list
Throws :
NoSuchMethodException - if a Constructor with the specified parameterTypes is not found.
SecurityException - If a security manager, s, is present.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getDeclaredConstructor() Constructor

import java.lang.reflect.Constructor;

public class Test
{

    public static void main(String[] args)
            throws NoSuchMethodException, SecurityException, ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c1 = Class.forName("java.lang.Integer");
        Class c2 = Class.forName("java.lang.String");

        // getDeclaredConstructor on myClass
        Constructor con = c1.getDeclaredConstructor(c2);

        System.out.println("Declared Constructor present in " + c1.getName() +
                                  " class specified by argument : " + c2.getName());

        System.out.println(con);
    }
}
```

输出:

```java
Declared Constructor present in java.lang.Integer class specified by argument : 
java.lang.String public java.lang.Integer(java.lang.String) 
throws java.lang.NumberFormatException
```

**12 时。建造师<？>[]getDeclaredConstructors()**:这个方法返回一个 Constructor 对象的数组，该数组反映了这个 class 对象所代表的类所声明的所有构造函数。这些是公共的、受保护的、默认的(包)访问和私有的构造函数。
如果这个 Class 对象表示接口、基元类型、数组类或 void，这个方法返回一个长度为 0 的数组。

```java
Syntax : 
public Constructor<?>[] getDeclaredConstructors() throws SecurityException
Parameters : 
NA
Returns :
the array of Constructor objects representing all the declared constructors of this class
Throws :
SecurityException - If a security manager, s, is present.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getDeclaredConstructors() Constructor

import java.lang.reflect.Constructor;

public class Test
{

    public static void main(String[] args)
            throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c = Class.forName("java.lang.String");

        // getDeclaredConstructors on myClass
        Constructor con[] = c.getDeclaredConstructors();

        System.out.println("Declared Constructors present in " +
                                c.getName() + " class are : ");

        // iterating through all constructors
        for (Constructor constructor : con)
        {
            System.out.println(constructor);
        }
    }
}
```

输出:

```java
Declared Constructors present in java.lang.String class are : 
public java.lang.String(byte[],int,int)
public java.lang.String(byte[],java.nio.charset.Charset)
public java.lang.String(byte[],java.lang.String) throws 
java.io.UnsupportedEncodingException
public java.lang.String(byte[],int,int,java.nio.charset.Charset)
public java.lang.String(byte[],int,int,java.lang.String) 
throws java.io.UnsupportedEncodingException
java.lang.String(char[],boolean)
public java.lang.String(java.lang.StringBuilder)
public java.lang.String(java.lang.StringBuffer)
public java.lang.String(byte[])
public java.lang.String(int[],int,int)
public java.lang.String()
public java.lang.String(char[])
public java.lang.String(java.lang.String)
public java.lang.String(char[],int,int)
public java.lang.String(byte[],int)
public java.lang.String(byte[],int,int,int)
```

**13。类<？> getDeclaringclass()** :如果这个 Class 对象所表示的类或者接口是另一个类的成员，那么这个方法返回的 Class 对象代表了它被声明所在的类。
如果此类或接口不是任何其他类的成员，则此方法返回 null。如果此类对象表示数组类、基元类型或 void，则此方法返回 null。

```java
Syntax : 
public Class<?>  getDeclaringClass()
Parameters : 
NA
Returns :
the declaring class of this class
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getDeclaringClass() Class
import java.lang.reflect.Method;
public class Test
{
    // any method
    public void m1()
    {
        System.out.println("Inside m1 method");
    }

    public static void main(String[] args)
    {

        // returns A class object
        Class c1 = Test.class;

        // getting all methods of Test class
        // Note that methods from Object class
        // are also inherited
        Method m[] = c1.getMethods();

        for (Method method : m)
        {
            // getDeclaringClass method
            // it return declared class of this method
            System.out.println(method.getName() + " is present in "
                                            + method.getDeclaringClass());
        }

    }
}
```

输出:

```java
main is present in class Test
m1 is present in class Test
wait is present in class java.lang.Object
wait is present in class java.lang.Object
wait is present in class java.lang.Object
equals is present in class java.lang.Object
toString is present in class java.lang.Object
hashCode is present in class java.lang.Object
getClass is present in class java.lang.Object
notify is present in class java.lang.Object
notifyAll is present in class java.lang.Object
```

**14。类<？> getEnclosingClass()** :此方法返回基础类的紧接封闭类。如果基础类是顶级类，此方法返回 null。

```java
Syntax : 
public Class<?> getEnclosingClass()
Parameters : 
NA
Returns :
the immediately enclosing class of the underlying class
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getEnclosingClass() Class

public class Test
{
    // any inner class of Test class
    class A{}

    public static void main(String[] args)
    {

        // returns A class object
        Class c1 = Test.A.class;

        // getEnclosingClass method
        // it returns the class object where A class present
        Class c2 = c1.getEnclosingClass();

        System.out.println("The class " + c1.getName() + " is present in class : ");

        System.out.println(c2);

    }
}
```

输出:

```java
The class Test$A is present in class : 
class Test
```

**15。方法 getEnclosingMethod()** :如果此 Class 对象表示方法中的本地或匿名类，则返回一个 Method 对象，该对象表示基础类的直接封闭方法。

```java
Syntax : 
public Class<?> getEnclosingMethod()
Parameters : 
NA
Returns :
the immediately enclosing method of the underlying class,
if that class is a local or anonymous class;
otherwise null
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getEnclosingMethod() method

import java.lang.reflect.Method;

public class Test
{
    // any method
    public static Class m1()
    {  
        // any local class in m1
        class A{};

        // returning class A
        return A.class;
    }

    // main method
    public static void main(String[] args)
            throws ClassNotFoundException
    {
        // returns A Class object
        Class c = Test.m1();

        // getEnclosingMethod method
        Method m = c.getEnclosingMethod();

        System.out.println("The class " + c.getName() + " is present in method : ");

        System.out.println(m);

    }
}
```

输出:

```java
The class Test$1A is present in method : 
public static java.lang.Class Test.m1()
```

**16。构造函数 getEnclosingConstructor()** :如果此 Class 对象表示构造函数中的局部或匿名类，则返回一个 Constructor 对象，该对象表示基础类的直接封闭构造函数。否则返回 null。

```java
Syntax : 
public Constructor<?> getEnclosingConstructor()
Parameters : 
NA
Returns :
the immediately enclosing constructor of the underlying class,
if that class is a local or anonymous class; 
otherwise null.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getEnclosingConstructor() Constructor

import java.lang.reflect.Constructor;

public class Test
{
    Class c;

    // default(any) constructor
    public Test()
    {
        // any local class
        class A{};

        // returns A class object
        c = A.class;
    }

    public static void main(String[] args)
    {
        // creating Test class object
        Test t = new Test();

        // getEnclosingConstructor method
        Constructor con = t.c.getEnclosingConstructor();

        System.out.println("The class " + t.c.getName()
                        + " is present in constructor : ");

        System.out.println(con);

    }
}
```

输出:

```java
The class Test$1A is present in Constructor : 
public Test()
```

**17。** [**保护域**](https://docs.oracle.com/javase/7/docs/api/java/security/ProtectionDomain.html) **获取保护域()**:返回该类的保护域。如果安装了安全管理器，此方法首先调用具有 runtime permission(“getprotection domain”)权限的安全管理器的 checkPermission 方法，以确保可以获得保护域。

```java
Syntax : 
public ProtectionDomain getProtectionDomain()
Parameters : 
NA
Returns :
the ProtectionDomain of this class
Throws :
SecurityException - if a security manager s exists 
and its checkPermission method doesn't allow getting the ProtectionDomain.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getProtectionDomain() method
public class Test
{
    public static void main(String[] args)
                         throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c1 = Class.forName("java.lang.String");

        // checking for assertion status of String class

        System.out.println("protection domain of " + c1.getName() + " class : ");

        // getProtectionDomain() method
        // it will print null as String class is loaded by
        // BootStrap class loader
        System.out.println(c1.getProtectionDomain());

    }
}
```

输出:

```java
protection domain of java.lang.String class : 
ProtectionDomain  null
 null

 java.security.Permissions@7852e922 (
 ("java.security.AllPermission" "" "")
)
```

**18。布尔运算不存在(类<？扩展注解>注解类()()**:如果指定类型的注解出现在这个元素上，这个方法返回真，否则返回假。这种方法主要是为了方便访问标记注释而设计的。

```java
Specified by:
isAnnotationPresent in interface AnnotatedElement
Syntax : 
public boolean isAnnotationPresent(Class<? extends Annotation> annotationClass) 
Parameters : 
annotationClass - the Class object corresponding to the annotation type
Returns :
true if an annotation for the specified annotation type is present on this element
false, otherwise
Throws:
NullPointerException - if the given annotation class is null
```

**19。boolean issynamic()**:这个方法判断这个类是否是[合成](http://stackoverflow.com/questions/399546/synthetic-class-in-java)类。

```java
Syntax : 
public boolean isSynthetic()
Parameters : 
NA
Returns :
return true if and only if this class is a synthetic class.
```

**20。** [**URL**](https://www.geeksforgeeks.org/url-class-java-examples/) **获取资源(字符串名称)**:查找给定名称的资源。用于搜索与给定类相关联的资源的规则通过定义类的[类加载器](https://docs.oracle.com/javase/7/docs/api/java/lang/ClassLoader.html)来实现。

```java
Syntax : 
public URL getResource(String name)
Parameters : 
name - name of the desired resource
Returns :
A URL object or null if no resource with this name is found
```

**21。InputStream getResourceAsStream(字符串名称)**:查找具有给定名称的资源。用于搜索与给定类相关联的资源的规则由该类的定义类加载器实现。

```java
Syntax : 
public InputStream getResourceAsStream(String name)
Parameters : 
name - name of the desired resource
Returns :
A InputStream object or null if no resource with this name is found
Throws:
NullPointerException - If name is null
```

**22。对象[] getSigners()** :获取该类的签名者。

```java
Syntax : 
public Object[] getSigners()
Parameters : 
NA
Returns :
the signers of this class, or null if there are no signers.
In particular,it returns null if this object represents a primitive type or void.
```

**23。注释[] getAnnotations()** :此方法返回此元素上存在的所有注释。如果此元素没有注释，它将返回长度为零的数组。
这个方法的调用者可以自由修改返回的数组；它对返回给其他调用方的数组没有影响。

```java
Specified by:
getAnnotations() in interface AnnotatedElement
Syntax : 
public Annotation[] getAnnotations()
Parameters : 
NA
Returns :
all annotations present on this element
```

**24。< A 扩展注释> A getAnnotation(类< A >注释类)**:如果存在此类注释，则该方法返回指定类型的此元素的注释，否则为空。

```java
Specified by:
getAnnotations() in interface AnnotatedElement
Syntax : 
public Annotation[] getAnnotations()
Parameters : 
annotationClass - the Class object corresponding to the annotation type
Returns :
return element's annotation for the specified annotation type if present on this element
else null
Throws:
NullPointerException - if the given annotation class is null
```

**25。annotation[]getDeclaredAnnotations()**:返回直接出现在此元素上的所有注释。与此接口中的其他方法不同，此方法忽略继承的注释。如果没有注释直接出现在这个元素上，它将返回一个长度为零的数组。
这个方法的调用者可以自由修改返回的数组；它对返回给其他调用方的数组没有影响。

```java
Specified by:
getDeclaredAnnotations in interface AnnotatedElement
Syntax : 
public Annotation[] getDeclaredAnnotations()
Parameters : 
NA
Returns :
All annotations directly present on this element
```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。