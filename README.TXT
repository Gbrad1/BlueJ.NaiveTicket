Project: naive-ticket-machine
Authors: David Barnes and Michael Kolling

This project is part of the material for the book

   Objects First with Java - A Practical Introduction using BlueJ
   Fourth edition
   David J. Barnes and Michael Kolling
   Pearson Education, 2008

It is discussed in chapter 2.

Purpose of project: To illustrate the basics of fields, constructors, and methods.
How to start this project: Create one or more TicketMachine objects.

See the doc directory for the chapter PDF

# NaiveTicket

The second Objects lab, from the BlueJ book's second chapter.

Look for the [Chapter 2 file](./doc/BlueJ-objects-first-ch2.pdf) you need in the [doc](./doc) folder.
There is 35 pages of reading and exercises in the chapter.

Work through all these exercises. You edit this file with your answers for these exercises.

### Exercise 2.1
* Create a TicketMachine object on the object bench.
-_-_-_-_-_-_-_-_-_-_-
 input 500 for value
-_-_-_-_-_-_-_-_-_-_-
* Upon viewing its methods, `getBalance`, `getPrice`, `insertMoney`, `printTicket`.
* Use `getPrice` method to view the value of the price of the tickets that was set when this object was created.
-_-_-_-_-_-_-_-_-_-_-
 The 'getPrice' returns a private int value of 500.
-_-_-_-_-_-_-_-_-_-_-
* Use `insertMoney` method to simulate inserting an amount of money into the machine.
-_-_-_-_-_-_-_-_-_-_-
 Inserted 1000
-_-_-_-_-_-_-_-_-_-_-
* Use `getBalance` to check that the machine has a record of the amount inserted.
-_-_-_-_-_-_-_-_-_-_-
 I am confirming that the 'getBalance' output 1000.  
-_-_-_-_-_-_-_-_-_-_-
	* You can insert several separate amounts of money into the machine, just like you might insert multiple coins or notes into a real machine. Try inserting the exact amount required for a ticket. As this is a simple machine, a ticket will not be issued automatically, so once you have inserted enough money, call the `printTicket` method. A facsimile ticket should be printed in the BlueJ terminal window.

	-_-_-_-_-_-_-_-_-_-_-
	 Terminal did not output any results. The String output when 'printTicket()' was run is "Ticket price: 500 cents. Your total is 1500."
	-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.2
* What value is returned if you check the machine’s balance after it has printed a ticket?

-_-_-_-_-_-_-_-_-_-_-
 The 'private int value' returns 0
-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.3
* Experiment with inserting different amounts of money before printing tickets.
	* Do you notice anything strange about the machine’s behavior?
	-_-_-_-_-_-_-_-_-_-_-
  I input the below values one at a time.
	300
	200
	The number of tickets that are available is 2.

	I inserted 100 more cents and the ticket number is still 2 with a total balance of 600.

	I inserted 1000 cents which is enough for two tickets. The total balance is now 1600 and the total ticket numbers is still 2.

	I attempted to printTicket() and resulted in "Ticket price: 500 cents. Your total is 3600."

	Balance is now 0
	Ticket number is now 3

	This means that it took all of the money and returned the incorrect number of tickets.
	-_-_-_-_-_-_-_-_-_-_-
	* What happens if you insert too much money into the machine – do you receive any refund?
	-_-_-_-_-_-_-_-_-_-_-
	 Inserted 2000 cents
	 printTicket() now outputs the total number of money put into the machine. The user is charged an extra 3600.  
	-_-_-_-_-_-_-_-_-_-_-
	* What happens if you do not insert enough and then try to print a ticket?
	-_-_-_-_-_-_-_-_-_-_-
	 The output still adds to the total and a ticket is printed.
	-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.4
* Try to obtain a good understanding of a ticket machine’s behavior by interacting with it on the object bench before we start looking at how the `TicketMachine` class is implemented in the next section.

### Exercise 2.5
* Create another ticket machine for tickets of a different price.
	* Buy a ticket from that machine.
	* Does the printed ticket look different?
	-_-_-_-_-_-_-_-_-_-_-
	 The output states the ticket price of the new machine(1000) and the total which is 1000. So far it appears normal.  
	-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.6
* Write out what you think the outer wrappers of the `Student` and `LabClass` classes might look like – do not worry about the inner part.

-_-_-_-_-_-_-_-_-_-_-
public class Student() {

}

public class LabClass() {

}
-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.7
Does it matter whether we write<br>
`public class TicketMachine`<br>
or<br>
`class public TicketMachine`<br>
in the outer wrapper of a class?
-_-_-_-_-_-_-_-_-_-_-
The Object should be named, "public class TicketMachine" because 1. we are determining that "TicketMachine" is the name of the class. This would allow us to then create a constructor using the same naming convention of the object to initialize it.
-_-_-_-_-_-_-_-_-_-_-

