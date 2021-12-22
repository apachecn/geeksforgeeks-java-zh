# Java . util . Java 中的可观察类

> 原文:[https://www . geesforgeks . org/Java-util-observable-class-Java/](https://www.geeksforgeeks.org/java-util-observable-class-java/)

**java.util.Observable** 用于创建程序其他部分可以观察的子类。当这种子类的对象发生变化时，观察类会得到通知。当观察者被告知有变化时，调用 **update( )** 方法。

```
Note:
```

观察类必须实现 ***观察者*** 界面，其中定义了 ***更新()*** 方法。

被观察的物体必须遵循两个简单的规则:

1.  如果改变，必须调用 **setChanged( )** 方法。
2.  当它准备通知观察者这个变化时，它必须调用 **notifyObservers( )** 方法。这导致调用观察对象中的**更新()**方法。

```
Be careful, if the object calls *notifyObservers( )* method without having previously called
*setChanged( )* method, no action will take place.
```

被观察对象必须同时调用 **setChanged( )** 和 **notifyObservers( )** 方法，才会调用 **update( )** 。
**Java . util . observatory 的构造函数:**

*   **可观测值()**
    用零观测值构造一个可观测值。

**方法:**

1.  **addObserver(Observer observer) :** Adds observer to the list of objects observing the invoking object.

    ```
    Syntax : public void addObserver(Observer observer)
    Exception : NullPointerException -> if the parameter observer is null

    ```

    ```
    // Java code to demonstrate addObserver() method
    import java.util.*;

    // This is the observer
    class Observer1 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Observer1 is added");
        }
    }

    // This is class being observed
    class BeingObserved extends Observable
    {
        void incre() 
        {
            setChanged();
            notifyObservers();
        }
    }

    class ObserverDemo {
        // Driver method of the program
        public static void main(String args[]) 
        {
            BeingObserved beingObserved = new BeingObserved();
            Observer1 observer1 = new Observer1();
            beingObserved.addObserver(observer1);
            beingObserved.incre();
        }
    }
    ```

    输出:

    ```
    Observer1 is added
    ```

2.  **setChanged() :** Called when the invoking object has changed.

    ```
    Syntax : protected void setChanged( )
    Exception : NA.

    ```

    ```
    // Java code to demonstrate setChanged() method
    import java.util.*;

    // This is first observer
    class Observer1 implements Observer
    {
        public void update(Observable obj, Object arg) { }
    }

    // This is class being observed
    class BeingObserved extends Observable
    {
        void func1()
        {
            setChanged();
            System.out.println("Change status with setChanged :" + hasChanged());
            notifyObservers();
        }

        void func2()
        {
            System.out.println("Change status without setChanged :" + hasChanged());
            notifyObservers();
        }
    }

    class ObserverDemo {
        // Driver method of the program
        public static void main(String args[]) 
        {
            boolean status;
            BeingObserved beingObserved = new BeingObserved();
            Observer1 observer1 = new Observer1();
            beingObserved.addObserver(observer1);
            beingObserved.func1();
            beingObserved.func2();
        }
    }
    ```

    输出:

    ```
    Change status with setChanged :true
    Change status without setChanged :false
    ```

3.  **clearChanged():** Indicates that this object has no longer changed, or that it has already notified all of its observers of its most recent change, so that the **hasChanged( )** method will now return **false**.

    ```
    Syntax : protected void clearChanged( )
    Exception : NA

    ```

    ```
    // Java code to demonstrate clearChanged() method
    import java.util.*;

    // This is the observer
    class Observer1 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Inside Observer1");
        }
    }

    // This is the class being observed
    class BeingObserved extends Observable
    {
        void func1()
        {
            setChanged();
            // clearChanged method removes all the changes made by setChanged method
            clearChanged();
            notifyObservers();

        }
    }

    class ObserverDemo {
    // Driver method of the program
        public static void main(String args[]) 
        {
            BeingObserved beingObserved = new BeingObserved();
            Observer1 observer1 = new Observer1();
            beingObserved.addObserver(observer1);
            beingObserved.func1();
        }
    }
    ```

    输出:

    ```
    No Output
    ```

    没有得到输出，因为 **clearChanged( )** 方法已经删除了所有的更改。

4.  **notifyObservers() :** Notifies all observers of the invoking object that it has changed by calling **update( )**.
    A null is passed as the second argument to **update( )**.

    ```
    Syntax : public void notifyObservers( )
    Exception : NA

    ```

    ```
    // Java code to demonstrate notifyObservers( ) method
    import java.util.*;

    // This is first observer
    class Observer1 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Observer1 Notified");
        }
    }

    // This is second observer
    class Observer2 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Observer2 Notified");
        }
    }

    // This is class being observed
    class BeingObserved extends Observable
    {
        void func1()
        {
            setChanged();
            /*This method notifies the change to all the 
            observers that are registered*/
            notifyObservers();

        }
    }

    class ObserverDemo {
        // Driver method of the program
        public static void main(String args[]) 
        {
            BeingObserved beingObserved = new BeingObserved();
            Observer1 observer1 = new Observer1();
            Observer2 observer2 = new Observer2();
            beingObserved.addObserver(observer1);
            beingObserved.addObserver(observer2);
            beingObserved.func1();
        }
    }
    ```

    输出:

    ```
    Observer2 Notified
    Observer1 Notified
    ```

5.  **notifyObservers(Object obj) :** Notifies all observers of the invoking object that it has changed by calling **update( )**.
    *obj* is passed as an argument to **update( )**.

    ```
    Syntax : public void notifyObservers(Object obj)
    Exception : NA

    ```

    ```
    // Java code to demonstrate notifyObservers(Object obj) method
    import java.util.*;

    // This is first observer
    class Observer1 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Observer1 Notified with value : " + 
                    ((Integer)arg).intValue());
        }
    }

    // This is second observer
    class Observer2 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Observer2 Notified with value : " + 
                    ((Integer)arg).intValue());
        }
    }

    // This is class being observed
    class BeingObserved extends Observable
    {
        void func1()
        {
            setChanged();
            /*This method notifies the change to all the 
            observers that are registered and passes an object*/
            notifyObservers(new Integer(10));

        }
    }

    class ObserverDemo {
        // Driver method of the program
        public static void main(String args[]) 
        {
            BeingObserved beingObserved = new BeingObserved();
            Observer1 observer1 = new Observer1();
            Observer2 observer2 = new Observer2();
            beingObserved.addObserver(observer1);
            beingObserved.addObserver(observer2);
            beingObserved.func1();
        }
    }
    ```

    输出:

    ```
    Observer2 Notified with value : 10
    Observer1 Notified with value : 10
    ```

6.  **countObservers( ) :** Returns the number of objects observing the invoking object.

    ```
    Syntax : public int countObservers( )
    Returns : the number of observers of this object
    Exception : NA

    ```

    ```
    // Java code to demonstrate countObservers() method
    import java.util.*;

    // This is first observer
    class Observer1 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Observer1");
        }
    }

    // This is second observer
    class Observer2 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Observer2");
        }
    }

    // This is class being observed
    class BeingObserved extends Observable
    {
        void func1()
        {
            setChanged();
            notifyObservers();
        }
    }

    class ObserverDemo {
        // Driver method of the program
        public static void main(String args[]) 
        {
            BeingObserved beingObserved = new BeingObserved();
            Observer1 observer1 = new Observer1();
            Observer2 observer2 = new Observer2();
            beingObserved.addObserver(observer1);
            beingObserved.addObserver(observer2);
            int count_observer = beingObserved.countObservers();
            System.out.println("Number of observers is " + count_observer);
            beingObserved.func1();
        }
    }
    ```

    输出:

    ```
    Number of observers is 2
    Observer2
    Observer1
    ```

7.  **deleteObserver(Observer observer):** Removes *observer* from the list of objects observing the invoking object.
    Passing **null** to this method will have no effect.

    ```
    Syntax : public void deleteObserver(Observer observer)
    Exception : NA

    ```

    ```
    // Java code to demonstrate deleteObserver(Observer observer) method
    import java.util.*;

    // This is first observer
    class Observer1 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Observer1");
        }
    }

    // This is second observer
    class Observer2 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Observer2");
        }
    }

    // This is class being observed
    class BeingObserved extends Observable
    {
        void func1()
        {
            setChanged();
            notifyObservers();
        }
    }

    class ObserverDemo {
        // Driver method of the program
        public static void main(String args[]) 
        {
            int count_observer;
            BeingObserved beingObserved = new BeingObserved();
            Observer1 observer1 = new Observer1();
            Observer2 observer2 = new Observer2();
            beingObserved.addObserver(observer1);
            beingObserved.addObserver(observer2);

            count_observer = beingObserved.countObservers();
            System.out.println("Number of observers before" + 
            " calling deleteObserver(): " + count_observer);
            beingObserved.func1();

            // Deleting observer1
            beingObserved.deleteObserver(observer1);
            count_observer = beingObserved.countObservers();
            System.out.println("No. of observers after"+ 
            " calling deleteObserver(): " + count_observer);
            beingObserved.func1();

        }
    }
    ```

    输出:

    ```
    Number of observers before calling deleteObserver(): 2
    Observer2
    Observer1
    No. of observers aftercalling deleteObserver(): 1
    Observer2
    ```

8.  **deleteObservers() :** Removes all observers for the invoking object.

    ```
    Syntax : public void deleteObservers()
    Exception : NA

    ```

    ```
    // Java code to demonstrate deleteObservers() method
    import java.util.*;

    // This is first observer
    class Observer1 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Observer1");
        }
    }

    // This is second observer
    class Observer2 implements Observer
    {
        public void update(Observable obj, Object arg) 
        {
            System.out.println("Observer2");
        }
    }

    // This is class being observed
    class BeingObserved extends Observable
    {
        void func1()
        {
            setChanged();
            notifyObservers(new Integer(10));
        }
    }

    class ObserverDemo {
        // Driver method of the program
        public static void main(String args[]) 
        {
            int count_observer;
            BeingObserved beingObserved = new BeingObserved();
            Observer1 observer1 = new Observer1();
            Observer2 observer2 = new Observer2();
            beingObserved.addObserver(observer1);
            beingObserved.addObserver(observer2);

            count_observer = beingObserved.countObservers();
            System.out.println("Number of observers before" + 
            " calling deleteObserver(): " + count_observer);
            beingObserved.func1();

            // Deleting all observers
            beingObserved.deleteObservers();
            count_observer = beingObserved.countObservers();
            System.out.println("No. of observers after "+ 
            "calling deleteObserver(): " + count_observer);
            beingObserved.func1();

        }
    }
    ```

    输出:

    ```
    Number of observers before calling deleteObserver(): 2
    Observer2
    Observer1
    No. of observers after calling deleteObserver(): 0
    ```

参考:[在 Java 中可见](https://docs.oracle.com/javase/8/docs/api/java/util/Observable.html)

本文由**迪帕克丑汉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。