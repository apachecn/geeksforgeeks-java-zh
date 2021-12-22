# 接口中方法的访问说明符

> 原文:[https://www.geeksforgeeks.org/g-fact-73/](https://www.geeksforgeeks.org/g-fact-73/)

在 Java 中，一个接口中的所有方法都是*公共的*，即使我们没有用方法名指定*公共的*。此外，数据字段是*公共静态最终*，即使我们没有提到它的字段名称。因此，必须初始化数据字段。

考虑下面的例子， *x* 默认为*公共静态最终*， *foo()* 为*公共*即使没有说明符。

```
interface Test {
  int x = 10;  // x is public static final and must be initialized here
  void foo();  // foo() is public
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。