# Java 中的最终数组

> 原文:[https://www.geeksforgeeks.org/final-arrays-in-java/](https://www.geeksforgeeks.org/final-arrays-in-java/)

预测后续 Java 程序的输出。

```
class Test 
{
    public static void main(String args[])
    {
       final int arr[] = {1, 2, 3, 4, 5};  // Note: arr is final
       for (int i = 0; i < arr.length; i++)
       {
           arr[i] = arr[i]*10;  
           System.out.println(arr[i]);          
       }      
    }    
}
```

输出:

```
10 
20 
30 
40 
50 
```

数组 *arr* 被声明为最终的，但是数组的元素被改变没有任何问题。[数组是对象](https://www.geeksforgeeks.org/g-fact-65/)和[对象变量在 Java 中总是引用](https://www.geeksforgeeks.org/g-fact-46/)。因此，当我们将一个对象变量声明为 final 时，这意味着该变量不能被更改为引用其他任何东西。例如，下面的程序 1 编译没有任何错误，程序 2 编译失败。

```
// Program 1
class Test 
{
    int p = 20;
    public static void main(String args[])
    {
       final Test t = new Test();       
       t.p = 30;
       System.out.println(t.p);   
    }    
}
```

产出:30

```
// Program 2
class Test 
{
    int p = 20;
    public static void main(String args[])
    {
       final Test t1 = new Test();       
       Test t2 = new Test();
       t1 = t2; 
       System.out.println(t1.p);      
    }    
}
```

输出:编译器错误:无法为最终变量 t1 赋值

*所以一个最终的数组意味着数组变量实际上是对一个对象的引用，不能改变为引用其他任何东西，但是数组的成员是可以修改的。*

作为练习，预测以下程序的输出

```
class Test 
{
    public static void main(String args[])
    {
       final int arr1[] = {1, 2, 3, 4, 5};
       int arr2[] = {10, 20, 30, 40, 50};
       arr2 = arr1;      
       arr1 = arr2;  
       for (int i = 0; i < arr2.length; i++)
          System.out.println(arr2[i]);          
    }    
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。