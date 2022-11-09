# Pattern Printing Logic with Example in Java

# Hey Reader,

If you are into development and preparing for interviews and want to get good handson on loops, here is the solution. We will learn the logic to write any pattern questions and it's types.

## The contents of the blog include:

1. Introduction on patterns
2. Types of patterns  
    i.  Logical explaination on each type of Pattern
    ii. Solving different types of patterns


## **1. Introduction on patterns**
       
Pattern printing questions are one of the important topic to be discussed in terms of interviews. Also it is helps to play between loops. Let us learn on some of the frequently used and asked pattern printing questions and logic.

Before proceeding into the types of Pattern, let us understand what are rows and columns.
- The horizontal data or values or symbols are known as rows.
- The vertical data or values or symbols are known as columns.


## **Types of patterns **

1. 	Increasing Pattern
2.	Decreasing Pattern
3.	Number Patterns
4.	Pascal Triangle Pattern
5.	Pyramid Patterns
6.	Hollow Pyramid Pattern

### **1. Increasing pattern**

First let us understand the logic behind Increasing pattern, so it will be easier to write the conditional loop to print the increasing patterns.
- For the outer row, the loop can be written as

```
for(int i = 0; i <= input; i++)
``` 
- For inner loop, in Increasing pattern, as the row increases the column also increases. Example 

```
*               Row = 1 Column = 1
**              Row = 2 Column = 2
***             Row = 3 Column = 3
****            Row = 4 Column = 4
*****           Row = 5 Column = 5
``` 
Here, we can conclude that **row == column** , so for inner loop columns, loop can be written as 

```
for(int j = 0; j <=i; j++)
``` 
Example Print for input size - 6
```
*                            inputSize = 5
**
***
****
*****
******


public static void printPattern(int inputSize){
  for(int i = 0; i <= inputSize; i++){
      for(int j = 0; j <=i; j++){
          System.out.print("*"+" ");
      }
      System.out.println();
  }

``` 
### **2. Decreasing Pattern**

In Decreasing Pattern, as the row increases the column decreases


```
*****               Row = 1 Column = 5   = 1 + 5 = 6
****                Row = 2 Column = 4   = 2 + 4 = 6
***                 Row = 3 Column = 3   = 3 + 3 = 6
**                  Row = 4 Column = 2   = 4 + 2 = 6
*                   Row = 5 Column = 1   = 5 + 1 = 6
``` 
Here, we can conclude that **row + column = inputSize + 1** , so for inner loop columns, loop can be written as 

```
for(int j  = 0;  j + i <= inputSize; j++)
``` 
Example Print for input size - 6

```
******                inputSize = 5
*****
****
***
**
*

public static void printPattern(int inputSize){
  for(int i = 0; i <= size; i++){
      for(int j = 0; j +i <= size; j++){
          System.out.print("*"+" ");
      }
      System.out.println();
  }

``` 
 
### **3. Number Patterns**

- Number pattern with increasing order works similar to increasing symbol pattern, but we will print number instead of symbols.

Number Pattern Example - 1
```
1                                   inputSize=5  
2 3 
4 5 6 
7 8 9 10 
11 12 13 14 15

public static void printPattern(int inputSize){
int count = 1;
for(int i = 0; i <= inputSize; i++){
    for(int j = 0; j<i; j++){
        System.out.print(count++ +"  ");
    }
    System.out.println();
}
``` 
Number Pattern Example - 2

```
1                                                inputSize = 5
2  2  
3  3  3  
4  4  4  4  
5  5  5  5  5  
6  6  6  6  6  6 

public static void printPattern(int inputSize){
int count = 1;
for(int i = 0; i <= inputSize; i++){
    for(int j = 0; j <=i; j++){
        System.out.print(count+"  ");
    }
    count++;
    System.out.println();
}
``` 
Number Pattern Example - 3

```
1                                               inputSize = 5
1 2 
1 2 3 
1 2 3 4 
1 2 3 4 5 

public static void printPattern(int inputSize){
for(int i = 0; i < inputSize; i++){
    int count = 1;
    for(int j = 0; j <= i ; j++){
        System.out.print(count +" ");
        count++;
    }
    System.out.println();
}
``` 
Number Pattern Example - 4 - [Number Decreasing Pattern]

```
5 4 3 2 1                                 inputSize = 5
5 4 3 2 
5 4 3 
5 4 
5 

public static void printPattern(int inputSize){
for(int i = 1; i <= inputSize; i++){
    for(int j = inputSize; j >= i ; j--){
        System.out.print(j +" ");
    }
    System.out.println();
}
``` 
Number Pattern Example - 5 

```
5 4 3 2 1                                  inputSize = 5
4 3 2 1
3 2 1
2 1
1

public static void printPattern(int inputSize){
for(int i = inputSize; i >= 1; i--){
    for(int j = i; j >= 1; j--){
        System.out.print(j+" ");
    }
    System.out.println();
}
``` 
Number Pattern Example - 6

