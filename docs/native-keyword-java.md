# Java 中的原生关键字

> 原文:[https://www.geeksforgeeks.org/native-keyword-java/](https://www.geeksforgeeks.org/native-keyword-java/)

native 关键字应用于方法，表示该方法是使用 JNI (Java Native Interface)在本机代码中实现的。native 是只适用于方法的修改器**，我们不能在其他地方应用。用 C、C++实现的方法称为本机方法或外来方法。**

native 关键字的主要目标是:

*   来提高系统的性能。
*   实现机器级/存储器级通信。
*   使用已经存在的遗留非 java 代码。

**说明:**Java 中的 Native 关键字

```java
// Class 1
// Helper class to illustrate native keyword 
class Native
{

    static
    {
        System.loadLibrary("Native library path");
    }

    // Native method 
    public native void m();
}

// Main class 
class GFG
{
    public static void main(String[] args)
    {
        // creating object of helper class inside main() 
        Native n = new Native();

        // Calling native method that is defined
        // inside  the above class
        n.m();
    }
}
```

请记住，关于原生关键字，有一些要点如下:

*   对于原生方法，实现已经在像 C、C++这样的旧语言中可用，我们不负责提供实现。因此，本机方法声明应以结尾；(分号)。
*   我们不能将一个原生方法声明为[抽象](https://www.geeksforgeeks.org/abstract-classes-in-java/)。
*   我们不能将一个原生方法声明为 [strictfp](https://www.geeksforgeeks.org/strictfp-keyword-java/) ，因为不能保证旧语言(C，C++)遵循 IEEE 754 标准。因此，本机 strictfp 组合对于方法来说是非法的组合。
*   native 关键字的主要优点是性能的提高，但是 native 关键字的主要缺点是它打破了 java 的平台无关性。

> 一定要通过 java 的 strictfp 关键字，因为这是一个即使是非常优秀的 java 开发人员都不知道的概念。

在本节中，我们将解释如何在 Java 中声明本机方法，以及如何生成相应的 C/C++函数原型。

**语法:**声明本机方法

```java
private native String getLine(String prompt);
```

**语法:**从母语方面

```java
javah -jni Prompt
```

```java
JNIEXPORT jstring JNICALL Java_Prompt_getLine(JNIEnv *, jobject, jstring);
```

**参考:**[http://www . codejava . net/Java-core/the-Java-language/native-关键字](http://www.codejava.net/java-core/the-java-language/native-keyword)
本文由 **Bishal Kumar Dubey** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。