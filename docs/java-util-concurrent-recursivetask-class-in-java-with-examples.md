# Java 中的 Java . util . concurrent . recursivetask 类，带示例

> 原文:[https://www . geesforgeks . org/Java-util-concurrent-recursivetask-class-in-Java-with-examples/](https://www.geeksforgeeks.org/java-util-concurrent-recursivetask-class-in-java-with-examples/)

**RecursiveTask** 是一个**抽象**类封装了一个返回结果的任务。它是**叉车**的一个子类。RecursiveTask 类被扩展以创建具有特定返回类型的任务。代表任务计算部分的代码保存在 RecursiveTask 的 **compute()** 方法中。

**RecursiveTask** 类多用于并行编程的上下文中。可以划分为独立子任务的任务，任务的最终结果可以从子任务的结果中获得，可以使用 RecursiveTask 更有效地实现。例如，在大数组中搜索元素。

**阶级等级**

```
java.lang.Object
↳ java.util.concurrent.ForkJoinTask
  ↳ java.util.concurrent.RecursiveTask<V>

```

**施工方**

1.  **RecursiveTask()**–使用默认设置创建 RecursiveTask 对象。

    ```
    public RecursiveTask()

    ```

**方法**

1.  **Calculation ()** – The method of defining the task.

    ```
    protected abstract void compute()

    ```

2.  **【 exec ()** –This method realizes the basic rules necessary for executing tasks.

    ```
    protected final boolean exec()

    ```

3.  **Getrawesult ()** –The function returns the value obtained after the task is completed, even if the task is abnormally completed. If the task has not been completed, it will return null.

    ```
    public final Void getRawResult()

    ```

4.  **setrawesult ()** –The function sets the return value of the task to the value passed in the parameter.

    ```
    protected final void setRawResult(Void mustBeNull)

    ```

示例演示 RecursiveTask

```
import java.util.concurrent.ForkJoinPool;
import java.util.concurrent.RecursiveTask;

public class RecursiveTaskDemo {
    public static void main(String[] args)
    {
        ForkJoinPool fjp = new ForkJoinPool();

        double[] nums = new double[5000];
        for (int i = 0; i < nums.length; i++) {
            nums[i] = (double)(((i % 2) == 0) ? i : -1);
        }
        Sum task = new Sum(nums, 0, nums.length);
        double summation = fjp.invoke(task);
        System.out.println("Summation " + summation);
    }
}

class Sum extends RecursiveTask<Double> {
    final int seqThreshold = 500;
    double[] data;
    int start, end;

    Sum(double[] data, int start, int end)
    {
        this.data = data;
        this.start = start;
        this.end = end;
    }

    @Override
    protected Double compute()
    {
        double sum = 0;
        if ((end - start) < seqThreshold) {
            for (int i = start; i < end; i++)
                sum += data[i];
        }
        else {
            int middle = (start + end) / 2;

            Sum subtaskA = new Sum(data, start, middle);
            Sum subtaskB = new Sum(data, middle, end);

            subtaskA.fork();
            subtaskB.fork();

            sum += subtaskA.join() + subtaskB.join();
        }
        return sum;
    }
}
```

**输出:**

```
Summation 6245000.0

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/recursivetask . html](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/RecursiveTask.html)