# Java-Kotlin-Android-Interview-Questions


Java Kotlin Android Interview Questions
Masai docs
Android interview questions
Mindorks
GitHub - MindorksOpenSource
External mcq
29 Advanced Android Interview Questions


Q1. What is the Result of the code below?
public class Parent {
public Parent() {
System.out.println(“Parent constructor called”);
}
}
public class Child extends Parent {
public Child(){
System.out.println(“Child Constructor called”);
}
}
public classTestDrive {
   public static void main(String[] args){
           Child child = new Child();
             }
}
o/p : If you create an object of child class then the parent class constructor gets called first.
Parent constructor called
Child Constructor called

Q2. What is this keyword?
The this keyword refers to the current object in a method or constructor.
Ex.
public class Main {
int x;
// Constructor with a parameter
public Main(int x) {
this.x = x;
}
// Call the constructor
public static void main(String[] args)  {
Main myObj = new Main(5);
System.out.println("Value of x = " + myObj.x);
}
}
Output : Value of x = 5
The most common use of this keyword is to eliminate the confusion between class attributes and parameters with the same name (because a class attribute is shadowed by a method or constructor parameter).
If you omit the keyword in the example above, the output would be "0" instead of "5".
this can also be used to:
Invoke current class constructor
Invoke current class method
Return the current class object
Pass an argument in the method call
Pass an argument in the constructor call

Q3. What is super()?
The super keyword in Java is a reference variable.
 super is used to refer to an immediate parent class object.
Whenever you create the instance of a subclass, an instance of the parent class is created implicitly which is referred to by a super reference variable.
Usage of Java super Keyword.
Super Keyword in Java - Javatpoint
super can be used to refer to an immediate parent class instance variable.
super can be used to invoke the immediate parent class method.
super() can be used to invoke immediate parent class constructor.
Ex.
class Animal{
String color="white";
}
class Dog extends Animal{
String color="black";
void printColor(){
System.out.println(color); //prints color of Dog class  //black
System.out.println(super.color); //prints color of Animal class  //white
}  
}
class TestSuper1{  
public static void main(String args[]){
Dog d=new Dog();
d.printColor();
}}
Output:
Black
white
 
Q4. Java operator overloading.
Java + operator and Operator overloading - Top Java Tutorial

Q5. What is the difference between Array and Arraylist?
Array:
Arrays are static in nature.  (Static means size of array are fixed)
The array is a part of and is present in java. util package.
Array elements are always stored in sequential memory locations. (Not parallel or random)
Array: a collection of a fixed number of components (elements), wherein all of the components have the same data type.
Arrays are further divided into One-dimensional arrays - arrays in which components are arranged in list form. Multi-dimensional array - array in which components are arranged in tabular form.
To know the total number of elements present in an array we use - > array.length instead of array.size().
Ex.
public class A {
   public static void main(String[] args) {
       int[] arr = new int[5];
       for (int i = 0; i < arr.length; i++) {
           System.out.println(i);
       }
   }
}
/*
0
1
2
3
4
Process finished with exit code 0
*/

Arraylist :
Arraylists are the extension of Arrays.
Arraylists are dynamic in nature. (Dynamic means size of array are not fixed)
ArrayList is a part of the collection framework.
Arraylist is present in the java.util package so we need to import it while writing the program.
Small,  “int” is the class version of “Integer”.
Primitive data type “int” doesn’t have class but “Integer” has class.
To know the total number of elements present in an array we use - > array.size()  instead of array.length.
Ex.
import java.util.ArrayList;
public class A {
   public static void main(String[] args) {
       ArrayList<Integer> arrayList = new ArrayList<>();
       arrayList.add(12);
       arrayList.add(20);
      // arrayList.remove(1);
       for (int i = 0; i < arrayList.size(); i++) {
           System.out.println(arrayList.get(i) + " ");
       }
   }
}
/*
12
20
Process finished with exit code 0
*/
Q6. What is abstraction in java?
A class which is declared with the abstract keyword is known as an abstract class in Java.
Abstract classes can have abstract and non-abstract methods.
Abstraction is a process of hiding the implementation details and showing only functionality to the user.
Ex, Sending SMS where you type the text and send the message. You don't know the internal processing about the message delivery.
Abstract keyword is non-access modifiers, used for classes and methods.
Abstraction can be achieved by abstract classes or interfaces.
Abstract method can be used only in abstract class and it does not have a body.
It is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).
It can have constructors and static methods also.
It can have final methods which will force the subclass not to change the body of the method.
There are two ways to achieve abstraction in java
Abstract class
Interface
Ex.
//class 1
abstract public class Abstraction {
   public abstract void animalSound(); //abstract method  //cannot have method body
   public void sleep() { //non abstract method or normal method
       System.out.println("The Dog is sleeping : zzz");
   }
}
//class 2
class Dog extends Abstraction {
   @Override
   public void animalSound() {
       System.out.println("The Dog says : Bow-Bow");
   }
}
//class 3
class MyClass {
   public static void main(String[] args) {
       Dog obj = new Dog();
       obj.animalSound();
       obj.sleep(); 
   }
}
/*
The Dog says : Bow-Bow
The Dog is sleeping : zzz
Process finished with exit code 0
*/

Q7. What is Interface in Java?
Another way of achieving abstraction in Java is through Interface.
An interface in Java is a blueprint of a class. It has static constants and abstract methods.
The interface in Java is a mechanism to achieve abstraction.
There can be only abstract methods in the Java interface, not method body.
 It is used to achieve abstraction and multiple inheritance in Java.
Interfaces can have abstract methods and variables. It cannot have a method body.
Java Interface also represents the IS-A relationship.
It cannot be instantiated just like the abstract class.
Ex.
public class InterfaceExample {

}
interface Birds {
   void fly();
   void cry();
}
class Animal1 {
   protected void sound() {
   }
}
class Eagle extends Animal1 implements Birds {
   @Override
   public void fly() {
       System.out.println("Eagle can fly");
   }
   @Override
   public void cry() {
       System.out.println("Eagle can cry");
   }
   @Override
   protected void sound() {
       System.out.println("Buck-Buck");
   }
}
class AnimalTestDriver {
   public static void main(String[] args) {
       Eagle eagle = new Eagle();
       eagle.fly(); //Eagle can fly
       eagle.cry(); //Eagle can cry
       eagle.sound(); //Buck-Buck
   }
}
/*
Eagle can fly
Eagle can cry
Buck-Buck
Process finished with exit code 0
*/

Q8. Why we cannot create the object of abstract class.
Because an abstract class is an incomplete class (incomplete in the sense it contains abstract methods without body)  so that  we cannot create an instance or object.
 
Q9. Why cannot we create the object of Interface?
Interface is basically a complete abstract class. That means Interfaces only have a declaration of method not their implementation. So if we don’t have any implementation of a method then that means if we create an object of that interface and call that method it compiles nothing as there is no code to compile.
To overcome this, firstly we have to create a class that implements that interface means that class is implementing the methods of that interface. Now when you create an object of this class it gives u the permission to access all methods of interface with their implementation in the class.
 
Q10. Difference between Abstract Class and Interface
An abstract class cannot support multiple inheritance.
but an interface can support multiple inheritance. Thus a class may inherit several interfaces but only one abstract class.
An abstract class can have a data member, abstract method, method body (non-abstract method), constructor.
An interface is like a "purely" abstract class. Interface methods are by definition public and abstract, so you cannot have non-abstract methods in your interface.
Abstract classes can have access modifiers such as, protected, internal, public, etc.
But for Interface, all methods of an interface must be defined as public.
If we add a new method to an abstract class then it is not mandatory to override that method.
If we add a new method to an Interface then we have to implement all methods of the interface.

Q11. What is Exception Handling and Types of errors?
Suppose you are creating an android game while coding you get errors which leads to crash the application so to avoid this crash we need to handle the program is called exception handling.
Types Of Errors :
A] Runtime Error:
The errors are passed by compile-time and these errors are identified at runtime execution of the program, such errors are known as Runtime errors.
Runtime Means?
When a source code is compiled and converted to byte code for ex. If the source.java file is compiled to the source. the class file then further this class file is converted to machine code via JVM meanwhile JVM will identify this is wrong, this is not possible, or not possible to find the main method all this process happens at runtime so it is called Runtime.
Ex.

Q12. What are the access modifiers you know? What does each one do?
There are four access modifiers in Java language (from strictest to the most lenient): PPPD and in Kotlin PPPI -> Internal
private variables, methods, constructors or inner classes are only visible to its' containing class and its' methods.
This modifier is most commonly used, for example, to allow variable access only through getters and setters or to hide underlying implementation of classes that should not be used by the user and therefore maintain encapsulation.
Singleton constructor is also marked private to avoid unwanted instantiation from outside.
2] Default (no keyword is used) this modifier can be applied to classes, variables, constructors and methods and allows access from classes and methods inside the same package.
3] protected can be used on variables, methods and constructors, therefore, allowing access only to subclasses and classes that are inside the same package as protected members' class.
4] public modifier is widely-used on classes, variables, constructors and methods to grant access from any class and method anywhere.
It should not be used everywhere as it implies that data marked with the public is not sensitive and can not be used to harm the program.

Q13. What is String pool in java?
A string constant pool is a separate place in the heap memory where the values of all the strings which are defined in the program are stored.
It is also known as String Intern Pool or String Constant Pool.
String Pool in Java - Javatpoint

