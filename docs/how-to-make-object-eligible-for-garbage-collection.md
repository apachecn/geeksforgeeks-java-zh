# 如何在 Java 中让对象符合垃圾收集的条件？

> 原文:[https://www . geeksforgeeks . org/如何制作符合垃圾收集条件的对象/](https://www.geeksforgeeks.org/how-to-make-object-eligible-for-garbage-collection/)

如果对象的引用变量在执行过程中从程序中丢失，则该对象有资格被[垃圾收集](https://www.geeksforgeeks.org/garbage-collection-java/)。有时它们也被称为**遥不可及的物体**。

**什么是物体的参照物？**

*新的*运算符为对象动态分配内存，并返回对它的引用。这个引用是 new 分配的对象在内存中的地址。引用是一个地址，指示对象的变量、方法等在哪里。被储存起来。

当分配给变量或作为参数传递给方法时，实际上并不使用这些对象。对对象的引用无处不在。示例:

```java
Box mybox =  new Box();   //referencing to object

```

**Java 中不可达对象的角色**

在 java 中，运行时分配的内存，即堆区域，可以通过垃圾收集过程释放。这只不过是一种释放内存的方法，程序员并没有使用它。在 java 中，只有不再引用它们的对象才有资格进行垃圾收集。

**使对象符合垃圾收集条件的方法:**

*请注意，在丢弃对该对象的所有引用之前，该对象不能成为垃圾收集的候选对象。*

1.  **Object created inside a method :** When a method is called it goes inside the stack frame. When the method is popped from the stack, all its members dies and if some objects were created inside it then these objects becomes unreachable or anonymous after method execution and thus becomes eligible for garbage collection
    .Example:

    ```java
    /* Java program to demonstrate that 
    objects created inside a method will becomes
    eligible for gc after method execution terminate */

    class Test
    {

        // to store object name
        String obj_name;

        public Test(String obj_name) 
        {
            this.obj_name = obj_name;
        }

        static void show()
        {
            //object t1 inside method becomes unreachable when show() removed
            Test t1 = new Test("t1"); 
            display();

        }
        static void display()
        {
            //object t2 inside method becomes unreachable when display() removed
            Test t2 = new Test("t2"); 
        }

        // Driver method
        public static void main(String args[])
        {
            // calling show()
            show();

            // calling garbage collector
            System.gc();
        }

        @Override
        /* Overriding finalize method to check which object
        is garbage collected */
        protected void finalize() throws Throwable 
        {
            // will print name of object
            System.out.println(this.obj_name + " successfully garbage collected");
        }
    }
    ```

    输出:

    ```java
    t2 successfully garbage collected
    t1 successfully garbage collected

    ```

    **注意:**如果一个方法返回在其内部创建的对象，并且我们通过使用引用类型变量来存储这个对象引用，那么它不再适合垃圾收集。

2.  **Reassigning the reference variable:** When reference id of one object is referenced to reference id of some other object then the previous object has no any longer reference to it and becomes unreachable and thus becomes eligible for garbage collection.Example:

    ```java
    /* Java program to demonstrate gc
     when one object referred to other object */

    class Test
    {
        // to store object name
        String obj_name;

        public Test(String obj_name) 
        {
            this.obj_name = obj_name;
        }

        // Driver method
        public static void main(String args[])
        {
            Test t1 = new Test("t1");
            Test t2 = new Test("t2");

            //t1 now referred to t2
            t1 = t2;

            // calling garbage collector
            System.gc();
        }

        @Override
        /* Overriding finalize method to check which object
         is garbage collected */
        protected void finalize() throws Throwable 
        {
            // will print name of object
            System.out.println(this.obj_name + " successfully garbage collected");
        }
    }
    ```

    输出:

    ```java
    t1 successfully garbage collected

    ```

3.  **Nullifying the reference variable :** When all the reference variables of an object are changed to NULL, it becomes unreachable and thus becomes eligible for garbage collection.Example:

    ```java
    /* Java program to demonstrate gc
     when object reference changed to NULL */

    class Test
    {
        // to store object name
        String obj_name;

        public Test(String obj_name) 
        {
            this.obj_name = obj_name;
        }

        // Driver method
        public static void main(String args[])
        {
            Test t1 = new Test("t1");

            /* t1 being used for some purpose in program */

            /* When there is no more use of t1, make the object
               referred by t1 eligible for garbage collection */        
            t1 = null;

            // calling garbage collector
            System.gc();
        }

        @Override
        /* Overriding finalize method to check which object
         is garbage collected */
        protected void finalize() throws Throwable 
        {
            // will print name of object
            System.out.println(this.obj_name + " successfully garbage collected");
        }
    }
    ```

    输出:

    ```java
    t1 successfully garbage collected

    ```

4.  **Anonymous object :** The reference id of an anonymous object is not stored anywhere. Hence, it becomes unreachable.
    Example:

    ```java
    /* Java program to demonstrate gc
     of anonymous objects */

    class Test
    {
        // to store object name
        String obj_name;

        public Test(String obj_name) 
        {
            this.obj_name = obj_name;
        }

        // Driver method
        public static void main(String args[])
        {
            //anonymous object without reference id
            new Test("t1"); 

            // calling garbage collector
            System.gc();
        }

        @Override
        /* Overriding finalize method to check which object
         is garbage collected */
        protected void finalize() throws Throwable 
        {
            // will print name of object
            System.out.println(this.obj_name + " successfully garbage collected");
        }
    }
    ```

    输出:

    ```java
    t1 successfully garbage collected

    ```

**相关文章:** [孤岛](https://www.geeksforgeeks.org/island-of-isolation-in-java/)

本文由**阿普尔瓦·辛格和高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。