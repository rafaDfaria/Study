monday, 02. January 2017 12:28
#YDKJS UP & Going
##Notes Chapter1: Into Programming.


**CODE:** 
The source code of a program, statements set line by line to tell the computer what tasks to perform.

**Statements:**
A group of words, numers and operators to perform an specfic task.

**Expressions:**
An expression is any reference to a variable or value, or a set of variables and valueus combined with operators.
2 = Literal value expression
n = variable expression
n * 2 = arithmetic expression
y = n * 2 assignment expression

**Executing a Program:**
Your source code aka just *CODE*, needs to be interpreted or compiled to be executed by computers.

Javascript is interpreted each time it's run.

**Output:**

Gives a message to the user, in Javascript we can use:
*console.log()* Show a message in console.
*alert();* create a pop-up box on the users screens, user needs to hit ok button to close.

**Input:**
Usually we'll get input from users using the HTML to show a text box and use Javascript to gather information from that text box.
But on the book the easier way to do that is using the *prompt("")* command.
like n = prompt ("insert your value to be stored by n).

**Operators:**

Assignment: =

Math: + (adition), - (substraction), * (multiplication), / (division)

Compound Assignment: +=, -=, *= and /=
combines math operators with assignment, like ( a += 2 **==** a = a + 2).

Object Property Acess: **.** as in console.log(), console is an object and log is it's value.

Equality: 

Comparison: < > <= >=

Lógical: && (AND) || (or)

Note: For much more detail, and coverage of operators not mentioned here, see the Mozilla Developer Network (MDN)'s "Expressions and Operators" (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators).

**Values & Types:**

Numbers, Strings and Booleans (true or false).

String: "I am a string";
String: 'I am also a string';
Number: 42;
Boolean: true;
Boolean: false;

**Converting Between Types:**

Coercion is the action of converting an Type into another, 

var a = "42";
var b = Number( a );

console.log( a );   // "42" (string)
console.log( b );   // 42

**NOTE:**However, implicit coercion is a mechanism that can be learned, and moreover should be learned by anyone wishing to take JavaScript programming seriously. Not only is it not confusing once you learn the rules, it can actually make your programs better! The effort is well worth it. For more information on coercion, see Chapter 2 of this title and Chapter 4 of the Types & Grammar title of this series.

**Code Comments:**
Doens't exist an universal rule about how to comment a code, but:

- Code without comments is suboptimal.
- Too many comments (one per line, for example) is probably a sign of poorly written code.
- Comments should explain why, not what. They can optionally explain how if that's particularly confusing.

// This is a single-line Comment
/* This a mult line
coment */

**Variables:**

 Javascript uses the Dynamic typing, which allows a variable to hold any type of value at any time.
 
 Variables can be set as constants, when you declare a variable with a value and INTEND for that value to not change throughtout the program.
 
 By convention constants are usually capitalized, with underscores between multiple words. **VAR_CONSTANT**
 
 Example of constant:
 
 var **TAX_RATE** = 0.08;    // 8% sales tax

var amount = 99.99;

amount = amount * 2;

amount = amount + (amount * **TAX_RATE**);

console.log( amount );              // 215.9784
console.log( amount.**toFixed( 2 )** ); // "215.98"
.toFixed(..) let us specify how many decimal places we'd like the number shows.

The newst version of JavaScript include a new way to declare constants, by using *const* instead of *var*:

// like in the ES6:
const TAX_RATE = 0.08;
var amount = 99.99;

**Blocks:**

A block is defined by wrapping one or more statements inside a curly-brace pair { .. } usually only used in if's, loops, etc.

**Conditionals:**

ifs, if elses, switchs, just like in C.

JavaScript defines a list of specific values that are considered "falsy" because when coerced to a boolean, they become false -- these include values like 0 and "". Any other value not on the "falsy" list is automatically "truthy" -- when coerced to a boolean they become true. Truthy values include things like 99.99 and "free". See "Truthy & Falsy" in Chapter 2 for more information.

**Loops:**

Used to repeat a set of actions until a certain condition fails, loops can take different forms, but they all satisfy this basic behavior.

A loop includes the test condition as well as a block (typically as { .. }). Each time the loop block executes, that's called an *iteration*.

Example of While and Do While.

while (numOfCustomers > 0){
	console.log( "How may I help you?);
	numOfCustormers = numOfCustomers -1;
	}

// Versus

Do {
	console.log ("How may I help you?");
	numOfCustomers = numOfCustomers -1;
}while (numOfCustomers >0);

The only practical difference between these loops is whether the conditional is tested before the first iteration (while) or after the first iteration (do..while), even if the condition is false the (do..while) will run it just the first time.

The *for* loop:
The for loop has three clauses: the initialization clause (var i=0), the conditional test clause (i <= 9), and the update clause (i = i + 1). So if you're going to do counting with your loop iterations, for is a more compact and often easier form to understand and write.

**Function:**

A function is a reusable piece of your code, is generally a named section of code that can be "called" by name, and the code inside it will be run each time.

function printAmount(){
	console.log (amount.toFixed(2));
	}
var amount = 99.99;
printAmount();
amount = amount * 2;
printAmount();
**NOTE** Function is a must to make reusable and optimal code, **MASTER IT**.





**Scope:**

The current context of execution. The context in which values and expressions are "visible," or can be referenced. If a variable or other expression is not "in the current scope," then it is unavailable for use. 

A function serves as a closure in JavaScript, and thus creates a scope, so that (for example) a variable defined exclusively within the function cannot be accessed from outside the function or within other functions.


function one() {
    // this `a` only belongs to the `one()` function
    var a = 1;
    console.log( a );
}

function two() {
    // this `a` only belongs to the `two()` function
    var a = 2;
    console.log( a );
}

one();      // 1
two();      // 2

An scope can be nested inside another scope, just like blow up a balloon inside another balloon.
Scopes can also be layered in a hierarchy, so that child scopes have access to parent scopes, but not vice versa.

function outer() {
    var a = 1;
    function inner() {
        var b = 2;
        // we can access both `a` and `b` here
        console.log( a + b );   // 3
            }
                inner();
    // we can only access `a` here
    console.log( a );           // 1
}
outer();


#Review

Learning programming is like build a tower of blocks.
You shall first put one block, and another block on the top, and another one, and so goes on.
One concept at a time, I have to know the foundation of those concepts.

- You need operators to perform actions on values.
- You need values and types to perform different kinds of actions like math on numbers or output with strings.
- You need variables to store data (aka state) during your program's execution.
- You need conditionals like if statements to make decisions.
- You need loops to repeat tasks until a condition stops being true.
- You need functions to organize your code into logical and reusable chunks.

Code comments are one effective way to write more readable code, which makes your program easier to understand, maintain, and fix later if there are problems.

Finally, don't neglect the power of practice. The best way to learn how to write code is to write code.







 
 