Q14. The difference between == and === ?
== converts the variable values to the same type before performing the comparison. This is called type coercion.
=== does not do any type conversion (coercion) and returns true only if both values and types are identical for the two variables being compared.
 
Q15. What is the difference between StringBuffer() and StringBuilder() ?


No.
StringBuffer
StringBuilder
1)
StringBuffer is synchronized i.e. thread-safe.
It means two threads can't call the methods of StringBuffer simultaneously.
StringBuilder is non-synchronized i.e. not thread-safe. 
It means two threads can call the methods of StringBuilder simultaneously.
2)
StringBuffer is less efficient than StringBuilder.
StringBuilder is more efficient than StringBuffer.
3)
StringBuffer was introduced in Java 1.0
StringBuilder was introduced in Java 1.5


Difference between StringBuffer and StringBuilder

Q16. What is Deadlock in Java?
Deadlock describes a situation where two or more threads are blocked forever, waiting for each other
Deadlock in Java is a part of multithreading. 
Deadlock can occur in a situation when a thread is waiting for an object lock that is acquired by another thread and a second thread is waiting for an object lock that is acquired by the first thread. Since, both threads are waiting for each other to release the lock, the condition is called deadlock.

Q17. What is throw? Or throwable in java?
The Throwable class is the superclass of all errors and exceptions in the Java language. Only objects that are instances of this class (or one of its subclasses) are thrown by the Java Virtual Machine or can be thrown by the Java throw statement.
 
Q18. Java static keyword? Static method?
The static keyword in Java is used for memory management mainly. The static keyword belongs to the class rather than an instance of the class.
The static can be:
Variable (also known as a class variable)
Method (also known as a class method)
Block
Nested class
3.  Ex.
public class DemonstrateStatic {
   public static void CreatingStatic() {   // static method
       System.out.println("This is static method no obj created");
   }
   public void nonStaticMethod() {  // non-static method
       System.out.println("This is non-static method, obj created");
   }
   public static void main(String[] args) {
       //need to create object for non-static method
       DemonstrateStatic obj = new DemonstrateStatic();
       obj.nonStaticMethod();
       // calling CreatingStatic without creating obj of DemonstrateStatic class
       CreatingStatic();
   }
}
/*
This is non-static method, obj created
This is static method no obj created
Process finished with exit code 0
*/
Q19. What is garbage collection in java?
In java, garbage means unreferenced objects.
Garbage Collection is the process of reclaiming the runtime unused memory automatically. In other words, it is a way to destroy unused objects.
https://www.javatpoint.com/Garbage-Collection
Ex.
public class JavaGC {
   public void finalize() {
       System.out.println("object is garbage collected");
   }
   public static void main(String[] args) {
       JavaGC obj = new JavaGC();
       JavaGC obj1 = new JavaGC();
       obj = null;
       obj1 = null;
       System.gc();
   }
}
/*
object is garbage collected
object is garbage collected
Process finished with exit code 0
*/
Ex. By creating anonymous object
public class JavaGC {
   public void finalize() {
       System.out.println("object is garbage collected");
   }
   public static void main(String[] args) {
       new JavaGC(); //creating anonymous obj
       System.gc();
   }
}
/*
object is garbage collected
Process finished with exit code 0
*/
Q20. What is the difference between final, finally, finalize?
Difference between final, finally and finalize - javatpoint
 



Key
final
finally
finalize
1.
Definition
final is the keyword and access modifier which is used to apply restrictions on a class, method or variable.
finally is the block in Java Exception Handling to execute the important code whether the exception occurs or not.
finalize is the method in Java which is used to perform clean up processing just before an object is garbage collected.
2.
Applicable to
Final keyword is used with the classes, methods and variables.
Finally, block is always related to the try and catch block in exception handling.
finalize() method is used with the objects.
3.
Functionality
(1) Once declared, the final variable becomes constant and cannot be modified.
(2) final method cannot be overridden by subclass.
(3) final class cannot be inherited.
(1) finally block runs the important code even if an exception occurs or not.
(2) finally block cleans up all the resources used in try block
finalize method performs the cleaning activities with respect to the object before its destruction.
4.
Execution
Final method is executed only when we call it.
Finally the block is executed as soon as the try-catch block is executed.
Its execution is not dependent on the exception.
The finalize method is executed just before the object is destroyed.



Q21. do it is mandatory that to use finally block in try block
Only try block is mandatory while catch and finally blocks are optional.
finally block :- An optional finally block gives us a chance to run the code which we want to execute every time a try-catch block is completed – either with errors or without any error.
The finally block statements are guaranteed of execution even if we fail to handle the exception successfully in the catch block.
Java try catch finally Blocks - HowToDoInJava.
 
Q21. Types of references?
Types of References in Java - GeeksforGeeks

Q22. If class is static then can we create an instance of static class?
Yes
Static class is a nested class itself. We cannot declare the top level class or outer class or parent class as a static class but we can declare the inner class as a static class and access all static methods without creating an object of the inner class.
Ex. 
public class StaticMethod {
   public static class Abc {
       public static void HotBomb() { //static method
           System.out.println("HotBomb Called");
       }
       public void CoolBomb() { //non static method
           System.out.println("Cool Bomb Called");
       }
       public static void main(String[] args) {
           HotBomb(); //without creating obj of Abc we can access static method
           Abc obj = new Abc();
           obj.CoolBomb(); //with creating obj of Abc we can access non static method
       }
   }
}
/*
HotBomb Called
Cool Bomb Called
Process finished with exit code 0
*/
Q23. What is synchronization?
Synchronization in Java - What? Why? Everything you need to know

Q24. What is a double colon (::) operator or scope resolution operator or method reference operator?
https://www.geeksforgeeks.org/double-colon-operator-in-java/

Q25. What is the return type of constructions?
Constructors do not have any return type, not even void. ... Explanation: A constructor is a method that initializes an object immediately upon creation. It has the same name as that of the class in which it resides.

Q26. 







KOTLIN

Q1. What are visibility modifiers in Kotlin?
A visibility modifier or access specifier or access modifier is a concept that is used to define the scope of something in a programming language. In Kotlin, we have four visibility modifiers:
private: visible inside that particular class or file containing the declaration.
protected: visible inside that particular class or file and also in the subclass of that particular class where it is declared.
internal: visible everywhere in that particular module.
public: visible to everyone.
Note: By default, the visibility modifier in Kotlin is public.
Learn more about visibility modifiers in Kotlin from MindOrks blog.

Q2. JvmStatic, JvmOverloads, and JvmField in Kotlin
JvmStatic, JvmOverloads, and JvmField in Kotlin

Q3. What are Coroutines ? What is the difference between a Thread and Coroutines ?
Coroutines come into the picture when big tasks like downloading, uploading of files, these kind of huge tasks if we perform them  on the Main thread then application freezes and ANR msg appears to avoid it we launch Coroutines.

Q4. Difference between a Thread and Coroutines?
Threads :
Threads can run in parallel, threads can wait for each other and communicate with each other.
Threads are basically units of execution. Threads are directly attached to a process called zygote process in android.
Threads are expensive. Creating and stopping them is expensive. 
Threads are managed by the OS. Thread scheduler adds extra overhead to schedule the threads.
There are 4 types of threads : 1. IO 2. Main 3. Default 4. Unconfined
Coroutines :
Coroutines are light-weight threads, actually, they are not threads but we launch coroutines on threads.
Coroutines are not bound to any particular thread.
Coroutines are not managed by the operating system, but by the Kotlin Runtime.
Like Threads only coroutines can run in parallel, coroutines can wait for each other and communicate with each other.
Coroutines are very very cheap - almost free. 
Functions which run parallel.
Coroutines are asynchronous by default.
It can be canceled once it starts.
It also can be suspended, which means it can pause or resume at any point in time.

Q5. Why are the Coroutines very cheap?
In general, Kotlin Coroutines are presented as a lightweight alternative to Java Threads. You would probably ask why creating them is much cheaper than creating threads. 
The answer is very simple – because they are not using such threads as normal threads 😉 Of course, it’s a joke, but the first important thing you should know about coroutines is that they are using thread pools in the background. So, it’s not a “magical” technology, that is better than threads, but just a different concept of concurrency used in your applications.

Q6. How does Kotlin work on Android?
Just like Java, the Kotlin code is also compiled into the Java bytecode and is executed at runtime by the Java Virtual Machine i.e. JVM. When a Kotlin file named Main.kt is compiled then it will eventually turn into a class and then the bytecode of the class will be generated. The name of the bytecode file will be MainKt.class and this file will be executed by the JVM.
 
Q7. Why should we use Kotlin?
Kotlin is concise
Kotlin is null-safe
Kotlin is interoperable
Learn about these features from MindOrks video.
 
Q8. What is the difference between the variable declaration with var and val?
If you want to declare some mutable(changeable) variable, then you can use var. For the immutable variable, use val i.e. val variables can't be changed once assigned.
 
Q9. What is the difference between the variable declaration with var and val?
Both the variables that are declared with val and const are immutable in nature. But the value of the const variable must be known at the compile-time whereas the value of the val variable can be assigned at runtime also.
Learn more about the difference between const and val from MindOrks blog.

 Var : If you want to declare some mutable(changeable) variable, then you can use var. 
Ex. var firstVariable : Int = 3
fun main() {
   var name: String = "Lloyd"
  // println(name)  //Lloyd
   name = "Avadhut"
   print(name)
}
/*
Avadhut
*/
Val : For the immutable variable, use val i.e. val variables can't be changed once assigned.
Ex. var secondVariable : Int =5
fun main() {
   val name: String = "Lloyd"
  // println(name)  //Lloyd
   name = "Avadhut" //its show error
   print(name)
}
fun main() {
   val name: String = "Lloyd"
   print(name)
}
//Lloyd

