## Java Hello world


A "Hello World" is a simple program that print the 《Hello World》 text on the screen 
lets see how the Java "Hello world" program work

 >### Java Hello World Program 

```
// Your First Program

class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!"); 
    }
}
```
>### Output

```
Hello, World!
```
## **How Java "Hello World !" Program work** (Explain all the parts of its code )

### 1. `// Your First Program` 
In Java this is called comment any line started with `//` is a comment its completely ignored from Java compiler , that's why you can find it in any Java program because alot of programmers use it to explain the intent and functionality of the program to make their program easy to understand by users reading
### 2. `class HelloWorld {....}` 
In Java every application Begain with a class definition because you can't write a code without a class *( every code in Java must be inside a class exept the declaration of packages )*
In our program `HelloWorld` is the name of the class and the class definition is : 
```
class HelloWorld {
 // code goes here 
}
```
For now just keep in mind that every Java application has a class definition and the name of the class must match the filename in Java 
### 3. `public static void main(String[] args) {....}`
This is the main methode the most populair method in Java , the java compiler starts executing the code from the main method that's why  every Java program must have thus method
 For now just remember that the main method is the raison why Java application work if your application don't have the main method don't expect the output or the result in general condition.

[more about main method]( https://blog.mouadoumous.online/the-main-method-in-java )
The signature of the main method in Java is : 
```
public static void main(String[] args) {
       // code goes here 
}
```
### 4. `System.out.println("Hello, World!");`
This code is print statement its print the text "Hello World" to the console (your screen) the text inside the quotation marks is called *String* in Java 

The fist thing you have to notice is that the print statement is inside in main function which is inside the class definition 

>I hope that help you to  understand every part of Hello World code 
Now we going to see the thing you must take away 

## **Thing to take away**
1. A valid Java application must have a class definition (that match the filename)
 
2. Every valid Java application contain the main method ( one main method ) 

3. The main method must be inside the class definition 
In general condition every method in Java must be inside a class definition 

4. Dont forget call your code inside the main method to guarantee that the compiler execute your code so your program does exactly what you want 

>This is a valid Java program that does nothing.

```
public class HelloWorld {
    public static void main(String[] args) {
        // Write your code here
    }
}
```
I hope you understand all of that if you like my article please follow me to recieve more article about Java programming language 

> 🙋‍♂️ so long ! Have a good day 






