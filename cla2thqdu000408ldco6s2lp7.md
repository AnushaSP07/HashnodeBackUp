# Recursion In Programming !!!

# Hey Aspirant!!!!

In this blog let us understand and make our hand dirty by writing programs using Recursion.

**The Contents of the article includes:**
1. What is Recursion?
2. Base Condition in Recursion
3. Why Recursion?
4. Programs using Recursion.

## What is Recursion?

A recursion is a function which calls itself inside its own function. This technique of calling function itself provides a way to break complicated problems down into simple problems which are easier to solve.

- **Recursion calls **are stored in STACK fashion i.e. new function call on the TOP [LIFO - Last In First Out] this approach is called Recursion Stack. 
- Recursion Stack is stored in Heap Memory. 
- All the other Data structures like Arrays, Stack, Queue, Map, Set will occupy memory during **Compilation**. 
- Only Recursion will occupy space during **Execution**. Because compiler will never tell the logic is correct or not, it will only check the syntax errors. 

```
public int fact(int n){
	if(n == 1 || n == 0){
		return 1;
	}
	return n * fact(n-1);
}
``` 
This function will now get to know, I'm calling myself inside my own function that is why I'm Recursion.

**Sequence of the above function will stored in stack as:**

fact(1) --> fact(2) --> fact(3) --> fact(4) -->fact(5)   which is called **STACK order** which is stored in** HEAP**.

- While the function is not finished it will remain in STACK
- When the function finish execution, it is removed from stack and the flow of program is restored to where the function is called.

Understanding of recursion might take time but the easiest way to understand it better is by experimenting how it works.

**Recursion Syntax:**

```
void methodName()
{
//code to be executed  
	methodName()
	{ 
	//calling same method  
	}
}
``` 

## Base Condition in Recursion

- A condition where our recursion will stop making new calls.
- If there is no base condition, function call will keep happening Stack will be filled and leads to StackOverFlow Error

 
## Why Recursion?
-  Recursion helps in solving bigger or complex problems in a simple way.
- We can convert the Recursion solution into iteration and vice versa.
- In Recursion Space Complexity is not constant because of Recursive calls.
- Recursion helps in breaking down bigger problems into smaller problems.

**a. Can All Recursive code can be solved by Iteration?**
- Yes

**b. Can All Iterative code can be solved by Recursion?**
- Yes

## How to understand and approach a problem as Recursion problem?
- Identify if you can break down a problem with smaller problems.
- Write the recurrence relation if needed, the formula which we can identify using recursion is known as **Recurrence Relation.**
- Base conditions will already be provided with the questions

## Example Programs using Recursion

**Program 1:  Find nth Fibonacci number**

```
static int fibo(int n){
		if(n < 2){
			return n;
		}
		return fibo(n - 1) + fibo(n - 2);
}

Input: num = 6
Output : 8
``` 
**Program 2:  Print linearly number from N**

```
static int printLinearFromN(int num){
		if(num == 0){
			return num;
		}
		System.out.println(num);
		return printLinearFromN(num - 1);
	}

Input: num = 6
Output : 6 5 4 3 2 1
``` 
**Program 3:  Print linearly number from 1 to N**

```
static void printLinearly(int num){
		if(num == 0){
			return;
		}
		printLinearly(num - 1);
		System.out.println(num);
	}

Input: num = 6
Output : 1 2 3 4 5 6
``` 
**Program 4:  Factorial of a number**

```
static int fact(int n){
		if(n <= 1){
			return 1;
		}
		return n * fact(n - 1);
	}

Input : 5
Output : 5 * 4 * 3* 2 * 1 = 120
``` 
**Program 5:  Sum of a given Digit or an Integer**
```
static int sumOfInteger(int n){
		if(n % 10 == 0){
			return 0;
		}
		return (n % 10) + sumOfInteger(n / 10);
	}

Input: 123
Output :  1 + 2 + 3 = 6
``` 
**Program 6:  Infinite Recursion**

```
static void infiniteRecursion(int n){
		if(n == 0){
			return;
		}
		System.out.println(n);
		infiniteRecursion(n--);   // Infinite error 
        infiniteRecursion(--n);  // for Input 5 , output - 5 4 3 2 1
	}

``` 
**Program 7:  Reverse a Number**

```
static int sum = 0;
	static void reverseNumber(int n){
		
		if(n == 0){
			return;
		}
		int remainder = n % 10;
		sum = sum * 10 + remainder;
		reverseNumber(n / 10);
	}

input : 5674
output : 4765
``` 
**Program 8:  count zero's in a number**

```
static int countZero(int n, int count) {
		if(n == 0) {
			return count;
		}
		int remainder = n % 10;
		if(remainder == 0) {
			return countZero(n/10, count + 1);
		}
		return countZero(n/10, count);
	}

input : 200800, 0
output : 4
``` 
**Program 9:  count the number of steps LeetCode:1342**

```
static int numberOfSteps(int num, int steps) {
		if(num == 0) {
			return steps;
		}
		if(num % 2 == 0) {
			return numberOfSteps(num/2, steps+1);
		}
		return numberOfSteps(num-1, steps+1);
	}

input : 14
output : 6
``` 
**Program 10:  Print Triangle of * using Recursion**

```
static void triangle(int row, int column) {
		if(row == 0) {
			return;
		}
		if(column < row) {
			System.out.print("*");
			triangle(row, column+1);
		}else {
			System.out.println();
			triangle(row-1, 0);
		}
	}

input : 5
output : 
*****
****
***
**
*
``` 
**Program 11:  Bubble sort using Recursion**

```
static void bubbleSort(int[] arr, int row, int column) {
		if(row == 0) {
			return;
		}
		if(column < row) {
			if(arr[column] > arr[column + 1]) {
				// swap
				int temp = arr[column];
				arr[column] = arr[column + 1];
				arr[column + 1] = temp;
			}
			bubbleSort(arr, row, column + 1);
		}else {
			bubbleSort(arr, row - 1, 0);
		}
	}

input: 
int[] arr = {4, 3 , 5, 2, 1}; bubbleSort(arr, arr.length - 1, 0);
output: [1, 2, 3, 4, 5]
``` 
**Program 12:  String is palindrome or not using recursion**

```
static boolean isPalindrome(String s, int i) {
		if(i > s.length()/2) {
			return true;
		}
		return s.charAt(i) == s.charAt(s.length() - i -1) &&
               isPalindrome(s, i+1);
	}

input : madam, 0
output : true
``` 
**Program 13:  Reverse String using recursion**

```
static String recursiveMethod(String str){
	     if ((null == str) || (str.length() <= 1)){
	            return str;
	     }
	     return recursiveMethod(str.substring(1)) + str.charAt(0);
	}

input : MyJava
output : avaJyM
``` 

*Thank you for reading and spending time here. Please like the article, it will encourage me to write more such articles. Do share your valuable suggestions, I appreciate your honest feedback!!!*