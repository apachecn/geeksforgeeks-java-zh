# Java 程序打印字母倒心形图案

> 原文:[https://www . geesforgeks . org/Java-程序转打印-字母-倒心形-图案/](https://www.geeksforgeeks.org/java-program-to-print-alphabet-inverted-heart-pattern/)

字母倒心形图案由两部分组成。图案的上半部分是三角形。图案的底部有两个峰和一个间隙。因此，所需的模式如图所示。

插图:

```
                   A                   
                  BBB                  
                 CCCCC                 
                DDDDDDD                
               EEEEEEEEE               
              FFFFFFFFFFF              
             GGGGGGGGGGGGG             
HHHHHHHHHHHHHHH            
           IIIIIIIIIIIIIIIII           
          JJJJJJJJJJJJJJJJJJJ          
         KKKKKKKKKKKKKKKKKKKKK         
        LLLLLLLLLLLLLLLLLLLLLLL        
       MMMMMMMMMMMMMMMMMMMMMMMMM       
      NNNNNNNNNNNNNNNNNNNNNNNNNNN      
     OOOOOOOOOOOOOOOOOOOOOOOOOOOOO     
    PPPPPPPPPPPPPPPPPPPPPPPPPPPPPPP    
   QQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQ   
  RRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRR  
 SSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSS 
TTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTT
UUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUU
 VVVVVVVVVVVVVVVVV  VVVVVVVVVVVVVVVVV 
  WWWWWWWWWWWWWWW    WWWWWWWWWWWWWWW  
   XXXXXXXXXXXXX      XXXXXXXXXXXXX   
    YYYYYYYYYYY        YYYYYYYYYYY    
     ZZZZZZZZZ          ZZZZZZZZZ     
```

**进场:**

打印相同的方法非常简单，首先我们将关注上半部分，去掉下半部分。所以我们只需要打印上面的金字塔模式，在那里我们需要维护和更新增加字母的额外计数。从字符类型的首字母开始，隐式转换为整数类型，并使用相应的 ASCII 值将增量传递给字符。类似地，对于下半部分，在基本考虑打印空白之后

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to print Alphabet Inverted Heart Pattern

// Main class
class GFG {

    // Main Method
    public static void main(String[] args)
    {

        // Declaring a variables to initializing with the
        // value to

        // 1\. set the size of Inverted Heart
        int size = 39;

        // 2\. set the size of upper part of Inverted Heart
        int tri_size = 20;

        // 3\. set the size of base part of Inverted Heart
        int base_size = 6;

        // 4\. set the character to be printed in first row
        // of pattern
        char a = 'A';

        // Declaring and initializing variable representing
        // number of characters to be printed in a row
        int n = 1;

        // Upper part of the pattern

        for (int i = 0; i < tri_size; i++) {

            // Declaring variable representing white spaces
            // to be printed before and after triangle
            int spaces = (size - n) / 2;

            // Iterating using for loop to print spaces
            for (int j = 0; j < spaces; j++) {
                System.out.print(" ");
            }

            // Iterating using for loop to print characters
            for (int j = 0; j < n; j++) {
                System.out.print(a);
            }

            // Iterating using for loop to print spaces
            for (int j = 0; j < spaces; j++) {
                System.out.print(" ");
            }

            // By now over with one row so switching to next
            // row
            System.out.println();

            n = n + 2;

            // Incrementing the alphabet characters
            // Initially at 'a' now getting to 'b'
            a++;
        }

        // Declaring and initializing variable representing
        // number of spaces to be printed in base part
        int spaces_end = 0;

        // Declaring and initializing variable representing
        // number of spaces to be printed between two part
        // of base
        int spaces_between = 0;

        // For loop to print base part
        for (int i = 0; i < base_size; i++) {
            n = (size - (2 * (spaces_end)) - spaces_between)
                / 2;

            // For loop to print space before base part-1
            for (int j = 0; j < spaces_end; j++) {
                System.out.print(" ");
            }

            // For loop to print base part-1
            for (int j = 0; j < n; j++) {
                System.out.print(a);
            }

            // For loop to print spaces between two base
            // parts
            for (int j = 0; j < spaces_between; j++) {
                System.out.print(" ");
            }

            // For loop to print base part-2
            for (int j = 0; j < n; j++) {
                System.out.print(a);
            }

            // For loop to print spaces after base part-2
            for (int j = 0; j < spaces_end; j++) {
                System.out.print(" ");
            }

            // Again in lowe half now done with one row
            // so switching to next row
            System.out.println();

            // Similarly incrementing letter and spaces by
            // unity
            a++;
            spaces_end++;
            spaces_between = spaces_between + 2;
        }
    }
}
```

**Output**

```
                   A                   
                  BBB                  
                 CCCCC                 
                DDDDDDD                
               EEEEEEEEE               
              FFFFFFFFFFF              
             GGGGGGGGGGGGG             
            HHHHHHHHHHHHHHH            
           IIIIIIIIIIIIIIIII           
          JJJJJJJJJJJJJJJJJJJ          
         KKKKKKKKKKKKKKKKKKKKK         
        LLLLLLLLLLLLLLLLLLLLLLL        
       MMMMMMMMMMMMMMMMMMMMMMMMM       
      NNNNNNNNNNNNNNNNNNNNNNNNNNN      
     OOOOOOOOOOOOOOOOOOOOOOOOOOOOO     
    PPPPPPPPPPPPPPPPPPPPPPPPPPPPPPP    
   QQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQ   
  RRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRR  
 SSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSS 
TTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTT
UUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUU
 VVVVVVVVVVVVVVVVV  VVVVVVVVVVVVVVVVV 
  WWWWWWWWWWWWWWW    WWWWWWWWWWWWWWW  
   XXXXXXXXXXXXX      XXXXXXXXXXXXX   
    YYYYYYYYYYY        YYYYYYYYYYY    
     ZZZZZZZZZ          ZZZZZZZZZ     
```