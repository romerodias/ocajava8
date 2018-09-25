## Redundand Imports

1. Does not compile

```java
import java.util.*;
import java.sql.*; //Does not compile
```

When the class is found in multiple packages, Java gives the compiler error: The type Date is ambiguous.

2. Does not compile

```java
import java.util.Date;
import java.sql.Date;
```

The compiler tells you: The import java.sql.Date collides with another import statment.

## Order of Initialization
```java
public class Chick {
   private String name = "Fluffy";
  { System.out.println("setting field"); }
  public Chick() {
    name = "Tiny";
    System.out.println("setting constructor");
  }    
  public static void main(String[] args) {
    Chick chick = new Chick();
    System.out.println(click.name);
  }
}
```
#### Running this example print this:
setting field  
setting constructor  
Tiny   
Start with the main() method
Call the constructor of click
First it initializes name to Fluffy
Next it executes the print statement in the instance initilizer of line 3. Once all the fields and instance initilizer have run, Java return to the constructor. Line 5 changes the value of name to Tinny and line 6 prints another statement. At this point, the constructor is done executing ahd goes back to the print statement on line 10.


### Primitive Data types

Keyword | Type | Example
--|
boolean | true or false | true
byte | 8-bit integral value | -128 to 127
short | 16-bit integral value | 123
int | 32-bit integral value | 123
long | 64-bit integral value | 123
float | 32-bit float-point value | 123.45f
double | 64-bit floatpoint value | 123.456
char | 16-bit Unicode value | 'a'


```java
long max = 3123456789; // does not compile
```
Java complains the number is out of range. Ant it is - for an int. However, we don't hava an int. The solution is to add the caracter L to the number;

```java
long max = 3123456789L; // now Java knows it is a long
```

A feature added in Java 7, you can have undersocres in numbers to make them easier to Redundand
```java
int million1 = 1000000;
int million2 = 1_000_000;
double notAtStart = _1000.00; // doest not compiler
double notAtEnd = 1000.00_; // does not compiler
double notByDecimal = 1000_.00; //does not compiler
double annoyingButLegal = 1_00_.0_0; // this one compiles
```
