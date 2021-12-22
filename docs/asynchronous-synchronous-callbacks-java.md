# Java 中的异步和同步回调

> 原文:[https://www . geesforgeks . org/异步-同步-回调-java/](https://www.geeksforgeeks.org/asynchronous-synchronous-callbacks-java/)

回调函数是一个作为参数传递给另一个函数的函数，预计在某种事件之后执行。回调函数的目的是通知一个类同步/异步，如果另一个类中的一些工作已经完成。这在处理异步任务时非常有用。假设我们想执行一些常规任务，比如点击按钮后执行一些操作或显示内容，或者从互联网上获取数据。这也用于事件处理，因为当通过回调函数单击按钮时，我们会收到通知。

这种设计模式用于[观察者设计模式](https://www.geeksforgeeks.org/observer-pattern-set-1-introduction/)。观察者模式是一种软件设计模式，其中一个被称为主体的对象维护一个被称为观察者的依赖者列表，并自动通知他们任何状态变化，通常是通过调用他们的一个方法([来源:维基](https://en.wikipedia.org/wiki/Observer_pattern))。

在 Java 中，回调可以使用接口来实现。实施的一般程序如下。

```java
  1\. Define the methods in an interface that we want to invoke after callback.
  2\. Define a class that will implement the callback methods of the interface.
  3\. Define a reference in other class to register the callback interface.
  4\. Use that reference to invoke the callback method.

```

**同步回拨**

代码执行将在继续之前阻止或等待事件。在您的事件返回响应之前，您的程序不会继续执行。所以基本上，回调在返回 call 语句之前执行所有的工作。同步回调的问题是它们似乎滞后。

下面是这个原则的简单实现

```java
// Java program to illustrate synchronous callback
interface OnGeekEventListener {

    // this can be any type of method
    void onGeekEvent();
}

class B {

    private OnGeekEventListener mListener; // listener field

    // setting the listener
    public void registerOnGeekEventListener(OnGeekEventListener mListener)
    {
        this.mListener = mListener;
    }

    // my synchronous task
    public void doGeekStuff()
    {

        // perform any operation
        System.out.println("Performing callback before synchronous Task");

        // check if listener is registered.
        if (this.mListener != null) {

            // invoke the callback method of class A
            mListener.onGeekEvent();
        }
    }

    // Driver Function
    public static void main(String[] args)
    {
        B obj = new B();
        OnGeekEventListener mListener = new A();
        obj.registerOnGeekEventListener(mListener);
        obj.doGeekStuff();
    }
}

class A implements OnGeekEventListener {

    @Override
    public void onGeekEvent()
    {
        System.out.println("Performing callback after synchronous Task");
        // perform some routine operation
    }
    // some class A methods
}
```

输出:

```java
Performing callback before synchronous Task
Performing callback after synchronous Task

```

**异步回调**

异步调用不会阻止程序执行代码。当调用从事件返回时，调用返回回调函数。因此，在 Java 的上下文中，我们必须创建一个新的线程，并调用该线程中的回调方法。回调函数可以从线程调用，但不是必需的。回调也可以启动一个新线程，从而使它们自己异步。

下面是这个原理的简单实现。

```java
// Java program to illustrate Asynchronous callback

interface OnGeekEventListener {

    // this can be any type of method
    void onGeekEvent();
}

class B {

    private OnGeekEventListener mListener; // listener field

    // setting the listener
    public void registerOnGeekEventListener(OnGeekEventListener mListener)
    {
        this.mListener = mListener;
    }

    // My Asynchronous task
    public void doGeekStuff()
    {

        // An Async task always executes in new thread
        new Thread(new Runnable() {
            public void run()
            {

                // perform any operation
                System.out.println("Performing operation in Asynchronous Task");

                // check if listener is registered.
                if (mListener != null) {

                    // invoke the callback method of class A
                    mListener.onGeekEvent();
                }
            }
        }).start();
    }

    // Driver Program
    public static void main(String[] args)
    {

        B obj = new B();
        OnGeekEventListener mListener = new A();
        obj.registerOnGeekEventListener(mListener);
        obj.doGeekStuff();
    }
}

class A implements OnGeekEventListener {

    @Override
    public void onGeekEvent()
    {
        System.out.println("Performing callback after Asynchronous Task");
        // perform some routine operation
    }
    // some class A methods
}
```

输出:

```java
Performing operation in Asynchronous Task
Performing callback after Asynchronous Task

```

**何时使用什么**

**同步回调:**任何具有多个任务的进程，其中任务必须按顺序执行，并且不占用太多时间，都应该使用同步回调。
例如:你在排队买票，直到你前面的人都拿到票，你才能拿到票。

**异步回调:**当任务彼此不依赖并且可能需要一些时间来执行时，我们应该使用异步回调。
例如:当你点餐时，其他人也可以在餐厅点餐。他们不必等待你的命令完成，如果你从网上下载一首歌，得到一个应用编程接口响应。

**参考文献:**
[https://www . javaworld . com/article/2077462/learn-Java/Java-tip-10–implement-Callback-routines-in-Java . html](https://www.javaworld.com/article/2077462/learn-java/java-tip-10--implement-callback-routines-in-java.html)
T6】https://en . Wikipedia . org/wiki/Callback _(computer _ programming)