Q10. How do you ensure null safety ?. in kotlin.
In java, if we assign a null value to a variable then it shows NULL POINTER EXCEPTION ie. NPE
But in kotlin if we assign value to a variable then it shows COMPILE TIME ERROR
Ex.  
fun main() {
   var name: String = "MindOrks"
   name = null //error
}
So to assign null values to a variable you need to declare variable “name” as a nullable string and during accessing the variable you need to use the safe call operator “?.”
Ex.
fun main() {
   var name: String? = "MindOrks"
   println(name) // MindOrks
   //assigning the variable 1
   name = null
   println(name?.length) //null
   //assigning the variable 2
   name = "Avadhut J"
   print(name.length)
//we have replaced it with dot bcoz Unnecessary safe call on a non-null receiver of type String?
}
/*
MindOrks
null
9
Process finished with exit code 0
*/
Learn more about safe calls(?.) and null check(!!) from MindOrks blog.
 
Q11. What is the difference between safe calls(?.) and null check(!!)?
Safe call operator i.e. ?. is used to check if the value of the variable is null or not. If it is null then null will be returned otherwise it will return the desired value.
Ex.
var name: String? = "MindOrks"
println(name?.length) // 8
name = null
println(name?.length) // null
If you want to throw a NullPointerException when the value of the variable is null, then you can use the null check or !! operator.
var name: String? = "MindOrks"
println(name?.length) // 8
name = null
println(name!!.length) // KotlinNullPointerException
Learn more about safe calls(?.) and null check(!!) from MindOrks blog.
 
Q12. Do we have a ternary operator in Kotlin just like java?
No, we don't have a ternary operator in Kotlin but you can use the functionality of ternary operator by using if-else or Elvis operator.
 
Q13. What is the Elvis operator in Kotlin?
In Kotlin, you can assign null values to a variable by using the null safety property. To check if a value is having null value then you can use if-else or can use the Elvis operator i.e. ?: 
For example:
var name:String? = "Mindorks"
val nameLength = name?.length ?: -1
println(nameLength)
The Elvis operator(?:) used above will return the length of the name if the value is not null otherwise if the value is null, then it will return -1.
					or
Elvis operator (?:) is used to return the not null value even if the conditional expression is null. It is also used to check the null safety of values.
Kotlin Elvis Operator - javatpoint
 
Q14. How to convert a Kotlin source file to a Java source file?
Steps to convert your Kotlin source file to Java source file:
Open your Kotlin project in the IntelliJ IDEA / Android Studio.
Then navigate to Tools > Kotlin > Show Kotlin Bytecode.
Now click on the Decompile button to get your Java code from the bytecode.
Learn more about the conversion steps from MindOrks blog.

Q15. What is the use of @JvmStatic, @JvmOverloads, and @JvmFiled in Kotlin?
@JvmStatic: This annotation is used to tell the compiler that the method is a static method and can be used in Java code.
@JvmOverloads: To use the default values passed as an argument in Kotlin code from the Java code, we need to use the @JvmOverloads annotation.
@JvmField: To access the fields of a Kotlin class from Java code without using any getters and setters, we need to use the @JvmField in the Kotlin code.
Learn more about @JvmStatic, @JvmOverloads, and @JvmField in Kotlin from MindOrks blog.
 
Q16. What is a data class in Kotlin?
Data class is a simple class that is used to hold data/state and contains standard functionality. 
A data keyword is used to declare a class as a data class.
In Kotlin,
data class Developer  (val name:   String,   val age:  Int)
When we mark a class as a data class, you don’t have to implement or create the following functions as we do in Java.
hashCode()
equals()
toString()
copy()
The compiler automatically creates these internally, so it also leads to clean code. Although, there are few requirements that data classes need to fulfill:
The primary constructor needs to have at least one parameter.
All primary constructor parameters need to be marked as val or var
Data classes cannot be abstract, open, sealed, or inner.
Learn Kotlin - Data Class.
 
Q17. Can we use primitive types such as int, double, float in Kotlin?
In Kotlin, we can't use primitive types directly. We can use classes like Int, Double, etc. as an object wrapper for primitives. 
But the compiled bytecode has these primitive types.
 
Q18. What is String Interpolation in Kotlin?
If you want to use some variable or perform some operation inside a string then String Interpolation can be used. 
You can use the $ sign to use some variable in the string or can perform some operation in between {} sign.
Ex.
var name = "MindOrks"
print("Hello! I am learning from $name")
 
Q19. What do you mean by destructuring in Kotlin?
Destructuring is a convenient way of extracting multiple values from data stored in(possibly nested) objects and Arrays. It can be used in locations that receive data (such as the left-hand side of an assignment). Sometimes it is convenient to destructure an object into a number of variables,
Ex.
val (name, age) = developer
Now, we can use name and age independently like below:
println(	name)
println(age)
Learn more about Kotlin Destructuring from MindOrks blog.
 
Q20. When to use the lateinit keyword in Kotlin?
lateinit is late initialization.
Normally, properties declared as having a non-null type must be initialized in the constructor. However, fairly often this is not convenient.
For example, properties can be initialized through dependency injection, or in the setup method of a unit test. In this case, you cannot supply a non-null initializer in the constructor, but you still want to avoid null checks when referencing the property inside the body of a class. To handle this case, you can mark the property with the lateinit modifier.
Learn more about lateinit from MindOrks blog.
 
Q21. How to check if a lateinit variable has been initialized or not?
You can check if the lateinit variable has been initialized or not before using it with the help of isInitialized method. This method will return true if the lateinit property has been initialized otherwise it will return false.
Ex.
class Person {
 lateinit var name: String
 fun initializeName() {
 println(this::name.isInitialized)
 name = "MindOrks" // initializing name
 Println	(this::name.isInitialized)
 }
}
fun main(args: Array<String>) {
 Person().initializeName()
}
Learn more about it from MindOrks blog.
 
Q22. What is the difference between lateinit and lazy in Kotlin?
lazy can only be used for val properties, whereas lateinit can only be applied to var because it can’t be compiled to a final field, thus no immutability can be guaranteed.
If you want your property to be initialized from outside in a way probably unknown beforehand, use lateinit.
Learn more about the difference between lateinit and lazy from MindOrks blog.
 
Q23. Is there any difference between == operator and === operator?
Yes. The == operator is used to compare the values stored in variables and the === operator is used to check if the reference of the variables are equal or not. But in the case of primitive types, the === operator also checks for the value and not reference.
Ex.
// primitive example
val int1 = 10
val int2 = 10
println(int1 == int2) // true
println(int1 === int2) // true
// wrapper example
val num1 = Integer(10)
val num2 = Integer(10)
println(num1 == num2) // true
println(num1 === num2) //false
 
Q24. What is the forEach in Kotlin?
In Kotlin, to use the functionality of a for-each loop just like in Java, we use a forEach function.
Ex.
var listOfMindOrks = listOf("mindorks.com", "blog.mindorks.com", "afteracademy.com")
listOfMindOrks.forEach {
 Log.d(TAG,it)
}
 
Q25.What is a companion object in  Kotlin?
In Kotlin without creating instances of class we can call member functions of class or methods of class using the companion object.
Companion objects are created inside the class.
In Kotlin, if you want to write a function or any member of the class that can be called without having the instance of the class then you can write the same as a member of a companion object inside the class.
To create a companion object, you need to add the companion keyword in front of the object declaration.
By declaring the companion object, you can access the members of the class by class name only ( which is without explicitly creating the instance of the class).
To create a companion object, you need to add the companion keyword in  front of the object declaration.
 Learn more about companion object.
Ex.
companion object Test {
   fun callMe() =  print("This block is static Block")
   var someInteger: Int = 10
}
Ex. of companion object declaration
Companion object in Kotlin
class CompanionClass {
   companion object Test {
       fun callMe() =  print("This block is static Block")
       var someInteger: Int = 10
   }
   fun notStaticMethod() {
       println("This block is not static block")
   }
}
fun main() {
   val c = CompanionClass()
  c.notStaticMethod() //this is not static so we need to create obj of class then called method from that class
  	 CompanionClass.callMe()  //this is static method so we called  this way ...need not to create obj for static method
   println(CompanionClass.Test.someInteger)
}
/*
This block is not a static block
This block is static Block10
*/
 
Q26. What is the equivalent of Java static methods in Kotlin?
Read more about this from MindOrks blog.
To achieve the functionality similar to Java static methods in Kotlin, we can use:
companion object
package-level function
Object
 
Q27. How to create a Singleton class in Kotlin?
A singleton class is a class that is defined in such a way that only one instance of the class can be created and is used where we need only one instance of the class like in logging, database connections, etc.
To create a Singleton class in Kotlin, you need to use the object keyword.
object AnySingletonClassName
Note: You can't use constructor in object, but you can use init.
Learn more about Singleton class from MindOrks blog.
 
Q28. What are init blocks in Kotlin?
init blocks are initializer blocks that are executed just after the execution of the primary constructor. 
A class file can have one or more init blocks that will be executed in series. If you want to perform some operation in the primary constructor, then it is not possible in Kotlin, for that, you need to use the init block.
Learn more about init blocks from MindOrks blog.
 
