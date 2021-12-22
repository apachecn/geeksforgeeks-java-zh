# 如何用 java 处理 Java . lang . unsafedlinkerror？

> 原文:[https://www . geeksforgeeks . org/how-handle-Java-lang-unsafiedlinkerror-in-Java/](https://www.geeksforgeeks.org/how-to-handle-java-lang-unsatisfiedlinkerror-in-java/)

**Java . lang . unsafeliedlinkerror**是 LinkageError 类的子类。当 Java 虚拟机(JVM)没有找到声明为“本机”的方法时，它将抛出不满意的链接错误。

现在让我们讨论一下它是什么时候发生的，为什么会发生。Java.lang.UnsatisfiedLinkError 发生在程序编译期间。正是因为这个原因，编译器没有找到原生库，一个只包含指定操作系统的原生代码的库，像**这样的原生库。Windows 中的 dll** ，**。所以 Linux 中的**和**。Mac 中的 dylib** 。该错误的层次结构如下所示:

```
Java.lang.Object
    Java.lang.Throwable
        Java.lang.Error
            Java.lang.LinkageError
                Java.lang.UnsatisfiedLinkError
```

**例**

## 爪哇

```
// Java Program to Illustrate UnsatisfiedLinkError

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Loading the External Library
    //"libfile" is name of C file
    static {
        System.loadLibrary("libfile");
    }

    //Method 1
    // To define externally in C file
    native void cfun();

    // Method 2
    // Main driver method
    public static void main(String[] args) {
        // Creating the object of above class inside main()
        GFG g = new GFG();

        // Calling over the above method
        g.cfun();
    }
}
```