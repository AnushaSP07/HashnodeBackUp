# Java 8 - Interview Questions and Answers - 1

# Hey Reader,

If you are preparing for a Java interview, then this article would be most useful. Since, after the continuous upgradation of Java versions, the interview questions also increasing. 
Here, I have listed the most useful and commonly asked interview questions on Java 8.

## The contents of the article includes the Interview questions on the following topics with examples:

1.  Lambda Expression
2. Method reference
3. Functional Interface

### Lambda Expression

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665599563544/cGTWNz88s.png align="left")

**1. What is lambda expressions?**

Lambda expressions are code segments that behaves like a regular method. They are designed to accept a set of parameters as input and return a value as an output. Unlike methods, lambda expression does not mandatorily require a specific name.

**2.  Why we need lambda expression?**
 
- Lambda can be created without instantiating a class
- Lambda can be treated as an object
- It enables functional programming and decrease the number of lines of coding

Lambda expression syntax: 
```
(argument-list) -> {body}  
``` 

Java lambda expression is consisted of three components.

**Argument-list: ** It can be empty or non-empty as well.

**Arrow-token:** It is used to link arguments-list and body of expression.

**Body:** It contains expressions and statements for lambda expression.

```
No Parameter Syntax: 
() -> {  
//Body of no parameter lambda  
} 

One Parameter Syntax:
(p1) -> {  
//Body of single parameter lambda  
}

Two Parameter Syntax:
(p1,p2) -> {  
//Body of multiple parameter lambda  
}  

``` 

**3. How lambda expression and functional interfaces are related?**

Functional interface is an interface of java with one abstract method. In addition of creating an interface instance by declaring and instantiating a class, instance of functional interface can be crated with lambda expression.

**4. Will lambda expression create an object whenever it's executed?**

- No, only one instance will be created it creates singletons for all expressions that don't capture values. 
- On every evaluation, a new object need not be allocated. 
- Objects created by different lambda expressions do not have to be of the same class.
- Each object created by evaluation does not have to be of the same class. 
- It is not necessary to create a previous lambda evaluation if an existing instance is already present.

## Method references


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665601120301/yWCJvIv9r.png align="left")

**1. What is method reference?**

Method references are a special type of lambda expressions. They are used to create simple lambda expressions by referencing existing methods.

**2.  What are the types of method reference?**

There are 4 kinds of method reference.

- Static method reference
- Instance method of particular object.
- Instance methods of an arbitrary object of a particular type
- Constructor

**Reference of a static method:**

```
List<String> messages = Arrays.asList("hello", "baeldung", "readers!");
``` 
We can achieve this by leveraging a simple lambda expression calling the StringUtils.capitalize() method directly:

```
messages.forEach(word -> StringUtils.capitalize(word));
``` 

Or, we can use a method reference to simply refer to the capitalize static method:

```
messages.forEach(StringUtils::capitalize);
``` 

**Reference to an Instance Method of a Particular Object **

To demonstrate this type of method reference, let's consider two classes:


```
public class Bicycle {
    private String brand;
    private Integer frameSize;
    // standard constructor, getters and setters
}
public class BicycleComparator implements Comparator {
    @Override
    public int compare(Bicycle a, Bicycle b) {
        return a.getFrameSize().compareTo(b.getFrameSize());
    }
}

```

And, let's create a BicycleComparator object to compare bicycle frame sizes:

```
BicycleComparator bikeFrameSizeComparator = new BicycleComparator();
``` 
We could use a lambda expression to sort bicycles by frame size, but we'd need to specify two bikes for comparison:

```
createBicyclesList().stream()
  .sorted((a, b) -> bikeFrameSizeComparator.compare(a, b));
``` 
Instead, we can use a method reference to have the compiler handle parameter passing for us:

```
createBicyclesList().stream()
  .sorted(bikeFrameSizeComparator::compare);
``` 
The method reference is much cleaner and more readable, as our intention is clearly shown by the code.
 
**Reference to an Instance Method of an Arbitrary Object of a Particular Type**

This type of method reference is similar to the previous example, but without having to create a custom object to perform the comparison.
Let's create an Integer list that we want to sort:

List<Integer> numbers = Arrays.asList(5, 3, 50, 24, 40, 2, 9, 18);

If we use a classic lambda expression, both parameters need to be explicitly passed, while using a method reference is much more straightforward:


```
numbers.stream()
  .sorted((a, b) -> a.compareTo(b));
numbers.stream()
  .sorted(Integer::compareTo);
```
Even though it's still a one-liner, the method reference is much easier to read and understand.

**Reference to a Constructor **

We can reference a constructor in the same way that we referenced a static method in our first example. The only difference is that we'll use the new keyword.

