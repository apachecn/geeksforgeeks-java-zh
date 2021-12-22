# Java 中的 Java.lang.System 类

> 原文:[https://www.geeksforgeeks.org/java-lang-system-class-java/](https://www.geeksforgeeks.org/java-lang-system-class-java/)

系统类提供的功能包括标准输入、标准输出和错误输出流；访问外部定义的属性和环境变量；一种加载文件和库的方法；和一种用于快速复制阵列的一部分的实用方法。它扩展了类对象。

**字段:**

1.  **公共静态最终输入流在:**的“标准”输入流。该流已经打开，可以提供输入数据。通常，该流对应于键盘输入或由主机环境或用户指定的另一个输入源。
2.  **公共静态最终打印流输出:**标准输出流。该流已经打开，可以接受输出数据。通常，此流对应于显示输出或主机环境或用户指定的另一个输出目标。
3.  **公共静态最终打印流错误:**标准错误输出流。该流已经打开，可以接受输出数据。
    通常，该流对应于显示输出或主机环境或用户指定的另一个输出目的地。按照惯例，该输出流用于显示错误消息或用户应该立即注意到的其他信息，即使主要输出流(变量 out 的值)已被重定向到通常不会持续监控的文件或其他目标。

**方法:**

**1。静态空数组副本(对象源，int sourceStart，对象目标，int targetStart，int size):** 复制数组。要复制的数组在 source 中传递，复制将在 source 中开始的索引在 sourceStart 中传递。将接收拷贝的数组被传入目标，拷贝将从目标中的哪个点开始的索引被传入目标开始。大小是复制的元素数量。

```
Syntax: public static void arraycopy(Object source, 
int sourceStart, Object Target, int targetStart, int size)
Returns: NA.
Exception: 
IndexOutOfBoundsException - if copying would cause access of data 
outside array bounds.
ArrayStoreException - if an element in the source array could not 
be stored into the target array because of a type mismatch.
NullPointerException - if either source or target is null.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating arraycopy() method
import java.lang.*;
import java.util.Arrays;
class SystemDemo
{
    public static void main(String args[])
    {
        int[] a = {1, 2, 3, 4, 5};
        int[] b = {6, 7, 8, 9, 10};

        System.arraycopy(a, 0, b, 2, 2);

        // array b after arraycopy operation
        System.out.println(Arrays.toString(b));

    }
}
```

**输出:**

```
[6, 7, 1, 2, 10]
```

**2。静态字符串 clearProperty(字符串键):**删除指定键指示的系统属性。

```
Syntax: public static String clearProperty(String key)
Returns: the previous string value 
of the system property, or null if there was no property 
with that key.
Exception: 
SecurityException - if a security manager exists and its 
checkPropertyAccess method doesn't allow 
access to the specified system property.
NullPointerException - if key is null.
IllegalArgumentException - if key is empty.
```

**3。静态字符串 getProperty(字符串键):**获取指定键指示的系统属性。

```
Syntax: public static String getProperty(String key)
Returns: the string value of the system 
property, or null if there is no property with that key.
Exception: 
SecurityException - if a security manager exists and its 
checkPropertyAccess method doesn't allow access to the 
specified system property.
NullPointerException - if key is null.
IllegalArgumentException - if key is empty.
```

**4。静态字符串获取属性(字符串键，字符串定义):**获取指定键指示的系统属性。

```
Syntax: public static String getProperty(String key, String def)
Returns: the string value of the system property,
 or the default value if there is no property with that key.
Exception: 
SecurityException - if a security manager exists and its 
checkPropertyAccess method doesn't allow access to the 
specified system property.
NullPointerException - if key is null.
IllegalArgumentException - if key is empty.
```

**5。静态字符串设置属性(字符串键，字符串值):**设置由指定键指示的系统属性。

```
Syntax: public static String setProperty(String key, String value)
Returns: the previous value of the system 
property, or null if it did not have one.
Exception: 
SecurityException - if a security manager exists and its checkPermission 
method doesn't allow setting of the specified property.
NullPointerException - if key or value is null.
IllegalArgumentException - if key is empty.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating clearProperty(), getProperty()
// and setProperty() methods
import java.lang.*;
import static java.lang.System.clearProperty;
import static java.lang.System.setProperty;
import java.util.Arrays;
class SystemDemo
{
    public static void main(String args[])
    {
        // checking specific property
        System.out.println(System.getProperty("user.home"));

        // clearing this property
        clearProperty("user.home");

        System.out.println(System.getProperty("user.home"));

        // setting specific property
        setProperty("user.country", "US");

        // checking property
        System.out.println(System.getProperty("user.country"));

        // checking property other than system property
        // illustrating getProperty(String key, String def)
        System.out.println(System.getProperty("user.password",
              "none of your business"));
    }
}
```

**输出:**

```
/Users/abhishekverma
null
US
none of your business
```

**6。static Console():**返回与当前 Java 虚拟机关联的唯一 Console 对象(如果有)。

```
Syntax: public static Console console()
Returns: The system console, if any, otherwise null.
Exception: NA
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating console() method
import java.io.Console;
import java.lang.*;
import java.util.Currency;
import java.util.Locale;
class SystemDemo
{
    public static void main(String args[]) throws NullPointerException
    {

        Console c = System.console();
        if(c != null)
        {
           Currency currency = Currency.getInstance(Locale.ITALY);
           c.printf(currency.getSymbol());
            c.flush();
        }
        else
            System.out.println("No console attached");
    }
}
```

输出:

```
No console attached
```

**7。静态长 currentimemillis():**以毫秒为单位返回当前时间。请注意，虽然返回值的时间单位是毫秒，但值的粒度取决于底层操作系统，可能会更大。例如，许多操作系统以几十毫秒为单位测量时间。

```
Syntax: public static long currentTimeMillis()
Returns: the difference, measured in milliseconds,
 between the current time and midnight, January 1, 1970 UTC.
Exception: NA.
```

**8。static long nanoTime():** 返回正在运行的 Java 虚拟机的高分辨率时间源的当前值，单位为纳秒。

```
Syntax: public static long nanoTime()
Returns: the current value of the running Java
 Virtual Machine's high-resolution time source, in nanoseconds
Exception: NA
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating currentTimeMillis() method
import java.lang.*;
class SystemDemo
{
    public static void main(String args[]) throws NullPointerException
    {
        System.out.println("difference between the "
                + "current time and midnight,"
                + " January 1, 1970 UTC is: " +
                System.currentTimeMillis());
        System.out.println("current time in "
                + "nano sec: " +
                System.nanoTime());
    }
}
```

输出:

```
difference between the current time 
and midnight, January 1, 1970 UTC is: 
1499520649545
current time in nano sec: 29976939759226
```

**9。静态无效退出(int 状态):**终止当前运行的 Java 虚拟机。该参数用作状态代码；按照惯例，非零状态码表示异常终止。
这个方法调用类 Runtime 中的 exit 方法。此方法从不正常返回。
调用 System.exit(n)实际上相当于调用:
Runtime.getRuntime()。出口(n)

```
Syntax: public static void exit(int status)
Returns: NA
Exception: 
SecurityException - if a security manager exists and its 
checkExit method doesn't allow exit with the specified status.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating exit() method
import java.lang.*;
class SystemDemo
{
    public static void main(String args[]) throws NullPointerException
    {
        System.gc();
        System.out.println("Garbage collector executed ");

        System.out.println(System.getProperty("os.name"));

        System.exit(1);

        // this line will not execute as JVM terminated
        System.out.println("JVM terminated");
    }
}
```

输出:

```
Garbage collector executed 
Mac OS X
```

**10。静态 void gc():** 运行垃圾收集器。调用 gc 方法建议 Java 虚拟机扩展回收未使用对象的工作，以便使它们当前占用的内存可用于快速重用。当方法调用返回控制权时，Java 虚拟机已经尽最大努力从所有丢弃的对象中回收空间。

```
Syntax: public static void gc()
Returns: NA
Exception: NA
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating gc() method
import java.lang.*;
class SystemDemo
{
    public static void main(String args[])
    {
        Runtime gfg = Runtime.getRuntime();
        long memory1, memory2;
        Integer integer[] = new Integer[1000];

        // checking the total memory
        System.out.println("Total memory is: "
                           + gfg.totalMemory());

        // checking free memory
        memory1 = gfg.freeMemory();
        System.out.println("Initial free memory: "
                                      + memory1);

        // calling the garbage collector on demand
        System.gc();

        memory1 = gfg.freeMemory();

        System.out.println("Free memory after garbage "
                           + "collection: " + memory1);

        // allocating integers
        for (int i = 0; i < 1000; i++)
            integer[i] = new Integer(i);

        memory2 = gfg.freeMemory();
        System.out.println("Free memory after allocation: "
                           + memory2);

        System.out.println("Memory used by allocation: " +
                                    (memory1 - memory2));

        // discard integers
        for (int i = 0; i < 1000; i++)
            integer[i] = null;

        System.gc();

        memory2 = gfg.freeMemory();
        System.out.println("Free memory after  "
            + "collecting discarded Integers: " + memory2);
    }
}
```

输出:

```
Total memory is: 128974848
Initial free memory: 126929976
Free memory after garbage collection: 128632160
Free memory after allocation: 127950520
Memory used by allocation: 681640
Free memory after  collecting discarded Integers: 128643472
```

**11 时。静态映射 getenv():** 返回当前系统环境的不可修改的字符串映射视图。环境是从名称到值的依赖于系统的映射，从父进程传递到子进程。
如果系统不支持环境变量，则返回一个空映射。

```
Syntax: public static Map getenv()
Returns: the environment as a map of variable names to values.
Exception: 
SecurityException - if a security manager exists and its 
checkPermission method doesn't allow access to the process 
environment
```

**12 时。静态字符串 getenv(字符串名称):**获取指定环境变量的值。环境变量是依赖于系统的外部命名值。
系统属性和环境变量在概念上都是名称和值之间的映射。这两种机制都可以用来将用户定义的信息传递给 Java 进程。环境变量具有更全局的效果，因为它们对定义它们的过程的所有后代都是可见的，而不仅仅是直接的 Java 子过程。它们在不同的操作系统上可能有微妙的不同语义，例如不区分大小写。由于这些原因，环境变量更有可能产生意想不到的副作用。最好尽可能使用系统属性。当需要全局效果时，或者当外部系统接口需要环境变量(如 PATH)时，应该使用环境变量。

```
Syntax: public static String getenv(String name)
Returns: the string value of the variable,
 or null if the variable is not defined in the system environment.
Exception: 
NullPointerException - if name is null
SecurityException - if a security manager exists and 
its checkPermission method doesn't allow access to the
 environment variable name.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating getenv() method
import java.lang.*;
import java.util.Map;
import java.util.Set;
class SystemDemo
{
    public static void main(String args[])
    {
        Map<String, String> gfg = System.getenv();
        Set<String> keySet = gfg.keySet();
        for(String key : keySet)
        {
            System.out.println("key= " + key);
        }

        // checking specific environment variable
        System.out.println(System.getenv("PATH"));
    }
}
```

输出:

```
key= JAVA_MAIN_CLASS_5396
key= PATH
key= J2D_PIXMAPS
key= SHELL
key= USER
key= TMPDIR
key= SSH_AUTH_SOCK
key= XPC_FLAGS
key= LD_LIBRARY_PATH
key= __CF_USER_TEXT_ENCODING
key= Apple_PubSub_Socket_Render
key= LOGNAME
key= LC_CTYPE
key= XPC_SERVICE_NAME
key= PWD
key= JAVA_MAIN_CLASS_2336
key= SHLVL
key= HOME
key= _
/usr/bin:/bin:/usr/sbin:/sbin
```

**13。静态属性 getProperties():** 确定当前系统属性。

```
Syntax: public static Properties getProperties()
Returns: the system properties.
Exception: 
SecurityException - if a security manager exists and 
its checkPropertiesAccess method doesn't allow access 
to the system properties.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating getProperties() method
import java.lang.*;
import java.util.Properties;
import java.util.Set;
class SystemDemo
{
    public static void main(String args[])
    {
        Properties gfg = System.getProperties();
        Set<Object> keySet = gfg.keySet();
        for(Object key : keySet)
        {
            System.out.println("key= " + key);
        }
    }
}
```

输出:

```
key= java.runtime.name
key= sun.boot.library.path
key= java.vm.version
key= user.country.format
key= gopherProxySet
key= java.vm.vendor
key= java.vendor.url
key= path.separator
key= java.vm.name
key= file.encoding.pkg
key= user.country
key= sun.java.launcher
key= sun.os.patch.level
key= java.vm.specification.name
key= user.dir
key= java.runtime.version
key= java.awt.graphicsenv
key= java.endorsed.dirs
key= os.arch
key= java.io.tmpdir
key= line.separator
key= java.vm.specification.vendor
key= os.name
key= sun.jnu.encoding
key= java.library.path
key= java.specification.name
key= java.class.version
key= sun.management.compiler
key= os.version
key= http.nonProxyHosts
key= user.home
key= user.timezone
key= java.awt.printerjob
key= file.encoding
key= java.specification.version
key= java.class.path
key= user.name
key= java.vm.specification.version
key= sun.java.command
key= java.home
key= sun.arch.data.model
key= user.language
key= java.specification.vendor
key= awt.toolkit
key= java.vm.info
key= java.version
key= java.ext.dirs
key= sun.boot.class.path
key= java.vendor
key= file.separator
key= java.vendor.url.bug
key= sun.io.unicode.encoding
key= sun.cpu.endian
key= socksNonProxyHosts
key= ftp.nonProxyHosts
key= sun.cpu.isalist
```

**14。静态 SecurityManager getSecurityManager():**获取系统安全接口。

```
Syntax: static SecurityManager getSecurityManager()
Returns: if a security manager has 
already been established for the current application,
 then that security manager is returned; otherwise, 
null is returned.
Exception: NA
```

**15。静态无效设置安全管理器:**设置系统安全性。

```
Syntax: public static void setSecurityManager(SecurityManager s)
Returns: NA.
Exception: 
SecurityException - if the security manager has 
already been set and its checkPermission method 
doesn't allow it to be replaced.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating setSecurityManager()
// and getSecurityManager() method
import java.lang.*;
class SystemDemo
{
    public static void main(String args[])
    {
        SecurityManager gfg = new SecurityManager();

        // setting the security manager
        System.setSecurityManager(gfg);

        gfg = System.getSecurityManager();
        if(gfg != null)
            System.out.println("Security manager is configured");
    }
}
```

输出:

```
Security manager is configured
```

**16。静态 void setErr(PrintStream err):** 重新分配“标准”错误输出流。

```
Syntax: public static void setErr(PrintStream err)
Returns: NA
Exception: 
SecurityException - if a security manager exists and its
 checkPermission method doesn't allow reassigning of the
 standard error output stream.
```

**17。静态 void setIn(InputStream in):** 重新分配“标准”输入流。

```
Syntax: public static void setIn(InputStream in)
Returns: NA.
Exception: 
SecurityException - if a security manager exists and its
 checkPermission method doesn't allow reassigning of the
 standard input stream.
```

**18。静态无效设置(打印流输出):**重新分配“标准”输出流。

```
Syntax: public void setOut(PrintStream out)
Returns: NA
Exception: 
SecurityException - if a security manager exists and its
 checkPermission method doesn't allow reassigning of the
 standard output stream.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating setOut(), setIn() and setErr() method
import java.lang.*;
import java.util.Properties;
import java.io.*;
class SystemDemo
{
    public static void main(String args[])  throws IOException 
    {
        FileInputStream IN = new FileInputStream("input.txt");
        FileOutputStream OUT = new FileOutputStream("system.txt");

        // set input stream
        System.setIn(IN);
        char c = (char) System.in.read();
        System.out.print(c);

        // set output stream
        System.setOut(new PrintStream(OUT));
        System.out.write("Hi Abhishek\n".getBytes());

        // set error stream
        System.setErr(new PrintStream(OUT));
        System.err.write("Exception message\n".getBytes());
    }
}
```

**输出:**上述 java 代码的输出取决于“input.txt”文件中的内容。
创建自己的“input.txt”，然后运行代码并检查输出。

**19。静态空加载(字符串文件名):**从本地文件系统加载一个具有指定文件名的代码文件作为动态库。文件名参数必须是完整的路径名。

```
Syntax: public static void load(String filename)
Returns: NA
Exception: 
SecurityException - if a security manager exists and
 its checkLink method doesn't allow loading of the specified
 dynamic library
UnsatisfiedLinkError - if the file does not exist.
NullPointerException - if filename is null
```

**20。静态 void loadLibrary(字符串 libname):** 加载 libname 参数指定的系统库。库名映射到实际系统库的方式取决于系统。

```
Syntax: public static void loadLibrary(String libname)
Returns: NA
Exception: 
SecurityException - if a security manager exists and its 
checkLink method doesn't allow loading of the specified dynamic
 library
UnsatisfiedLinkError - if the library does not exist.
NullPointerException - if libname is null
```

**21。静态字符串映射库名(String libname):** 将库名映射为表示本机库的平台特定字符串。

```
Syntax: public static String mapLibraryName(String libname)
Returns: a platform-dependent native library name.
Exception: NullPointerException - if libname is null
```

**22。static void run finalization():**运行任何等待终结的对象的终结方法。调用此方法表明，Java 虚拟机将努力扩展到运行已被发现被丢弃但其最终方法尚未运行的对象的最终方法。当控制从方法调用返回时，Java 虚拟机已经尽了最大努力来完成所有未完成的终结。

```
Syntax: public static void runFinalization()
Returns: NA
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating runFinalization(), load()
// loadLibrary() and mapLibraryName() method
import java.lang.*;
class SystemDemo
{
    public static void main(String args[]) throws NullPointerException
    {

        // map library name
        String libName = System.mapLibraryName("os.name");
        System.out.println("os.name library= " + libName);

        //load external libraries
        System.load("lixXYZ.so");
        System.loadLibrary("libos.name.dylib");

        //run finalization
        System.runFinalization();

    }
}
```

输出:

```
os.name library= libos.name.dylib
```

**23。静态 int identity HashCode(Object x):**为给定对象返回与默认方法 hash code()返回的哈希代码相同的哈希代码，无论给定对象的类是否覆盖 hashCode()。空引用的哈希代码为零。

```
Syntax: public static int identityHashCode(Object x)
Returns: the hashCode.
Exception: NA.
```

**24。静态通道继承通道():**返回从创建该 Java 虚拟机的实体继承的通道。

```
Syntax: public static Channel inheritedChannel().
Returns:  inherited channel, if any, otherwise null.
Exception: 
IOException - If an I/O error occurs
SecurityException - If a security manager is present and
 it does not permit access to the channel.
```

**25。静态字符串行分隔符():**返回依赖于系统的行分隔符字符串。它总是返回相同的值-系统属性行分隔符的初始值。

```
Syntax: public static String lineSeparator()
Returns: On UNIX systems, it returns "\n";
 on Microsoft Windows systems it returns "\r\n".
Exception: NA
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating lineSeparator(), inherentChannel()
// and identityHashCode() method
import java.io.IOException;
import java.lang.*;
import java.nio.channels.Channel;
class SystemDemo
{
    public static void main(String args[])
            throws NullPointerException,
            IOException
    {

        Integer x = 400;
        System.out.println(System.identityHashCode(x));

        Channel ch = System.inheritedChannel();
        System.out.println(ch);

        System.out.println(System.lineSeparator());

    }
}
```

输出:

```
1735600054
null
"\r\n"
```

本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。