# Java 中的 Java . lang . stacktracelement 类

> 原文:[https://www . geesforgeks . org/Java-lang-stack trace element-class-Java/](https://www.geeksforgeeks.org/java-lang-stacktraceelement-class-java/)

堆栈跟踪中的元素，由 Throwable.getStackTrace()返回。每个元素代表一个堆栈帧。除了堆栈顶部的框架之外，所有的堆栈框架都表示一个方法调用。堆栈顶部的框架表示生成堆栈跟踪的执行点。

此类描述单个堆栈帧，它是异常发生时堆栈跟踪的单个元素。

*   除了堆栈顶部的框架之外，所有的堆栈框架都表示一个方法调用。
*   堆栈顶部的框架表示生成堆栈跟踪的执行点。
*   每个堆栈帧代表一个执行点，包括方法名、文件名和源代码行号。
*   **StackTraceElement** 的数组由**可投掷**类的**getstack trace()**T4】方法返回。

**构造函数:**创建一个表示指定执行点的堆栈跟踪元素。

```
StackTraceElement(String declaringClass, 
String methodName, String fileName, int lineNumber)
```

**参数:**

*   **declaring class**–包含由堆栈跟踪元素表示的执行点的类的完全限定名。
*   **method name**–包含由堆栈跟踪元素表示的执行点的方法的名称。
*   **文件名**–包含由堆栈跟踪元素表示的执行点的文件的名称，如果该信息不可用，则为空
*   **行号**–包含该堆栈跟踪元素表示的执行点的源行的行号，如果该信息不可用，则为负数。值-2 表示包含执行点的方法是本机方法。

**抛出:**null pointerexception–如果 declaringClass 或 methodName 为空。

**方法:**

**1。布尔等于(ob):** 如果调用的**堆栈元素**与在 **ob** 中传递的相同，则返回 try。否则返回假。

```
Syntax: public boolean equals(ob)
Returns: true if the specified object is 
another StackTraceElement instance representing the same execution 
point as this instance.
Exception: NA
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating equals() method
import java.lang.*;
import java.io.*;
import java.util.*;
public class StackTraceElementDemo
{ 
    public static void main(String[] arg)
    {
        StackTraceElement st1 = new StackTraceElement("foo", "fuction1",
                                                   "StackTrace.java", 1);
        StackTraceElement st2 = new StackTraceElement("bar", "function2",
                                                   "StackTrace.java", 1);

        Object ob = st1.getFileName();

        // checking whether file names are same or not
        System.out.println(st2.getFileName().equals(ob));
    }
}
```

输出:

```
true
```

**2。String getClassName():** 返回调用 **StackTraceElement** 描述的执行点的类名。

```
Syntax: public String getClassName().
Returns: the fully qualified name of the Class
containing the execution point represented by this stack trace element.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating getClassName() method.
import java.lang.*;
import java.io.*;
import java.util.*;
public class StackTraceElementDemo
{ 
    public static void main(String[] arg)
    {  
        System.out.println("Class name of each thread involved:");
        for(int i = 0; i<2; i++)
        {  
            System.out.println(Thread.currentThread().getStackTrace()[I].
            getClassName());
        }
    }
}
```

输出:

```
Class name of each thread involved:
java.lang.Thread
StackTraceElementDemo
```

**3。字符串 getFileName():** 返回调用 **StackTraceElement** 描述的执行点的文件名。

```
Syntax: public String getFileName().
Returns: the name of the file containing 
the execution point represented by this stack trace element,
or null if this information is unavailable.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating getFileName() method.
import java.lang.*;
import java.io.*;
import java.util.*;
public class StackTraceElementDemo
{ 
   public static void main(String[] arg)
   {
       System.out.println("file name: ");
       for(int i = 0; i<2; i++)
       System.out.println(Thread.currentThread().getStackTrace()[i].
        getFileName());
   }
}
```

输出:

```
file name: 
Thread.java
StackTraceElementDemo.java
```

**4。int getLineNumber():** 返回调用**stacktracelement**描述的执行点的源代码行号。在某些情况下，行号将不可用，在这种情况下，将返回负值。

```
Syntax: public int getLineNumber().
Returns: the line number of the source line 
containing the execution point represented by this stack 
trace element, or a negative number if this information is 
unavailable.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating getLineNumber() method.
import java.lang.*;
import java.io.*;
import java.util.*;
public class StackTraceElementDemo
{ 
   public static void main(String[] arg)
   {
       System.out.println("line number: ");
       for(int i = 0; i<2; i++)
       System.out.println(Thread.currentThread().getStackTrace()[i].
        getLineNumber());
   }
}
```

输出:

```
line number: 
1556
10
```

**5。String getMethodName():** 返回调用 **StackTraceElement** 描述的执行点的方法名。

```
Syntax: public String getMethodName().
Returns: the name of the method containing the 
execution point represented by this stack trace element.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating getMethodName() method.
import java.lang.*;
import java.io.*;
import java.util.*;
public class StackTraceElementDemo
{ 
   public static void main(String[] arg)
   {
       System.out.println("method name: ");
       for(int i = 0; i<2; i++)
       System.out.println(Thread.currentThread().getStackTrace()[i].
        getMethodName());
   }
}
```

输出:

```
method name: 
getStackTrace
main
```

**6。int hashCode():** 返回调用 **StackTraceElement** 的哈希代码。

```
Syntax: public int hashCode().
Returns: a hash code value for this object.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating hashCode() method.
import java.lang.*;
import java.io.*;
import java.util.*;
public class StackTraceElementDemo
{ 
   public static void main(String[] arg)
   {
       System.out.println("hash code: ");
       for(int i = 0; i<2; i++)
       System.out.println(Thread.currentThread().getStackTrace()[i].
        hashCode());
   }
}
```

输出:

```
hash code: 
-1225537245
-1314176653
```

**7。如果调用的**堆栈跟踪元素**描述了一个本地方法，则返回真。否则返回 false。**

```
Syntax: public boolean isNativeMethod().
Returns: true if the method containing the execution 
point represented by this stack trace element is a native method.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating isNativeMethod() method.
import java.lang.*;
import java.io.*;
import java.util.*;
public class StackTraceElementDemo
{ 
   public static void main(String[] arg)
   {

       for(int i = 0; i<2; i++)
       System.out.println(Thread.currentThread().getStackTrace()[i].
        isNativeMethod());
   }
}
```

输出:

```
false
false
```

**8。字符串 toString():** 返回调用序列的等效字符串。

```
Syntax: public String toString().
Returns: a string representation of the object.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating toString() method.
import java.lang.*;
import java.io.*;
import java.util.*;
public class StackTraceElementDemo
{ 
   public static void main(String[] arg)
   {
       System.out.println("String equivalent: ");
       for(int i = 0; i<2; i++)
       System.out.println(Thread.currentThread().getStackTrace()[i].
        toString());
   }
}
```

输出:

```
String equivalent: 
java.lang.Thread.getStackTrace
StackTraceElementDemo.main
```

本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。