Q29. What are the types of constructors in Kotlin?
Primary constructor: These constructors are defined in the class header and you can't perform some operation in it, unlike Java's constructor.
Secondary constructor: These constructors are declared inside the class body by using the constructor keyword. You must call the primary constructor from the secondary constructor explicitly. Also, the property of the class can’t be declared inside the secondary constructor. There can be more than one secondary constructor in Kotlin.
 Learn more about Primary and Secondary constructors from MindOrks blog.
 
Q30. Is there any relationship between primary and secondary constructors?
Yes, when using a secondary constructor, you need to call the primary constructor explicitly.
 
Q31. What is the default type of argument used in a constructor?
By default, the type of arguments of a constructor in val. But you can change it to var explicitly.
 
Q32. What are Coroutines in Kotlin?
A framework to manage concurrency in a more performant and simple way with its lightweight thread which is written on top of the actual threading framework to get the most out of it by taking the advantage of cooperative nature of functions.
This is an important interview question.
Learn more about Kotlin Coroutines with examples from MindOrks blog
 
Q33. What is the suspend function in Kotlin Coroutines?
Suspend function is the building block of the Coroutines in Kotlin. Suspend function is a function that could be started, paused, and resume. 
To use a suspend function, we need to use the suspend keyword in our normal function definition.
Learn more about the suspend function from MindOrks blog.
 
Q34. What is the difference between Launch and Async in Kotlin Coroutines?
The difference is that the launch{} does not return anything and the async{} returns an instance of Deferred<T>, which has an await() function that returns the result of the coroutine like we have future in Java in which we do future.get() to the get the result.
In other words:
launch: fire and forget
async: perform a task and return a result
 Learn more about Launch vs Async from MindOrks video.
 
Q35. How Exception Handling is done in Kotlin Coroutines?
Learn from MindOrks blog.
 
Q36. How to choose between a switch and when in Kotlin?
Whenever we want to handle many if-else conditions, then we generally use switch-case statements. But Kotlin provides a more concise option i.e. in Kotlin, we can use it when in place of the switch. And, when can be used as:
expression
arbitrary condition expression
without argument
with two or more choices
For example:
when(number) {
 1 -> println("One")
 2, 3 -> println("Two or Three")
 4 -> println("Four")
 else -> println("Number is not between 1 and 4")
}
Learn more about when from MindOrks blog.
 
Q37. What is the open keyword in Kotlin used for?
By default, the classes and functions are final in Kotlin. So, you can't inherit the class or override the functions. To do so, you need to use the open keyword before the class and function. For example:
 Learn more about open keyword from MindOrks blog.
 
Q38. What are lambda expressions?
Lambdas expressions are anonymous functions that can be treated as values i.e. we can pass the lambdas expressions as arguments to a function, return them, or do any other thing we could do with a normal object. 
For example:
val add : (Int, Int) -> Int = { a, b -> a + b }
val result = add(9, 10)
Learn more about Lambdas from MindOrks blog.
 
Q39. What are Higher-Order functions in Kotlin?
A higher-order function is a function that takes functions as parameters or returns a function. 
For example, A function can take functions as parameters.
fun passMeFunction(abc: () -> Unit) {
 // I can take function
 // do something here
 // execute the function
 abc()
}
For example, A function can return another function.
fun add(a: Int, b: Int): Int {
 return a + b
}
And, we have a function returnMeAddFunction which takes zero parameters and returns a function of the type ((Int, Int) -> Int).
fun returnMeAddFunction(): ((Int, Int) -> Int) {
 // can do something and return function as well
 // returning function
 return ::add
}
And to call the above function, we can do:
val add = returnMeAddFunction()
val result = add(2, 2)
Learn more about Higher-Order functions from MindOrks blog.
 
Q40. What are extension functions in Kotlin?
Extension functions are like extensive properties attached to any class in Kotlin. By using extension functions, you can add some methods or functionalities to an existing class even without inheriting the class. 
For example: Let's say, we have views where we need to play with the visibility of the views. So, we can create an extension function for views like,
fun View.show() {
 this.visibility = View.VISIBLE
}
fun View.hide() {
 this.visibility = View.GONE
}
and to use it we use, like,
toolbar.hide()
Learn more about extension functions from MindOrks blog.
 
Q41. What is an infix function in Kotlin?
An infix function is used to call the function without using any bracket or parenthesis.
You need to use the infix keyword to use the infix function.
Ex.
class Operations {
 var x = 10; 
 infix fun minus(num: Int) {
 	this.x = this.x - num
 } 
}
fun main() {
 val opr = Operations()
 opr minus 8
 print(opr.x)
}
 
Q42. What is an inline function in Kotlin?
Inline function instructs compiler to insert complete body of the function wherever that function got used in the code. 
To use an Inline function, all you need to do is just add an inline keyword at the beginning of the function declaration.
Learn more about Inline functions from MindOrks blog.
 
Q43. What is noinline in Kotlin?
While using an inline function and want to pass some lambda function and not all lambda functions as inline, then you can explicitly tell the compiler which lambda it shouldn't inline.
Ex.
inline fun doSomethingElse(abc: () -> Unit, noinline xyz: () -> Unit) {
 abc()s
 xyz()
}
Learn more about noinline functions from MindOrks blog.
 
Q44. What are Reified types in Kotlin?
When you are using the concept of Generics to pass some class as a parameter to some function and you need to access the type of that class, then you need to use the reified keyword in Kotlin.
For example:
inline fun <reified T> genericsExample(value: T) {
 println(value)
 println("Type of T: ${T::class.java}")
}
fun main() {
 genericsExample<String>("Learning Generics!")
 genericsExample<Int>(100)
}
Learn more about Reified keyword from MindOrks blog.
 
Q45. What is the operator overloading in Kotlin?
In Kotlin, we can use the same operator to perform various tasks and this is known as operator overloading. To do so, we need to provide a member function or an extension function with a fixed name and operator keyword before the function name because normally also, when we are using some operator then under the hood some function gets called. 
For example, if you are writing num1+num2, then it gets converted to num1.plus(num2).
For example:
fun main() {
 val bluePen = Pen(inkColor = "Blue")
 bluePen.showInkColor()
 val blackPen = Pen(inkColor = "Black")
 blackPen.showInkColor()
 val blueBlackPen = bluePen + blackPen
 blueBlackPen.showInkColor()
}
 operator fun Pen.plus(otherPen: Pen):Pen{
 val ink = "$inkColor, ${otherPen.inkColor}"
 return Pen(inkColor = ink)
 }
 data class Pen(val inkColor:String){
 fun showInkColor(){ println(inkColor)}
 }
Learn more about operator overloading from MindOrks blog.
 
Q46. Explain the use-case of let, run, with, also, apply in Kotlin.
Learn from MindOrks blog.
 
Q47. What are pair and triple in Kotlin?
Pair and Triples are used to return two and three values respectively from a function and the returned values can be of the same data type or different.
Ex.
val pair = Pair("My Age: ", 25)
print(pair.first + pair.second)
Learn more about Pairs and Triples from MindOrks blog.
 
Q48. What are labels in Kotlin?
Any expression written in Kotlin is called a label. For example, if we are having a for-loop in our Kotlin code then we can name that for-loop expression as a label and will use the label name for the for-loop.
We can create a label by using an identifier followed by the @ sign. 
For example, name@, loop@, xyz@, etc. The following is an example of a label:
loop@ for (i in 1..10) {
 // some code goes here
}
The name of the above for-loop is loop.
Learn more about labels in Kotlin from MindOrks blog.
 
Q49. What are the benefits of using a Sealed Class over Enum?
Sealed classes give us the flexibility of having different types of subclasses and also containing the state. The important point to be noted here is the subclasses that are extending the Sealed classes should be either nested classes of the Sealed class or should be declared in the same file as that of the Sealed class.
Learn more about Sealed classes from MindOrks blog.
 
Q50. What are collections in Kotlin?
Learn from MindOrks video.
 
51. What are scopes in Kotlin Coroutines?
Learn from MindOrks blog.
 
Q52. What is the difference between FlatMap and Map in Kotlin?
FlatMap is used to combine all the items of lists into one list.
Map is used to transform a list based on certain conditions.
 Read more about FlatMap and Map in Kotlin from MindOrks blog.
 
Q53. What is the difference between List and Array types in Kotlin?
If you have a list of data that is having a fixed size, then you can use an Array. But if the size of the list can vary, then we have to use a mutable list.
Learn more about the difference between List and Array from MindOrks blog.
 
Q54. Can we use the new keyword to instantiate a class object in Kotlin?
No, in Kotlin we don't have to use the new keyword to instantiate a class object. To instantiate a class object, simply we use:
Ex.
var varName = ClassName()

Q55. What is a Singleton Class in Kotlin?
A singleton class is a class that is defined in such a way that only one instance of the class can be created and used everywhere.
How to create a singleton class in Kotlin?
The following rules are followed to make a Singleton class:
A private constructor
A static reference of its class
One static method
Globally accessible object reference
Consistency across multiple threads
Properties of Singleton Class
Following are the properties of a typical singleton class:
Only one instance: The singleton class has only one instance and this is done by providing an instance of the class, within the class. Also, outer classes and subclasses should be prevented from creating the instance.
Globally accessible: The instance of the singleton class should be globally accessible so that each class can use it.
In Kotlin, we need to use the object keyword to use the Singleton class.
The object class can have functions, properties, and the init method. 
The constructor method is not allowed in an object so we can use the init method if some initialization is required and the object can be defined inside a class. The object gets instantiated when it is used for the first time.
Let’s have an example of the Singleton class in Kotlin.
In Kotlin, we need to use the object keyword to use the Singleton class. 
The object class can have functions, properties, and the init method. 
The constructor method is not allowed in an object so we can use the init method if some initialization is required and the object can be defined inside a class. The object gets instantiated when it is used for the first time.
Ex.
object Singleton{
   init {
       println("Singleton class invoked.")
   }
   var variableName = "I am Var"
   fun printVarName(){
       println(variableName)
   }
}
fun main() {
   Singleton.printVarName()
   Singleton.variableName = "New Name"
   var a = A()
}
class A {
   init {
       println("Class init method. Singleton variableName property : ${Singleton.variableName}")
       Singleton.printVarName()
   }
}
/*
Singleton class invoked.
I am Var
Class init method. Singleton variableName property: New Name
New Name
Process finished with exit code 0
*/
 