* Edit the source of the `TicketMachine` class to make the change and then close the editor window.
	* Do you notice a change in the class diagram?
	-_-_-_-_-_-_-_-_-_-_-
	 Yes, the widgets for "TicketMachine" and "TicketMachineTest" are clearly broken.  
	-_-_-_-_-_-_-_-_-_-_-
	* What error message do you get when you now press the compile button?
	-_-_-_-_-_-_-_-_-_-_-
	 We get 4 error messages:
	 1. <identifier> expected
	 2. <identifier> expected
	 3. illegal start of expression
	 4. invalid method declaration: return type required  
	-_-_-_-_-_-_-_-_-_-_-
	* Do you think this message clearly explains what is wrong?
	-_-_-_-_-_-_-_-_-_-_-
	 Maybe not at this moment in my understanding of Java but it it's not impossible to work with.  
	-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.8
* Check whether or not it is possible to leave out the word `public` from the outer wrapper of the `TicketMachine` class.
-_-_-_-_-_-_-_-_-_-_-
 I received no errors for this. From an initial perspective, this works fine.
-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.9
* From your earlier experimentation with the ticket machine objects within BlueJ you can probably remember the names of some of the methods – `printTicket`, for instance.
	* Look at the class definition in Code 2.1 and use this knowledge, along with the additional information about ordering we have given you, to try to make a list of the names of the fields, constructors, and methods in the `TicketMachine` class.
	* Hint: There is only one constructor in the class.

	-_-_-_-_-_-_-_-_-_-_-
	 -fields-
	 		price
			Balance
			total
			ticketNumber

	 -constructors-
	 		There is only one constructor and that is "public TicketMachine".

	 -methods-
	 		getPrice(), getTicketNumber(), getBalance(), insertMoney(), calculateTotal(), incrementTicketNumber(), printTicket()
	-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.10
* Do you notice any features of the constructor that make it significantly different from the other methods of the class?
-_-_-_-_-_-_-_-_-_-_-
 The constructor in this case is the same name as the Class. As it should be. The constructor also sets the values for the fields which were defined under the main class.   
-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.11
* What do you think is the type of each of the following fields?

```java
private int count; <-- integer
private Student representative; <-- Student
private Server host; <--- Server
```

### Exercise 2.12
* What are the names of the following fields?

```java
private boolean alive; <-- alive
private Person tutor; <-- tutor
private Game game; <-- game
```
### Exercise 2.13

In the following field declaration from the TicketMachine class<br>

```java
private int price;
```
does it matter which order the three words appear in?
-_-_-_-_-_-_-_-_-_-_-
 Yes
-_-_-_-_-_-_-_-_-_-_-
* Edit the `TicketMachine` class to try different orderings. After each change, close the editor.
	* Does the appearance of the class diagram after each change give you a clue as to whether or not other orderings are
possible?
-_-_-_-_-_-_-_-_-_-_-
 Yes, they are wrong.   
-_-_-_-_-_-_-_-_-_-_-
	* Check by pressing the compile button to see if there is an error message.
	* Make sure that you reinstantiate the original version after your experiments!

### Exercise 2.14
* Is it always necessary to have a semicolon at the end of a field declaration?
-_-_-_-_-_-_-_-_-_-_-
 Yes, or else it will skip the white space that comes after and immediately complete all code until a ';' is reached.  
-_-_-_-_-_-_-_-_-_-_-
* Once again, experiment via the editor.
* The rule you will learn here is an important one, so be sure to remember it.


### Exercise 2.15
* Write in full the declaration for a field of type `int` whose name is `status`.
-_-_-_-_-_-_-_-_-_-_-
 private int status;
-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.16
* To what class does the following constructor belong?
```
public Student(String name)
```
-_-_-_-_-_-_-_-_-_-_-
 The Student class  
-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.17
* How many parameters does the following constructor have and what are their types?
```
public Book(String title, double price)
```
-_-_-_-_-_-_-_-_-_-_-
 The constructor belongs to the class "Book" and has the below two parameters
 1. title which has the primitive data type of double
 2. price which has has the data type of "String".
-_-_-_-_-_-_-_-_-_-_-

### Exercise 2.18
* Can you guess what types some of the `Book` class’s fields might be?
-_-_-_-_-_-_-_-_-_-_-
 Field examples for "Book"
 private String Title;
 private int numberOfPages;
 private int numberOfCopies;
 private double price;  
-_-_-_-_-_-_-_-_-_-_-
* Can you assume anything about the names of its fields?
-_-_-_-_-_-_-_-_-_-_-
 As stated above, we can assume the data types of these fields based on the values that would be assigned to the fields. 
-_-_-_-_-_-_-_-_-_-_-

READ upto and INCLUDING section 2.15 of this chapter.
