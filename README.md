# JAVA DEVELOPER CERTIFICATION
## CHAPTER 1
## Table of contents
[[_TOC_]]

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
* Import statements tell Java which packages to look in for classes.
* Package names are hierarchical like the mail as well.
*  The rule for package names is that they are mostly letters or numbers separated by periods (.)
### Wildcards
* The * is a wildcard that matches all classes in the package.
* It doesn’t import child packages, fields, or methods; it imports only classes.

### Redundant Imports
* There’s one special package in the Java world called java.lang. This package is special in that it is automatically imported.
* Another case of redundancy involves importing a class that is in the same package as the class importing it.  Java automatically looks in the current package for other classes.
* you can only have one wildcard and it must be at the end
* import java.nio.file.Paths.*; // NO GOOD - you cannot import methods (only class names)

### Naming Conflicts
* One of the reasons for using packages is so that class names don’t have to be unique across all of Java.  A common example of this is the Date class.
```
import java.util.*;
import java.sql.*; // causes Date declaration to not compile
```
* When the class is found in multiple packages, Java gives you a compiler error.

```
import java.util.Date;
import java.sql.*;
```
* If you explicitly import a class name, it takes precedence over any wildcards present. Java thinks, “The programmer really wants me to assume use of the java.util.Date class.”
* Sometimes you really do want to use Date from two different packages.
* When this happens, you can pick one to use in the import and use the other’s fully qualified class name [the package name, a period (.), and the class name] to specify that it’s special.
```
import java.util.Date;
 
public class Conflicts {
   Date date;
   java.sql.Date sqlDate;
 
}
 
```
* Or you could have neither with an import and always use the fully qualified class name.
```
public class Conflicts {
java.util.Date date;
java.sql.Date sqlDate;

}
```

### Compiling and Running Code with Packages
* You can use an asterisk to specify that you’d like to include all Java files in a directory. 
* However, you cannot use a wildcard to include subdirectories. If you were to write javac *.java, the code in the packages would not be picked up.

### Using an Alternate Directory
* By default, the javac command places the compiled classes in the same directory as the source code. 
* It also provides an option to place the class files into a different directory. The -d option specifies this target directory.
* Java options are case sensitive. This means you cannot pass -D instead of -d.
```
javac -d classes packagea/ClassA.java packageb/ClassB.java
```
* The correct answer is classes/packagea/ClassA.class. The package structure is preserved under the requested target directory.
* To run the program, you specify the classpath so Java knows where to find the classes. 
* There are three options you can use. All three of these do the same thing:
``` 
java -cp classes packageb.ClassB
java -classpath classes packageb.ClassB
java --class-path classes packageb.ClassB
```
### Compiling with JAR Files
* A Java archive (JAR) file is like a zip file of mainly Java class files.
* The period (.) indicates you want to include the current directory in the classpath.
* Windows uses semicolons (;) to separate parts of the classpath; other operating systems use colons. (:)
* Just like when you’re compiling, you can use a wildcard (*) to match all the JARs in a directory. Here’s an example:
``` 
java -cp "C:\temp\directoryWithJars\*" myPackage.MyClass
```
### Creating a JAR File
* To do so, you use the jar command.
* The simplest commands create a jar containing the files in the current directory.
``` 
jar -cvf myNewFile.jar .
jar --create --verbose --file myNewFile.jar .
```
* Alternatively, you can specify a directory instead of using the current directory.
```  
jar -cvf myNewFile.jar -C dir .
```
* changes to the classes directory and adds to foo.jar all files within the classes directory (without creating a classes directory in the jar file), then changes back to the original directory before changing to the bin directory to add xyz.class to foo.jar. If classes holds files bar1 and bar2, then here's what the jar file contains using jar tf foo.jar:
``` 
jar uf foo.jar -C classes . -C bin xyz.class
```
### Running a Program in One Line with Packages
* You can use single-file source-code programs from within a package as long as they rely only on classes supplied by the JDK. This code meets the criteria.

### Ordering Elements in a Class
* Comments can go anywhere in the code.
* Element - Package declaration - Required - No - Where does it go? - First line in the file
* Element - Import statements - Required - No - Where does it go? - Immediately after the package (if present)
* Element - Class declaration - Required - Yes - Where does it go? - Immediately after the import (if any)
* Element - Field declarations - Required - No - Where does it go? - Any top-level element in a class
* Element - Method declarations - Required - No - Where does it go? - Any top-level element in a class
```
package structure;      // package must be first non-comment
import java.util.*;     // import must come after package
public class Meerkat {  // then comes the class
   double weight;       // fields and methods can go in either order
   public double getWeight() {
      return weight; }
   double height;    // another field - they don't need to be together
}
```
* Think of the acronym <b>PIC</b> (picture): package, import, and class. Fields and methods are easier to remember because they merely have to be inside a class.
* You need to know one more thing about class structure for the 1Z0-815 exam: multiple classes can be defined in the same file, but only one of them is allowed to be public. 
* The public class matches the name of the file. 
* For example, these two classes must be in a file named Meerkat.java:
``` 
public class Meerkat { }
class Paw { }
```
* A file is also allowed to have neither class be public. As long as there isn’t more than one public class in a file, it is okay.
## Code Formatting on the Exam
* Code that begins with a class name
* Code that begins with a method declaration
* Code that begins with a code snippet that would normally be inside a class or method
* Code that has line numbers that don’t begin with 1
* Also note that imports will be not removed to save space if the package statement is present. This is because imports go after the package statement.
* Remember that extra whitespace doesn’t matter in Java syntax. The exam may use varying amounts of whitespace to trick you.
