# Java 中的 Nashorn JavaScript 引擎，带示例

> 原文:[https://www . geesforgeks . org/nashorn-JavaScript-engine-in-Java-with-examples/](https://www.geeksforgeeks.org/nashorn-javascript-engine-in-java-with-examples/)

**Nashorn** : Nashorn 是一款 [JavaScript 引擎](https://www.geeksforgeeks.org/what-happens-inside-javascript-engine/)，在 JDK 8 推出。在纳斯霍恩的帮助下，我们可以在 [Java 虚拟机](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/)上执行 JavaScript 代码。Nashorn 在 JDK 8 中推出，取代现有的 JavaScript 引擎，即 Rhino。就性能而言，Nashorn 远远优于 Rhino。调用动态特性、将 JavaScript 代码转换成字节码并直接存入内存等功能的使用使得 Nashorn 在 JDK 8 中更加出名。我们可以通过使用命令行工具和将 JavaScript 代码嵌入到 Java 源代码中来执行 JavaScript 代码。

**使用控制台执行 JavaScript 代码:**对于 Nashorn 引擎，Java 8 引入了一个新的命令行工具，即 **jjl** 。我们必须按照以下步骤通过控制台执行 JavaScript 代码:

*   创建一个名为 geeks.js 的文件。
*   打开 geeks.js，将以下代码写入文件并保存。

    ```
    var gfg= function(){  
        print("Welcome to Geeksforgeeks!!!");  
    };  
    gfg(); 
    ```

*   打开 CMD，写 **jjl geeks.js** 按回车键。它将生成以下输出:

    ```
    Welcome to Geeksforgeeks!!!

    ```

**通过将 JavaScript 文件嵌入到 Java 代码中来执行 JavaScript 文件:**借助 **ScriptEngine** 类，我们可以通过将 JavaScript 文件嵌入到 Java 代码中来执行 JavaScript 文件。ScriptEngine 类在 JDK 6 中引入。在 ScriptEngine 类的帮助下，我们可以创建一个 javaScript 引擎，通过 JavaScript 引擎，我们可以执行 JavaScript 文件。

**例 1:**

```
// Program to illustrate embedding
// of JavaScript file into Java code

import javax.script.*;
import java.io.*;

public class Geeksforgeeks {
    public static void main(String[] args)
        throws Exception
    {

        // Here we are generating Nashorn JavaScript Engine
        ScriptEngine ee = new ScriptEngineManager()
                              .getEngineByName("Nashorn");

        // Reading JavaScript file create in first approach
        ee.eval(new FileReader("geeks.js"));
    }
}
```

**输出:**

```
Welcome to Geeksforgeeks!!!

```

**例 2:**

```
// Program to illustrate embedding
// of JavaScript code into Java code

import javax.script.*;
import java.io.*;

public class Geeksforgeeks {
    public static void main(String[] args)
        throws Exception
    {

        // Here we are generating Nashorn JavaScript Engine
        ScriptEngine ee = new ScriptEngineManager()
                              .getEngineByName("Nashorn");

        // Instead of reading JavaScript code from a file.
        // We can directly paste the JavaScript
        // code inside Java Code
        ee.eval("print('Welcome to Geeksforgeeks!!!"
                + " Executing JavaScript code with the"
                + " help of Nashorn engine');");
    }
}
```

**输出:**

> 欢迎来到极客乐园！！！在 Nashorn 引擎的帮助下执行 JavaScript 代码

除此之外，**在 Nashorn JavaScript Engine 的帮助下，我们可以像**一样执行多个操作:

1.  **Providing JavaScript variable from Java Code**: Suppose we have one JavaScript file name with geeks.js and geeks.js requires one variable during execution. With the help of Nashorn, we can pass the variable to JavaScript file from java code.

    **示例 1:** geeks.js 文件，需要**名**变量才能执行

    ```
    // JavaScript file name with geeks.js
    print("Welcome to Geeksforgeeks!!! Mr. "+name);  
    ```

    **示例 2:** 为 JS 文件提供**名称**变量的 Java 代码

    ```
    // Program to illustrate passing of variable
    // from java code to javascript file

    import javax.script.*;
    import java.io.*;

    public class Geeksforgeeks {
        public static void main(String[] args)
            throws Exception
        {
            ScriptEngine ee
                = new ScriptEngineManager()
                      .getEngineByName("Nashorn");
            Bindings bind
                = ee.getBindings(
                    ScriptContext.ENGINE_SCOPE);
            bind.put("name", "Bishal Kumar Dubey");
            ee.eval(new FileReader("geeks.js"));
        }
    }
    ```

    **输出:**

    ```
    Welcome to Geeksforgeeks!!! Mr. Bishal Kumar Dubey

    ```

2.  **Calling JavaScript function from Java code:** We can call JavaScript function from Java code with the help of Nashorn. Suppose we create one file name with geeks.js and the file contains two functions like below:

    ```
    // JavaScript file name with geeks.js

    var func1 = function(){  
        print("Simple JavaScript function!!!");  
    }  

    var func2 = function(reader){  
        print("Hello "+reader);  
    }  
    ```

    ```
    // Program to illustrate calling of
    // JavaScript function from Java code

    import javax.script.*;
    import java.io.*;

    public class Geeksforgeeks {
        public static void main(String[] args)
            throws Exception
        {
            ScriptEngine ee
                = new ScriptEngineManager()
                      .getEngineByName("Nashorn");
            ee.eval(new FileReader("geeks.js"));
            Invocable invocable = (Invocable)ee;

            // Here we are calling func1
            invocable.invokeFunction("func1");

            // Here we are calling func2
            // as well as passing argument
            invocable.invokeFunction("func2",
                                     "Bishal Kumar Dubey");
        }
    }
    ```

    **输出:**

    ```
    Simple JavaScript function!!!
    Hello Bishal Kumar Dubey

    ```