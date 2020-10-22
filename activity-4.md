### Ques-1 ###
Code example of inheritance. Reuse static/non-static method(s) & static/non-static variable(s).
### Ques-2 ###
Code example of instance of operator using classes as BaseParent->Parent->Child.
### Ques-3 ###
Code example of super constructor.
### Ques-4 ###
Does multiple object created in inheritance hierarchy.
### Ques-5 ###
Does super constructor invocation creates one more object.
### Ques-6 ###
Code example of method hiding.
### Ques-7 ###
Code example of variable hiding.
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
