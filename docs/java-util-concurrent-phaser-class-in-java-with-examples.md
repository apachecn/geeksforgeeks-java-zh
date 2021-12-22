# Java 中的 Java.util.concurrent.Phaser 类，带示例

> 原文:[https://www . geesforgeks . org/Java-util-concurrent-phaser-class-in-Java-with-examples/](https://www.geeksforgeeks.org/java-util-concurrent-phaser-class-in-java-with-examples/)

Phaser 的主要目的是实现代表一个或多个活动阶段的线程同步。它允许我们定义一个同步对象，等待一个特定的阶段完成。然后进入下一阶段，直到该阶段结束。它还可以用于同步单个相位，在这方面，它的作用很像 CyclicBarrier。

**等级体系**

```
java.lang.Object
  ? java.util.concurrent
    ? Class Phaser 
```

**语法**

```
public class Phaser
  extends Object
```

**施工人员:**

*   **移相器()**–这将创建一个最初注册方为零的移相器。一个线程只能在注册后使用这个相位器。

```
public Phaser()
```

*   **相位器(int parties)**–这创建了一个相位器，需要 parties 数量的线程才能前进到下一个阶段。

```
public Phaser(int parties)
throws IllegalArgumentException
```

*   **相位器(相位器父级)**–这将为新对象指定父级相位器。注册方的数量设置为零。

```
public Phaser(Phaser parent)
```

*   **相位器(相位器父级，inter parties)**–这将为新创建的对象指定一个父级相位器，以及进入下一阶段所需的参与方数量。

```
public Phaser(Phaser parent, int parties)
throws IllegalArgumentException
```

**示例 1:**

**注意**:输出可能会随着每次运行而变化。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to show Phaser Class

import java.util.concurrent.Phaser;

// A thread of execution that uses a phaser.
class MyThread implements Runnable {
    Phaser phaser;
    String title;

    public MyThread(Phaser phaser, String title)
    {
        this.phaser = phaser;
        this.title = title;

        phaser.register();
        new Thread(this).start();
    }

    @Override public void run()
    {
        System.out.println("Thread: " + title
                           + " Phase Zero Started");
        phaser.arriveAndAwaitAdvance();

        // Stop execution to prevent jumbled output
        try {
            Thread.sleep(10);
        }
        catch (InterruptedException e) {
            System.out.println(e);
        }

        System.out.println("Thread: " + title
                           + " Phase One Started");
        phaser.arriveAndAwaitAdvance();

        // Stop execution to prevent jumbled output
        try {
            Thread.sleep(10);
        }
        catch (InterruptedException e) {
            System.out.println(e);
        }

        System.out.println("Thread: " + title
                           + " Phase Two Started");
        phaser.arriveAndDeregister();
    }
}

public class PhaserExample {
    public static void main(String[] args)
    {
        Phaser phaser = new Phaser();
        phaser.register();
        int currentPhase;

        System.out.println("Starting");

        new MyThread(phaser, "A");
        new MyThread(phaser, "B");
        new MyThread(phaser, "C");

        // Wait for all threads to complete phase Zero.
        currentPhase = phaser.getPhase();
        phaser.arriveAndAwaitAdvance();
        System.out.println("Phase " + currentPhase
                           + " Complete");
        System.out.println("Phase Zero Ended");

        // Wait for all threads to complete phase One.
        currentPhase = phaser.getPhase();
        phaser.arriveAndAwaitAdvance();
        System.out.println("Phase " + currentPhase
                           + " Complete");
        System.out.println("Phase One Ended");

        currentPhase = phaser.getPhase();
        phaser.arriveAndAwaitAdvance();
        System.out.println("Phase " + currentPhase
                           + " Complete");
        System.out.println("Phase Two Ended");

        // Deregister the main thread.
        phaser.arriveAndDeregister();
        if (phaser.isTerminated()) {
            System.out.println("Phaser is terminated");
        }
    }
}
```

**Output**

```
Starting
Thread: B Phase Zero Started
Thread: A Phase Zero Started
Thread: C Phase Zero Started
Thread: A Phase One Started
Thread: B Phase One Started
Thread: C Phase One Started
Phase 0 Complete
Phase Zero Ended
Phase 1 Complete
Phase One Ended
Thread: C Phase Two Started
Thread: A Phase Two Started
Thread: B Phase Two Started
Phase 2 Complete
Phase Two Ended
Phaser is terminated

```

**示例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to show Phaser Class

import java.util.concurrent.Phaser;

// A thread of execution that uses a phaser.
class MyThread implements Runnable {
    Phaser phaser;
    String title;

    public MyThread(Phaser phaser, String title)
    {
        this.phaser = phaser;
        this.title = title;

        phaser.register();
        new Thread(this).start();
    }

    @Override public void run()
    {
        System.out.println("Thread: " + title
                           + " Phase Zero Started");
        phaser.arriveAndAwaitAdvance();

        // Stop execution to prevent jumbled output
        try {
            Thread.sleep(10);
        }
        catch (InterruptedException e) {
            System.out.println(e);
        }

        System.out.println("Thread: " + title
                           + " Phase One Started");
        phaser.arriveAndAwaitAdvance();

        // Stop execution to prevent jumbled output
        try {
            Thread.sleep(10);
        }
        catch (InterruptedException e) {
            System.out.println(e);
        }

        System.out.println("Thread: " + title
                           + " Phase Two Started");
        phaser.arriveAndDeregister();
    }
}

public class PhaserExample {
    public static void main(String[] args)
    {
        Phaser phaser = new Phaser();
        phaser.register();
        int currentPhase;

        System.out.println("Starting");

        new MyThread(phaser, "A");
        new MyThread(phaser, "B");
        new MyThread(phaser, "C");

        // Wait for all threads to complete phase Zero.
        currentPhase = phaser.getPhase();
        phaser.arriveAndAwaitAdvance();
        System.out.println("Phase " + currentPhase
                           + " Complete");
        System.out.println("Phase Zero Ended");

        // Wait for all threads to complete phase One.
        currentPhase = phaser.getPhase();
        phaser.arriveAndAwaitAdvance();
        System.out.println("Phase " + currentPhase
                           + " Complete");
        System.out.println("Phase One Ended");

        currentPhase = phaser.getPhase();
        phaser.arriveAndAwaitAdvance();
        System.out.println("Phase " + currentPhase
                           + " Complete");
        System.out.println("Phase Two Ended");

        // Deregister the main thread.
        phaser.arriveAndDeregister();
        if (phaser.isTerminated()) {
            System.out.println("Phaser is terminated");
        }
    }
}
```

**Output**

```
Starting
Thread: C Phase Zero Started
Thread: A Phase Zero Started
Thread: B Phase Zero Started
Thread: B Phase One Started
Thread: C Phase One Started
Thread: A Phase One Started
Phase 0 Complete
Phase Zero Ended
Phase 1 Complete
Phase One Ended
Thread: A Phase Two Started
Thread: C Phase Two Started
Thread: B Phase Two Started
Phase 2 Complete
Phase Two Ended
Phaser is terminated

```

**方法:**

*   **int register()**–该方法用于在相位器构建完成后注册各方。它返回它注册到的阶段的阶段号。

```
public int register()
throws IllegalArgumentException
```

*   **int react()**–这个方法表示一个线程已经完成了部分任务。它不会暂停调用线程的执行。如果相位器已经终止，它返回当前相位号或负值。

```
public int arrive()
throws IllegalStateException
```

*   **int arriveandunregulator()**–该方法使一个线程能够到达某个阶段并注销自己，而无需等待其他线程到达。如果相位器已经终止，它返回当前相位号或负值。

```
public int arriveAndDeregister()
throws IllegalStateException
```

*   **int arriveandwaitadvance()**–这个方法在某个阶段暂停线程的执行，等待其他线程。如果相位器已经终止，它返回当前相位号或负值。

```
public int arriveAndAwaitAdvance()
throws IllegalStateException
```

*   **final int getPhase()**–该方法返回当前相数。如果调用阶段终止，则返回负值。

```
public final int getPhase() 
```

*   **布尔 onAdvance(int phase，int parties)**–该方法有助于定义阶段推进应该如何发生。为此，用户必须重写此方法。要终止相位器，onAdvance()方法返回 true，否则返回 false

```
protected boolean onAdvance(int phase, int parties)
```

**演示相位器类**方法的示例–该方法被覆盖，因此相位器只执行指定数量的相位。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the methods of Phaser class

import java.util.concurrent.Phaser;

// Extend MyPhaser and override onAdvance()
// so that only specific number of phases
// are executed
class MyPhaser extends Phaser {
    int numPhases;
    MyPhaser(int parties, int phaseCount)
    {
        super(parties);
        numPhases = phaseCount - 1;
    }

    @Override
    protected boolean onAdvance(int phase,
                                int registeredParties)
    {
        System.out.println("Phase " + phase
                           + " completed.\n");

        // If all phases have completed, return true.
        if (phase == numPhases || registeredParties == 0) {
            return true;
        }

        // otherwise, return false
        return false;
    }
}

// A thread of execution that uses a phaser
class ModifiedThread implements Runnable {
    Phaser phsr;
    String name;

    ModifiedThread(Phaser p, String n)
    {
        phsr = p;
        name = n;
        phsr.register();
        new Thread(this).start();
    }

    @Override public void run()
    {
        while (!phsr.isTerminated()) {
            System.out.println("Thread " + name
                               + " Beginning Phase "
                               + phsr.getPhase());
            phsr.arriveAndAwaitAdvance();

            try {
                Thread.sleep(10);
            }
            catch (InterruptedException e) {
                System.out.println(e);
            }
        }
    }
}

public class PhaserExample2 {
    public static void main(String[] args)
    {
        MyPhaser phsr = new MyPhaser(1, 4);
        System.out.println("Starting");

        new ModifiedThread(phsr, "A");
        new ModifiedThread(phsr, "B");
        new ModifiedThread(phsr, "C");

        while (!phsr.isTerminated()) {
            phsr.arriveAndAwaitAdvance();
        }
        System.out.println("The phaser is terminated\n");
    }
}
```

**Output**

```
Starting
Thread B Beginning Phase 0
Thread C Beginning Phase 0
Thread A Beginning Phase 0
Phase 0 completed.

Thread A Beginning Phase 1
Thread B Beginning Phase 1
Thread C Beginning Phase 1
Phase 1 completed.

Thread C Beginning Phase 2
Thread A Beginning Phase 2
Thread B Beginning Phase 2
Phase 2 completed.

Thread A Beginning Phase 3
Thread B Beginning Phase 3
Thread C Beginning Phase 3
Phase 3 completed.

The phaser is terminated

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/phaser . html](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/Phaser.html)