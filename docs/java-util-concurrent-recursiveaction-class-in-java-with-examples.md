# Java 中的 Java . util . concurrent . recursiveaction 类，带示例

> 原文:[https://www . geesforgeks . org/Java-util-concurrent-recursiveaction-class-in-Java-with-examples/](https://www.geeksforgeeks.org/java-util-concurrent-recursiveaction-class-in-java-with-examples/)

**RecursiveAction** 是一个**抽象**类封装了一个不返回结果的任务。它是 **ForkJoinTask** 的一个子类，这是一个抽象类，代表了一个可以在多核系统中独立内核上执行的任务。RecursiveAction 类被扩展以创建一个具有 **void** 返回类型的任务。代表任务计算部分的代码保存在 RecursiveAction 的 **compute()** 方法中。

RecursiveAction 用于可以划分并并行执行的任务。这些任务不应返回任何值。例如，使用 RecursiveAction 可以很容易地实现对大数组的排序，将数组分成可管理的小块，每个部分在单独的核心上进行排序。

**阶级等级**

```java
java.lang.Object
↳ java.util.concurrent.ForkJoinTask<Void>
  ↳ java.util.concurrent.RecursiveAction

```

**递归函数的构造函数:**

1.  **RecursiveAction**: Creates an object of RecursiveAction with default settings.

    **语法:**

    ```java
    public RecursiveAction()

    ```

**方法**

1.  **计算()**–它是完成任务执行的计算的方法。

    **语法:**

    ```java
    protected abstract void compute()

    ```

2.  **exec()**–该方法实现了执行 RecursiveAction 任务所必需的基本规则。

    **语法:**

    ```java
    protected final boolean exec()

    ```

3.  **getRawResult()**–函数返回任务完成状态。它总是返回 null。

    **语法:**

    ```java
    public final Void getRawResult()

    ```

4.  **setRawResult()**–该函数将任务完成状态设置为参数中传递的值。

    **语法:**

    ```java
    protected final void setRawResult(Void mustBeNull)

    ```

**示例**:演示递归动作类

```java
// Java program to demonstrate RecursiveAction Class

import java.util.concurrent.ForkJoinPool;
import java.util.concurrent.RecursiveAction;

public class ForkJoinDemo {
    public static void main(String[] args)
    {
        // Create a pool of threads.
        ForkJoinPool fjp = new ForkJoinPool();
        double[] nums = new double[100000];

        // Give nums some values
        for (int i = 0; i < nums.length; i++) {
            nums[i] = (double)i;
        }
        System.out.println("A portion of the original sequence");
        for (int i = 0; i < 9; i++) {
            System.out.print(nums[i] + " ");
        }
        System.out.println();
        SqrtTransform task
            = new SqrtTransform(nums, 0, nums.length);

        // Start the task
        fjp.invoke(task);
        System.out.println("A portion of the transformed sequence"
                           + " (to four decimal places): ");
        for (int i = 0; i < 9; i++) {
            System.out.printf("%.4f ", nums[i]);
        }
        System.out.println();
    }
}

// A task that transforms the elements into their square roots
class SqrtTransform extends RecursiveAction {
    final int seqThreshold = 1000;

    double[] data;

    // Determines what part of data to process
    int start, end;

    SqrtTransform(double[] data, int start, int end)
    {
        this.data = data;
        this.start = start;
        this.end = end;
    }

    // The method where parallel computation will occur
    @Override
    protected void compute()
    {
        // If the number of elements are less
        // than the sequential threshold
        if ((end - start) < seqThreshold) {
            for (int i = start; i < end; i++) {
                data[i] = Math.sqrt(data[i]);
            }
        }
        else {
            // Otherwise, continue to break the data into smaller pieces
            // Find the midpoint
            int middle = (start + end) / 2;

            // Invoke new tasks, using the subdivided tasks.
            invokeAll(new SqrtTransform(data, start, middle),
                      new SqrtTransform(data, middle, end));
        }
    }
}
```

**输出:**

```java

A portion of the original sequence
0.0 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 
A portion of the transformed sequence (to four decimal places): 
0.0000 1.0000 1.4142 1.7321 2.0000 2.2361 2.4495 2.6458 2.8284 

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/recursiveaction . html](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/RecursiveAction.html)