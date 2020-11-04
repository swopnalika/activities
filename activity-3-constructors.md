### Ques-1 ### 
**Write a simple example of a Product class where it uses this constructor with paremeterized constructor**

```java
public class Product {

    private String name;
    private String carType;

    // Constructor.
    public Product(){
        this.name = "No Name";
        this.carType = "No Type";
    }
    public Product(String model){
        this.name = "Honda " + model;
    }
    
    public Product(String model, String carType){
        this.name = model;
        this.carType = carType;
    }
    
    public String getName(){
        return this.name;
    }
    
    public String getCarType(){
        return this.name;
    }

    public static void main(String args[]){
        Product car = new Product("Civic");
        System.out.println( car.getName() );
        
        // Other Way To Initialize
        Product car = new Product("Civic","Sedan");
        System.out.println( car.getName() + " "+ car.getCarType() );
        
    }
}

```
### Ques-2 ###
**Does toString() method present in java.lang.Object class? If yes what the implementaion for toString() method given by java.lang.Object class**
* Yes, the toString() is present in java.lang.Object class.
* The toString() method returns the string representation of the object
* By overriding toString(), we can get the desired output, such as states of an object.
* By applying toString() on an object of a class, it will retuen the fully qualified class name and hexadecimal representation of hashCode separated by a @ symbol of the object.
### Ques-3 ###
**Override toString() method in the class A (as given below) such that it will print the value of i, j, k**
```java
public class Test {
    public static void main(String[] args) {
        A a = new A(10, 20);
        a.setK(400);
        System.out.println(a);
    }
}

class A {
    private int i;
    private int j;
    private int k;

    public A(int i, int j) {
        this.i = i;
        this.j = j;
    }

    public int getI() {
        return i;
    }

    public void setI(int i) {
        this.i = i;
    }

    public int getJ() {
        return j;
    }

    public void setJ(int j) {
        this.j = j;
    }

    public int getK() {
        return k;
    }

    public void setK(int k) {
        this.k = k;
    }
}
```
**Solution**
```java
public class Test {
    public static void main(String[] args) {
        A a = new A(10, 20);
        a.setK(400);
        System.out.println(a);
    }
}

class A {
    private int i;
    private int j;
    private int k;

    public A(int i, int j) {
        this.i = i;
        this.j = j;
    }

    public int getI() {
        return i;
    }

    public void setI(int i) {
        this.i = i;
    }

    public int getJ() {
        return j;
    }

    public void setJ(int j) {
        this.j = j;
    }

    public int getK() {
        return k;
    }

    public void setK(int k) {
        this.k = k;
    }

    @Override
    public String toString() {
        return "A{" +
                "i=" + i +
                ", j=" + j +
                ", k=" + k +
                '}';
    }
}
```
### Ques-4 ###
**What is StackOverflowError. When it occurs. It comes under which package in java library**  
* StackOverflowError is a compile time error in java.  
* It arises due to recursive function call, that finally leads to an infinity loop and finally JVM goes out of memory for the program.  
* This usually happens if we do not put a terminating code to the recursive funtion call.
* It comes under the library : java.lang.StackOverflowError  


### Ques-5 ###
**Will the below code compile? Find the output of the below code**
```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
    }
}

class A
{
    private int x =11;
    public A()
    {
        new A(10);
    }

    public A(int x)
    {
        this();
        this.x = x;
    }
}
```
* Yes, the above code will compile fine.
* But it will throw RunTime error : java.lang.StackOverflowError
* It happens because of the statement new A(10); calls the parameterized constructor and again the this(); inside parameterized constructor will invoke again the no argument constructor, and hence finally fall in a recursive infinity loop.
### Ques-6 ###
**Will the below code compile. If not why**
```java
class A
{
    private int x =11;
    public A()
    {
        this(10);
    }

    public A(int x)
    {
        this();
        this.x = x;
    }
}
```
* No, this time the code will not compile, it will show compile time error of Recursive Constructor Invokation
* Here a compile time error occurs as we are invokinng constructor using this(), which will refer to the same object & same object calling to the constructor, but in the above case the new keyword would creat new object each time for invoking the constructor, so that program will go out of memory of JVM where as this program will throw compile time error.

