## Java data types (primitive)

# Java data Types 
data types specify the type of data  that can be store inside variable in Java 

Java is a statically-typed language. This means that all variables must be declared before they can be used.
```
int speed;
```
Here the variable is `speed` and the data type is `int`

The `int` data type determines that the variable speed can only contain integers 

There are 8 data types in Java programming language, known as primitive data types.

> **Note : ** there is also referenced data type (object type)

## **Primitive data Types**
### 1. Boolean type 
the boolean data type has just two possible value true or false nothing else 
They are usually used to handle *true/false* conditions 
> Exemple : Java boolean data type 

```
class Main {
  public static void main(String[] args) {
    	
    boolean flag = true;
    System.out.println(flag);    // prints true
  }
}
```
### 2. byte type 
1. The byte data type can store whole numbers from -128 to 127. 
2. This can be used instead of int or other integer types to save memory when you are certain that the value will be within -128 and 127
3. Default value: 0
>Example : Java byte data type 

```
class Main {
  public static void main(String[] args) {

    byte range;
    range = 124;
    System.out.println(range);    // prints 124
  }
}
```


### 3. short type 
1. The short data type can store whole numbers from -32768 to 32767 (16-bit signed two's complement integer).
2. If it's certain that the value of a variable will be within -32768 and 32767, then it is used instead of other integer data types (int, long).
3. Default value: 0
>Exemple : java short data type

```
class Main {
  public static void main(String[] args) {
    	
    short temperature;
    temperature = -200;
    System.out.println(temperature);  // prints -200
  }
}
```
### 4. int type 
1. The int data type can store whole numbers from -2147483648 to 2147483647. In general, the int data type is the preferred data type when we create variables with a numeric value.(32-bit signed two's complement integer).
2. If you are using Java 8 or later, you can use an unsigned 32-bit integer. This will have a minimum value of 0 and a maximum value of 232-1. To learn more, visit How to use the unsigned integer in java 8?
3. Default value: 0
>Exemple Java int data type 

```
class Main {
  public static void main(String[] args) {
    	
    int range = -4250000;
    System.out.println(range);  // print -4250000
  }
}
```
### 5. long type
1. The long data type can have values from -263 to 263-1 (64-bit signed two's complement integer).
2. If you are using Java 8 or later, you can use an unsigned 64-bit integer with a minimum value of 0 and a maximum value of 264-1.
3. Default value: 0
>Exemple Java long data type

```
class LongExample {
  public static void main(String[] args) {   	
    long range = -42332200000L;
    System.out.println(range);    // prints -42332200000
  }
}
```
Notice, the use of L at the end of -42332200000. This represents that it's an integral literal of the long type. You will learn about integral literals later in this article.

### 6. double type
1. The double data type is a double-precision 64-bit floating-point.
2. It should never be used for precise values such as currency.
3. Default value: 0.0 (0.0d)
>Example 6: Java double data type

```
class Main {
  public static void main(String[] args) {
    	
    double number = -42.3;
    System.out.println(number);  // prints -42.3
  }
}
```
### 7. float type
1. The float data type is a single-precision 32-bit floating-point.Learn more about single-precision and double-precision floating-point if you are interested.
2. It should never be used for precise values such as currency.
3. Default value: 0.0 (0.0f)
>Example Java float data type

```
class Main {
  public static void main(String[] args) {
    	
    float number = -42.3f;
    System.out.println(number);  // prints -42.3
  }
}
```
Notice that, we have used -42.3f instead of -42.3in the above program. It's because -42.3 is a double literal.

To tell the compiler to treat -42.3 as float rather than double, you need to use f or F.

If you want to know about single-precision and double-precision, visit Java single-precision and double-precision floating-point.
### 8. char type
1. It's a 16-bit Unicode character.
2. The minimum value of the char data type is '\u0000' (0) and the maximum value of the is '\uffff'.
3. Default value: '\u0000'

Example 8: Java char data type

```
class Main {
  public static void main(String[] args) {
    	
    char letter = '\u0051';
    System.out.println(letter);  // prints Q
  }
}
```
Here, the Unicode value of Q is \u0051. Hence, we get Q as the output.

> Here is another example:

```
class Main {
  public static void main(String[] args) {
    	
    char letter1 = '9';
    System.out.println(letter1);  // prints 9
    	
    char letter2 = 65;
    System.out.println(letter2);  // prints A

  }
}
```
Here, we have assigned 9 as a character (specified by single quotes) to the letter1 variable. However, the letter2 variable is assigned 65 as an integer number (no single quotes).

Hence, A is printed to the output. It is because Java treats characters as integral types and the ASCII value of A is 65. To learn more about ASCII, visit What is ASCII Code?.

If you are looking for String type i can tell you that Strings  are not a primitive types instead they are object from the Java.lang.String class

I hope that help ):

👨‍💻 By Mouad Oumous