Q56. What are Higher order functions in Kotlin?
A higher-order function is a function that takes functions as parameters or returns a function.
Understanding Higher-Order Functions and Lambdas in Kotlin
 
Q57. What are extension functions in Kotlin?
As the name implies, the extension functions are the functions that help us to extend the functionality of classes without having to touch their code.
In other words, the extension functions in Kotlin allow us to extend the functionality of a class by adding new functions.
The class doesn’t have to belong to us (could it be a third-party library) and also without requiring us to inherit the class.
Kotlin extension function
Ex.
// A sample class to demonstrate extension functions
class Circle(val radius: Double) {
   // member function of class
   fun area(): Double {
       return Math.PI * radius * radius;
   }
}
fun main() {
   // Extension function created for a class Circle
   fun Circle.perimeter(): Double {
       return 2 * Math.PI * radius;
   }
   // create object for class Circle
   val newCircle = Circle(2.5);
   // invoke member function
   println("Area of the circle is ${newCircle.area()}")
   // invoke extension function
   println("Perimeter of the circle is ${newCircle.perimeter()}")
}
 
Ex.  2
class Square(var side: Int) {
  	 fun area(): Int {
       return side * side
   }
}
fun main() {
   fun Square.perimeter(): Int {
       return 4 * side
   }
   val obj = Square(2)
   println(obj.area())
   print(obj.perimeter())
}
/*
4
8
Process finished with exit code 0
*/
Another example, let’s see how we can use this with Android View.
fun ImageView.loadImage(url: String) {
Glide.with(context).load(URL).into(this)
}
// now we can use like this
imageView.loadImage(url)
 
Q58. What is an inline function?
Inline function instructs the compiler to insert the complete body of the function wherever that function got used in the code.
Java does not provide inline functions; it is typically done by the JVM at execution time but kotlin provides keyword inline.
Ex
fun doSomething() {
   println("doSomething start");
   doSomethingElse() { }
   println("doSomething end");
}
inline fun doSomethingElse(myFun: () -> Unit) {
   myFun()
   println("code inside inline function")
}
fun main() {
   doSomething()
}
/*
doSomething start
code inside inline function
doSomething end
Process finished with exit code 0*/
 Here, we have the following two functions:
doSomething()
doSomethingElse()
Both are normal functions. doSomething() function is calling the doSomethingElse() function.
In order to understand it better, let's see the decompiled code
In Android Studio. Go to: Tools -> Kotlin -> Show Kotlin Bytecode, then click the Decompile button.
Now, we can see that the code of the doSomethingElse() function is copied inside the doSomething() function. And the doSomething() function is no more calling the doSomethingElse() function. This is all because we have used the inline keyword.
So, when to make the function inline and when not:
When the function code is very small, it's a good idea to make the function inline.
When the function code is large and called from so many places, it's a bad idea to make the function inline, as the large code will be repeated again and again.
Understanding inline, noinline, and crossinline in Kotlin.
 
Q59. What are lambda’s expression?
A lambda expression is a short block of code that takes in parameters and returns a value. Lambda expressions are similar to methods, but they do not need a name and they can be implemented right in the body of a method.
Lambdas Expressions are essentially anonymous functions that we can treat as values – we can, for example, pass them as arguments to functions, return them, or do any other thing we could do with a normal object.
Now, let's learn it by a simple example in Kotlin:
Val   doNothing :   (Int) -> Int = { value -> value }
This is a lambda expression that does nothing. Here the
{ value -> value }   is a complete function in itself. It takes an int as a parameter and returns a value as an int.
In (Int) -> Int
(Int) represents input int as a parameter.
Int represents return type as an int.
So, the doNothing is a function in itself that takes a value as an int and returns the same value as an int.
 
Q60. What is  Kotlin —  lateinit vs lazy?
 Lateinit keyword
There are many cases when you need to create a variable but you don't want to initialize it at the time of declaration/creation of the variable because you are sure that the variable will be initialized before its access/usage.
Learn Kotlin - lateinit vs lazy
Lazy keyword
There are certain classes whose object initialization is very heavy and takes so much time that it results in the delay of the whole class creation process.
 
Q61. What is destructuring in kotlin?
​​Learn Kotlin- Destructuring Declarations
 
Q62. Kotlin basic important questions
Kotlin Interview Questions 2022 - Courseya

Q63. Does Kotlin provide a new keyword?
Kotlin does not have a “new” keyword. To create a class instance, call the constructor just like a regular function.
How objects are created in kotlin?
var  obj = Animal();
obj.  -> Object is available for accessing class method
How objects are created in java?
	Animal obj = new Animal();
	obj.  -> object available for accessing class method
	
Q64. What are sealed classes in Kotlin?
Whenever you want to define a limited set of classes we can use sealed classes.
Sealed classes are defined by the keyword “sealed” before the class.
Kotlin Sealed Class represent restricted class hierarchies, where a value can have a type from a restricted set.
Sealed classes are like abstract classes; they can not be instantiated directly.
Multiple objects are possible in sealed classes but not possible in enum classes.
About Sealed Classes
A Sealed Class has a specific number of sub-classes.
Location
All the classes that directly inherit a sealed class should be present in the same Kotlin file.
Constructors
Sealed Class cannot have non-private constructors.
Private is the default access modifier for constructors in Sealed Class.
Abstract
By default, a Sealed Class is abstract.
Hence, a Sealed Class cannot be instantiated and all other properties pertaining to Abstract Class hold for a Sealed Class.
https://www.tutorialkart.com/kotlin/kotlin-sealed-class/
Ex.
sealed class ArithmeticOperation
class Add(val a: Int, val b: Int) : ArithmeticOperation()
class Subtract(val a: Int, val b: Int) : ArithmeticOperation()
class Multiply(val a: Int, val b: Int) : ArithmeticOperation()
class Divide(val a: Int, val b: Int) : ArithmeticOperation()
 
fun execute(op: ArithmeticOperation) = when (op) {
   is Add -> op.a + op.b
   is Subtract -> op.a - op.b
   is Multiply -> op.a * op.b
   is Divide -> op.a / op.b
}
 
fun main(args: Array<String>) {
   val a = 4 ; val b = 3
   val operation1 = Add(a, b)
   val result1 = execute(operation1)
   println("Addition : $result1")
 
   val operation2 = Subtract(a, b)
   val result2 = execute(operation2)
   println("Subtraction : $result2")
 
   val operation3 = Multiply(a, b)
   val result3 = execute(operation3)
   println("Multiplication : $result3")
 
   val operation4 = Divide(a, b)
   val result4 = execute(operation4)
   println("Division : $result4")
}
/*
Addition : 7
Subtraction : 1
Multiplication : 12
Division : 1
Process finished with exit code 0
*/
 
Q65. 
 
 
 
 
 
 
 
ANDROID
 
Q1. What intent filter in android?
An intent filter is an expression in an app's manifest file that specifies the type of intents that the component would like to receive.
An intent filter for an activity, make it possible for other apps to directly start your activity with a certain kind of intent.
By default :
<intent-filter>
   <action android:name="android.intent.action.MAIN" />
   <category android:name="android.intent.category.LAUNCHER" />
</intent-filter>
</intent-filter>
contained in:
<activity>
<activity-alias>
<service>
<receiver>
<provider>
must contain:
<action>
If <action> is not present then :-  it show error
Could not identify launch activity: Default Activity not found
Error while Launching activity
can contain:
<category>
<data>

Q2. What is service?
A Service is an application component that can perform long-running operations in the background. OR if you want to perform long-running operations without any UI like playing music, downloading a file even if the  app is not in the foreground or the app is killed then we can use services.
Service runs on the main thread and performs long-running operations.
A Service is an application component that doesn’t have any UI.
The service class is an abstract class having predefined one method overriding onBind().
For service 3 life cycles are very important 1) onCreate() 2) onDestroy() 3) onStartCommand().
Once started, a service might continue running for some time, even after the user switches to another application.
Additionally, a component can bind to a service to interact with it and even perform interprocess communication (IPC). For example, a service can handle network transactions, play music, perform file I/O, or interact with a content provider, all from the background.
The prime aim of a service is to ensure that the application remains active in the background so that the user can operate multiple applications at the same time. Ex gaana app, Airtel Wynk app.
Services overview | Android Developers
 https://data-flair.training/blogs/android-service-tutorial/

