# Java . lang . inheritable threadlocal 类，带示例

> 原文:[https://www . geesforgeks . org/Java-lang-inheritable threadlocal-class-examples/](https://www.geeksforgeeks.org/java-lang-inheritablethreadlocal-class-examples/)

Java . lang . inheritable ThreadLocal 类扩展 thread local 以提供从父线程到子线程的值继承:创建子线程时，子线程接收父线程有值的所有可继承线程本地变量的初始值。

父线程，默认情况下**线程本地**变量不可用于子线程。
T3【建造师】T4:

```
**InheritableThreadLocal gfg_tl = new InheritableThreadLocal();**
```

它是**线程本地**的子类，因此**线程本地**中的所有方法默认情况下对**继承线程本地**可用。
只包含一种方法:
**语法:**

```
public Object childValue(Object parentValue) 
```

在启动子线程之前，在父线程中调用(重写)此方法。

*   如果我们想让父线程、线程局部变量值对子线程可用，那么我们应该去找 **InheritableThreadLocal** 类。
*   默认情况下，子线程值与父线程值完全相同。但是我们可以通过覆盖 **childValue** 方法为子线程提供自己定制的值。

示例:

```
// Java program to illustrate parent thread, ThreadLocal variable
// by default not available to child thread

class ParentThread extends Thread {
    public static ThreadLocal gfg_tl = new ThreadLocal();
    public void run()
    {

        // setting the new value
        gfg_tl.set("parent data");

        // returns the ThreadLocal value associated with current thread
        System.out.println("Parent  Thread Value :" + gfg_tl.get());

        ChildThread gfg_ct = new ChildThread();
        gfg_ct.start();
    }
}

class ChildThread extends Thread {
    public void run()
    {

        // returns  the ThreadLocal value associated with current thread
        System.out.println("Child Thread Value :" + ParentThread.gfg_tl.get());
        /* null (parent thread variable 
        thread local value is not available to child thread ) */
    }
}
class ThreadLocalDemo {
    public static void main(String[] args)
    {
        ParentThread gfg_pt = new ParentThread();
        gfg_pt.start();
    }
}
```

```
Output:
Parent Thread Value:parent data
Child Thread Value:null (by default initialValue is null)

```

```
// Java program to illustrate inheritance of customized value
// from parent thread to child thread

class ParentThread extends Thread {
    // anonymous inner class  for overriding childValue method.
    public static InheritableThreadLocal gfg_tl = new InheritableThreadLocal() {
        public Object childValue(Object parentValue)
        {
            return "child data";
        }
    };
    public void run()
    {
        // setting the new value
        gfg_tl.set("parent data");
        // parent data
        System.out.println("Parent Thread Value :" + gfg_tl.get());

        ChildThread gfg_ct = new ChildThread();
        gfg_ct.start();
    }
}
class ChildThread extends Thread {

    public void run()
    {
        // child data
        System.out.println("Child Thread Value :" + ParentThread.gfg_tl.get());
    }
}
class ThreadLocalDemo {

    public static void main(String[] args)
    {
        ParentThread gfg_pt = new ParentThread();
        gfg_pt.start();
    }
}
```

```
Output:
Parent Thread Value:parent data 
Child Thread Value:child data

```

**第一个场景**:在上面的程序中，如果我们用 ThreadLocal 替换 InheritableThreadLocal，并且我们没有覆盖 childValue 方法，那么输出是:

```
Output:
Parent Thread Value: parent data 
Child Thread Value:null   (by default initialValue is null)

```

**第二个场景**:在上面的程序中，如果我们维护的是 InheritableThreadLocal，并且没有覆盖 childValue 方法，那么输出就是:

```
Output :
Parent Thread Value:parent data 
Child Thread Value:parent data

```

**第三个场景**:在上面的程序中，如果我们维护的是 InheritableThreadLocal，同时我们也在覆盖 childValue 方法，那么输出就是:

```
Output:
Parent Thread Value:parent data 
Child Thread Value:child data

```