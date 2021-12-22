# 加工中的创意编程|集合 1(随机漫步机)

> 原文:[https://www . geesforgeks . org/creative-programming-processing-set-1-random-walker/](https://www.geeksforgeeks.org/creative-programming-processing-set-1-random-walker/)

创造性编程是一种编程方法，其目标是创造一些表达性和可视化的东西，而不是纯粹的功能性的东西。这种编程方法被用来创建现场艺术品、图形模拟和可视化算法。有许多用于创造性或可视化编程的工具和库，其中 Processing 应用最广泛。Processing 是一种为可视化编程目的而构建的开源编程语言和 IDE。处理可免费下载[这里](https://processing.org/download/)。它也可以作为 python 方言( [processing.py](http://py.processing.org/) )和 javascript 框架( [p5.js](https://p5js.org/) )使用。在本文中，我们将构建一个简单的随机行走程序，它只是一个在画布上随机移动的球。

每个加工草图通常包括两个功能-

*   `setup()`–开始时调用一次，一般用于初始化目的。
*   `draw()`–默认每秒调用 30 次，使动画的默认帧率为每秒 30 帧。

**实现草图-**
示例代码已经使用处理库和处理 IDE 用 java 编写。

```
Walker w; // Walker object

void setup() // Called at the beginning once
{
    size(640, 360); // Declaring size of the output window
    w = new Walker(); // Initializing the new walker object
}

void draw() // Called every frame
{
    background(255); // Setting a white background
    w.display(); // Displaying the walker object
}
```

**沃克类的实现-**

```
class Walker // The walker class
{
    PVector location; // A vector object representing the location

    Walker() // Constructor to initialize the data member.
    {
        // Initial location of the walker object is
        // set to the middle of the output window.
        location = new PVector(width / 2, height / 2);
    }

    void display() // Function to display the walker object
    {
        // Drawing a black circle of radius 10 at location
        fill(0);
        ellipse(location.x, location.y, 10, 10);
    }
}
```

此时，如果我们运行草图，它只是显示一个位于输出屏幕中心的球-
为了移动助行器对象，我们将向`Walker`类添加一个`walk()`函数，并在草图中的`draw()`函数内调用它。我们还在`Walker`中增加了`checkEdges()`功能，防止`Walker`物体移出屏幕。我们还必须修改草图，以包括我们在`Walker`类中添加的新功能。我们还可以多做一件事，把`background()`功能移到`setup()`里面。这样，背景不会每次都更新，我们就能看到沃克物体留下的痕迹。

**草图的修改实现-**

```
// Program to implement random walker

Walker w; // Walker object

void setup() // Called at the beginning once
{
    size(640, 360); // Declaring size of the output window
    background(255); // Setting a white background
    w = new Walker(); // Initializing the new walker object
}

void draw() // Called every frame
{
    w.walk(); // Walking the Walker object
    w.checkEdges(); // Checking for edges of the output screen.
    w.display(); // Displaying the walker object
}
```

**沃克类的修改实现-**

```
class Walker // The walker class
{
    PVector location; // A vector object representing the location

    Walker() // Constructor to initialize the data member.
    {
        // Initial location of the walker object is
        // set to the middle of the output window.
        location = new PVector(width / 2, height / 2);
    }

    void walk()
    {
        // The x and y values of the location
        // vector are incremented by a random value
        // between -5 and 5
        location.x += random(-5, 5);
        location.y += random(-5, 5);
    }

    // Function to prevent the Walker to move out of the screen
    void checkEdges()
    {
        if (location.x < 0)
            location.x = 0;
        else if (location.x > width)
            location.x = width;
        if (location.y < 0)
            location.y = 0;
        else if (location.y > height)
            location.y = height;
    }

    void display() // Function to display the walker object
    {
        // Drawing a black circle of radius 10 at location
        fill(0);
        ellipse(location.x, location.y, 10, 10);
    }
}
```

本文由 **Soumik Rakshit** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。