Q3. What are Broadcasts in android?
Broadcast is one  of the android application components.
Broadcast in android is the system-wide events that can occur when the device starts, when a message is received on the device or when incoming calls are received, or when a device goes to airplane mode, etc.
Broadcast Receivers are used to respond to these system-wide events.
Broadcast Receivers allow us to register for the system and application events, and when that event happens, then the register receivers get notified.
Broadcast Receiver in Android With Example
There are mainly two types of Broadcast Receivers:
Static Broadcast Receivers: These types of Receivers are declared in the manifest file and work even if the app is closed.
Dynamic Broadcast Receivers: These types of receivers work only if the app is active or minimized.
Since API Level 26, most of the broadcast can only be caught by the dynamic receiver, so we have implemented dynamic receivers in our sample project given below. There are some static fields defined in the Intent class which can be used to broadcast different events. We have taken a change of airplane mode as a broadcast event, but there are many events for which the broadcast register can be used. Following are some of the important system-wide generated intents:-
                       Intent
Description Of Event
android.intent.action.BATTERY_LOW :
Indicates low battery condition on the device.
android.intent.action.BOOT_COMPLETED
This is broadcast once after the system has finished booting
android.intent.action.CALL
 To perform a call to someone specified by the data
android.intent.action.DATE_CHANGED 
Indicates that the date has changed
android.intent.action.REBOOT
Indicates that the device has been a reboot
android.net.conn.CONNECTIVITY_CHANGE
The mobile network or wifi connection is changed(or reset)
android.intent.ACTION_AIRPLANE_MODE_CHANGED
This indicates that airplane mode has been switched on or off.




Q4. Activity backStack?
BackStack means we are adding to stack data structure

Q5. What is the fragment lifecycle in android?
Android fragments have their own life cycle very similar to an android activity. This section briefs different stages of its life cycle.
 

Android Fragments and its Lifecycle
Android - Fragments

Q6. Explain Fragments in detail?
Fragment is a UI component; it is a child of activity i.e. without activity fragment cannot exist. Activity is the parent of fragments. 
We can have 100 fragments in one activity but handling fragments is the toughest part
Fragments are a bit lightweight ex. Whatsapp, Instagram, etc.
You can have multiple fragments in one activity but you cannot have two activities on one screen. That's not possible. Activity is the mother of fragments.
Fragment is what basically you can have multiple views on one screen.
There are two methods of launching  fragment 
Static fragment (You put fragment in XML file)  and 
Dynamic fragment (You launch fragment on click of a button or  onCreate() Method you launch fragment).
Every created fragment is a reusable component.  Ex. Your internet connection goes off then just shows an image and text “No internet  Connection”, this  created  fragment we can use in many places throughout projects.


There are different transaction methods in fragments.
Add() 
replace()
remove()

Q7. Different Launch Modes in Android?
Android is having four launch modes as follows:
What are launch Modes in Android with examples | by Lloyd Dcosta | Medium
https://github.com/Dcosta2205/LaunchModes/
Android Launch Mode
Android Activity launchMode Explained, Must-know for Android Development

Q8. Difference Between View and ViewGroup in Android?
In Android Layout is used to describe the user interface for an app or activity, and it stores the UI elements that will be visible to the user. An android app’s user interface is made up of a series of View and ViewGroup elements.
View:
The view is a basic building block of UI (User Interface) in android.
View refers to the android. view.View class, which is the base class of all UI classes.
The View class is the base class or we can say that it is the superclass for all the GUI components in android. For example, the EditText class is used to accept the input from users in android apps, which is a subclass of View, and another example of the TextView class which is used to display text labels in Android apps is also a subclass of View. These are some of the view subclasses available in android.
TextView
EditText
ImageView
RadioButton
Button
ImageButton
CheckBox
DatePicker
Spinner
ProgressBar etc.
B) ViewGroup:
The ViewGroup class is a subclass of the View class.
ViewGroup Refer to the android. view.ViewGroup class
The ViewGroup will provide an invisible container to hold other Views or ViewGroups and to define the layout properties. For example, Linear Layout is the ViewGroup that contains UI controls like Button, TextView, etc., and other layouts also.
 Following are the commonly used ViewGroup subclasses used in android applications.
FrameLayout
WebView
ListView
GridView
LinearLayout
RelativeLayout
TableLayout and many more.
                                          View
                                                      ViewGroup
The view is a simple rectangle box that responds to the user’s actions.
ViewGroup is the invisible container. It holds View and ViewGroup
The view is the SuperClass of All components like TextView, EditText, ListView, etc
ViewGroup is a collection of Views(TextView, EditText, ListView, etc..), somewhat like a container.
A View object is a component of the user interface (UI) like a button or a text box, and it’s also called a widget.
A ViewGroup object is a layout, that is, a container of other ViewGroup objects (layouts) and View objects (widgets)
Examples are EditText, Button, CheckBox, etc.
For example, LinearLayout is the ViewGroup that contains Button(View), and other Layouts also.
View refers to the android. view. View class
ViewGroup refers to the android. view.ViewGroup class
android. view.The view is the base class of all UI classes.
ViewGroup is the base class for Layouts.

Q9. What is the difference between context and application context in Android?
They are both instances of Context, but the application instance is tied to the lifecycle of the application, while the Activity instance is tied to the lifecycle of an Activity. Thus, they have access to different information about the application environment.
 
Q10. What is Parcelable vs Serializable in android?
Serializable is a standard Java interface. You simply mark a class Serializable by implementing the interface, and Java will automatically serialize it in certain situations.
Parcelable is an Android-specific interface where you implement the serialization yourself.
Unlike Serializable, Parcelable reflection won't be used so it is faster and has better performance.
Android Parcelable is not made to save objects into the files, so if you want to save an object in the file you must use Serializable.
Know more about Serializable and Parcelable :
Android: Difference between Parcelable and Serializable? - Stack Overflow.
 
Q11. RecyclerView Multiple View Types in Android
In order to display a list in your application, we all must have used RecyclerView in Android. For example, the emails in the Gmail app, the feeds on Facebook and Instagram, messages in WhatsApp, all are done with the help of RecyclerView.
But one thing that you might have noticed is that while using RecyclerView, we define a view and the list items are displayed according to that view only. But what if you want to add different view types in the RecyclerView, you can add Multiple Views in the same RecyclerView.
Welcome to MindOrks! In this blog, we are going to learn how to use Multiple Views in RecyclerView.
You can find the whole project used in this tutorial from here.
So, let's get started with the project setup.
RecyclerView Multiple View
We can add multiple views in a RecyclerView. For example, the feed page on Facebook is an example of Multiple Views. You can add images, videos, text or a combination of all in the same RecyclerView.
Another example can be WhatsApp chatting. The message that we send can be thought to be placed in a RecyclerView. So, when you send the message, it appears on the right-hand side of the screen. But if someone from the other side sends a message, then it appears on the left-hand side. So, there is a change in the view type.
RecyclerView Multiple View Types in Android
 
Q12. What is Live data in android?
Live data is part of Jetpack.
LiveData is an observable data holder class. Unlike a regular observable, LiveData is lifecycle-aware, meaning it respects the lifecycle of other app components, such as activities, fragments, or services. This awareness ensures LiveData only updates app component observers that are in an active lifecycle state.
Updating the UI of the application due to changes in some data is one of the most used tasks in Android. For example, whenever you like some post on Instagram, then the like count will be increased and also the color of the like button will be changed to red from white. So, here we are changing the UI based on some data and there are many other examples of these kinds of UI changes due to some change in data in Android. So, these changes in the views of your app can be carried out with the help of ViewModel and to make the working of a ViewModel easy, Google introduced the concept of LiveData. LiveData is a part of Android Jetpack and in this blog, we are going to understand the concept of LiveData in Android.
Understanding LiveData in Android
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
Q13. Difference Between MVP and MVVM Design Pattern?
Difference Between MVP and MVVM Architecture Pattern in Android - GeeksforGeeks
MVP(Model View Presenter)
MVVM(Model View ViewModel)
It resolves the problem of having a dependent View by using Presenter as a communication channel between Model and View. 
This architecture pattern is more event-driven as it uses data binding and thus makes easy separation of core business logic from the View.
The one-to-one relationship exists between the Presenter and the View.
Multiple Views can be mapped with a single ViewModel.
The Presenter has knowledge about the View.
ViewModel has no reference to the View.
The model layer returns the response of the user’s input to the Presenter which forwards it to View.
After performing operations according to the user’s input, the Model layer returns the response to the View.
The presenter handles the application flow and the View is the actual application.
ViewModel is the actual application and View is the interface for the user in order to interact with the app.
The project file will contain more classes as well as code.
The Project file will contain more classes but less code per class.
Ideal for simple and complex applications.
Not ideal for small scale projects.
Easy to carry out Unit testing but a tight bond of View and Presenter can make it slightly difficult.
Unit testability is highest in this architecture.

Q14. What is a Gradle?
Gradle is a build system (open source). It has its own repository github.com/gradle/gradle.
Gradle is a build automation tool for multi-language software development. 
It is written in Java, Groovy and Kotlin languages.
Gradle  is used to control the development process from the tasks of compilation and testing, deployment, and publishing.
“Gradle” are scripts where one can automate the tasks. For example, the simple task to copy some files from one directory to another can be performed by the Gradle build script before the actual build process happens.
Gradle was designed for multi-project builds, which can grow to be large.
Android | build.gradle - GeeksforGeeks
  Ex.

 

 
Q15. What is DDMS in Android?
DDMS stands for Dalvik Debug Monitor Server in Android.
As part of Android Studio, DDMS is one of the most significant introspection tools available to Android devs.
It's used for debugging, diagnostics, and profiling.
DDMS is a debugging tool from the Android software development kit (SDK). Able to monitor operations in the emulator as well as real devices, DDMS reports the details of each processing thread and time spent whether in the app or Android OS.
Android DDMS: A Guide to the Ultimate Android Console.
 