```
5                                           inputSize = 5
5 4 
5 4 3 
5 4 3 2 
5 4 3 2 1

public static void printPattern(int inputSize){
for(int i = inputSize; i >= 1; i--){
    for(int j = inputSize; j >= i; j--){
        System.out.print(j+" ");
    }
    System.out.println();
}
``` 
Number Pattern Example - 7

```
1                                         inputSize = 5
1 2 1 
1 2 3 2 1 
1 2 3 4 3 2 1 
1 2 3 4 5 4 3 2 1 

public static void printPattern(int inputSize){
for(int i = 1; i <= inputSize; i++){
    for(int j = 1; j <= i; j++){
        System.out.print(j+" ");
    }
    for(int j = i-1; j >=1; j--){
        System.out.print(j+" ");
    }
    System.out.println();
}
``` 
Number Pattern Example - 8

```
1                                       inputSize =5
1 0 
1 0 1 
1 0 1 0 
1 0 1 0 1 

public static void printPattern(int inputSize){
for(int i = 1; i <= inputSize; i++){
    for(int j = 1; j <= i; j++){
        if(j%2==0){
            System.out.print(0+" ");
        }else{
            System.out.print(1+" ");
        } 
    }
    System.out.println();
}

``` 
Character Pattern Example - 9

```
A                                                 inputSize = 5
B B 
C C C 
D D D D 
E E E E E 
F F F F F F 

public static void printPattern(int inputSize){
int num = 65;
for(int i = 0; i <= inputSize; i++){
    for(int j = 0; j <= i; j++){
        System.out.print((char)num +" ");
    }
    num++;
    System.out.println();
}
```
Character Pattern Example - 10

```
A                                           inputSize = 5
B C 
C D E 
D E F G 
E F G H I 
F G H I J K 

public static void printPattern(int inputSize){
int num = 65;
for(int i = 0; i <= inputSize; i++){
    for(int j = 0; j <= i; j++){
        System.out.print((char) (num + j) +" ");
    }
    num++;
    System.out.println();
}
``` 
 


### **4. Pascal Triangle Patterns**
- Pascal's Triangle is a never-ending equilateral triangle in which the arrays of numbers arranged in a triangular manner. 
- The triangle starts at 1 and continues placing the number below it in a triangular pattern. - Remember that Pascal's Triangle never ends.
- Pascal Triangle is a pattern of the triangle which is based on nCr combination.
where 
```
nCr = n! / (n - r)! * (r!)
``` 
 Pascal Triangle Pattern 

```
          1                                        inputSize = 5
        1   1
      1   2   1
    1   3   3   1
  1   4   6   4   1

public static void printPattern(int inputSize){
int num = 1;
for(int i = 0; i < inputSize; i++){
    for(int space = 1; space < inputSize-i; ++space){
        System.out.print(" ");
    }
    for(int j = 0; j <= i; j++){
        if(j == 0 || i == 0){
            num = 1;
        }else{
            num = num * (i - j + 1) / j;
        }
        System.out.print(" "+num);
    }
    System.out.println();
}
``` 
### **5. Pyramid Patterns**

Pyramid Pattern Example - 1

```
     1                                           inputSize = 5
    2 2 
   3 3 3 
  4 4 4 4 
 5 5 5 5 5 

public static void printPattern(int inputSize){
int count = 1;
for(int i = inputSize; i > 0; i--){
    for(int j = 1; j <=i; j++){
        System.out.print(" ");
    }
    for(int j = 1; j <= count; j++){
        System.out.print(count+" ");
    }
    System.out.println();
    count++;
}
``` 

Pyramid Pattern Example - 2

```
     1                                       inputSize = 5
    1 2 
   1 2 3 
  1 2 3 4 
 1 2 3 4 5 

public static void printPattern(int inputSize){
int count = 1;
for(int i = inputSize; i > 0; i--){
    for(int j = 1; j <=i; j++){
        System.out.print(" ");
    }
    for(int j = 1; j <= count; j++){
        System.out.print(j+" ");
    }
    System.out.println();
    count++;
}
``` 
### 6. Decreasing Pattern with space

```
     *
    **
   ***
  ****
 *****
******
          
inputSize = 6

public static void printPattern(int inputSize){
    for(int i = 0; i < n; i++){
          int j=1;
          while(j < n-i){
              System.out.print(" ");
              j++;
          }
          for(int k = j; k <=n; k++){
              System.out.print("*");
          }
             System.out.println();
       }
}
``` 

*Thank you for reading and spending time here. Please like the article, it will encourage me to write more such articles. Do share your valuable suggestions, I appreciate your honest feedback!!
*