### Ques-1 ###
Code example of inheritance. Reuse static/non-static method(s) & static/non-static variable(s).
```java

```
### Ques-2 ###
Code example of instanceof operator using classes as BaseParent->Parent->Child.
* Soln.
```java
interface Animal{}
class Mammal implements Animal{}

public class Dog extends Mammal {

   public static void main(String args[]) {
      Mammal m = new Mammal();
      Dog d = new Dog();

      System.out.println(m instanceof Animal);
      System.out.println(d instanceof Mammal);
      System.out.println(d instanceof Animal);
   }
}
```
* Output  
true  
true   
true  


### Ques-3 ###
Code example of super constructor.
* Soln   
```java
class A
{
    A(){
        super(); 
        System.out.println("class A");
    }
}

class B extends A{
    B(){
        super(); 
        System.out.println("class B");
    }
}

public class C extends B
{
    public static void main(String args[])
    {
        C c  = new C(); //Parent constructor will get called 
    }
}
}
```
* Output  
class A  
class B
### Ques-4 ###
Does multiple object created in inheritance hierarchy.
### Ques-5 ###
Does super constructor invocation creates one more object.
### Ques-6 ###
Code example of method hiding.
```java
class Parent {  

 public static void sleep() { 
  System.out.println("Sleeps at 11 PM");
  }
   } 
 
class Child extends Parent {  

 public static void sleep() {
  System.out.println("Sleeps at 9 PM"); 
  }
   }  

 public class Code {  

 public static void main(String[] args) {
  Parent p = new Parent(); 
  Parent c = new Child(); 
  p.sleep(); 
  c.sleep(); 
  }
   }
```
* Output  
Sleeps at 11 PM  
Sleeps at 11 PM

### Ques-7 ###
Code example of variable hiding.
```java
public class Shadowing
{
    int x = 10;
 
    void methodOne(int x)
    {
        //local x shadows or hides global x
 
        System.out.println(x);   //output : 20
    }
 
    public static void main(String[] args)
    {
        Shadowing shadow = new Shadowing();
        shadow.methodOne(20);
    }
}
```

* Class ‘Shadowing’ has global variabe ‘x’ and it’s scope is inside the class. ‘methodOne()’ of this class also has a local variable with the same name  and it’s scope is inside the method.
* If you try to print the ‘x’ inside the methodOne(), the value of local variable is printed but not that of global variable
* Because, local ‘x’ shadows or hides global ‘x’. This is called variable hiding or shadowing. 
### Ques-8 ###
Does static methods overridden.
### Ques-9 ###
Deos private methods overriden.
### Ques-10 ###
By default any class extends which class.
### Ques-11 ###
List down the public/protected (inherited) methods present in java.lag.Object class.
### Ques-12 ###
Find the output:
```java
class A
{
  public int i = 10;
  public int j = 20;
}
class B extends A
{
   public int i = 100;
   public int sumValue(int x)
   {
      return x + this.i + this.j +  super.i + super.j;
   }
}

class Test
{
  public static void main(String[] args)
  {
    A a = new B();
    int result = a.sumValue(a.i);
    System.out.println(result);
  }

}
```
### Ques-13 ###
Fix the code with all the approaches you know.
```java
class A
{
  private int i;
  public A(int i)
  {
     this.i = i;
  }
}

class B extends A
{
   public B()
   {
   
   }
}
```
