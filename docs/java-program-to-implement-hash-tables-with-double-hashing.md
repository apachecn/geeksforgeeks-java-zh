# 用双哈希实现哈希表的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-哈希表-带双哈希/](https://www.geeksforgeeks.org/java-program-to-implement-hash-tables-with-double-hashing/)

[双哈希](https://www.geeksforgeeks.org/double-hashing/)是开放寻址方案中的一种技术。还有普通的散列函数。在开放寻址方案中，实际的散列函数取普通散列函数，当它的空间不为空时，它将执行另一个散列函数来获得一些空间来插入。双哈希是开放寻址哈希表中的一种冲突解决技术。当发生冲突时，它使用代码中提到的第二个散列函数(myhash2)应用于密钥的思想。

它是开放寻址中使用的技术。在本文中，我们将使用两个散列函数。使用的第一个函数类似于线性探测(线性探测是计算机编程中的一种方案，用于解决哈希表中的冲突、用于维护键值对的集合并查找与给定键相关联的值的数据结构)、表大小或“键-模”，但是如果发生冲突，则应用第二个哈希函数。

> 注意:它用于开放寻址，在开放寻址中我们使用散列函数。第一个函数与线性探测(HASH_TABLE_SIZE 或 key-mod)中使用的相同，但是如果发生冲突，则可以应用第二个哈希函数。

![](img/0f75a3f4a644e5a8b7a547a4f7f10be4.png)

我们需要记住两个条件。

*   我们的第二个散列函数从不计算为零。
*   它必须能到达细胞，即所有细胞必须首先探测。

**算法:**

```java
h1(key) = key% hash_table_size
```

```java
h2(key) = PM-(key%PM)*PM 
// where PM is prime number
```

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to implement hashtable in
// double hashing

// Importing input output classes
import java.io.*;

// Class 1
// Helper Class
// LinkedHashEntry
class ValueEntry {

    // Member variables of the class
    String key;
    int value;

    // Constructor of this class
    // Parameterized constructor
    ValueEntry(String key, int value)
    {
        // This keyword refers to current object
        // for assigning values to same object itself
        this.key = key;

        // this operator is pointer which contains location
        // of  that container that have key and value pairs
        this.value = value;
    }
}

// Class 2
// Helper Class
//  HashTable
class HashTable {

    // Member variable of this class
    private int HASH_TABLE_SIZE;
    private int size;
    private ValueEntry[] table;
    private int totalprimeSize;

    // Constructor of this class
    // Parameterized constructor
    public HashTable(int ts)
    {
        // Initializing the member variables
        size = 0;
        HASH_TABLE_SIZE = ts;
        table = new ValueEntry[HASH_TABLE_SIZE];

        // Iterating using for loop over table
        for (int i = 0; i < HASH_TABLE_SIZE; i++)
            table[i] = null;
        totalprimeSize = getPrime();
    }

    // Method 1
    // To check for the prime number
    public int getPrime()
    {
        // Iterating using for loop in reverse order
        for (int i = HASH_TABLE_SIZE - 1; i >= 1; i--) {

            // Initially assigning count to zero
            int cnt = 0;

            // Now, iterating from 2 upto the desired number
            // to be checked by dividing it with all no
            // in between [2 - no]
            for (int j = 2; j * j <= i; j++)

                // If number is divisible
                // means not a prime number
                if (i % j == 0)

                    // So simply move to next number
                    // to check for divisibility by
                    // incrementing the count variable
                    cnt++;

            // By now number is not divisible
            // hence count holds 0 till last
            if (cnt == 0)

                // It means it is a prime number so
                // return the number as it is a prime number
                return i;
        }

        // Returning a prime number
        return 3;
    }

    // Method 2
    // To get number of key-value pairs
    public int getSize() { return size; }
    public boolean isEmpty() { return size == 0; }

    //
    /* Function to clear hash table */
    public void makeEmpty()
    {
        size = 0;
        for (int i = 0; i < HASH_TABLE_SIZE; i++)
            table[i] = null;
    }

    // Method 3
    // To get value of a key
    public int getkey(String key)
    {
        int hash1 = myhash1(key);
        int hash2 = myhash2(key);

        while (table[hash1] != null
               && !table[hash1].key.equals(key)) {
            hash1 += hash2;
            hash1 %= HASH_TABLE_SIZE;
        }
        return table[hash1].value;
    }

    // Method 4
    // To insert a key value pair
    public void insert(String key, int value)
    {
        // checking the size of table and
        //  comparing it with users input value
        if (size == HASH_TABLE_SIZE) {

            // Display message
            System.out.println("Table is full");
            return;
        }

        int hashing1 = myhash1(key);
        int hashing2 = myhash2(key);
        while (table[hashing1] != null) {
            hashing1 += hashing2;
            hashing1 %= HASH_TABLE_SIZE;
        }

        table[hashing1] = new ValueEntry(key, value);
        size++;
    }

    // Method 5
    // To remove a key
    public void remove(String key)
    {
        int hash1 = myhash1(key);
        int hash2 = myhash2(key);
        while (table[hash1] != null
               && !table[hash1].key.equals(key)) {
            hash1 += hash2;
            hash1 %= HASH_TABLE_SIZE;
        }
        table[hash1] = null;
        size--;
    }

    // Method 6
    // Function gives a hash value for a given
    // string basically it is linear probing
    private int myhash1(String y)
    {
        int myhashVal1 = y.hashCode();
        myhashVal1 %= HASH_TABLE_SIZE;
        if (myhashVal1 < 0)
            myhashVal1 += HASH_TABLE_SIZE;
        return myhashVal1;
    }

    // Method 7
    // Remember that the above function namely 'myhash'
    // is used for double hashing

    // Now after linear probing, quadratic probing
    //  is used in which two myhash functions are used
    //  as it is double chaining
    private int myhash2(String y)
    {
        int myhashVal2 = y.hashCode();
        myhashVal2 %= HASH_TABLE_SIZE;
        if (myhashVal2 < 0)
            myhashVal2 += HASH_TABLE_SIZE;
        return totalprimeSize - myhashVal2 % totalprimeSize;
    }

    // Method 8
    // To print the hash table
    public void printHashTable()
    {
        // Display message
        System.out.println("\nHash Table");

        for (int i = 0; i < HASH_TABLE_SIZE; i++)
            if (table[i] != null)
                System.out.println(table[i].key + " "
                                   + table[i].value);
    }
}

// Class 3
// Main class
// Class for DoubleHashingHashTableTest
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Display message
        System.out.println("Hash Table Testing");

        // Creating an object of HashTable
        // in the main() method
        // Custom hashtable of size 100
        // means 100 key-value pairs the
        // above hashtable can hold
        HashTable ht = new HashTable(100);

        // Inserting custom values to the hashtable
        // that is key and value pairs
        // Custom inputs
        ht.insert("prime", 97);
        ht.insert("even", 96);
        ht.insert("odd", 95);

        // Printing hash table after insertion of
        // key value pairs and calling function
        // which prints out the hashtable.
        //
        // Calling the function as usual
        // with the help of objects
        ht.printHashTable();
    }
}
```

**Output**

```java
Hash Table Testing

