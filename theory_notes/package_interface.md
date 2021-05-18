# Java packages and interfaces

## Package

Packages are container for java classes.
***Syntax***

``` java
package pkg;
// pkg is package name
```

* It can be nested

### Access
<br>
|  | Private | No Modifier | Protected | Public |
| --- | --- | --- | --- | --- |
| Same class | Yes | Yes | Yes | Yes |
| Same package<br>`Subclass` | No | Yes | Yes | Yes |
| Same package<br>`Non-subclass` | No | Yes | Yes | Yes |
| Different package <br>`subclass` | No | No | Yes | Yes |
| Different package<br>`Non-Subclass` | No | No | No | Yes |

## Interface

Interface is much  similar to **abstract** class. It is used to define the methods which implementing class must implement.
***Syntax***
<br>
``` java
access interface name {
    return-type method-name1(parameter-list);
    return-type method-name2(parameter-list);
    type final-varname1 = value;
    type final-varname2 = value;
    // ...
    return-type method-nameN(parameter-list);
    type final-varnameN = value;
}
```

> Default access interface is only available to it's other member of the same package

<br>
### Accessing Implementations Through Interface References
<br>
``` java
// Callback - interface
// Client1 - A class which implements Callback
// Client2 - A class which implements Callback
Callback c = new Client1();
c.callback();

// assign it to another reference
c = new Client2();
c.callback();
```

### Partially implemented

If a class does implement full methods of the interface then that class should be declared as **Abstract**

### **Variable in interface**

All variable in interface should be <span style="color:  #202124;;">initialize</span> and they are implicitly **static and final.**
<br>
### Shared constants

We can use the above feature to share the constants b/w multiple classes or interfaces.

We can have a interface
<br>
``` java
public interface Run {
	int step = 10;
	String val = "Testing...";
}
```

and we can use this in any class like below.
<br>
``` java
System.out.println(Run.val);
// this class does't need to implement the interface
```

* Interface can be extended
*
