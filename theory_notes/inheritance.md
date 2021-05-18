# Java Specs

## Default Access modifire

``` java
class Test{
	int val;
	void print(){
		// do something...
	}
}
```

`val` and `print` will be by default `public` under it's own package. It can not be accessed out side of it's package.

## Static Methods

Method declared as static have several restrictions:

* They only cal **static** methods
* They must access only **static** data
* They can not call `this` and `super` in any way

## static Block

We can have a static block, which can initialize all the static data before the object creation.

``` java
class Test{
	static int a = 90;
	static int b;
	static {
		b = a+5;
	}
}
```

This static block will run as soon as the class is loaded. It'll run before the `main()` function.

## Inner class

* inner class is declared inside outer class
* inner class instance has directly access to it's outer member even private memebers. But, it should not `static`.
* outer can not access inner
* `static` inner class has to create an object of outer in order to access outer members.

## Variable Length Arguments

``` java
// v is treated as array by compiler
void varArgs(int ...v){
	// do somethingg...
}

// call
varArgs(1,2,3);

// fixed parameter
valid: varArgs(int a, int b, int ...args){}
invalid: varArgs(int a, int ...args, int b){}
```

## Super class reference to subclass

When a super class reference variable points to any sub class object, then that variable can only access the data which are part of super class.

## `super`

`super` can access data members and methods of just super class.

`super.member`.

> There is one more restriction to be aware of: there must be only one varargs parameter

## Using Abstract classes

**Syntax**

``` java
abstract type name(parameter-list);
```

### Facts

* Any class that contain one or more abstract methods must be declared as abstract.
* There can be no objects of an abstract class.
* We can not declare **abstract** constructors or static methods.
* Any subclass of an abstract class must define all of the super class methods or must be declared as abstract itself.
* Abstract class can have data members.
* Abstract class reference can be used as pointer of it's sub class instance.

## Using final with Inheritance
**syntax**
```java
final void meth() {
    System.out.println("This is a final method.");
}
```

### Facts

* Methods declared as final can not be overiden
* It can improve performance, because compiler knows that this method can not be overridden by any subclass. 
* It's call is resolved at compile time, rather than run time.

## Using final to Prevent Inheritance
**syntax**
```java
final class A {
// ...
}
```
### Facts

* Methods of a class declared as `final` will automatically declared as `final`.


