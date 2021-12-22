# Java 中的 Java.io.Console 类

> 原文:[https://www.geeksforgeeks.org/java-io-console-class-java/](https://www.geeksforgeeks.org/java-io-console-class-java/)

Java.io.Console 类提供了访问与当前 Java 虚拟机关联的基于字符的控制台设备(如果有)的方法。控制台类是由 JDK 6 添加到 java.io 中的。

**要点:**

*   它用于从控制台读写(如果有)。
*   控制台主要是一个便利类，因为它的大部分功能都可以通过 System.in 和 System.out 获得。但是，它的使用可以简化某些类型的控制台交互，尤其是在从控制台读取字符串时。
*   Console supplies no constructors. Instead, a Console object is obtained by calling System.console( ), which is shown here:

    ```java
    static  Console console( )
    ```

    如果控制台可用，则返回对它的引用。否则，返回 null。控制台并非在所有情况下都可用。因此，如果返回空值，就不可能有控制台输入/输出。

*   它提供了读取文本和密码的方法。如果您使用控制台类读取密码，它将不会显示给用户。java.io.Console 类与系统控制台内部相连。

**重要方法:**

*   **writer :** 检索与此控制台关联的唯一 PrintWriter 对象。
    **语法:** 

```java
public PrintWriter writer() 
Returns: The printwriter associated with this console
```

*   **读取器:**检索与此控制台关联的唯一读取器对象。
    **语法:** 

    ```java
    public Reader reader()  
    Returns: The reader associated with this console

    ```

    *   **格式:**使用指定的格式字符串和参数将格式化字符串写入控制台的输出流。
    **语法:** 

    ```java
    public Console format(String fmt, Object... args)
    Parameters:
    fmt - A format string as described in Format string syntax
    args - Arguments referenced by the format specifiers in the format string. 
    If there are more arguments than format specifiers, the extra arguments are ignored.
    Returns:This console
    Throws: IllegalFormatException 

    ```

    *   **printf :** 使用指定的格式字符串和参数将格式化字符串写入控制台输出流的便捷方法。
    **语法:**

    ```java
    public Console printf(String format, Object... args) Parameters:
    format - A format string as described in Format string syntax.
    args - Arguments referenced by the format specifiers in the format string. 
    If there are more arguments than format specifiers, the extra arguments are ignored.
    Returns:This console
    Throws:IllegalFormatException 

    ```

    *   **readLine :** 提供格式化提示，然后从控制台读取单行文本。
    **语法:**

    ```java
    public String readLine(String fmt,Object... args) 
    Parameters:
    fmt - A format string as described in Format string syntax.
    args - Arguments referenced by the format specifiers in the format string. 
    If there are more arguments than format specifiers, the extra arguments are ignored.
    Returns: A string containing the line read from the console, 
    not including any line-termination characters, or null 
    if an end of stream has been reached.
    Throws: IllegalFormatException
    IOError - If an I/O error occurs.

    ```

    *   **读取线:**从控制台读取单行文本。
    **语法:**

    ```java
    public String readLine() 
    Returns: A string containing the line read from the console,
     not including any line-termination characters, or null 
    if an end of stream has been reached.
    Throws: IOError 

    ```

    *   **读取密码:**提供格式化提示，然后在禁用回显的情况下从控制台读取密码或密码短语。
    **语法:**

    ```java
    public char[] readPassword(String fmt,Object... args)
    Parameters:
    fmt - A format string as described in Format string syntax for the prompt text.
    args - Arguments referenced by the format specifiers in the format string.
    Returns: A character array containing the password or passphrase read 
    from the console, not including any line-termination characters, or null 
    if an end of stream has been reached.
    Throws: IllegalFormatException 
    IOError
    ```

    *   **读取密码:**从禁用回显的控制台读取密码或密码短语
    **语法:**

    ```java
    public char[] readPassword() Returns: A character array containing the password or passphrase 
    read from the console, not including any line-termination characters, or null 
    if an end of stream has been reached.
    Throws:IOError
    ```

    *   **flush : **Flushes the console and forces any buffered output to be written immediately .
    **Syntax:**

    ```java
    public void flush() Specified by: flush in interface Flushable
    ```

    **程序:**

    ```java
    // Java Program to demonstrate Console Methods

    import java.io.*;
    class ConsoleDemo 
    {
        public static void main(String args[]) 
        {
            String str;

            //Obtaining a reference to the console.
            Console con = System.console();

            // Checking If there is no console available, then exit.
            if(con == null) 
            {
                System.out.print("No console available");
                return;
            }

            // Read a string and then display it.
            str = con.readLine("Enter your name: ");
            con.printf("Here is your name: %s\n", str);

            //to read password and then display it
            System.out.println("Enter the password: ");
            char[] ch=con.readPassword();

            //converting char array into string
            String pass = String.valueOf(ch);
            System.out.println("Password is: " + pass);
        }
    }
    ```

    **输出:**

    ```java
    Enter your name: Nishant Sharma
    Here is your name: Nishant Sharma
    Enter the password: 
    Password is: dada

    ```

    注意:System.console()在联机 IDE 中返回空值

    本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。