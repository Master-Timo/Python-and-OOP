# Object Oriented Programming in Python

01. [Classes](https://github.com/arvimal/Python-and-OOP#01-classes)
02. [Instances, Instance methods, Instance attributes](https://github.com/arvimal/Python-and-OOP#02-instances-instance-methods-instance-attributes)
03. [Class attributes](https://github.com/arvimal/Python-and-OOP#03-class-attributes)
04. [The __init__ constructor](https://github.com/arvimal/Python-and-OOP#04-the-init-constructor)
05. [Inheritance (Inheriting {attributes,methods,constructors etc..})](https://github.com/arvimal/Python-and-OOP#05-inheritance-inheriting-attributesmethodsconstructors-etc)
06. [Encapsulation](https://github.com/arvimal/Python-and-OOP#06-encapsulation)
07. [Polymorphism](https://github.com/arvimal/Python-and-OOP#07-polymorphism)
08. [Instance methods](https://github.com/arvimal/Python-and-OOP#08-instance-methods)
09. [Class methods](https://github.com/arvimal/Python-and-OOP#09-class-methods)
10. [Multiple Inheritance and how lookup works](https://github.com/arvimal/Python-and-OOP#10-multiple-inheritance-and-how-lookup-works)
11. [Method Resolution Order (MRO)](https://github.com/arvimal/Python-and-OOP#11-method-resolution-order-mro)
12. [Decorators](https://github.com/arvimal/Python-and-OOP#12-decorators)
13. [Static methods](https://github.com/arvimal/Python-and-OOP#13-static-methods)
14. [Class methods](https://github.com/arvimal/Python-and-OOP#14-class-methods)


# NOTES
------------
#### 01. Classes

------------
#### 02. Instances, Instance methods, Instance attributes

------------
#### 03. Class attributes

------------
#### 04. The __init__ constructor

------------
#### 05. Inheritance (Inheriting {attributes,methods,constructors etc..})

------------
#### 06. Encapsulation

------------
#### 07. Polymorphism

------------
#### 08. Instance methods

------------
#### 09. Class methods

-------------
#### 10. Multiple Inheritance and how lookup works

* Any class can inherit from other classes.
* Any python class can inherit from multiple classes at the same time.
* The class that inherits another class is called the Base/Child class.
* The class being inherited by the Child class is called the Parent class.
* The child class inherits any methods and attributes defined in the parent classes.

-------------
#### 11. Method Resolution Order (MRO)

* Python has a method lookup order, called `MRO` (Method Resolution Order)
* The MRO path can be printed to stdout using `<class-name>.mro()`
* Python, by default, uses a depth-first ordering while following MRO.

* ie.. Imagine you have four classes, A, B, C, D.

  1. You instance is created from `D`.
  2. `D` inherits from `B` and `C`
  3. `B` inherits from `A`.
  4. Both `C` and `A` has a method with the same name.
  5. Since python follows a depth-first MRO, the method is called from `A`

REFERENCE: Check the code examples in:
  * 14-multiple-inheritance-1.py
  * 15-multiple-inheritance-2.py

In some cases, the inheritance can get quite cumbersome when multiple classes inherit from the same classes, in multiple levels. 

**NOTE** : From Python2.3, the MRO has changed slightly in order to speed up the method lookups.

The MRO lookup now skips/omits the initial occurrences of classes which occurs multiple time in the lookup path.

* Example:
  1. Four classes, A, B, C, D.
  2. D inherits from both B and C
  3. B inherits from A
  4. C inherits from A
  5. Both C and A contains a similar named method.
  6. Your instance in created from class D.
  7. You try a lookup for the method which is named both in A and C.
  8. The usual lookup should be D -> B -> A -> C -> A
  	a. Hence since the method exists in A and C, it should return from A.
  	b. But since the class A is occurring twice and due to the new MRO method, the lookup will be 
  	D -> B -> C -> A.
  9. The lookup should return the method from class C, rather than A.

REFERENCE: Check the code example in:
  * 16-multiple-inheritance-3.py

--------------
#### 12. Decorators

--------------
#### 13. Static methods

--------------
#### 14. Class methods

--------------
#### 15.