Q16. What is a model class?
The model class is a set of classes that hold your data and business logic.
 In model class, there are mainly three methods —
Constructor: It is a bridge between model and adapter class.
Getter method: This method is used for getting the values of any property.
Setter method: This method is used for setting the value of any property
 
Q17. What are Interceptors?
According to documentation, Interceptors are a powerful mechanism that can monitor, rewrite, and retry the API call. So basically, when we do some API calls, we can monitor the call or perform some tasks.
OkHttp Interceptor - Making the most of it
 
Q18. What is a Room and How does it work?
​​Room is a persistence library, part of the Android Architecture Components. 
​​Room makes it easier to work with SQLiteDatabase objects in your app, decreasing the amount of boilerplate code and verifying SQL queries at compile time.
7 Steps To Room. A step by step guide on how to migrate.
 
Q19. What is pending intent in Android?
A PendingIntent itself is simply a reference to a token maintained by the system describing the original data used to retrieve it. This means that, even if its owning application's process is killed, the PendingIntent itself will remain usable from other processes that have been given it.
Pending intent extends Parcelable
class PendingIntent: Parcelable	
A PendingIntent is a token that you give to a foreign application (e.g. NotificationManager, AlarmManager, Home Screen AppWidgetManager or other 3rd party applications), which allows the foreign application to use your application’s permissions to execute a predefined piece of code.
If you want a foreign application to perform any Intent operation at a future point in time, then we will use PendingIntent.
Example: If you are building an SMS app and you want to open your application when a new message notification comes. In that situation, you have to use PendingIntent.
Intent v/s PendingIntent v/s Sticky Intent | Android Creativity Best Article 
What is an Android PendingIntent? - Stack Overflow
 
Q20. What is pending and sticky intent?
Intent - is a message-passing mechanism between components of Android, except for Content Provider. You can use Intent to start any component.
Sticky Intent - Sticky intents are associated with the android system for future broadcast events. For example, if a BATTERY_LOW event occurs then that Intent will stick with Android so that any future requests for BATTERY_LOW will return the Intent. OR An intent that is used with a sticky broadcast, is called a sticky intent. This intent will stick with the android system for future broadcast receiver requests.
Pending Intent - If you want someone to perform any Intent operation at a future point of time on behalf of you, then we will use Pending Intent. OR that intent that you want to trigger at some time in future when your application is not alive.
 
Q21. What is the lifecycle of a View?
Understanding View Lifecycle in Android
Android View Lifecycle
 
Q22. Explain constraint layout in android?
A ConstraintLayout is present in  ViewGroup that allows you to position and size widgets in a flexible way.
Note: ConstraintLayout is available as a support library that you can use on Android systems starting with API level 9 (Gingerbread).
Note: You cannot have a circular dependency in constraints.
ConstraintLayout | Android Developers.
Guidelines in Constraint Layout are invisible lines that are not visible to users but help developers to design the layout easily and constrain views to these guidelines, so that design can be more clear and interactive. But guidelines only work in Constraint Layout as guidelines require something to be constrained to them.
There are two types of guidelines:
Horizontal Guidelines: These guidelines have a height of zero and its width is equal to its parent Constraint Layout.
Vertical Guidelines: These guidelines have a width of zero and its height is equal to its parent Constraint Layout.
Guidelines in Android ConstraintLayout - GeeksforGeeks
However in the constraint layout even if you drag and drop an element in the design view when you run the app things may be shifted around.
We can design UI without touching the XML part of the code
Flat view hierarchy unlike other layouts, so does the better performance than the relative layout.
Note: ​​I am saying it again, designing UI using constraint layout is the same as designing UI in iOS,  so in future, if you work on iOS you will find it easier if you have used constraint layout.
When to use ConstraintLayout?
ConstraintLayout allows us to create large and complex layouts, without using nested views/layouts.
In ConstraintLayout we don’t need to code our layout, because we can arrange our views directly from the Layout Editor’s visual tool.
 
Q23. What are the differences between constraint layout and relative layout?
Constraint Layout:
However in the constraint layout even if you drag and drop an element in the design view when you run the app things may be shifted around.
We can design UI without touching the XML part of the code
Flat view hierarchy unlike other layouts, so does the better performance than the relative layout.
Note: ​​I am saying it again, designing UI using constraint layout is the same as designing UI in iOS,  so in future, if you work on iOS you will find it easier if you have used constraint layout.
When to use ConstraintLayout?
ConstraintLayout allows us to create large and complex layouts, without using nested views/layouts.
In ConstraintLayout we don’t need to code our layout, because we can arrange our views directly from the Layout Editor’s visual tool.
Relative Layout:
A relative layout via drag and drop automatically has its dimensions relative to other elements inferred, so when you run the app what you see is what you get.
In relative layout, it's hard to set the constraints without touching the XML design.
When to use RelativeLayout?
If you want to deal with more sophisticated views in our application, we can rely on RelativeLayout.
In RelativeLayout we can specify how child views are positioned relative to each other.
 
Q24. Explain activity lifecycle methods in different scenarios like when the home button is clicked, when the back button is clicked, moving from Activity A to B.
 
Q25. Explain activity lifecycle methods?
Android Activity Lifecycle is controlled by 7 methods of the android.app.  Activity class. The android Activity is the subclass of ContextThemeWrapper class.
An activity is a single screen in android. It is like a window or frame of Java.
With the help of activity, you can place all your UI components or widgets on a single screen.
The 7 lifecycle method of Activity describes how the activity will behave at different states.
Method
Description
onCreate
called when activity is first created.
onStart
called when activity is becoming visible to the user.
onResume
called when the activity will start interacting with the user.
onPause
called when activity is not visible to the user.
onStop
called when activity is no longer visible to the user.
onRestart
called after your activity is stopped, prior to starting.
onDestroy
called before the activity is destroyed.


 
 
 
Q26. Fragment add, replace. What are the different lifecycle methods that are called?
 
 
Q27. What are View Binding, Data Binding? Differences View Binding and Data Binding
View Binding library is faster than Data Binding library as it is not utilizing annotation processors underneath, and when it comes to compile-time speed View Binding is more efficient.
The one and only function of View Binding is to bind the views in the code. While Data Binding offers some more options like Binding Expressions, which allows us to write expressions that connect variables to the views in the layout.
Data Binding Library works with Observable Data objects, you don't have to worry about refreshing the UI when underlying data changes.
The Data Binding library provides us with Binding Adapters.
Data Binding library provides us with Two-way Data Binding, this is a technique of binding your objects to XML layouts so that both object and layout can send data to each other.
To understand View Binding and Data Binding in detail you can go through these articles,
Android ViewBinding, Jetpack Compose | Geek Culture
https://anubhav-arora.medium.com/android-view-binding-v-s-data-binding
 
Q28. Service vs Async task differences.
​​Thread: is a unit of execution that runs "parallel" to the Main Thread is an important point, you can't update a UI component from any thread here except the main thread.
AsyncTask:  
1. In Android, AsyncTask (Asynchronous Task) allows us to run the instruction in the background and then synchronize again with our main thread. This class will override at least one method i.e. doInBackground(Params) and most often will override the second method onPostExecute(Result).
2. AsyncTask is going to do background operation on the background thread and update on the main thread. Async tasks help us to make communication between the background thread to the main thread.
3. The AsyncTask class is firstly executed using execute() method. In the first step AsyncTask     is called onPreExecute() then onPreExecute() calls doInBackground() for background processes and then doInBackground() calls onPostExecute() method to update the UI.
4. Android AsyncTask example and explanation
5. AsyncTask Tutorial With Example Android Studio Abhi Android
Service:
Solves the problem because it lives separate from the activity that invokes it so it can continue running even when the activity is destroyed, it runs in the Main Thread (beware of ANR) using a background service (extend IntentService it creates the worker thread automatically for you). Service is like an activity without UI, and is good for long tasks.
 

Difference between Service, Threads, AsyncTask
Difference Between Thread, Service, and AsyncTask in Android

Q29. How do you pass data between two fragments?
When working with child fragments, your parent fragment and its child fragments might need to share data with each other. To share data between these fragments, use the parent fragment as the ViewModel scope.
Fragment to Fragment Communication in Android using Shared ViewModel - GeeksforGeeks
 
Q30. What is a shared ViewModel?
Shared ViewModel in Android: Shared between Fragments
https://www.google.com/search

Q31. How do you pass data between 2 activities?
Through Intent we can move from one activity to another activity and Intent can also be used to pass the data from one activity to another activity.
Mandatory Article Passing data between Activities using Intent in Android
How can I transfer the data between two activities in android
Passing data between activities

Q32. How to retain form data when the screen is rotated?
https://www.google.com/search

Q33. What are dex files in android?
Compiled Android application code file.
Android programs are compiled into .dex (Dalvik Executable) files, which are in turn zipped into a single .apk file on the device. .dex files can be created automatically by Android, by translating the compiled applications written in the Java programming language.
 
Q34. What are apk files in android?
APK stands for Android Package (sometimes Android Package Kit or Android Application Package).
An APK is an archive file, meaning that it contains multiple files, plus some metadata about them.
APK file is familiar with other types of archive files, like ZIP and RAR.
APK file written in either Java or Kotlin.
.apk is an extension for all android apps.
What Is an APK File and What Does It Do? Explained
 
Q35. Which are the Fastest layout and the difference between Constraint, Linear, Relative layout.
Constraint Linear is the fastest layout in android.

