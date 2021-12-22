# 比较 Java 中的日期

> 原文:[https://www.geeksforgeeks.org/compare-dates-in-java/](https://www.geeksforgeeks.org/compare-dates-in-java/)

[日期类](https://www.geeksforgeeks.org/date-class-java-examples/)代表特定的时间瞬间，精度为毫秒。java.util 包的 Date 类实现了可序列化、可克隆和可比较的接口。它提供了用 java 处理日期和时间的构造函数和方法。
以下是 java 中比较日期的方法

1.  **使用**[**date . compare to()**](https://www.geeksforgeeks.org/util-date-class-methods-java-examples/):
    **涉及的步骤:**
    1.  为 SimpleDateFormat 类创建一个对象，用格式 yyyy-mm-dd 初始化它。
    2.  使用上述对象初始化日期变量。
    3.  使用日期类的 compareTo()函数进行日期比较
    4.  打印结果。
2.  **使用** [**Date.before()，Date.after()和 Date.equals()**](https://www.geeksforgeeks.org/util-date-class-methods-java-examples/) 。
    这种方法比第一种简单。
    **涉及的步骤:**
    1.  为 SimpleDateFormat 类创建一个对象，用格式 yyyy-mm-dd 初始化它。
    2.  使用上述对象初始化日期变量。
    3.  使用 date 类的 after()和 before 函数进行日期比较
    4.  打印结果。
3.  **使用** [**历.前()**](https://www.geeksforgeeks.org/calendar-before-method-in-java/)**[**历.后()**](https://www.geeksforgeeks.org/java-util-calendar-method/) **和** [**历.等于()**](https://www.geeksforgeeks.org/calendar-equals-method-in-java/) 。
    **涉及的步骤:**

    1.  为 SimpleDateFormat 类创建一个对象，用格式 yyyy-mm-dd 初始化它。
    2.  使用上述对象初始化日期变量。
    3.  使用 getinstance()函数初始化日历类对象。
    4.  使用日历类的 setTime()函数将值分配给日历对象。
    5.  使用 Calendar 类的 after()和 before 函数进行日期比较
    6.  打印结果。** 
4.  ****使用 Java 8 的 isBefore()、isAfter()、isEqual()和 compareTo()方法**:在 Java 8 中，isBefore()、isAfter()、isEqual()和 compareTo()用于比较 LocalDate、LocalTime 和 LocalDateTime。
    T3】涉及的步骤:

    1.  创建本地日期类的对象。
    2.  使用日期类的 isAfter()，isBefore()和 isEqual()函数来比较日期。
    3.  打印结果。**