Hash Table
prime 97
even 96
odd 95
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to implement hashtable in
// double hashing

// Here performing additional task
// which is to remove the entered items

// Importing input output classes
import java.io.*;
// Importing all classes from java.util package
import java.util.*;

// Class 1
// Class LinkedHashEntry
class ValueEntry {

  // Member variables of this class
    String key;
    int value;

    // Constructor of this class
    // Parameterized constructor
    ValueEntry(String key, int value)
    {
        // 'This' keyword refers to the current object itself
        // to assign the values
        this.key = key;

        // This keyword is pointer which contains location
        // of  that container that have key and value pairs
       this.value = value;
    }
}

// Class 2
// Helper class
// Class HashTable
class HashTable {

    // Member variable of this class
    private int HASH_TABLE_SIZE;
    private int size;
    private ValueEntry[] table;
    private int totalprimeSize;

    // Constructor of this class
    // Parameterized constructor
    public HashTable(int ts)
    {
        // Initially, initializing the parameters
        //  to some values
        size = 0;
        HASH_TABLE_SIZE = ts;
        table = new ValueEntry[HASH_TABLE_SIZE];

        // Iterating using for loop over table
        for (int i = 0; i < HASH_TABLE_SIZE; i++)

            // Initially table is empty
            table[i] = null;
        totalprimeSize = getPrime();
    }

    // Method 1
    // To check  for the prime number
    public int getPrime()
    {
        // Iterating over hashtable using nested for loops
        //  in reverse order
        for (int i = HASH_TABLE_SIZE - 1; i >= 1; i--) {

            // Initially count is zero
            int cnt = 0;

            for (int j = 2; j * j <= i; j++)
                if (i % j == 0)
                    cnt++;
            if (cnt == 0)
                return i;
        }
        // Returning  a prime number
        return 3;
    }

