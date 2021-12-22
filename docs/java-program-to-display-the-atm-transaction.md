# 显示自动柜员机交易的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到显示-atm-transaction/](https://www.geeksforgeeks.org/java-program-to-display-the-atm-transaction/)

让我们构建一个 Java 程序来表示自动柜员机交易，其中用户必须从屏幕上显示的选项中选择输入。屏幕上可用的选项包括诸如取款、存款、余额等操作。

**以下是 ATM 机**

1.  withdraw
2.  deposit
3.  Check balance
4.  quit

**接近每个选项**

**A .撤回:**

1.  将用户希望提取的金额作为输入。
2.  如果余额大于或等于提取金额，则执行交易并给用户所需的金额。
3.  否则打印资金不足消息。

**B .存款:**

1.  Enter the amount that the user wants to deposit.
2.  Add the received user inputs, balance and update their values.
3.  Balance = balance+deposit.
4.  Print a message on the screen that the deposit transaction has been successful.

**C .检查余额:**

*   Print a message on the screen showing the value of the balance amount.

**D .退出:**

*   Exit the current trading mode, and the user returns to the home page or initial screen.

下面是上述方法的实现。

## 爪哇

```
// Java Program to Display the ATM Transaction
import java.io.*;
public class GFG {

    // Display current balance in account
    public static void displayBalance(int balance)
    {
        System.out.println("Current Balance : " + balance);
        System.out.println();
    }

    // Withdraw amount and update the balance
    public static int amountWithdrawing(int balance,
                                        int withdrawAmount)
    {
        System.out.println("Withdrawn Operation:");
        System.out.println("Withdrawing Amount : "
                           + withdrawAmount);
        if (balance >= withdrawAmount) {
            balance = balance - withdrawAmount;
            System.out.println(
                "Please collect your money and collect the card");
            displayBalance(balance);
        }
        else {
            System.out.println("Sorry! Insufficient Funds");
            System.out.println();
        }
        return balance;
    }

    // Deposit amount and update the balance
    public static int amountDepositing(int balance,
                                       int depositAmount)
    {
        System.out.println("Deposit Operation:");
        System.out.println("Depositing Amount : "
                           + depositAmount);
        balance = balance + depositAmount;
        System.out.println(
            "Your Money has been successfully deposited");
        displayBalance(balance);
        return balance;
    }

    public static void main(String args[])
    {
        int balance = 10000;
        int withdrawAmount = 5000;
        int depositAmount = 2000;

        // calling display balance
        displayBalance(balance);
        // withdrawing amount
        balance
            = amountWithdrawing(balance, withdrawAmount);
        // depositing amount
        balance = amountDepositing(balance, depositAmount);
    }
}
```

**输出**

```
Current Balance : 10000

Withdrawn Operation:
Withdrawing Amount : 5000
Please collect your money and collect the card
Current Balance : 5000

Deposit Operation:
Depositing Amount : 2000
Your Money has been successfully deposited
Balance : 7000
```

**时间复杂度:** O(1)