# Java 中的 Java.lang.Class 类|集合 1

> 原文:[https://www . geesforgeks . org/Java-lang-class-class-Java-set-1/](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)

Java 在 java.lang 包中提供了一个名为 **Class** 的类。类的实例表示运行的 Java 应用程序中的类和接口。基本的 Java 类型(布尔型、字节型、字符型、短整型、整型、长整型、浮点型和双精度型)和关键字 *void* 也表示为类对象。它没有公共构造函数。类对象由 Java 虚拟机( [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) )自动构造。这是最后一节课，所以我们不能延长。

类类方法在[反射](https://www.geeksforgeeks.org/reflection-in-java/) API 中被广泛使用。

**创建类对象**

创建类对象有三种**方式:**

1.  ****Class.forName(“className”) :** Since class Class doesn’t contain any constructor, there is static **factory** method present in class Class, which is *Class.forName()* , used for creating object of class Class. Below is the syntax :

    ```
    Class c = Class.forName(String className)

    ```

    上面的语句为作为字符串参数(类名)传递的类创建了类对象。请注意，参数类名必须是要为其创建类对象的所需类的完全限定名。java 中返回相同类对象的任何类中的方法也称为工厂方法。要为其创建类对象的类名在运行时确定。** 
2.  ****Myclass.class :** When we write .class after a class name, it references the Class object that represents the given class. It is mostly used with primitive data types and only when we know the name of class. The class name for which Class object is to be created is determined at compile-time. Below is the syntax :

    ```
    Class c = int.class

    ```

    请注意，此方法与类名一起使用，而不是与类实例一起使用。例如

    ```
    A a = new A();   // Any class A
    Class c = A.class; // No error
    Class c = a.class; // Error 

    ```** 
3.  ****obj.getClass() :** 这个方法出现在 [Object](https://www.geeksforgeeks.org/object-class-in-java/) 类中。它返回这个(obj)对象的运行时类。下面是语法:

    ```
    A a = new A();   // Any class A
    Class c = a.getClass();

    ```** 

****方法:****

1.  ****String toString()** : This method converts the Class object to a string. It returns the string representation which is the string “class” or “interface”, followed by a space, and then by the fully qualified name of the class. If the Class object represents a primitive type, then this method returns the name of the primitive type and if it represents *void* then it returns “void”.

    ```
    Syntax : 
    public String toString()
    Parameters : 
    NA
    Returns :
    a string representation of this class object.
    Overrides :
    toString in class Object

    ```

    ```
    // Java program to demonstrate toString() method
    public class Test
    {
        public static void main(String[] args)
                             throws ClassNotFoundException
        { 
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.String");
            Class c2 = int.class;
            Class c3 = void.class;

            System.out.print("Class represented by c1: ");

            // toString method on c1
            System.out.println(c1.toString());

            System.out.print("Class represented by c2: ");

            // toString method on c2
            System.out.println(c2.toString());

            System.out.print("Class represented by c3: ");

            // toString method on c3
            System.out.println(c3.toString());
        }
    }
    ```

    输出:

    ```
    Class represented by c1: class java.lang.String
    Class represented by c2: int
    Class represented by c3: void

    ```** 
2.  ****Class<?> forName(String className)** : As discussed earlier, this method returns the Class object associated with the class or interface with the given string name. The other variant of this method is discussed next.

    ```
    Syntax : 
    public static Class<?> forName(String className) throws ClassNotFoundException
    Parameters : 
    className - the fully qualified name of the desired class.
    Returns :
    return the Class object for the class with the specified name.
    Throws :
    LinkageError : if the linkage fails
    ExceptionInInitializerError - if the initialization provoked by this method fails
    ClassNotFoundException - if the class cannot be located

    ```

    ```
    // Java program to demonstrate forName() method
    public class Test
    {
        public static void main(String[] args)
                             throws ClassNotFoundException
        {
            // forName method
            // it returns the Class object for the class 
            // with the specified name 
            Class c = Class.forName("java.lang.String");

            System.out.print("Class represented by c : " + c.toString());
        }
    }
    ```

    输出:

    ```
    Class represented by c : class java.lang.String

    ```** 
3.  ****Class<?> forName(String className,boolean initialize, ClassLoader loader)** : This method also returns the Class object associated with the class or interface with the given string name using the given class loader.

    指定的类加载器用于加载类或接口。如果参数加载器为空，则通过中的引导类加载器加载该类。只有当 initialize 参数为 true 并且该类之前没有初始化过时，该类才会初始化。

    ```
    Syntax : 
    public static Class<?> forName(String className,boolean initialize, ClassLoader loader) 
    throws ClassNotFoundException
    Parameters : 
    className - the fully qualified name of the desired class
    initialize - whether the class must be initialized
    loader - class loader from which the class must be loaded
    Returns :
    return the Class object for the class with the specified name.
    Throws :
    LinkageError : if the linkage fails
    ExceptionInInitializerError - if the initialization provoked by this method fails
    ClassNotFoundException - if the class cannot be located

    ```

    ```
    // Java program to demonstrate forName() method
    public class Test
    {
        public static void main(String[] args)
                             throws ClassNotFoundException
        {
            // returns the Class object for this class
            Class myClass = Class.forName("Test");

            ClassLoader loader = myClass.getClassLoader();

            // forName method
            // it returns the Class object for the class 
            // with the specified name using the given class loader
            Class c = Class.forName("java.lang.String",true,loader);

            System.out.print("Class represented by c : " + c.toString());
        }
    }
    ```

    输出:

    ```
    Class represented by c : class java.lang.String

    ```** 
4.  ****T newInstance()** : This method creates a new instance of the class represented by this Class object. The class is created as if by a *new* expression with an empty argument list. The class is initialized if it has not already been initialized.

    ```
    Syntax : 
    public T newInstance() throws InstantiationException,IllegalAccessException
    TypeParameters : 
    T - The class type whose instance is to be returned
    Parameters : 
    NA
    Returns :
    a newly allocated instance of the class represented by this object.
    Throws :
    IllegalAccessException - if the class or its nullary constructor is not accessible.
    InstantiationException - if this Class represents an abstract class, an interface,
    an array class, a primitive type, or void
    or if the class has no nullary constructor; 
    or if the instantiation fails for some other reason.
    ExceptionInInitializerError - if the initialization provoked by this method fails.
    SecurityException - If a security manager, s, is present

    ```

    ```
    // Java program to demonstrate newInstance() method
    public class Test
    {
        public static void main(String[] args)
                             throws ClassNotFoundException, InstantiationException,
                             IllegalAccessException
        {
            // returns the Class object for this class
            Class myClass = Class.forName("Test");

            // creating new instance of this class
            // newInstance method
            Object obj = myClass.newInstance();

            // returns the runtime class of obj
            System.out.println("Class of obj : " + obj.getClass());
        }
    }
    ```

    输出:

    ```
    Class of obj : class Test

    ```** 
5.  ****boolean isInstance(Object obj)** : This method determines if the specified Object is assignment-compatible with the object represented by this Class. It is equivalent to [instanceof](https://www.geeksforgeeks.org/java-instanceof-and-its-applications/) operator in java.

    ```
    Syntax : 
    public boolean isInstance(Object obj)
    Parameters : 
    obj - the object to check
    Returns :
    true if obj is an instance of this class else return false

    ```

    ```
    // Java program to demonstrate isInstance() method
    public class Test
    {
        public static void main(String[] args)
                             throws ClassNotFoundException
        {
            // returns the Class object for the class 
            // with the specified name 
            Class c = Class.forName("java.lang.String");

            String s = "GeeksForGeeks";
            int i = 10;

            // checking for Class instance
            // isInstance method
            boolean b1 = c.isInstance(s);
            boolean b2 = c.isInstance(i);

            System.out.println("is s instance of String : " + b1);
            System.out.println("is i instance of String : " + b1);

        }
    }
    ```

    输出:

    ```
    is s instance of String : true
    is i instance of String : false

    ```** 
6.  ****boolean isAssignableFrom(Class<?> cls)** : This method determines if the class or interface represented by this Class object is either the same as, or is a superclass or superinterface, of the class or interface represented by the specified Class parameter.

    ```
    Syntax : 
    public boolean isAssignableFrom(Class<?> cls)
    Parameters : 
    cls - the Class object to be checked
    Returns :
    true if objects of the type cls can be assigned to objects of this class
    Throws:
    NullPointerException - if the specified Class parameter is null.

    ```

    ```
    // Java program to demonstrate isAssignableFrom() method
    public class Test extends Thread
    {
        public static void main(String[] args)
                             throws ClassNotFoundException, InstantiationException,
                             IllegalAccessException
        {
            // returns the Class object for this class
            Class myClass = Class.forName("Test");

            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.Thread");
            Class c2 = Class.forName("java.lang.String");

           // isAssignableFrom method on c1
           // it checks whether Thread class is assignable from Test
           boolean b1 = c1.isAssignableFrom(myClass);

           // isAssignableFrom method on c2
           // it checks whether String class is assignable from Test
           boolean b2 = c2.isAssignableFrom(myClass);

           System.out.println("is Thread class Assignable from Test : " + b1);
           System.out.println("is String class Assignable from Test : " + b2);

        }
    }
    ```

    输出:

    ```
    is Thread class Assignable from Test : true
    is String class Assignable from Test : false

    ```** 
7.  ****boolean isInterface()** : This method determines if the specified Class object represents an [interface](https://www.geeksforgeeks.org/interfaces-in-java/) type.

    ```
    Syntax : 
    public boolean isInterface()
    Parameters : 
    NA
    Returns :
    return true if and only if this class represents an interface type else return false

    ```

    ```
    // Java program to demonstrate isInterface() method
    public class Test
    {
        public static void main(String[] args)
                             throws ClassNotFoundException
        {
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.String");
            Class c2 = Class.forName("java.lang.Runnable");

            // checking for interface type

            // isInterface method on c1
            boolean b1 = c1.isInterface();

            // is Interface method on c2
            boolean b2 = c2.isInterface();

            System.out.println("is java.lang.String an interface : " + b1);
            System.out.println("is java.lang.Runnable an interface : " + b2);
        }
    }
    ```

    输出:

    ```
    is java.lang.String an interface : false
    is java.lang.Runnable an interface : true

    ```** 
8.  ****boolean isPrimitive()** : This method determines if the specified Class object represents a primitive type.

    ```
    Syntax : 
    public boolean isPrimitive() 
    Parameters : 
    NA
    Returns :
    return true if and only if this class represents a primitive type else return false

    ```

    ```
    // Java program to demonstrate isPrimitive method
    public class Test
    {
        public static void main(String[] args) 
        {
            // returns the Class object associated with an integer;
            Class c1 = int.class;

           // returns the Class object associated with Test class
            Class c2 = Test.class;

            // checking for primitive type

            // isPrimitive method on c1
            boolean b1 = c1.isPrimitive();

            // isPrimitive method on c2
            boolean b2 = c2.isPrimitive();

            System.out.println("is "+c1.toString()+" primitive : " + b1);
            System.out.println("is "+c2.toString()+" primitive : " + b2);
        }
    }
    ```

    输出:

    ```
    is int primitive : true
    is class Test primitive : false

    ```** 
9.  ****boolean isArray()** : This method determines if the specified Class object represents an array class.

    ```
    Syntax : 
    public boolean isArray() 
    Parameters : 
    NA
    Returns :
    return true if and only if this class represents an array type else return false

    ```

    ```
    // Java program to demonstrate isArray method
    public class Test
    {
        public static void main(String[] args)
        {
            int a[] = new int[2];

            // returns the Class object for array class
            Class c1 = a.getClass();

            // returns the Class object for Test class
            Class c2 = Test.class;

            // checking for array type

            // isArray method on c1
            boolean b1 = c1.isArray();

            // is Array method on c2
            boolean b2 = c2.isArray();

            System.out.println("is "+c1.toString()+" an array : " + b1);
            System.out.println("is "+c2.toString()+" an array : " + b2);

        }
    }
    ```

    输出:

    ```
    is class [I an array : true
    is class Test an array : false

    ```** 
10.  ****boolean is onymous class()**:当且仅当这个类是匿名类时，这个方法返回 true。匿名类类似于本地类，只是它们没有名称。

    ```
    Syntax : 
    public boolean isAnonymousClass() 
    Parameters : 
    NA
    Returns :
    true if and only if this class is an anonymous class.
    false,otherwise.

    ```** 
11.  ****布尔 isLocalClass()** :当且仅当此类是本地类时，此方法返回 true。本地类是在 Java 代码块中本地声明的类，而不是作为类的成员。

    ```
    Syntax : 
    public boolean isLocalClass()
    Parameters : 
    NA
    Returns :
    true if and only if this class is a local class.
    false,otherwise.

    ```** 
12.  ****boolean isMemberClass()** : This method returns true if and only if the this class is a Member class.A member class is a class that is declared as a non-static member of a containing class.

    ```
    Syntax : 
    public boolean isMemberClass() 
    Parameters : 
    NA
    Returns :
    true if and only if this class is a Member class.
    false,otherwise.

    ```

    下面是解释 isAnonymousClass()方法、isLocalClass 方法和 isMemberClass()方法的使用的 Java 程序。

    ```
    // Java program to demonstrate isAnonymousClass() ,isLocalClass 
    // and isMemberClass() method

    public class Test
    {
        // any Member class of Test
        class A{}

        public static void main(String[] args) 
        {
            // declaring an anonymous class
            Test t1 = new Test()
            {
                //  class definition of anonymous class
            };

            // returns the Class object associated with t1 object
            Class c1 = t1.getClass();

            // returns the Class object associated with Test class
            Class c2 = Test.class;

            // returns the Class object associated with A class
            Class c3 = A.class;

            // checking for Anonymous class
            // isAnonymousClass method
            boolean b1 = c1.isAnonymousClass();
            System.out.println("is "+c1.toString()+" an anonymous class : "+b1);

            // checking for Local class
            // isLocalClass method
            boolean b2 = c2.isLocalClass();
            System.out.println("is "+c2.toString()+" a local class : " + b2);

            // checking for Member class
            // isMemberClass method
            boolean b3 = c3.isMemberClass();
            System.out.println("is "+c3.toString()+" a member class : " + b3);

        }
    }
    ```

    输出:

    ```
    is class Test$1 an anonymous class : true
    is class Test a local class : false
    is class Test$A a member class : true

    ```** 
13.  ****boolean isEnum()** : This method returns true if and only if this class was declared as an enum in the source code.

    ```
    Syntax : 
    public boolean isEnum() 
    Parameters : 
    NA
    Returns :
    true iff this class was declared as an enum in the source code.
    false,otherwise.

    ```

    ```
    // Java program to demonstrate isEnum() method

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

            // checking for Enum class
            // isEnum method
            boolean b1 = c1.isEnum();
            boolean b2 = c2.isEnum();

            System.out.println("is "+c1.toString()+" an Enum class : " + b1);
            System.out.println("is "+c2.toString()+" an Enum class : " + b2);
        }
    }
    ```

    输出:

    ```
    is class Color an Enum class : true
    is class Test an Enum class : false

    ```** 
14.  ****boolean isAnnotation()** : This method determines if this Class object represents an annotation type. Note that if this method returns true, isInterface() method will also return true, as all annotation types are also interfaces.

    ```
    Syntax : 
    public boolean isAnnotation() 
    Parameters : 
    NA
    Returns :
    return true if and only if this class represents an annotation type else return false

    ```

    ```
    // Java program to demonstrate isAnnotation() method

    // declaring an Annotation Type
    @interface A
    {
         // Annotation element definitions
    }

    public class Test
    {
        public static void main(String[] args)
                             throws ClassNotFoundException
        {
            // returns the Class object associated with A  annotation
            Class c1 = A.class;

            // returns the Class object associated with Test class
            Class c2 = Test.class;

            // checking for annotation type
            // isAnnotation method
            boolean b1 = c1.isAnnotation();
            boolean b2 = c2.isAnnotation();

            System.out.println("is "+c1.toString()+" an annotation  : " + b1);
            System.out.println("is "+c2.toString()+" an annotation : " + b2);

        }
    }
    ```

    输出:

    ```
    is interface A an annotation  : true
    is class Test an annotation : false

    ```** 
15.  ****String getName()** : This method returns the name of the entity (class, interface, array class, primitive type, or void) represented by this Class object, as a String.

    ```
    Syntax : 
    public String getName()
    Parameters : 
    NA
    Returns :
    returns the name of the name of the entity 
    represented by this object.

    ```

    ```
    // Java program to demonstrate getName() method
    public class Test
    {
        public static void main(String[] args) 
        {
            // returns the Class object associated with Test class
            Class c = Test.class;

            System.out.print("Class Name associated with c : ");

            // returns the name of the class
            // getName method
            System.out.println(c.getName());
        }
    }
    ```

    输出:

    ```
    Class Name associated with c : Test

    ```** 
16.  ****String getSimpleName()** : This method returns the name of the underlying class as given in the source code. It returns an empty string if the underlying class is anonymous class.

    数组的简单名称是附加了“]”的组件类型的简单名称。特别是组件类型为匿名的数组的简单名称是“[]”。

    ```
    Syntax : 
    public String getSimpleName()
    Parameters : 
    NA
    Returns :
    the simple name of the underlying class

    ```

    ```
    // Java program to demonstrate getSimpleName() method
    public class Test
    {
        public static void main(String[] args) 
                throws ClassNotFoundException 
        {
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.String");

            System.out.print("Class Name associated with c : ");

            // returns the name of the class
            // getName method
            System.out.println(c1.getName());

            System.out.print("Simple class Name associated with c : ");

            // returns the simple name of the class
            // getSimpleName method
            System.out.println(c1.getSimpleName());
        }
    }
    ```

    输出:

    ```
    Class Name associated with c : java.lang.String
    Simple class Name associated with c : String

    ```** 
17.  ****ClassLoader getClassLoader()** : This method returns the class loader for this class. If the class loader is bootstrap classloader then this method returned null, as bootstrap classloader is implemented in native languages like C, C++.
    If this object represents a primitive type or void,then also null is returned.

    ```
    Syntax : 
    public ClassLoader getClassLoader()
    Parameters : 
    NA
    Returns :
    the class loader that loaded the class or interface represented by this object
    represented by this object.
    Throws :
    SecurityException - If a security manager and its checkPermission method 
    denies access to the class loader for the class.

    ```

    ```
    // Java program to demonstrate getClassLoader() method
    public class Test
    {
        public static void main(String[] args)
                             throws ClassNotFoundException
        {
            // returns the Class object for this class
            Class myClass = Class.forName("Test");

            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.String");

            // returns the Class object for primitive int
            Class c2 = int.class;

            System.out.print("Test class loader : ");

            // getting the class loader for Test class
            // getClassLoader method on myClass
            System.out.println(myClass.getClassLoader());

            System.out.print("String class loader : ");

            // getting the class loader for String class
            // we will get null as String class is loaded
            // by BootStrap class loader
            // getClassLoader method on c1
            System.out.println(c1.getClassLoader());     

            System.out.print("primitive int loader : ");

            // getting the class loader for primitive int
            // getClassLoader method on c2
            System.out.println(c2.getClassLoader());
        }
    }
    ```

    输出:

    ```
    Test class loader : sun.misc.Launcher$AppClassLoader@73d16e93
    String class loader : null
    primitive int loader : null

    ```** 
18.  ****TypeVariable<Class<T>>[ ] getTypeParameters()** : This method returns an array of [TypeVariable](https://docs.oracle.com/javase/7/docs/api/java/lang/reflect/TypeVariable.html) objects that represent the type variables declared by the generic declaration represented by this [GenericDeclaration](https://docs.oracle.com/javase/7/docs/api/java/lang/reflect/GenericDeclaration.html) object, in declaration order

    ```
    Syntax : 
    public TypeVariable<Class<T>>[] getTypeParameters()
    Specified by:
    getTypeParameters in interface GenericDeclaration
    Parameters : 
    NA
    Returns :
    an array of TypeVariable objects that represent the type variables declared 
    by this generic declaration represented by this object.
    Throws :
    GenericSignatureFormatError - if the generic signature of this generic declaration 
    does not conform to the format specified in JVM.

    ```

    ```
    // Java program to demonstrate getTypeParameters() method

    import java.lang.reflect.TypeVariable;

    public class Test
    {
        public static void main(String[] args)
                             throws ClassNotFoundException
        {
            // returns the Class object for the class 
            // with the specified name 
            Class c = Class.forName("java.util.Set");

            // getting array of TypeVariable for myClass object
            // getTypeParameters method
            TypeVariable[] tv = c.getTypeParameters();

            System.out.println("TypeVariables in "+c.getName()+" class : ");

            // iterating through all TypeVariables
            for (TypeVariable typeVariable : tv)
            {
                System.out.println(typeVariable);
            }

        }
    }
    ```

    输出:

    ```
    TypeVariables in java.util.Set class : 
    E

    ```** 
19.  ****Class<? super T> getSuperclass()** : This method returns the Class representing the superclass of the entity (class, interface, primitive type or void) represented by this Class.
    If this Class represents either the Object class, an interface, a primitive type, or void, then null is returned.
    If this object represents an array class then the Class object representing the Object class is returned.

    ```
    Syntax : 
    public Class<? super T> getSuperclass() 
    Parameters : 
    NA
    Returns :
    the superclass of the class represented by this object

    ```

    ```
    // Java program to demonstrate getSuperclass() method

    // base class
    class A
    {
        // methods and fields
    }

    // derived class
    class B extends A
    {

    }

    // Driver class
    public class Test
    {
        public static void main(String[] args) 
                throws ClassNotFoundException 

        {
            // returns the Class object associated with Test class
            Class myClass = Test.class;

            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("A");
            Class c2 = Class.forName("B");
            Class c3 = Class.forName("java.lang.Object");

            // getSuperclass method returns the superclass of the class represented 
            // by this class object 

            System.out.print("Test superclass : ");

            // getSuperclass method on myClass
            System.out.println(myClass.getSuperclass());

            System.out.print("A superclass : ");

            // getSuperclass method on c1
            System.out.println(c1.getSuperclass());

            System.out.print("B superclass : ");

            // getSuperclass method on c2
            System.out.println(c2.getSuperclass());

            System.out.print("Object superclass : ");

            // getSuperclass method on c3
            System.out.println(c3.getSuperclass());
        }
    }
    ```

    输出:

    ```
    Test superclass : class java.lang.Object
    A superclass : class java.lang.Object
    B superclass : class A
    Object superclass : null

    ```** 
20.  ****Type getGenericSuperclass()** : This method returns the Type representing the direct superclass of the entity (class, interface, primitive type or void) represented by this Class.

    如果此类表示对象类、接口、基元类型或 void，则返回 null。如果此对象表示数组类，则返回表示对象类的类对象。

    ```
    Syntax : 
    public Type getGenericSuperclass()
    Parameters : 
    NA
    Returns :
    the superclass of the class represented by this object
    Throws:
    GenericSignatureFormatError - if the generic class signature does not conform to the format 
    specified in JVM
    TypeNotPresentException - if the generic superclass refers to a non-existent 
    type declaration MalformedParameterizedTypeException - if the generic 
    superclass refers to a parameterized type
    that cannot be instantiated for any reason

    ```

    ```
    // Java program to demonstrate 
    // getGenericSuperclass() method
    public class Test
    {
        public static void main(String[] args) 
                throws ClassNotFoundException 

        {
            // returns the Class object associated with Test class
            Class myClass = Test.class;

            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.util.ArrayList");
            Class c3 = Class.forName("java.lang.Object");

            // getGenericSuperclass method returns the generic 
            // superclass of the class represented 
            // by this class object 

            System.out.print("Test superclass : ");

            // getGenericSuperclass method on myClass
            System.out.println(myClass.getGenericSuperclass());

            System.out.print("ArrayList superclass : ");

            // getGenericSuperclass method on c1
            System.out.println(c1.getGenericSuperclass());

            System.out.print("Object superclass : ");

            // getGenericSuperclass method on c3
            System.out.println(c3.getGenericSuperclass());
        }
    }
    ```

    输出:

    ```
    Test superclass : class java.lang.Object
    Set superclass : java.util.AbstractList<E>
    Object superclass : null

    ```** 
21.  ****Class<?>[] getInterfaces()** : This method returns the interfaces implemented by the class or interface represented by this object.

    如果此对象表示不实现接口的类或接口，则方法返回长度为 0 的数组。
    如果这个对象表示一个基元类型或者 void，那么这个方法返回一个长度为 0 的数组。

    ```
    Syntax : 
    public Class<?>[] getInterfaces()
    Parameters : 
    NA
    Returns :
    an array of interfaces implemented by this class.

    ```

    ```
    // Java program to demonstrate getInterfaces() method

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

    // Driver class
    public class Test
    {
        public static void main(String[] args) 
                throws ClassNotFoundException 

        {
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("B");
            Class c2 = Class.forName("java.lang.String");

            // getInterface method on c1
            // it returns the interfaces implemented by B class
            Class c1Interfaces[] = c1.getInterfaces();

            // getInterface method on c2
            // returns the interfaces implemented by String class
            Class c2Interfaces[] = c2.getInterfaces();

            System.out.println("interfaces implemented by B class : ");

            // iterating through B class interfaces
            for (Class class1 : c1Interfaces) 
            {
                System.out.println(class1);
            }

            System.out.println("interfaces implemented by String class : ");

            // iterating through String class interfaces
            for (Class class1 : c2Interfaces) 
            {
                System.out.println(class1);
            }
        }
    }
    ```

    输出:

    ```
    interfaces implemented by B class : 
    interface A
    interfaces implemented by String class : 
    interface java.io.Serializable
    interface java.lang.Comparable
    interface java.lang.CharSequence

    ```** 
22.  ****Type[] getGenericInterfaces()** : This method returns the Types representing the interfaces directly implemented by the class or interface represented by this object.

    如果此对象表示不实现接口的类或接口，则方法返回长度为 0 的数组。
    如果这个对象表示一个基元类型或者 void，那么这个方法返回一个长度为 0 的数组。

    ```
    Syntax : 
    public Type[] getGenericInterfaces()
    Parameters : 
    NA
    Returns :
    an array of interfaces implemented by this class
    Throws:
    GenericSignatureFormatError - if the generic class signature does not conform to the format 
    specified in JVM
    TypeNotPresentException - if the generic superinterfaces refers to 
    a non-existent type declaration MalformedParameterizedTypeException - if the
    generic superinterfaces refers to a parameterized type
    that cannot be instantiated for any reason

    ```

    ```
    // Java program to demonstrate getGenericInterfaces() method

    import java.lang.reflect.Type;

    public class Test
    {
        public static void main(String[] args) 
                throws ClassNotFoundException 

        {
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.util.Set");

            // getGenericInterfaces() on c1
            // it returns the interfaces implemented by Set interface
            Type c1GenericInterfaces[] = c1.getGenericInterfaces();

            System.out.println("interfaces implemented by Set interface : ");

            // iterating through Set class interfaces
            for (Type type : c1GenericInterfaces)
            {
                System.out.println(type);
            }
        }
    }
    ```

    输出:

    ```
    interfaces implemented by Set interface : 
    java.util.Collection<E>

    ```** 
23.  ****Package getPackage()** : This method returns the package for this class. The classloader subsystem in [JVM Architecture](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) used this method to find the package of a class or interface.

    ```
    Syntax : 
    public Package getPackage()
    Parameters : 
    NA
    Returns :
    the package of the class, 
    or null if no package information is available
    from the archive or codebase. 

    ```

    ```
    // Java program to demonstrate getPackage() method
    public class Test
    {
        public static void main(String[] args) throws ClassNotFoundException
        {
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.String");
            Class c2 = Class.forName("java.util.ArrayList");

            // getting package of class

            // getPackage method on c1
            System.out.println(c1.getPackage());

            // getPackage method on c2
            System.out.println(c2.getPackage());

        }
    }
    ```

    输出:

    ```
    package java.lang, Java Platform API Specification, version 1.8
    package java.util, Java Platform API Specification, version 1.8

    ```** 
24.  ****Field[] getFields()** : This method returns an array of Field objects reflecting all the accessible public fields of the class(and of all its superclasses) or interface(and of all its superclasses) represented by this Class object.

    ```
    Syntax : 
    public Field[] getFields()  throws SecurityException
    Parameters : 
    NA
    Returns :
    the array of Field objects representing the public fields
    and  array of length 0 if the class or interface has no accessible public fields
    or if this Class object represents a primitive type or void.
    Throws :
    SecurityException - If a security manager, s, is present.

    ```

    ```
    // Java program to demonstrate getFields() method

    import java.lang.reflect.Field;

    public class Test
    {
        public static void main(String[] args) 
                throws SecurityException,ClassNotFoundException
        {
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.Integer");

            // getFields method on c1
            // it array of fields of Integer class
            Field F[] = c1.getFields();

            System.out.println("Below are the fields of Integer class : ");

            // iterating through all fields of  String class
            for (Field field : F) 
            {
                    System.out.println(field);
            } 
        }
    }
    ```

    输出:

    ```
    Below are the fields of Integer class :
    public static final int java.lang.Integer.MIN_VALUE
    public static final int java.lang.Integer.MAX_VALUE
    public static final java.lang.Class java.lang.Integer.TYPE
    public static final int java.lang.Integer.SIZE
    public static final int java.lang.Integer.BYTES

    ```** 
25.  ****Class<?>[ ] getClasses()** : This method returns an array containing Class objects representing all the public classes and interfaces that are members of the class represented by this Class object. The array contains public class and interface members inherited from superclasses and public class and interface members declared by the class.

    如果此类对象没有公共成员类或接口，则此方法返回长度为 0 的数组。
    如果这个 Class 对象表示一个基元类型、一个数组类或 void，那么这个方法也返回一个长度为 0 的数组。

    ```
    Syntax : 
    Class<?>[ ] getClasses()
    Parameters : 
    NA
    Returns :
    the array of Class objects representing the public members of this class
    Throws :
    SecurityException - If a security manager, s, is present.

    ```

    ```
    // Java program to demonstrate getClasses() method

    public class Test
    {
        // base interface
        public interface A
        {
            // methods and constant declarations
        }

        // derived class
        public class B implements A
        {
            // methods implementations that were declared in A
        }

        public static void main(String[] args) 
                throws ClassNotFoundException 

        {
            // returns the Class object associated with Test class
            Class c1 = Test.class;

            // getClasses method on c1
            // it returns the array of Class objects containing the all 
            // public classes and interfaces  represented by Test class
            Class[] c1Classes = c1.getClasses();

            System.out.println("public members of Test class : ");

            // iterating through all public members of Test class
            for (Class class1 : c1Classes)
            {
                System.out.println(class1);
            }

        }
    }
    ```

    输出:

    ```
    public members of Test class : 
    interface Test$A
    class Test$B

    ```** 
26.  ****Method[] getMethods()** : This method returns an array of Method objects reflecting all the accessible public methods of the class or interface and those inherited from superclasses and super interfaces represented by this Class object.

    ```
    Syntax : 
    public Method[] getMethods() throws SecurityException
    Parameters : 
    NA
    Returns :
    the array of Method objects representing the public methods
    and  array of length 0 if the class or interface has no accessible public method
    or if this Class object represents a primitive type or void.
    Throws :
    SecurityException - If a security manager, s, is present.

    ```

    ```
    // Java program to demonstrate getMethods() method

    import java.lang.reflect.Method;

    public class Test
    {
        public static void main(String[] args) 
                throws SecurityException,ClassNotFoundException
        {
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.Object");

            // getMethods method on c1
            // it returns array of methods of Object class
            Method M[] = c1.getMethods();

            System.out.println("Below are the methods of Object class : ");

            // iterating through all methods of Object class
            for (Method method : M) 
            {
            System.out.println(method);
            }
        }
    }
    ```

    输出:

    ```
    Below are the methods of Object class : 
    public final void java.lang.Object.wait() throws java.lang.InterruptedException
    public final void java.lang.Object.wait(long,int) throws java.lang.InterruptedException
    public final native void java.lang.Object.wait(long) throws java.lang.InterruptedException
    public boolean java.lang.Object.equals(java.lang.Object)
    public java.lang.String java.lang.Object.toString()
    public native int java.lang.Object.hashCode()
    public final native java.lang.Class java.lang.Object.getClass()
    public final native void java.lang.Object.notify()
    public final native void java.lang.Object.notifyAll()

    ```** 
27.  ****Constructor<?>[] getConstructors()** : This method returns an array of Constructor objects reflecting all the public constructors of the class represented by this Class object.

    ```
    Syntax : 
    public Constructor<?>[] getConstructors() throws SecurityException
    Parameters : 
    NA
    Returns :
    the array of Constructor objects representing the public constructors of this class
    and  array of length 0 if the class or interface has no accessible public constructor
    or if this Class object represents a primitive type or void.
    Throws :
    SecurityException - If a security manager, s, is present.

    ```

    ```
    // Java program to demonstrate getConstructors() method

    import java.lang.reflect.Constructor;

    public class Test
    {
        public static void main(String[] args) 
                throws SecurityException,ClassNotFoundException
        {
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.Boolean");

            // getConstructor method on c1
            // it returns an array of constructors of Boolean class
            Constructor C[] = c1.getConstructors();

            System.out.println("Below are the constructors of Boolean class :");

            // iterating through all constructors
            for (Constructor constructor : C) 
            {
            System.out.println(constructor);
            }
        }
    }
    ```

    输出:

    ```
    Below are the constructors of Boolean class :
    public java.lang.Boolean(boolean)
    public java.lang.Boolean(java.lang.String)

    ```** 
28.  ****Field getField(String fieldName)** : This method returns a Field object that reflects the specified public member field of the class or interface represented by this Class object.

    ```
    Syntax : 
    public Field getField(String fieldName) throws NoSuchFieldException,SecurityException
    Parameters : 
    fieldName -  the field name
    Returns :
    the Field object of this class specified by name
    Throws :
    NoSuchFieldException - if a field with the specified name is not found.
    NullPointerException - if fieldName is null
    SecurityException - If a security manager, s, is present.

    ```

    ```
    // Java program to demonstrate getField() method

    import java.lang.reflect.Field;

    public class Test
    {
        public static void main(String[] args) 
                throws SecurityException,ClassNotFoundException,
                       NoSuchFieldException
        {
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.Integer");

            // getField method on c1
            // it checks a public field in Integer class with specified parameter
            Field f = c1.getField("MIN_VALUE");

            System.out.println("public field in Integer class with MIN_VALUE name :");
            System.out.println(f);
        }
    }
    ```

    输出:

    ```
    public field in Integer class with MIN_VALUE name :
    public static final int java.lang.Integer.MIN_VALUE

    ```** 
29.  ****Method getMethod(String methodName,Class… parameterTypes)** : This method returns a Method object that reflects the specified public member method of the class or interface represented by this Class object.

    ```
    Syntax : 
    public Method getMethod(String methodName,Class... parameterTypes) throws 
    NoSuchFieldException,SecurityException
    Parameters : 
    methodName -  the method name
    parameterTypes - the list of parameters
    Returns :
    the method object of this class specified by name
    Throws :
    NoSuchMethodException - if a method with the specified name is not found.
    NullPointerException - if methodName is null
    SecurityException - If a security manager, s, is present.

    ```

    ```
    // Java program to demonstrate getMethod() method

    import java.lang.reflect.Method;

    public class Test
    {
        public static void main(String[] args) 
                throws SecurityException,ClassNotFoundException,
                       NoSuchMethodException
        {
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.Integer");
            Class c2 = Class.forName("java.lang.String");

            // getMethod method on c1
            // it checks for a public Method in Integer class
            Method m = c1.getMethod("parseInt",c2);

            System.out.println("method in Integer class specified by parseInt : ");
            System.out.println(m);
        }
    }
    ```

    输出:

    ```
    public method in Integer class specified by parseInt : 
    public static int java.lang.Integer.parseInt(java.lang.String) 
    throws java.lang.NumberFormatException

    ```** 
30.  ****Constructor<?> getConstructor(Class<?>… parameterTypes)** : This method returns a Constructor object that reflects the specified public constructor of the class represented by this Class object.The parameterTypes parameter is an array of Class objects that identify the constructor’s formal parameter types, in declared order.

    ```
    Syntax : 
    public Constructor<?> getConstructor(Class<?>... parameterTypes) 
    throws NoSuchMethodException,SecurityException
    Parameters : 
    parameterTypes - the list of parameters
    Returns :
    the Constructor object of the public constructor that matches the specified parameterTypes
    Throws :
    NoSuchMethodException - if a Constructor with the specified parameterTypes is not found.
    SecurityException - If a security manager, s, is present.

    ```

    ```
    // Java program to demonstrate 
    // getConstructor() Constructor

    import java.lang.reflect.Constructor;

    public class Test
    {
        public static void main(String[] args) 
                throws SecurityException,ClassNotFoundException,
                    NoSuchMethodException
        {
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.Integer");
            Class c2 = Class.forName("java.lang.String");

            // getConstructor method on c1
            // it checks a public Constructor in Integer class
            // with specified parameterTypes
            Constructor c = c1.getConstructor(c2);

            System.out.println("Constructor in Integer class & String parameterType:");
            System.out.println(c);
        }
    }
    ```

    输出:

    ```
    public Constructor in Integer class with String parameterType : 
    public java.lang.Integer(java.lang.String) throws java.lang.NumberFormatException

    ```

    **注:**方法 getFields()、getMethods()、getConstructors()、getField()、getMethod()、getConstructor()在 Reflection 中被广泛使用(参考[这篇](https://www.geeksforgeeks.org/reflection-in-java/)举例)** 
31.  ****T cast(Object obj)** : This method is used to casts an object to the class or interface represented by this Class object.

    ```
    Syntax : 
    public T cast(Object obj)
    TypeParameters : 
    T - The class type whose object is to be cast
    Parameters : 
    obj - the object to be cast
    Returns :
    the object after casting, or null if obj is null
    Throws :
    ClassCastException - if the object is not null and is not assignable to the type T. 

    ```

    ```
    // Java program to demonstrate cast() method
    class A
    {
       // methods and fields
    }

    class B extends A 
    {
        // methods and fields
    }

    // Driver Class
    public class Test
    {
        public static void main(String[] args) 
        {
            A a = new A();   

            System.out.println(a.getClass());

            B b = new B();

            // casting b to a
            // cast method
            a = A.class.cast(b);

            System.out.println(a.getClass());

        }
    }
    ```

    输出:

    ```
    class A
    class B

    ```** 
32.  ****<U> Class<? extends U> asSubclass(Class<U> clazz)** : This method is used to cast this Class object to represent a subclass of the class represented by the specified class object.It always returns a reference to this class object.

    ```
    Syntax : 
    public <U> Class<? extends U> asSubclass(Class<U> class)
    TypeParameters : 
    U - The superclass type whose object is to be cast
    Parameters : 
    clazz - the superclass object to be cast
    Returns :
    this Class object, cast to represent a subclass of the specified class object.
    Throws :
    ClassCastException - if this Class object does not represent a 
    subclass of the specified class
    (here "subclass" includes the class itself).

    ```

    ```
    // Java program to demonstrate asSubclass() method
    class A
    {
       // methods and fields
    }

    class B extends A 
    {
        // methods and fields
    }

    // Driver Class
    public class Test
    {
        public static void main(String[] args) 
        {
            A a = new A();   

            // returns the Class object for super class(A)
            Class superClass = a.getClass();

            B b = new B();

            // returns the Class object for subclass(B)
            Class subClass = b.getClass();

            // asSubclass method
            // it represent a subclass of the specified  class object
            Class cast = subClass.asSubclass(superClass);

            System.out.println(cast);

        }
    }
    ```

    输出:

    ```
    class B

    ```

    本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**