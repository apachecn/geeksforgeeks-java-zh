# 游戏服务器上的 Java 模式原型

> 原文:[https://www . geesforgeks . org/Java-pattern-游戏服务器原型/](https://www.geeksforgeeks.org/java-pattern-prototype-on-game-server/)

有时也称为克隆，基本上原型是一种生成式设计模式，它允许您复制对象，而不会使您的代码依赖于它们的类。

**想法**

想法是**创造一群怪物**来攻击我们的英雄/角色。为敌人设置了特定的配置–**敌人配置**。在原型的帮助下，我们将能够**复制基本敌人**并对他们进行分组。我们也可以复制组，组成大的单元。我们可以设置参数，例如，20 个近战敌人和 40 个远程敌人。基于基本配置，我们可以创建单元的副本。这将进一步允许我们克隆整个单位。很酷，不是吗？

**问题**

假设你有一个**敌人对象**，你想**创建**一个精确的**副本**。你会怎么做？首先，我们需要创建一个相同类的新对象。然后你需要**转到** **到** **原始对象的所有字段**并将它们的值复制到新对象。

好吧。但是有一个问题。**并不是所有的对象都可以通过这种方式复制**因为**的某些字段**可能是**关闭的**而**不是**的**从对象本身外部可见的**。

直接方法还有另一个问题。因为我们需要知道对象的类来创建副本，所以我们的代码依赖于该类。如果其他上瘾吓不倒我们，还有另一个障碍。例如，当方法中的参数接受任何遵循某个接口的对象时，有时您只知道对象遵循的接口，而不知道它的特定类。

**解决方案**

**原型**模板将克隆过程委托给自然克隆对象。该模板为所有支持克隆的对象声明了一个标准接口。此接口允许您克隆对象，而无需将任何代码绑定到该对象的类。通常，这样的接口只包含一个克隆方法。

克隆方法在所有类中的实现非常相似。方法创建当前类的对象，并将旧对象的所有字段值转移到新对象。您甚至可以复制私有字段，因为大多数编程语言允许对象访问属于同一类的其他对象的私有字段。

**支持克隆的对象称为原型**。当您的对象有几十个字段和数百种可能的配置时，克隆它们可以作为子类化的替代方法。

它是这样工作的:你创建了一组可以用各种方式定制的对象。当你需要一个像你定制的对象时，你**克隆原型**，而不是从头开始创建一个新的对象。

**适用性**

当您的代码不需要依赖于您需要复制的特定对象类时，请使用****原型** **模式** **。****

**当您的代码处理通过某些接口从第三方代码传递给您的对象时，这种情况经常发生。这些对象的具体类别是未知的，即使你想依赖它们，你也不能依赖它们。**

**原型模板为客户端代码提供了一个公共接口，以便与所有支持克隆的对象一起工作。该接口使客户端代码独立于克隆对象的特定类。**

****原型**模式**允许**您**使用**一组预先创建的对象，以各种方式配置为原型。**

**客户端可以找到合适的原型并克隆它，而不是实例化一个子类来匹配一些配置。**

****如何实施****

**创建一个原型接口，并在其中声明一个克隆方法。或者向现有类层次结构的所有类添加一个方法(如果有的话)。**

**原型类必须**定义一个**替代** **构造器**，该构造器将该类的一个对象作为参数。**构造器**必须**将类中定义的所有字段的**值**从传递的对象复制到新创建的实例。如果更改子类，必须调用父构造函数，让超类处理其私有字段的克隆。如果您的编程语言不支持方法重载，您可以定义一个特殊的方法来复制对象数据。构造函数是一个更方便的地方，因为它在调用新运算符后立即传递结果对象。******

克隆方法通常由一行组成:用原型构造函数开始一个新语句。请注意，每个类都必须显式重写 clone 方法，并使用其类名和新运算符。否则，克隆方法可以创建父类的对象。

或者，您可以创建一个集中式原型注册表来存储常用原型的目录。使用静态原型获取方法，您可以将注册表实现为新的工厂类，或者将其放在原型基类中。此方法应基于客户端代码传递给方法的搜索条件来搜索原型。需求可以是简单的字符串标记，也可以是一组复杂的搜索参数。一旦找到匹配的原型，注册表必须克隆它并将其返回给客户端。最后，用对原型注册表工厂方法的调用替换对子类构造函数的直接调用。

**复制敌人**

让我们看看如何在没有标准可克隆接口的情况下实现原型。

> **第一步:让我们创建一个基本的抽象类敌人**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Create Abstract Enemy class 

// Abstrat class
public abstract class Enemy {

  // enemy health
   public int health; 
   // enemy speed
   public int speed; 
   // enemy name
   public String name; 

   // Constructor 1
   // Base constructor 
   public Enemy() { 
   }

   // Constructor 2 
   // Copy constructor 
   public Enemy(Enemy target) {  

      // Check that target not empty
       if (target != null) {           

          // set base params and note 
           // this keyword refers to current instance itself
           this.health = target.health;
           this.speed = target.speed;
           this.name = target.name;
       }
   }

   // clone() method 
   public abstract Enemy clone(); 

   // Override equals() method 
   @Override
   public boolean equals(Object o) { 
       if (!(o instanceof Enemy)) return false;
       Enemy enemy = (Enemy) o;
       return enemy.health == health && enemy.speed == speed && Objects.equals(enemy.name, name);
   }

  // Override hashCode() method 
   @Override
   public int hashCode() {
       return Objects.hash(health, speed, name);
   }
}
```

> **第二步:我们需要几个敌人。**让它成为我和我的朋友

**例 2-A**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Let`s create ArcherEnemy with attack range

public class ArcherEnemy extends Enemy { // Enemy is a parent

   public int attackRange; // add new param

   public ArcherEnemy() {
   }

   public ArcherEnemy(ArcherEnemy target) { // clone constructor
       super(target); // first of all clone base Enemy
       if (target != null) {
           this.attackRange = target.attackRange; // then clone additional params
       }
   }

   /*
    Clone based on THIS enemy
   */
   @Override
   public Enemy clone() {
       return new ArcherEnemy(this);
   }

   @Override
   public boolean equals(Object o) {
       if (this == o) return true;
       if (o == null || getClass() != o.getClass()) return false;
       if (!super.equals(o)) return false;
       ArcherEnemy that = (ArcherEnemy) o;

       return attackRange == that.attackRange ;
   }

   @Override
   public int hashCode() {
       return Objects.hash(super.hashCode(), attackRange);
   }
}
```

**例 2-B**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Let`s create MeleeEnemy with 'melee params'

public class MeleeEnemy extends Enemy {

    public int blockChance; // add new param
    public boolean withShield; // add new param

    public MeleeEnemy() {}

    // Create clone constructor
    // clone base Enemy
    // and then clone additional params
    public MeleeEnemy(MeleeEnemy target)
    {
        super(target);
        if (target != null) {
            this.blockChance = target.blockChance;
            this.withShield = target.withShield;
        }
    }

    //  Clone class based on current values

    @Override public Enemy clone()
    {
        return new MeleeEnemy(this);
    }

    @Override public boolean equals(Object o)
    {
        if (this == o)
            return true;
        if (o == null || getClass() != o.getClass())
            return false;
        if (!super.equals(o))
            return false;

        MeleeEnemy that = (MeleeEnemy)o;

        return blockChance == that.blockChance
            && withShield == that.withShield;
    }

    @Override public int hashCode()
    {
        return Objects.hash(super.hashCode(), blockChance,
                            withShield);
    }
}
```

> **第三步:** **让我们测试克隆的创建，因为我们已经准备好了基本的敌人。**

**例 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustarey Creation of Clones

// Main class
public class Demo {

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating enemy list
        List<Enemy> enemyList = new ArrayList<>();
        // Creating enemy list copy
        List<Enemy> enemyListCopy = new ArrayList<>();

        // Create baseArcher
        ArcherEnemy baseArcher = new ArcherEnemy();

        // Setting attributes
        baseArcher.health = 150;
        baseArcher.speed = 35;
        baseArcher.name = "Base Archer";
        baseArcher.attackRange = 100;

        enemyList.add(baseArcher);

        // Create clone baseArcher
        ArcherEnemy baseArcherClone
            = (ArcherEnemy)baseArcher.clone();

        // Adding clone to enemyList
        enemyList.add(baseArcherClone);

        // Create baseMeleeEnemy
        MeleeEnemy baseMeleeEnemy = new MeleeEnemy();

        // Setting attributes
        baseMeleeEnemy.health = 10;
        baseMeleeEnemy.speed = 20;
        baseMeleeEnemy.name = "blue";
        baseMeleeEnemy.blockChance = 7;
        baseMeleeEnemy.withShield = true;

        // Now adding baseMeleeEnemy to enemyList
        // using add() method
        enemyList.add(baseMeleeEnemy);

        // Cloning whole list and comparing
        cloneAndCompare(enemyList, enemyListCopy);
    }

    // Method 1
    // To clone and compare
    private static void
    cloneAndCompare(List<Enemy> enemyList,
                    List<Enemy> enemyListCopy)
    {

        // Iterate over enemyList
        // using for-each loop
        for (Enemy enemy : enemyList) {

            // Clone enemyes and add into enemyListCopy
            enemyListCopy.add(enemy.clone());
        }

        // Compare enemyes in enemyList and in enemyListCopy
        for (int i = 0; i < enemyList.size(); i++) {

            // Checking that enemy and cloneEnemy have
            // different links
            if (enemyList.get(i) != enemyListCopy.get(i)) {

                // Simply printing the result
                System.out.println(
                    i
                    + ": Enemy are different objects (yay!)");

                // Check that they have same params
                if (enemyList.get(i).equals(
                        enemyListCopy.get(i))) {

                    // Print statement if they are identical
                    System.out.println(
                        i
                        + ": And they are identical (yay!)");
                }
                else { // Print statement if they are
                       // not-identical
                    System.out.println(
                        i
                        + ": But they are not identical (booo!)");
                }
            }
            else {

                // Print statement if Shape objects are same
                System.out.println(
                    i
                    + ": Shape objects are the same (booo!)");
            }
        }
    }
}
```

**输出:**

```
0: Enemy are different objects (yay!) // have different links
0: And they are identical (yay!)      // but have same inner state
1: Enemy are different objects (yay!) // have different links
1: And they are identical (yay!)      // but have same inner state
2: Enemy are different objects (yay!) // have different links
2: And they are identical (yay!)      // but have same inner state
```

> 我们有一份敌人名单，如果有必要，我们可以复制并传送给客户。**通过这种方法，我们有机会使用已经创建的敌人，并将它们组合成不同的组，将它们存储在复杂的数据结构中。**