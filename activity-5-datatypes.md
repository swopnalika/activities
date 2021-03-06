**Revise number systems: https://www.log2base2.com/number-system/decimal-number-system.html**

**Revise storage: https://www.log2base2.com/storage/how-data-is-stored-in-computer-memory.html**

**Revise datatype theory: https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html**

**Revise datatype: http://www.javalearningacademy.com/java-data-types/**

**Revise datatype: https://www.topperskills.com/tutorials/java/data-types-java.html**

**Revise Floating point representation: https://www.geeksforgeeks.org/introduction-of-floating-point-representation/**

**Revise Floating point precision: https://www.geeksforgeeks.org/difference-between-single-precision-and-double-precision**

**Revise Auto boxing & Auto unboxing: https://docs.oracle.com/javase/tutorial/java/data/autoboxing.html**

**1s complement**
* 1’s complement of a binary number is another binary number obtained by toggling all bits in it, i.e., transforming the 0 bit to 1 and the 1 bit to 0.
* Examples:  
  1's complement of "0111" is "1000"  
  1's complement of "1100" is  "0011" 

**2s complement**
* 2’s complement of a binary number is 1 added to the 1’s complement of the binary number.
* Examples:  
  2's complement of "0111" is  "1001"  
  2's complement of "1100" is  "0100" 


**Represent whole numbers (+ve / -ve ) or float point numbers (+ve / -ve) in binary format**

**Ques-convert between primtiive type and wrapper types**
* The automatic conversion of primitive data type into its corresponding wrapper class is known as autoboxing.
* For example, byte to Byte, char to Character, int to Integer, long to Long, float to Float, boolean to Boolean, double to Double, and short to Short.
```java
public class WrapperExample1{ 
 
public static void main(String args[]){  

 //Converting int into Integer  
int a=20;  
Integer i=Integer.valueOf(a); //converting int into Integer explicitly  
Integer j=a; //autoboxing, now compiler will write Integer.valueOf(a) internally  
  
System.out.println(a+" "+i+" "+j);  
 }
}  
```
***Output***  
20 20 20

* The automatic conversion of wrapper type into its corresponding primitive type is known as unboxing.
* It is the reverse process of autoboxing.
```java
public class WrapperExample2{   
 
public static void main(String args[]){
 
//Converting Integer to int    
Integer a=new Integer(3);    
int i=a.intValue(); //converting Integer to int explicitly  
int j=a; //unboxing, now compiler will write a.intValue() internally    
    
System.out.println(a+" "+i+" "+j);    
 }
}
```
***Output***  
3 3 3  

**Ques-convert string(decimal value) to long, int, short, byte**

**Ques-Understand the wrapper class hierachy. Explain the wrapper child classes for Number class**
* All the wrapper classes (Integer, Long, Byte, Double, Float, Short) are subclasses of the abstract class Number.
* The Number class is part of the java.lang package.


**Ques-Define auto boxing & auto unboxing with example**
* Converting a primitive value into an object of the corresponding wrapper class is called autoboxing. 
* For example, converting int to Integer class.
* Converting an object of a wrapper type to its corresponding primitive value is called unboxing.
* For example conversion of Integer to int

**Ques-Convert a string ("105") to integer. and print the doubleValue(), longValue(), byteValue(), floatValue(), shortValue(), toString()**

**Ques-Mention the fully qualified name of each wrapper class.**

**Ques Write the class definition for all wrapper class types.  Find  out the abstract methods peresent in the implemented interface.**
(Ex: public final class Float extends Number implements Comparable<Float>, Comparable: public int compareTo(T o); ).

