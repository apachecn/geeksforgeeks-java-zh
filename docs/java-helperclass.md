# Java |如何创建自己的助手类？

> 原文:[https://www.geeksforgeeks.org/java-helperclass/](https://www.geeksforgeeks.org/java-helperclass/)

助手类是一个 Java 类，包括基本的错误处理，一些助手函数等。Helper 类包含帮助程序的函数。这个类旨在快速实现基本功能，这样程序员就不必一次又一次地实现。它很容易访问，因为所有成员函数都是静态的，也就是说，它可以从任何地方访问。它实现了最常用的函数，不包括 java 库中已经存在的函数。

根据程序的需要，不同的助手类包含不同的方法。

**建议:为这个类制作一个名为 HelperClass 的包，并导入到你的 java 代码中**

下面是 helperclass 的一个例子。

```
// Example for helper class 
import java.lang.*;
import java.util.*;

class HelperClass {

    // to check whether integer is greater than 0 or not
    // usually used when we have to input a whole number
    // like taking input of number of test cases etc
    public static boolean isValidInteger(int test)
    {
        return (test >= 0);
    }

    // to check whether integer is greater than the lower
    //  bound and lower than the highest bound.
    public static boolean isValidInteger(int test, int low, 
                                               int high) {
        return (test >= low && test <= high);
    }

    // used when we want the user to input the number
    // exactly greater than the lower bound
    public static int getInRange(int low) {
        Scanner sc = new Scanner(System.in);
        int test;
        do 
        {
            test = sc.nextInt();
        } while (test < low);

        return test;
    }

    // used when we want the user to input the number
    // exactly greater than lower bound and lower than
    // the highest bound
    public static int getInRange(int low, int high) {
        Scanner sc = new Scanner(System.in);
        int test;
        do {
            test = sc.nextInt();
        } while (test < low || test > high);
        return test;
    }

    // to check whether an array contains any negative value
    public static boolean validatePositiveArray(int[] array, 
                                                  int n) {
        for (int i = 0; i < n; i++)         
            if (array[i] < 0) 
                return false;        
        return true;
    }

    // to check whether an array contains any positive value
    public static boolean validateNegativeArray(int[] array, 
                                                  int n) {
        for (int i = 0; i < n; i++)
            if (array[i] > 0) 
                return false;
        return true;
    }

    // check whether every element in the array is greater
    // than the lower bound
    public static boolean checkRangeArray(int[] array, 
                                     int n, int low) {
        for (int i = 0; i < n; i++)        
            if (array[i] < low)
                return false;
        return true;
    }

    // check whether every element in the array is greater
    // than the lower bound and lower than the highest bound
    public static boolean checkRangeArray(int[] array, int n,
                                         int low, int high) {
        for (int i = 0; i < n; i++)        
            if (array[i] < low || array[i] > high)             
                return false;
        return true;
    }

    // check whether two given sets as "arrays" are equal or not
    public static boolean isEqualSets(int[] array1, int n,
                                    int[] array2, int m) {
        if (n != m)         
            return false;
        HashMap<Integer, Integer> Map = 
                            new HashMap<Integer, Integer>();
        for (int i = 0; i < n; i++) 
           Map.put(new Integer(array1[i]), new Integer(1));
        for (int i = 0; i < m; i++) 
           Map.put(new Integer(array2[i]), new Integer(0));

        for (int i = 0; i < n; i++) 
           if (Map.get(array1[i]) == 1) 
             return false;
         return true;      
    }

    // calculating factorial of a number
    public static String factorial(int n) {
        String fact = new String("");
        int res[] = new int[500];

        res[0] = 1;
        int res_size = 1;

        for (int x = 2; x <= n; x++)
        res_size = multiply(x, res, res_size);

        for (int i = res_size - 1; i >= 0; i--)
        fact += Integer.toString(res[i]);

        return fact;
    }

    // Multiply x  with res[0..res_size-1]
    public static int multiply(int x, int res[], int res_size) {
        int carry = 0;    
        for (int i = 0; i < res_size; i++) {
           int prod = res[i] * x + carry;
           res[i] = prod % 10;    
           carry = prod / 10;
        }
        while (carry != 0) {
           res[res_size] = carry % 10;
           carry = carry / 10;
           res_size++;
        }
        return res_size;
    }

    // Checks whether the given number is prime or not
    public static boolean isPrime(int n) {
        if (n == 2) 
           return true;

        int squareRoot = (int)Math.sqrt(n);    
        for (int i = 1; i <= squareRoot; i++) 
          if (n % i == 0 && i != 1) 
             return false;
        return true;
    }

    // Returns nthPrimeNumber
    public static int nthPrimeNumber(int n) {
        int k = 0;
        for (int i = 2;; i++) {
          if (isPrime(i)) 
              k++;        
          if (k == n) 
              return i;
        }
    }

    // check whether the given string is palindrome or not
    public static boolean isPalindrome(String test) {
        int length = test.length();    
        for (int i = 0; i <= (test.length()) / 2; i++) 
          if (test.charAt(i) != test.charAt(length - i - 1)) 
             return false;
        return true;
    }

    // check whether two strings are anagram or not
    public static boolean isAnagram(String s1, String s2) {

        // Removing all white spaces from s1 and s2
        String copyOfs1 = s1.replaceAll("\\s", "");
        String copyOfs2 = s2.replaceAll("\\s", "");

        if (copyOfs1.length() != copyOfs2.length()) 
            return false;

        // Changing the case of characters of both copyOfs1 and
        // copyOfs2 and converting them to char array
        char[] s1Array = copyOfs1.toLowerCase().toCharArray();
        char[] s2Array = copyOfs2.toLowerCase().toCharArray();

        // Sorting both s1Array and s2Array
        Arrays.sort(s1Array);
        Arrays.sort(s2Array);

        // Checking whether s1Array and s2Array are equal    
        return (Arrays.equals(s1Array, s2Array));
     }    
} /*** end of helperClass **/

class Test {
    public static void main(String[] args) {

        int n = -5;    
        if (HelperClass.isValidInteger(n)) 
            System.out.println("True");
        else 
            System.out.println("False");

        String str = "madam";    
        if (HelperClass.isPalindrome(str)) 
           System.out.println("True");
        else 
           System.out.println("False");        
    }
}
```

```
False
True

```