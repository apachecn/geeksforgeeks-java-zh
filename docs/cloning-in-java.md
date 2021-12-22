# Java 中的克隆

> 原文:[https://www.geeksforgeeks.org/cloning-in-java/](https://www.geeksforgeeks.org/cloning-in-java/)

对象克隆意味着创建原始对象的精确副本。

如果一个类需要支持克隆，就必须实现 java.lang.Cloneable 接口，并从 Object 类中重写 clone()方法。克隆()方法的语法是:

```
protected Object clone() throws CloneNotSupportedException
```

如果对象的类没有实现可克隆接口，那么它会抛出一个异常“CloneNotSupportedException”。

```
// Java code for cloning an object

class Test implements Cloneable
{
    int a;
    int b;

    // Parameterized constructor
    Test(int a, int b)
    {
        this.a = a;
        this.b = b;
    }

    // Method that calls clone()
    Test cloning()
    {
        try
        {
            return (Test) super.clone();
        }
        catch(CloneNotSupportedException e)
        {
            System.out.println("CloneNotSupportedException is caught");
            return this;
        }
    }
}

class demo
{
    public static void main(String args[])
    {
        Test obj1 = new Test(1, 2);
        Test obj2 = obj1.cloning();
        obj1.a = 3;
        obj1.b = 4;
        System.out.println("Object2 is a clone of object1");
        System.out.println("obj1.a = " + obj1.a + " obj1.b = " + obj1.b);
        System.out.println("obj2.a = " + obj2.a + " obj2.b = " + obj2.b);
    }
}
```

输出:

```
Object2 is a clone of object1
obj1.a = 3 obj1.b = 4
obj2.a = 1 obj2.b = 2
```

本文由 Mehak Narang 发表。

如发现任何不正确的地方，请写评论，或者你想分享更多关于上述话题的信息