### Ques-7 ###
**Find the output with explanation**
```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
    }
}


class A
{
    private int x =11;
    public A()
    {
        this(10);
        if(x % 2 == 0)
        {
            System.out.println("even");
        }
        else
        {
            System.out.println("odd");
        }
    }
    
    public A(int x)
    {
        this.x = x;
    }
}
```
***Output***   
even
* The statement this(10); will invoke the parameterized constructore and inside that the value of x will be updated to 10 and 10%2 will be equal to zero, giving output as even.
### Ques-8 ###
**Will the below code compile?**
```java
class A
{
    public A()
    {
        new A();
    }
}
```
* On callinng the constructor, yes the code will compile but creat the error : StackOverflowError.
### Ques-9 ###
**Why the below code won't compile?**
```java
class A
{
    public A()
    {
        this();
    }
}
```
***This code will show compile time error : recurrsive contructor invokation***

### Ques-10 ###
**Find the output with explanation?**
```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
        System.out.println(a.hashValue == a.hashCode());
    }
}


class A
{
    public int i;
    public int hashValue;
    public A()
    {
        new A(10);
    }

    public A(int x)
    {
        this.i = x;
        this.hashValue = this.hashCode();
    }
}
```
***Output***  
False
* Inside class Test, we have created an object and assigned to an instance "a". So the call to constructor with no parameter will happen.
* But inside the no parameter constructor we have invoked the one parameter constructor using new keyword not by this. So inside one parameter constructor,the this will refer to the newly created object not the "a" instance and hence value of hashvalue will be updated for the new object only.
* So, the a.hasvalue gives the default integer value as 0 and a.hashCode() will produce the memory location whill will never be 0. Hence output is coming as false.
### Ques-11 ###
**Find the output with explanation?**
```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
        System.out.println(a.hashValue == a.hashCode());
    }
}

class A
{
    public int i;
    public int hashValue;
    public A()
    {
        this(10);
    }
    
    public A(int x)
    {
        this.i = x;
        this.hashValue = this.hashCode();
    }
}
```
* invoking one parameter constructor will also update the value for object "a" hence the value of hashvalue and hashCode() will be same.
### Ques-12
**Access Modifiers & Packages. Find the compilation errors & why? Find the output also by fixing them.**
```java
package com.pkg1;

class A
{
  private int i = 10;
  public int j = 100;
  int k = 50;
}

package com.pkg1;
class B
{
  public static void main(String[] args)
  {
    A a = new A();
	System.out.println(a.i);
	System.out.println(a.j);
	System.out.println(a.k); // why this is accessible?
  }
}

package com.pkg2;
class B
{
  public static void main(String[] args)
  {
    A a = new A();
	System.out.println(a.i);
	System.out.println(a.j);
	System.out.println(a.k); // why this is not accessible?
  }
}
```
## soln.
### Errors :
***Inside same package (com.pkg1)  
inside same class :***
private, public, protected, default acces modiferes are accessible  
***Inside same package (com.pkg1)  
different class:***
 public, protected, default acces modiferes are asscesable but private not accessible.   
 ***Different package (com.pkg1)***
 Only public access modifier is accesable  
 
* Hence for com.pkg1 : inside class B the public and default field is accesible but the private one is not accessible.

**Solution to the error**
* We can define a getter for the private field and access the value using the instance of class A. the code() is given below
```java
package com.pkg1;

public class B {
   public static void main(String[] args) {
       A a = new A();
//        System.out.println(a.i); // private access so not accessible
       System.out.println(a.getI()); // definig a public getter
       System.out.println(a.j);
       System.out.println(a.l);
       System.out.println(a.k); // why this is accessible?
   }
```
### Errors for com.pkg2 :

* Only sout(a.j); is accessible
* Other two have private and default access so these can't be accessible,

**Solution to the error**
* We have to import the package com.pkg1; and also need getters inside class A of pkg1 to access the field. The code is as follows
```java
package org.com.pkg2;
import org.com.pkg1.*; // importing pacjage
public class B {
    public static void main(String[] args) {
        A a = new A();
        System.out.println(a.i);
        System.out.println(a.getI()); // using getters
        System.out.println(a.getK()); // using getters
        System.out.println(a.j);
//        System.out.println(a.k); // default modifiers not accessible
    }
}
```
### Ques-13 ###
**Why we use getters and setters for a class. Give an example**
* Getters and setters are used to protect your data, particularly when creating classes.
* For each instance variable, a getter method returns its value while a setter method sets or updates its value. 
* Given this, getters and setters are also known as accessors and mutators, respectively.
```java
public class Vehicle {
  private String color;
  
  // Getter
  public String getColor() {
    return color;
  }
  
  // Setter
  public void setColor(String c) {
    this.color = c;
  }

public static void main(String[] args) {
  Vehicle v1 = new Vehicle();
  v1.setColor("Red");
  System.out.println(v1.getColor());
}
}
```
**Output**    
Red
### Ques-14 ###
**Why it is good to have private fields with public getters & setters?**
* making the field private while the getter/setter method is public, so it can be accessed by any packages.
