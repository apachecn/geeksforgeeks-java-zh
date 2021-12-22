# java 中的 java.lang.reflect.Proxy 类

> 原文:[https://www . geesforgeks . org/Java-lang-reflect-proxy-class-in-Java/](https://www.geeksforgeeks.org/java-lang-reflect-proxy-class-in-java/)

java.lang 包中有一个代理类。代理类有特定的方法用于创建动态代理类和实例，所有由这些方法创建的类都充当这个代理类的子类。

**类申报:**T0】

**字段:**

```java
protected InvocationHandler h
```

它处理这个代理实例的调用。

**建造师:**

```java
protected Proxy(InvocationHandler h) 
```

从通常是动态代理类的子类中构造代理实例。实例是用这个调用处理程序 h 的必需值自动创建的。

**创建调用处理程序:**

## Java

```java
// Invocation handler implementation
import java.lang.reflect.InvocationHandler;

class demoInvocationHandler implements InvocationHandler {
    @Override
    public Object invoke(Object proxy, Method method,
                         Object[] args) throws Throwable
    {
        return null;
    }
}

public class GFG {

    public static void main(String[] args)
    {
        InvocationHandler h = new demoInvocationHandler();
    }
}
```

### 方法

<figure class="table">

| **方法** | **描述** |
| getinvacationhandler_object | 此方法返回指定代理实例的调用处理程序。 |
| 类加载器，类> …接口) | 给定类加载器和接口数组，此方法返回代理类的 java.lang.Class 对象。 |
| isProxyClass(等级> cl) | 当且仅当使用 getProxyClass 方法或 newProxyInstance 方法将指定的类动态生成为代理类时，此方法才返回 true。 |
| newProxyInstance(ClassLoader，class>[]接口，调用处理程序 h) | 此方法返回指定接口的代理类的实例，该实例将方法调用分派给指定的调用处理程序。 |

</figure>

**1 .静态调用处理程序 getinvocationhandler(对象代理):**

返回此代理实例的调用处理程序。

## 爪哇

T0】输出

```java
demoInvocationHandler@378fd1ac
```