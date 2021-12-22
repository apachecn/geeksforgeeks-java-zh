# 如何在 Java 中使用 Enum 实现策略模式？

> 原文:[https://www . geeksforgeeks . org/如何使用 java 中的枚举实现策略模式/](https://www.geeksforgeeks.org/how-to-implement-a-strategy-pattern-using-enum-in-java/)

策略设计模式旨在提供一种从各种可互换策略中进行选择的方式。经典实现包括由每种技术实现的架构，并提供具体的执行实现。从接口引用中选择方法，并调用执行方法。

**战略设计模式的经典实现:**

战略接口必须由所有战略实施。

```
public interface Strategy {
  public void execute();
}
```

所有策略都必须实现策略接口两个类显示了策略接口的实现并创建了一个执行方法。

```
public class StrategyA implements Strategy {
 @Override
 public void execute(){
   System.out.print("Executing strategy A");
 }
}
```

```
public class StrategyB implements Strategy {
 @Override
 public void execute() {
   System.out.print("Executing strategy B");
 }
}
```

主类将选择策略并执行我们选择的策略的执行方法。

```
public class GFG {

 private Strategy strategy;

 public void setStrategy(Strategy strategy){
   this.strategy = strategy;
 }

 public void executeStrategy(){
   this.strategy.execute();
 }
}
```

使用策略的示例。

```
public class UseStrategy {

public static void main(String[] args){

Context context = new Context();

context.setStrategy(new StrategyA());
context.executeStrategy();

context.setStrategy(new StrategyB());
context.executeStrategy();
}
}
```

**列举战略设计模式的实施:**

它将有两个类:一个枚举类和一个使用它的类。所有神奇的事情都发生在枚举中，具体的策略实现就是定义每个枚举常量。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Implement a Strategy Pattern using Enum

enum Strategy {

  STRATEGY_A {
    @Override
    void execute() {
      System.out.println("Executing strategy A");
    }
  },

  STRATEGY_B {
    @Override
    void execute() {
      System.out.println("Executing strategy B");
    }
  };

  abstract void execute();
}

 class UseStrategy {

  public static void main(String[] args)
  {
    UseStrategy useStrategy = new UseStrategy();
    useStrategy.perform(Strategy.STRATEGY_A);
    useStrategy.perform(Strategy.STRATEGY_B);
  }

  private void perform(Strategy strategy) {
    strategy.execute();
  }
}
```

**Output**

```
Executing strategy A
Executing strategy B
```