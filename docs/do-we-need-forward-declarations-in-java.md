# 我们需要 Java 中的正向声明吗？

> 原文:[https://www . geesforgeks . org/do-we-need-forward-declarations-in-Java/](https://www.geeksforgeeks.org/do-we-need-forward-declarations-in-java/)

预测以下 Java 程序的输出。

```
// filename: Test2.java

// main() function of this class uses Test1 which is declared later in 
// this file
class Test2 {      
    public static void main(String[] args) {    
         Test1 t1 = new Test1();
         t1.fun(5);         
    }
}    
class Test1 {   
    void fun(int x) {
        System.out.println("fun() called: x = " + x);
    }
}
```

输出:

```
fun() called: x = 5
```

Java 程序编译运行良好。注意 *Test1* 和 *fun()* 在使用前没有声明。与 C++不同，我们不需要 Java 中的[转发声明](http://en.wikipedia.org/wiki/Forward_declaration)。从源文件中自动识别标识符(类名和方法名)。同样，库方法直接从库中读取，不需要创建带有声明的头文件。Java 使用命名方案，其中包名和公共类名必须分别跟在目录名和文件名之后。这种命名方案允许 Java 编译器定位库文件。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。