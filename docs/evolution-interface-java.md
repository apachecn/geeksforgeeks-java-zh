# Java 中接口的演进

> 原文:[https://www.geeksforgeeks.org/evolution-interface-java/](https://www.geeksforgeeks.org/evolution-interface-java/)

前提条件:[Java 中的接口](https://www.geeksforgeeks.org/interfaces-in-java/)
在 **Java SE 7** 或更早版本中，一个接口只能有:

*   常量变量
*   抽象方法

我们不能在接口中提供方法的实现。

```
public interface GFG{
      String a = "Geeksforgeeks is the best.";

      void hello(String a);
      void world(int x);
}
```

**Java SE 8:**
我们可以从 Java SE 8 及以后的版本在 Interface 中编写方法实现。我们需要使用“default”关键字来定义它们，如下所示。
在 Java SE 8 及更高版本中，一个接口只能有四种东西:

*   常量变量
*   抽象方法
*   默认方法
*   Static methods

    ```
    public interface GFG{
          String b = "Shubham is a brilliant coder.";

          default void hello(String a){
             System.out.println("Hello");
          }
          static void world(int x){
             System.out.println("World");
          }
          void bye();
       }
    ```

    **Java SE 9:**
    在 Java SE 9 及以后的版本中，我们可以使用如下所示的‘private’访问修饰符在 Interfaces 中编写私有方法(和其他私有方法一样)。
    在 Java SE 9 及更高版本中，一个接口可以有:

    *   常量变量
    *   抽象方法
    *   默认方法
    *   静态方法
    *   私有方法
    *   私有静态方法

    ```
    public interface GFG{
          String b = "Shubham is a brilliant coder.";

          default void hello(String a){
             System.out.println("Hello");
          }
          static void world(int x){
             System.out.println("World");
          }
          void bye();

          private void great(long v){

          }
       }
    ```

    本文由 **Shubham Juneja** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。