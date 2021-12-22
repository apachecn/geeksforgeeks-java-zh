# 在 Java 中，我们可以从另一个类调用一个类的 main()方法吗？

> 原文:[https://www . geesforgeks . org/in-Java-we-can-call-main-method-of-a-class-from-other-class/](https://www.geeksforgeeks.org/in-java-can-we-call-the-main-method-of-a-class-from-another-class/)

**在 Java 中，我们可以从另一个类调用一个类的 main()方法吗？**
或
**如何从我们的代码中调用‘公共静态 void main(String[]args)’方法？**

这些问题通常困扰着一个 Java 程序员。本文旨在以一种简单而有效的方式提供这些问题的答案。

正如我们所知，任何 Java 应用程序的 [main()方法](https://www.geeksforgeeks.org/main-method-compulsory-java/)就像 [Java 运行时环境](https://www.geeksforgeeks.org/differences-jdk-jre-jvm/)首先调用 main()方法一样。所以很明显，我们不需要自己调用 main()方法，因为它已经在程序启动时被调用了。但是如果我们想从程序的某个地方调用 main()方法呢？这就是问题所在。

**解决方案:**

尽管 Java 不喜欢从程序中的其他地方调用 main()方法，但它也不禁止人们这样做。所以，事实上，我们可以随时随地调用 main()方法。

但是从我们的代码中调用 main()方法很棘手。会导致很多**错误和异常**，比如:

*   **The main() method must be called from a static method only inside the same class.**

    ```
    // Java method to show that the main() method
    // must be called from a static method only
    // inside the same class

    import java.io.*;

    class GFG {

        // The method that calls the main() method
        // Note that this method is not static
        void mainCaller()
        {
            System.out.println("mainCaller!");

            // Calling the main() method
            main(null);
        }

        // main() method
        public static void main(String[] args)
        {
            System.out.println("main");

            // Calling the mainCalller() method
            // so that main() methiod is called externally
            mainCaller();
        }
    }
    ```

    **Java 代码编译错误:**

    ```
    prog.java:27: error: non-static method mainCaller()
                         cannot be referenced
                         from a static context
            mainCaller();
            ^
    1 error

    ```

*   **The main() method must be passed the String[] args while calling it from somewhere else.**

    ```
    // Java method to show that the main() method
    // must be passed the String[] args
    // while calling it from somewhere else

    import java.io.*;

    class GFG {

        // The method that calls the main() method
        static void mainCaller()
        {
            System.out.println("mainCaller!");

            // Calling the main() method
            // Note that no parameter is passed
            main();
        }

        // main() method
        public static void main(String[] args)
        {
            System.out.println("main");

            // Calling the mainCalller() method
            // so that main() methiod is called externally
            mainCaller();
        }
    }
    ```

    **Java 代码编译错误:**

    ```
    prog.java:17: error: method main in class GFG
                         cannot be applied to given types;
            main();
            ^
      required: String[]
      found: no arguments
      reason: actual and formal argument lists differ in length
    1 error

    ```

*   **Calling the main() method will lead to an infinite loop as the memory stack knows to run only the main() method.**

    ```
    // Java method to show that Calling the main() method
    // will lead to an infinite loop as the memory stack
    // knows to run only the main() method

    import java.io.*;

    class GFG {

        // The method that calls the main() method
        static void mainCaller()
        {
            System.out.println("mainCaller!");

            // Calling the main() method
            main(null);
        }

        // main() method
        public static void main(String[] args)
        {
            System.out.println("main");

            // Calling the mainCalller() method
            // so that main() methiod is called externally
            mainCaller();
        }
    }
    ```

    **Java 代码中的运行时错误:**

    ```
    RunTime Error in java code :-
     Exception in thread "main" java.lang.StackOverflowError

    mainCaller!
    main
    mainCaller!
    main
    mainCaller!
    main
    .
    .
    .

    ```

**正确的做法:**

**示例 1:** 从同一个类外部调用 main()方法

```
// Java method to show Calling main() method
// externally from the same class

import java.io.*;

class GFG {

    static int count = 0;

    // The method that calls the main() method
    static void mainCaller()
    {

        System.out.println("mainCaller!");
        count++;

        // Calling the main() only 3 times
        if (count < 3) {

            // Calling the main() method
            main(null);
        }
    }

    // main() method
    public static void main(String[] args)
    {
        System.out.println("main");

        // Calling the mainCalller() method
        // so that main() methiod is called externally
        mainCaller();
    }
}
```

**输出:**

```
main
mainCaller!
main
mainCaller!
main
mainCaller!

```

**示例 1:** 从另一个类外部调用 main()方法

```
// Java method to show Calling main() method
// externally from another class

import java.io.*;

class GFG {

    static int count = 0;

    // The method that calls the main() method
    static void mainCaller()
    {

        System.out.println("mainCaller!");
        count++;

        // Calling the main() only 3 times
        if (count < 3) {

            // Calling the main() method
            Test.main(null);
        }
    }
}

class Test {

    // main() method
    public static void main(String[] args)
    {
        System.out.println("main");

        // Calling the mainCalller() method
        // so that main() methiod is called externally
        GFG.mainCaller();
    }
}
```

**输出:**

```
main
mainCaller!
main
mainCaller!
main
mainCaller!

```