Let's create a Bicycle array out of a String list with different brands:
```
List<String> bikeBrands = Arrays.asList("Giant", "Scott", "Trek", "GT");
``` 
First, we'll add a new constructor to our Bicycle class:
```
public Bicycle(String brand) {
    this.brand = brand;
    this.frameSize = 0;
}
``` 
Next, we'll use our new constructor from a method reference and make a Bicycle array from the original String list:
```
bikeBrands.stream()
  .map(Bicycle::new)
  .toArray(Bicycle[]::new);
``` 
Notice how we called both Bicycle and Array constructors using a method reference, giving our code a much more concise and clear appearance.

## Functional Interface

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665684474266/fYRBwWrSv.png align="left")

**1. What is Functional Interface?**

An Interface that contains only one abstract method is known as functional interface. It can have any number of default and static methods. It can also declare methods of object class.
It can have **any number of default and static methods**. It can also **declare methods of object class**.

Functional interfaces are also known as Single Abstract Method Interfaces (SAM Interfaces). A functional interface can extend another interface only when it does not have any abstract method.

**2. Which are the existing Functional Interfaces before Java 8?**
  1. Runnable
  2. ActionListener
  3. Comparable 

**3. Name and explain the Java 8 Predefined Functional Interface?**

There are 4 main functional interface which could be used in different scenarios.

**1. Consumer:** It represents an operation that accepts a single argument and returns no result

```
@FunctionalInterface
interface Consumer{
	void acceptData(String s);
}

public class FunctionalInter {

	public static void main(String[] args) {
		
		Consumer consumer = (userData) -> System.out.println(userData.toUpperCase());
		consumer.acceptData("userInput");
	}
	
}
``` 

**a. BiConsumer: **
It represents an operation that accepts two input arguments and returns no result. It is a subtype of Consumer.


```
@FunctionalInterface
interface BiConsumer<String1, String2>{
	void acceptData(String1 s1, String2 s2);
}

public class FunctionalInter {

	public static void main(String[] args) {
		
		BiConsumer<String, String> biConsumer = (input1, input2) -> {
			System.out.println("input1 "+ input1 + "input2" +input2);
		};
	}
	
}
``` 

**2. Predicate**

Predicate will accept one argument, do some processing, and then return boolean

```
@FunctionalInterface
interface Predicate<Integer>{
	boolean test(Integer num);
}

public class FunctionalInter {

	public static void main(String[] args) {
		
		Predicate<Integer> num = (input) -> {return input % 2 == 0;};
		System.out.println("Result of num "+ num.test(4));
	}
	
}
``` 
**a. BiPredicate**
Instead of one argument, BiPredicate will accept two arguments and return boolean. And BiPredicate is a subtype of Predicate.

**3.  Function**

This interface accepts one argument and returns a value after the required processing. It is defined as below. The required processing logic will be executed on the invocation of the apply method.
```
@FunctionalInterface
interface Function<String1, String2>{
	String apply(String1 data);
}

public class FunctionalInter {

	public static void main(String[] args) {
		
		Function<String, String> upperCase = (name) -> name.toUpperCase();
		System.out.println("Result is "+ upperCase.apply("inputValue"));
	}
}
``` 
**a. BiFunction :**
The BiFunction is similar to Function except it accepts two inputs, whereas Function accepts one argument.

**b. UnaryOperator and BinaryOperator**

UnaryOperator and BinaryOperator,which extends the Function and BiFunction respectively. 

```
@FunctionalInterface
interface UnaryOperator<String> extends Function<String, String>{
}

@FunctionalInterface
interface BinaryOperator<String> extends BiFunction<String, String,String>{
}
public class FunctionalInter {

	public static void main(String[] args) {
		
		UnaryOperator<String> unaryOperator = (s) -> s.concat("concatData");
		System.out.println(unaryOperator.apply("inputData"));
	}
}
``` 
From the above interfaces, it is easy to understand that the UnaryOperator accepts a single argument and return a single argument, but both the input and output argument should be of same or similar type.

On the other hand, BinaryOperator accepts two arguments and returns one argument similar to BiFunction, but the type of all the input and output argument should be of similar type.

**4. Supplier**
Supplier functional interface does not accept any input; rather returns a single output. The following interface code is given for understanding.
```
@FunctionalInterface
interface Supplier<String> {
	
	String get();
}
public class FunctionalInter {

	public static void main(String[] args) {
		
		Supplier<String> helloWorld = () -> {
			return "Hello World";
		};
		
		String greet = helloWorld.get();
		System.out.println("The msg is "+greet);
	}
}
``` 

*Thank you for reading and spending time here. Please like the article, it will encourage me to write more such articles. Do share your valuable suggestions, I appreciate your honest feedback!!*