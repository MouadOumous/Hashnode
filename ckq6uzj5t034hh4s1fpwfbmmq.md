## System.err in Java | Mouad Oumous

Unix and C programmers are familiar with `stderr`, which is commonly used for error 
messages. `stderr` is a separate file pointer from stdout, but often means the same thing. 
Generally, stderr and stdout both send data to the console, whatever that is. However, 
stdout and `stderr` can be redirected to different places. For instance, output can be 
redirected to a file while error messages still appear on the console. 
`System.err` is Java's version of stderr. Like `System.out`, `System.err` is an instance of 
`java.io.PrintStream` , a subclass of `java.io.OutputStream` . System.err is most commonly used inside the catch clause of a try/catch block like this: 
```
try { 
 // Do something that may throw an exception. 
} 
catch (Exception e) { 
 System.err.println(e); 
} 
```
Finished programs shouldn't have much need for `System.err`, but it is useful while you're debugging. 

**See more**
> [System.out]( https://blog.mouadoumous.online/systemout-in-java )