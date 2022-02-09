# JAVA DEVELOPER CERTIFICATION
## CHAPTER 1
## Table of contents
* [Major Components of Java](##Major Components of Java)

## Major Components of Java

The Java Development Kit (JDK) contains the minimum software you need to do Java development. Key pieces include:
* javac - compiler - converts .java files to .class files
* java - launcher - creates the virtual machine and executes the program
* jar - archiver - package files together
* javadoc - api documentation - command for generating documentation.

## Bytecode
* Javac program generates instructions in a special format that the java command can run called bytecode. 
* Then java launches the Java Virtual Machine (JVM) before running the code.
* The JVM knows how to run bytecode on the actual machine it is on. You can think of the JVM as a special magic box on your machine that knows how to run your .class file.

## JRE in java 11
* In previous versions of Java, you could download a Java Runtime Environment (JRE) instead of the full JDK. The JRE was a subset of the JDK that was used for running a program but could not compile one. It was literally a subset. In fact, if you looked inside the directory structure of a JDK in older versions of Java, you would see a folder named jre.
* In Java 11, the JRE is no longer available as a stand-alone download or a subdirectory of the JDK.

## API -  Application programming interfaces 
* Common pieces of functionality and algorithms that developers need
* Luckily, we do not have to write each of these ourselves. Java comes with a large suite of application programming interfaces (APIs) that you can use. 

## Downloading a JDK
* Every six months, the version number of Java gets incremented.
* Java 11 came out in September 2018
* Every three years, Oracle has a long-term support (LTS) release. Unlike non-LTS versions that are supported for only six months, LTS releases have patches and upgrades available for at least three years. 

## Benefits of Java
### Object Oriented
* Java is an object-oriented language
* It  means all code is defined in classes, and most of those classes can be instantiated into objects.
* Java allows for functional programming within a class, but object-oriented is still the main organization of code.
### Encapsulation 
* Java supports access modifiers to protect data from unintended access and modification.
*  Most people consider encapsulation to be an aspect of object-oriented languages
### Platform Independent
* Java is an interpreted language that gets compiled to bytecode.A key benefit is that Java code gets compiled once rather than needing to be recompiled for different operating systems.
* write once, run everywhere.
* it is possible to write code that throws an exception in some environments, but not others.

### Robust (solidny)
One of the major advantages of Java over C++ is that it prevents memory leaks. Java manages memory on its own and does garbage collection automatically. Bad memory management in C++ is a big source of errors in programs.
### Simple 
Java was intended to be simpler to understand than C++.
* no pointers
* no operator overloading
### Secure 
Java code runs inside the JVM. This creates a sandbox that makes it hard for Java code to do evil things to the computer it is running on
### Multithreaded 
Java is designed to allow multiple pieces of code to run at the same time
### Backward Compatibility 
* The Java language architects pay careful attention to making sure old programs will work with later versions of Java.
* Deprecation is a technique to accomplish this where code is flagged to indicate it shouldn’t be used. 
* This lets developers know a different approach is preferred so they can start changing the code.
## Understanding the Java Class Structure
* classes are the basic building blocks
* To use most classes, you have to create objects.
* An object is a runtime instance of a class in memory.
* An object is often referred to as an instance since it represents a single representation of the class.
* A reference is a variable that points to an object.
###  Keyword
* Java calls a word with special meaning a keyword.
### Fields and Methods
* Java classes have two primary elements: 
* methods-often called functions or procedures in other languages
* fields- more generally known as variables.
* Together these are called the members of the class.
* Variables hold the state of the program, and methods operate on that state.

####  Method signature
* The method name and parameter types are called the method signature.
#### Method declaration
* The method declaration consists of additional information such as the return type.

### Comments
* Comments aren’t executable code, we can place them in many places.
* ``\\`` - A single-line comment begins with two slashes. The compiler ignores anything you type after that on the same line. 
* ``/* */`` -A multiple-line comment (also known as a multiline comment) includes anything starting from the symbol /* until the symbol */.

People often type an asterisk (*) at the beginning of each line of a multiline comment to make it easier to read, but you don’t have to.
* ``/** */`` - This special syntax tells the Javadoc tool to pay attention to the comment. Javadoc comments have a specific structure that the Javadoc tool knows how to read. 

### Classes vs Files
* Most of the time, each Java class is defined in its own .java file. It is usually public, which means any code can call it. 
* Java does not require that the class be public. 
* You can even put two classes in the same file. When you do so, at most one of the classes in the file is allowed to be public.
* If you do have a public class, it needs to match the filename.
### Writing a main() Method
* A Java program begins execution with its main() 
* The JVM calls on the underlying system to allocate memory and CPU time, access files, and so on.

#### Creating a main() Method
* The main() method lets the JVM call our code. 
* To compile Java code, the file <b>must have the extension .java.</b> The name of the file <b>must match the name of the class. </b>
* Result is a file of bytecode by the same name, but with a .class filename extension.
* Notice that we must omit the .class extension to run class
* Each file can contain only one public class.
* Allowed args in main
```
String[] args
String args[]
String... args
```

#### Passing Parameters to a Java Program
```
java Zoo Bronx Zoo
```
* Spaces are used to separate the arguments. 

## Running a Program in One Line
* Starting in Java 11, you can run a program without compiling it first—well, without typing the javac command that is. 
```
java SingleFileZoo.java Cleveland
```
* When running it as a one-liner, we write java SingleFileZoo.java
* When running it directly, you pass the java command the name of the file. This feature is called launching single-file source-code programs.
* This means if your program has two .java files, you still need to use javac.
* Java is still a compiled language, which means the code is being compiled in memory and the java command can give you a compiler error.
* Even if the code compiles properly, no .class file is created. 
* compiling your code in advance using javac will result in the program running faster, and you will definitely want to do that for real programs.
* Can only import code that came with the JDK

## Understanding Package Declarations and Imports
