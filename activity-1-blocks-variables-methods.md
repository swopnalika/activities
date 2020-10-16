# Activity 1 : Blocks
* Define a class called Test.java
* Add main method.
* Write System.out.println statement inside method with some message.
* Define 2 static blocks with some statements inside it.
* Create object of Test class inside main method using new. Run the Test class. See the output.
### Soln. ###
```java
public class Test {
    static int a;
    static int b;
    static int c;
    
    //static block1
    static {
        System.out.println("I am in static block 1");
        a = 10;
        b = 20;
        c = a+b;
     }
     
    //static block2
    static
    {
        System.out.println("I am in static block 2");

    }
    //non-static block
    {
        System.out.println("I am in non static block");
    }
    public static void main(String args[]) {
        new Test();
        System.out.println("I am in main method");
        System.out.println("Value of a = " + a);
        System.out.println("Value of b = " + b);
        System.out.println("sum of two numbers = " + c);
        
    }
}
```
***Output***  
I am in static block 1  
I am in static block 2  
I am in non static block  
I am in main method  
Value of a = 10  
Value of b = 20  
sum of two numbers = 30

# Activity 2 : Static Methods
* Define a class called Test.java
* Define main method.
* Define 2 static methods called as m1() and m2() with both having void return type. Add some statements in both of the methods.
* Call m1() from m2()
* From main method call m1() without creating object.
* Add a static block. call m1() from static block without using object. verify the output.
### Soln. ###
```java
public class Test{

    //find summation of series 1^2+2^2+3^2.....n^2


    static int n = 100;

    static void m1() {
        int sum = 0;
        for (int i = 1; i < n; i++) {
            sum = sum + (i * i);
        }
        System.out.println(" sum=" + sum);
    }

    static void m2() {
        System.out.println("I m in static block 2");
        m1();  // calling m1 from m2
    }

    public static void main(String args[]) {
        Test.m1(); //calling m1 without creating object
        m2();
    }
}
```
***Output***  
sum=328350  
I m in static block 2  
sum=328350

# Activity 3 : Non Static Methods
* Define a class called Test.java
* Define main method.
* Define 2 non-static methods called as m1() and m2() with both having void retunr type. Ass some statements in both of the methods.
* call m1() from m2().
* Inside main method create object of Test using new. Test var = new Test().
* using above reference variable of Test call m1()
* Add a non static block. call m1() from non static block. verify the outout.
### Soln. ###
```java
public class Test {

    void m1() {
        System.out.println("I m in non-static block 1");
    }

    void m2() {
        System.out.println("I m in non-static block 2");
        m1(); //calling m1 from m2
    }

    public static void main(String args[]) {
        Test var = new Test(); //object of test
        var.m1(); //calling m1 from object var
        var.m2();
    }
}


```
***Output***  
I m in non-static block 1  
I m in non-static block 2  
I m in non-static block 1  

# Activity 4 : Parameterized Methods
* Define a class called Test.java
* Define a main method.
* Create a static method sum(int x, int y) and having return type as int. This should give sum of x + y
* Call sum(10, 20) from main method and print the result inside main method
```java
public class Test {

    //static method with variable passed in parameter
    public static int sum(int x, int y) {
        return x + y;
    }

    //main method
    public static void main(String[] args) {
        System.out.println("sum of the 2 numbers:");
        System.out.println(sum(10, 20));

    }
}
```
***Output***  
sum of the 2 numbers:  
30
# Activity 5 : Variable Declaration
* You may see compilation error with this activity. Define a class called Test.java
* Define a main method.
* Declare a static variable x of type int at the class level. Declare a non static varaible y of type String at the class level. Run the class. Verify output.
* Define a static block. print the value of x & y inside static block. Run the class. Verify output.
* Define a non-static block. print the value of x & y inside non-static block. Run the class. Verify output.
* Define a static method m1() with void return type. print the value of x & y inside static method. Run the class. Verify output.
* Define a non-static method m2() with void return type. print the value of x & y inside non-static method. Run the class. Verify output.
* print the value of x & y inside main method. Run the class. Verify output.
* Inside main method create object of Test class using new. Test var = new Test();
* call m2() using the reference variable var. Run the class. Verify output.
* Inside main method call m1() without object. Run the class. Verify output.
* What is the default value for x and y you are getting here?
### Soln. ###
```java
public class Test {
    private static int x;
    public String y;

    static {
        System.out.println(x);
        System.out.println(y); // compile time error as non static field can't be accessed from a static block
    }

    {
    // non static block will not be executed until the creation of object
        System.out.println(x);
        System.out.println(y);
    }

    public static void m1(){
    // method will not be executed until the method call - no need of object to call static method.
        System.out.println(x);
        System.out.println(y); // compile time error
    }

    public void m2(){ 
     // method will not be executed until the method call - need an object to call the non-static method.
        System.out.println(x);
        System.out.println(y);
    }

    public static void main(String[] args) {
        System.out.println(x);
        System.out.println(y); // compile time error - non- static can not be called from static context
        Test var = new Test(); // this will invoke non static block
        var.m2(); // call m2() and execute it
        m1(); // direct call to static method from a static block
        // the default value of string field is = null
        // the default value of int field is = 0
    }
}

```
***Output***     
0  
0  
0  
null  
0  
null  
0  




# Activity 6 : Variable Declaration & Intialization
* You may see compilation error with this activity. Define a class called Test.java
* Define a main method.
* Declare a static variable x of type int at the class level. Declare a non static varaible y of type String at the class level. Run the class. Verify output.
* Define a static block. Initialize x = 20; and print x. Run the class. Verify output. 
* Define a static method m1(). Initialize x = 30; and print x. Run the class. Verify output.
* From the main method call m1() without object. Run the class. Verify output.
* Define a non static block. Initialize y = "hello"; and print y. Run the class. Verify output.
* Define a non static method m2(). Initialize y = "bye"; and print y. Run the class. Verify output.
* Inside main method create object of Test using new. Test var = new Test(); From the main method call var.m2(). Run the class. Verify output.
### Soln. ###
```java
public class Test {
    private static int x;
    public String y;

    static { // static blocks executes at the time of class load
        x = 20;
        System.out.println(x);
    }

    { // non static block will not be executed until the creation of object
        y = "hello";
        System.out.println(y);
    }

    public static void m1(){// method will not be executed until the method call - no need of object to call static met.
        x = 30;
        System.out.println(x);
    }

    public void m2(){ // method will not be executed until the method call - need a object to call the non static method
        y = "bye";
        System.out.println(y);
    }

    public static void main(String[] args) {
        System.out.println(x);
        Test var = new Test(); // this will invoke non static block
        var.m2(); // call m2() and execute it

    }
}
```
***Output***  
20  
20  
hello  
bye  
# Activity 7 : Final Variables or Constants
* Define a class called Test.java
* Define a main method.
* Declare a final static variable x of int type. Try to initialize this 2 times.
* Declare a final non static variable y of int type. Try to initialize this 2 times.