    // Method 2
    // To get snumber of key-value pairs
    public int getSize()
    { return size; }
    public boolean isEmpty()
    { return size == 0; }

    // Method 3
    // To clear the hash table
    public void makeEmpty()
    {
        // Initially size set to zero
        size = 0;
        for (int i = 0; i < HASH_TABLE_SIZE; i++)
            table[i] = null;
    }

    // Method 3
    // To get value of a key
    public int getkey(String key)
    {
        int hash1 = myhash1(key);
        int hash2 = myhash2(key);

        while (table[hash1] != null
               && !table[hash1].key.equals(key)) {
            hash1 += hash2;
            hash1 %= HASH_TABLE_SIZE;
        }
        return table[hash1].value;
    }

    // Method 4
    // To insert a key-value pair
    public void insert(String key, int value)
    {
        // Checking the size of table and
        // comparing it with users input value
        if (size == HASH_TABLE_SIZE) {

            // Display message
            System.out.println("Table is full");
            return;
        }

        int hashing1 = myhash1(key);
        int hashing2 = myhash2(key);

        while (table[hashing1] != null) {
            hashing1 += hashing2;
            hashing1 %= HASH_TABLE_SIZE;
        }

        table[hashing1] = new ValueEntry(key, value);
        size++;
    }

    // Method 4
    // To remove a key from hashtable
    public void remove(String key)
    {
        int hash1 = myhash1(key);
        int hash2 = myhash2(key);
        while (table[hash1] != null
               && !table[hash1].key.equals(key)) {
            hash1 += hash2;
            hash1 %= HASH_TABLE_SIZE;
        }

        table[hash1] = null;
        size--;
    }

    // Method 5
    // This method returns a hash value for a given
    //  string as it is linear probing
    private int myhash1(String y)
    {
        int myhashVal1 = y.hashCode();
        myhashVal1 %= HASH_TABLE_SIZE;
        if (myhashVal1 < 0)
            myhashVal1 += HASH_TABLE_SIZE;
        return myhashVal1;
    }

    // Method 6
    // In this function, 'myhash'function for double hashing
    // after linear probing. A quadratic probing is used in
    //  which two 'myhash' functions are used
    //  as it is double chaining
    private int myhash2(String y)
    {
        int myhashVal2 = y.hashCode();
        myhashVal2 %= HASH_TABLE_SIZE;
        if (myhashVal2 < 0)
            myhashVal2 += HASH_TABLE_SIZE;
        return totalprimeSize - myhashVal2 % totalprimeSize;
    }

    // Method 7
    // To print hash table
    public void printHashTable()
    {
        // Display message
        System.out.println("\nHash Table");

        // Iterating over the table
        for (int i = 0; i < HASH_TABLE_SIZE; i++)
            if (table[i] != null)
                System.out.println(table[i].key + " "
                                   + table[i].value);
    }
}

// Class 3
// Main class
// Class for DoubleHashingHashTableTest
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Display message
        System.out.println("Hash Table Testing");

        // Step 1: Creating an object of hashtable
        // of custom size 100 which signifies
        // table can hold 100 key-value pairs
        HashTable ht = new HashTable(100);

        // Step 2: Adding(appending) the values to
        // the hashtable object
        // Custom inputs of key-value pairs 
        ht.insert("prime", 97);
        ht.insert("even", 96);
        ht.insert("odd", 95);

        // Step 3: Printing hash table after insertion
        //  of key-value pairs

        // Calling print hash table function using object
        // we call it with object.function_name
        ht.printHashTable();

      // Primarily goal of the program
      // Step 4: Removing elements with using key values
      // using the remove() method
      ht.remove("prime");
      ht.printHashTable();
    }
}
```

**Output**

```java
Hash Table Testing

Hash Table
prime 97
even 96
odd 95

Hash Table
even 96
odd 95
```

> 同样，我们可以得到哈希表的大小，可以从哈希表中清除元素，可以在哈希函数中得到我们想要的元素。为了得到
> 
> *   对于大小可以使用 ht.getSize()
> *   For 元素可以使用 ht.get(字符串)
> 
> 其中 ht 是对象名。同样，我们可以在上面的代码中调用我们的其他函数。