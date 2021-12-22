# 默认虚拟行为在 C++和 Java 中有何不同？

> 原文:[https://www.geeksforgeeks.org/g-fact-43/](https://www.geeksforgeeks.org/g-fact-43/)

**方法的默认虚拟行为在 C++和 Java 中是相反的:**

在 C++中，默认情况下，类成员方法是非虚拟的。使用*虚拟*关键字可以使它们虚拟化。例如 *Base::show()* 在后续程序中是非虚拟的，程序打印*Base::show()称为“*。

```
#include<iostream>

using namespace std;

class Base {
public:      

    // non-virtual by default
    void show() {  
         cout<<"Base::show() called";
    }
};

class Derived: public Base {
public:      
    void show() {
         cout<<"Derived::show() called";
    }      
};

int main()
{
  Derived d;
  Base &b = d;   
  b.show(); 
  getchar();
  return 0;
}
```

在*基地定义前增加*虚*:【显示】(*)使程序打印*“派生的:【显示】()称为“*

在 Java 中，默认情况下方法是虚拟的，可以通过使用 *final* 关键字使方法成为非虚拟的。例如，在下面的 java 程序中， *show()* 默认为虚拟的，程序打印*“衍生的::show()”称为“*

```
class Base {

    // virtual by default
    public void show() {
       System.out.println("Base::show() called");
    }
}

class Derived extends Base {
    public void show() {
       System.out.println("Derived::show() called");
    }
}

public class Main {
    public static void main(String[] args) {
        Base b = new Derived();;
        b.show();
    }
}
```

与 C++非虚拟行为不同的是，如果我们在*基*中 show()的定义前加上 *final* ，那么上述程序编译失败。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。