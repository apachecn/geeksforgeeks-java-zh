# 如何通过标注改善你的安卓编码？

> 原文:[https://www . geesforgeks . org/如何通过注释改进你的安卓编码/](https://www.geeksforgeeks.org/how-to-improve-your-android-coding-through-annotation/)

注释是一种元数据。[元数据](https://www.geeksforgeeks.org/difference-between-data-and-metadata/)则是提供其他数据信息的数据集合。在 Android 中使用注释的方式有很多。然而，在这一节中，我们将讨论如何利用注释来改进我们的安卓编码。官方的说法是，安卓已经有了支持注释，你可以通过依赖来合并，如下图所示

```
compile ‘com.android.support:support-*annotations:latestVersionHere*’
```

在这里，我们正在讨论一些伟大的注释，这肯定会帮助你。

### **空性注释**

注释@Nullable 和@NonNull 用于验证变量、参数甚至返回值是否为空。

*   **@ nullable:** This class represents a variable, parameter or return value that can be null.
*   **@ nonnullable:** A variable, parameter or return value that cannot be empty.

## Java

```
@NonNull
public View aFunction(@Nullable String gfg1, @NonNull String gfg2) {
 // gfg1 can be null
 // gfg2 cannot be null
 // a non null view is required as a return
}
```