# Java 中的 Java.lang.Package 类

> 原文:[https://www.geeksforgeeks.org/java-lang-package-class-java/](https://www.geeksforgeeks.org/java-lang-package-class-java/)

Java 2 添加了一个名为 Package 的类，它封装了与包相关的版本数据。包版本信息变得越来越重要，因为包激增，并且因为 java 程序可能需要知道包的可用版本。
加载类的类加载器实例检索并提供该版本信息。通常，它存储在与类一起分发的清单中。它扩展了类对象并实现了注释删除。

**方法:**

1.  **getAnnotation(Class annotationClass):** Returns this element’s annotation for the specified type if such an annotation is present, else null.

    ```
    Syntax: public  A getAnnotation(Class annotationClass)
    Returns: this element's annotation for the specified 
    annotation type if present on this element, else null.
    Exception: NullPointerException - if the given annotation class is null.

    ```

    ```
    // Java code illustrating getAnnotation() method 
    import java.lang.annotation.Retention;
    import java.lang.annotation.RetentionPolicy;
    import java.lang.reflect.Method;

    // declare a annotation type
    @Retention(RetentionPolicy.RUNTIME)
    @interface Demo 
    {
       String str();
       int val();
    }

    public class PackageDemo 
    {

       // setting values for the annotation
       @Demo(str = " Gfg Demo Annotation", val = 100)

       // a method to call in the main
       public static void gfg() throws NoSuchMethodException 
       {
          PackageDemo ob = new PackageDemo();

             Class c = ob.getClass();

             // get the method example
             Method m = c.getMethod("gfg");

             // get the annotation for class Demo
             Demo annotation = m.getAnnotation(Demo.class);

             // checking the annotation
             System.out.println(annotation.str() + " " + annotation.val());
        } 

       public static void main(String args[]) throws Exception
       {
          gfg();
       }
    }
    ```

    输出:

    ```
    Gfg Demo Annotation 100

    ```

2.  **Annotation[] getAnnotations():** Returns all annotations present on this element. (Returns an array of length zero if this element has no annotations.) The caller of this method is free to modify the returned array; it will have no effect on the arrays returned to other callers.

    ```
    Syntax: public Annotation[] getDeclaredAnnotations().
    Returns: All annotations directly present on this element.
    Exception: NA.

    ```

    ```
    // Java code illustrating getAnnotation() method
    import java.lang.annotation.Annotation;
    import java.lang.annotation.Retention;
    import java.lang.annotation.RetentionPolicy;
    import java.lang.reflect.Method;

    // declare a annotation type
    @Retention(RetentionPolicy.RUNTIME)
    @interface Demo 
    {
       String str();
       int val();
    }

    public class PackageDemo 
    {

       // setting values for the annotation
       @Demo(str = " Gfg Demo Annotation", val = 100)

       // a method to call in the main
       public static void gfg() throws NoSuchMethodException 
       {
          PackageDemo ob = new PackageDemo();

             Class c = ob.getClass();

             // get the method example
             Method m = c.getMethod("gfg");

             // get the annotation for class Demo
             Demo annotation = m.getAnnotation(Demo.class);

             // checking the annotation
             System.out.println(annotation.str() + " " + annotation.val());
             Annotation[] gfg_ann = m.getAnnotations();

             for(int i = 0; i < gfg_ann.length; i++)
             {
                 System.out.println(gfg_ann[i]);
             }
        } 

       public static void main(String args[]) throws Exception
       {
          gfg();
       }
    }
    ```

    输出:

    ```
    Gfg Demo Annotation 100
    @Demo(str= Gfg Demo Annotation, val=100)

    ```

3.  **Annotation[] getDeclaredAnnotations():** Returns all annotations that are directly present on this element. Unlike the other methods in this interface, this method ignores inherited annotations. (Returns an array of length zero if no annotations are directly present on this element.) The caller of this method is free to modify the returned array; it will have no effect on the arrays returned to other callers.

    ```
    Syntax: public Annotation[] getDeclaredAnnotations().
    Returns: All annotations directly present on this element.
    Exception: NA.

    ```

    ```
    // java code illustrating getDeclaredAnnotation() method
    import java.lang.annotation.Annotation;
    import java.lang.annotation.Retention;
    import java.lang.annotation.RetentionPolicy;
    import java.lang.reflect.Method;

    // declare a annotation type
    @Retention(RetentionPolicy.RUNTIME)
    @interface Demo 
    {
       String str();
       int val();
    }

    public class PackageDemo 
    {

       // setting values for the annotation
       @Demo(str = " Gfg Demo Annotation", val = 100)

       // a method to call in the main
       public static void gfg() throws NoSuchMethodException 
       {
          PackageDemo ob = new PackageDemo();

             Class c = ob.getClass();

             // get the method example
             Method m = c.getMethod("gfg");

             // get the annotation for class Demo
             Demo annotation = m.getAnnotation(Demo.class);

             // checking the annotation
             System.out.println(annotation.str() + " " + annotation.val());
             Annotation[] gfg_ann = m.getDeclaredAnnotations();

             for(int i = 0; i < gfg_ann.length; i++)
             {
                 System.out.println(gfg_ann[i]);
             }
        } 

       public static void main(String args[]) throws Exception
       {
          gfg();
       }
    }
    ```

    输出:

    ```
     Gfg Demo Annotation 100
    @Demo(str= Gfg Demo Annotation, val=100)

    ```

4.  **String getImplementationTitle():**返回此包的标题。

    ```
    Syntax: public String getImplementationTitle()
    Returns: the title of the implementation, null is returned if it is not known.
    Exception: NA

    ```

5.  **String getImplementationVersion():**返回此实现的版本。它由该实现的供应商分配的任何字符串组成，没有 Java 运行时指定或期望的任何特定语法。可以将它与该供应商用于该包的实现的其他包版本字符串进行比较，以确定是否相等。

    ```
    Syntax: public String getImplementationVersion()
    Returns: the version of the implementation, null is returned if it is not known.
    Exception: NA

    ```

6.  **String getImplementationVendor():**返回提供此实现的组织、供应商或公司的名称。

    ```
    Syntax: public String getImplementationVendor().
    Returns: the vendor that implemented this package.
    Exception: NA.

    ```

7.  **String getName():** 返回该包的名称。

```
Syntax: public String getName()
Returns: The fully-qualified name of this package as defined
 in section 6.5.3 of The Java™ Language Specification, for example, java.lang.
Exception: NA

```

```
// Java code illustrating getName(), getImplementationTitle()
// and getImplementationVendor() and getImplementationVersion()
// methods
class PackageDemo
{
    public static void main(String arg[])
    {
        Package pkgs[];
        pkgs = Package.getPackages();

        for(int i=0; i<1; i++)
        {
            //  name of the package
            System.out.println(pkgs[i].getName());

            // checking title of this implementation
            System.out.println(pkgs[i].getImplementationTitle());

            // checking the vendor
            System.out.println(pkgs[i].getImplementationVendor());

            // version of this implementation
            System.out.println(pkgs[i].getImplementationVersion());

        }
    }
}
```

输出:

```
sun.reflect
Java Runtime Environment
Oracle Corporation
1.8.0_121

```

14.  **静态包 getPackage(字符串名称):**在调用者类加载器实例中按名称查找包。调用方类加载器实例用于查找与命名类对应的包实例。如果调用方类加载器实例为空，则搜索系统类加载器实例加载的包集以找到命名包。

    ```
    Syntax: public static Package getPackage(String name)
    Returns: the package of the requested name. It may 
    be null if no package information is available from the archive or 
    codebase.
    Exception: NA

    ```

15.  **static Package[] getPackages():** Get all the packages currently known for the caller’s ClassLoader instance. Those packages correspond to classes loaded via or accessible by name to that ClassLoader instance. If the caller’s ClassLoader instance is the bootstrap ClassLoader instance, which may be represented by null in some implementations, only packages corresponding to classes loaded by the bootstrap ClassLoader instance will be returned.

    ```
    Syntax: public static Package[] getPackages()
    Returns: a new array of packages known to the callers 
    ClassLoader instance. An zero length array is returned if none are known.
    Exception: NA

    ```

    ```
    // Java code illustrating getPackages() method
    class PackageDemo
    {
        public static void main(String arg[])
        {
            Package pkgs[];
            pkgs = Package.getPackages();

            Package pkg = Package.getPackage("java.lang");

            for(int i=0; i<1; i++)
            {
            System.out.println(pkg.getName());
            System.out.println(pkgs[i].getName());
            }
        }
    }
    ```

    输出:

    ```
    java.lang
    sun.reflect

    ```

16.  **字符串 getSpecificationTitle():** 返回这个包实现的规范的标题。

    ```
    Syntax: public String getSpecificationTitle()
    Returns: the specification title, null is returned 
    if it is not known.
    exception: NA.

    ```

17.  **字符串 getSpecificationVersion():** 返回此包实现的规范的版本号。此版本字符串必须是由“.”分隔的非负十进制整数序列 s 和可能有前导零。比较版本字符串时，会比较最重要的数字。

    ```
    Syntax: public String getSpecificationVersion().
    Returns: the specification version, null is returned 
    if it is not known.
    Exception: NA.

    ```

18.  **String getSpecificationVendor():**返回拥有并维护实现此包的类的规范的组织、供应商或公司的名称。

    ```
    Syntax: public String getSpecificationVendor()
    Returns: the specification vendor, null is returned
     if it is not known.
    Exception: NA.

    ```

19.  **int hashCode():** Return the hash code computed from the package name.

    ```
    Syntax: Return the hash code computed from the package name.
    Exception: NA
    Returns: the hash code.

    ```

    ```
    // Java code illustrating hashCode(), getSpecificationTitle()
    // getSpecificationVendor() and getSpecificationVersion()
    class PackageDemo
    {
        public static void main(String arg[])
        {
            Package pkgs[];
            pkgs = Package.getPackages();

            for(int i=0; i<1; i++)
            {
                //  name of the package
                System.out.println(pkgs[i].hashCode());

                // checking title 
                System.out.println(pkgs[i].getSpecificationTitle());

                // checking the vendor
                System.out.println(pkgs[i].getSpecificationVendor());

                // checking version
                System.out.println(pkgs[i].getSpecificationVersion());

            }
        }
    }
    ```

    输出:

    ```
    685414683
    Java Platform API Specification
    Oracle Corporation
    1.8

    ```

20.  **boolean isCompatibleWith(需要字符串):**将此包的规格版本与所需版本进行比较。如果此包规范版本号大于或等于所需版本号，则返回 true。

    ```
    Syntax: public boolean isCompatibleWith(String desired).
    Returns: true if this package's version number is 
    greater than or equal to the desired version number
    Exception: 
    NumberFormatException - if the desired or current version is not 
    of the correct dotted form.

    ```

21.  **布尔值 isSealed():** 如果此包是密封的，则返回 true。

    ```
    Syntax: public boolean isSealed()
    Returns: true if the package is sealed, false otherwise.
    Exception: NA

    ```

22.  **布尔值 isSealed(URL url):** 如果此包相对于指定的代码源 URL 是密封的，则返回 true。

    ```
    Syntax: public boolean isSealed(URL url)
    Returns: true if this package is sealed with respect to url
    Exception: NA

    ```

23.  **String toString():** Returns the string representation of this Package. Its value is the string “package ” and the package name. If the package title is defined it is appended. If the package version is defined it is appended.

    ```
    Syntax: public String toString()
    Returns: the string representation of the package.
    Exception: NA

    ```

    ```
    // java code illustrating isCompatibleWith(), toString(),
    // isSealed methods

    import java.net.MalformedURLException;
    import java.net.URL;

    class PackageDemo
    {
        public static void main(String arg[]) throws MalformedURLException
        {
            Package pkg = Package.getPackage("java.lang");

            // checking if pkg is compatible with 1.0
            System.out.println(pkg.isCompatibleWith("1.0"));

            // checking if packet is sealed
            System.out.println(pkg.isSealed());

            URL url = new URL("https://www.youtube.com/");

            System.out.println(pkg.isSealed(url));

            // string equivalent of package
            System.out.println(pkg.toString());

        }
    }
    ```

    输出:

    ```
    true
    false
    false
    package java.lang, Java Platform API Specification, version 1.8

    ```

本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。