Q36. What are ADB files in android?
ADB stands for Android Debug Bridge.
ADB is an important command-line tool that lets you communicate with a device. 
By the use of ADB commands we can perform actions, such as installing, debugging apps, uninstalling.
It also provides access to a Unix shell that you can use to run a variety of commands on a device. Ex. from the terminal by typing command we can uninstall an application that is installed in mobile or emulator.

Q37. Types of services?
​​Android Service Tutorial - Lifecycle, Methods & Implementation - DataFlair
Android Service Tutorial - javatpoint

Q38. How does communication between two services happen?
We already know that we can communicate with Service from an activity just by using method startService() and passing Intent to the argument in the method, or either we can use bindService() to bind the service to the activity with argument Intent.
Android : Service Communication with Activity

Q39.  Difference between Context and getContext?
Context is basically present in Activity class  when we extend …
ie. public class MainActivity extends AppCompatActivity
ie. public class AppCompatActivity extends FragmentActivity implements AppCompatCallback,
ie. public class FragmentActivity extends ComponentActivity implements
ie. public class ComponentActivity extends androidx.core.app.ComponentActivity implements
ie. public class ComponentActivity extends Activity implements
.
.
.
ie. public class ContextWrapper extends Context
ie. public abstract class Context {

getContext - 
1. Is present in Fragment the “Context” which we have seen above is not present in Fragment.
2. But internally Fragment extends some other class like Fragment So “Context” is not possible in fragments.
3. But the getContext() method is possible in fragments.
4. public class Fragment implements ComponentCallbacks, OnCreateContextMenuListener, 	- > 	This class has a getContext() method.
Ex. while setting the recycler view in fragment we use the getContext() method instead of “this”.
You cannot say “this” because it's a non-activity class so use the getContext()  method.

Q40. When to use service & when to use a work manager?
Service:
A Service is an application component that can perform long-running operations in the background. OR if you want to perform long-running operations without any UI like playing music, downloading a file even if the  app is not in the foreground or the app is killed then we can use services.
Service runs on the main thread and performs long-running operations.
A Service is an application component that doesn’t have any UI.
The service class is an abstract class having predefined one method overriding onBind().
For service 3 life cycles are very important 1) onCreate() 2) onDestroy() 3) onStartCommand().
Once started, a service might continue running for some time, even after the user switches to another application.
Additionally, a component can bind to a service to interact with it and even perform interprocess communication (IPC). For example, a service can handle network transactions, play music, perform file I/O, or interact with a content provider, all from the background.
The prime aim of a service is to ensure that the application remains active in the background so that the user can operate multiple applications at the same time. Ex gaana app, Airtel Wynk app.
Services overview | Android Developers
B) WorkManager:
WorkManager is intended for work that is required to run reliably even if the user navigates off a screen, the app exits, or the device restarts. 
For example: Sending logs or analytics to backend services. Periodically syncing application data with a server.
Another important thing introduced with Android Jetpack is WorkManager.
WorkManager is part of Android Jetpack. WorkManager helps us to execute our tasks immediately or at an appropriate time.
Android WorkManager Tutorial - Performing Tasks in Background

Q41. What is the difference between context and application?
In getApplicationContext(), our Context is tied to Application and its lifecycle. We can think of it as the layer behind the whole application. 
The difference is that the Application's Context is not UI related. It means that we shouldn't use it to Inflate a Layout, Start an Activity nor Show a Dialog.

Q42. How to Communicate Between Fragments in Android?
We can communicate within fragments using the ViewModel.
We can also communicate between fragments using Interface.
How to Communicate Between Fragments in Android

Q43. What is proguard and how to use it to reduce apk size in android?
ProGuard is used for 3 things  :
Minifying the code - It will remove unused code
Obfuscate the code - It will make application difficult to reverse engineering because it will change the name of class. Suppose you have created MainActivity as class name it will minify to class A or Abc and also it will minify unused methods.
Optimize code - There is a need to use an inline function in a program but you have not used it. So it will make an inline function and then it will reduce code or optimized code.

Q44. Why we are using service instead of thread in android
Service is a component of Android. It is also an Activity but has no interface.
Threads run in the lifecycle of Activity, and are killed/stopped when an Activity is destroyed. Services run in the background, have their own life cycle that is independent of the life cycle of the Activity.

Q45. Service vs IntentService in Android?
Service vs IntentService in Android

Q46. How do you pass data between two fragments?
By Interface 2. ViewModel
 
Q.47 Types of Android Services
1. Foreground Services
Foreground services are those services that are visible to the users. 
The users can interact with them at ease and track what’s happening. These services continue to run even when users are using other applications.
The perfect example of this is Music Player and Downloading.
2. Background Services
These services run in the background, such that the user can’t see or access them. These are the tasks that don’t need the user to know them.
Task run even if we kill the app from the background.
Ex. Gaana streaming app, Airtel wynk app, Syncing and Storing data.
3. Bound Services
Bound service runs as long as some other application component is bound to it. Many components can bind to one service at a time, but once they all unbind, the service will destroy.
To bind an application component to the service, bindService() is used.
 
Q48. What is a model class?
The model class is a set of classes that hold your data and business logic.
 In model class, there are mainly three methods —
Constructor: It is a bridge between model and adapter class.
Getter method: This method is used for getting the values of any property.
Setter method: This method is used for setting the value of any property
 
Q49. What is a Room and How does it work?
​​Room is a persistence library, part of the Android Architecture Components. 
​​Room makes it easier to work with SQLiteDatabase objects in your app, decreasing the amount of boilerplate code and verifying SQL queries at compile time.
7 Steps To Room. A step by step guide on how to migrate.
 
Q50. Fragment-Add-Replace-Remove-LifeCycle-Callbacks.
https://github.com/avadhutjc/Fragment-Add-Replace-Remove-LifeCycle-Callbacks
 
Q51. What are main 3 components of recycler view in android
A layout manager. 
An adapter.
A ViewHolder.
 
Q51. What are different Logcat methods in Android?
The different LogCat methods are:
Log.v(); // Verbose
Log.d(); // Debug
Log.i(); // Info
Log.w(); // Warning
Log.e(); // Error

Q52. What is Appcompat activity?
androidx.appcompat.app.AppCompatActivity.  -> Base class for activities that wish to use some of the newer platform features on older Android devices.

Q53. Which methods must be implemented for SQLiteOpenHelper?
SQLiteOpenHelper class is used for database creation and version management. 
For performing any database operation, you have to provide the implementation of onCreate() and onUpgrade() methods of SQLiteOpenHelper class.

Q54. Which of the following methods is called only once in a fragment lifecycle?
OnCreate and OnDestroy id fired only once.

Q55. Can you return null if the fragment does not provide a UI.
Yes we can return null -> see onCreateView()
onAttach() — This method called first, To know that our fragment has been attached to an activity. We are passing the Activity that will host our fragment.
onCreate() —  This method called when a fragment instance initializes, just after the onAttach where fragment attaches to the host activity.
onCreateView() —  The method called when it’s time for the fragment to draw its user interface for the first time. To draw a UI for your fragment, you must return a View component from this method that is the root of your fragment’s layout. You can return null if the fragment does not provide a UI.
onActivityCreated() — This method called when Activity completes its onCreate() method
onStart() — This method called when a fragment is visible.
onResume() — This method called when a fragment is visible and allowing the user to interact with it. Fragment resumes only after activity resumes.
 
Q56.  Android Architecture
Android Architecture - GeeksforGeeks
 
Q57.  Network  Handler class
package com.abc.assignment.remote
import retrofit2.HttpException
import java.net.SocketTimeoutException
data class Resource<out T>(val status: Status, val data: T?, val message: String?) {
   companion object {
       fun <T> success(data: T?): Resource<T> {
           return Resource(
               Status.SUCCESS,
               data,
               null
           )
       }
 
       fun <T> error(msg: String, data: T?): Resource<T> {
           return Resource(
               Status.ERROR,
               data,
               msg
           )
       }
       fun <T> loading(data: T?): Resource<T> {
           return Resource(
               Status.LOADING,
               data,
               null
           )
       }
   }
}
enum class Status {
   SUCCESS,
   ERROR,
   LOADING
}enum class ErrorCodes(val code: Int) {
   SocketTimeOut(-1)
}
open class ResponseHandler {
   fun <T : Any> handleSuccess(data: T?): Resource<T> {
       return Resource.success(data)
   }
   fun <T : Any> handleException(e: Exception): Resource<T> {
       return when (e) {
           is HttpException -> Resource.error(
               getErrorMessage(e.code()),
               null
           )
           is SocketTimeoutException -> Resource.error(
               getErrorMessage(ErrorCodes.SocketTimeOut.code),
               null
           )
           else -> Resource.error(
               getErrorMessage(Int.MAX_VALUE),
               null
           )
       }
   }
 
   private fun getErrorMessage(code: Int): String {
       return when (code) {
           ErrorCodes.SocketTimeOut.code -> "Timeout"
           401 -> "Unauthorized"
           404 -> "Not found"
           409 -> "Conflicts found"
           500 -> "Server Error"
           else -> "Something went wrong"
       }
   }
}
Q58. What is meant by restful api?
Full form of REST API is the Representational State Transfer Application Programming Interface more commonly known as REST API web service.
It means when a RESTful API is called, the server will transfer a representation of the requested resource's state to the client system.
REST was created by computer scientist Roy Fielding.
https://www.google.com/search?q
 
Q59. 
 
 

