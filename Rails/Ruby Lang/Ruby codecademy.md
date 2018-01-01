
## Data Types: Numbers, Strings, Booleans

In Ruby, your information (or data) can come in different types. There are three data types in Ruby that we're interested in right now: 

* numbers, 
* booleans (which can be true or false), and 
* strings (words or phrases like "I'm learning Ruby!").

Computer programs exist to quickly analyze and manipulate data. For that reason, it's important for us to understand the different data types that we can use in our programs.

Reminder: never use **quotation marks** (' or ") with booleans, or Ruby will think you're talking about a string (a word or phrase) instead of a value that can be true or false. It's also important to remember that Ruby is case-sensitive (it cares about capitalization).

**Instructions**

Set the following variables to the corresponding values:

my_num to the value 25
my_boolean to the value true
my_string to the value "Ruby" (note the capitalization!)

A :

	my_num = 25     # Add your code here!

	my_boolean = true     # And here!

	my_string = 'Ruby'    # Also here.

---

## Variables

One of the most basic concepts in computer programming is the **variable**. You can think of a variable as a word or name that grasps a single value. For example, let's say you needed the number 25 from our last example, but you're not going to use it right away. You can set a variable, say my_num, to grasp (memahami) the value 25 and hang onto it for later use, like this:

my_num = 25

Declaring variables in Ruby is easy: you just write out a name like **my_num**, use = to assign it a value, and you're done! If you need to change a variable, **no sweat**: just type it again and hit = to assign it a new value.

**Instructions**

Set the variable my_num to the value 100, then click the Run button to run your code.

A :

	my_num = 100

---

## Math

Ruby isn't limited to simple expressions of assignment like my_num = 100; it can also do all the math you learned about in school.

There are six arithmetic operators we're going to focus on:

* Addition (+)
* Subtraction (-)
* Multiplication (*)
* Division (/)
* Exponentiation (**)
* Modulo (%)

The only ones that probably look weird to you are **exponentiation** and **modulo**. 

**Exponentiation** raises one number (the base) to the power of the other (the exponent). For example, **2**3** is 8, since 2**3 means "give me 2 * 2 * 2" (2 multiplied together 3 times). 3**2 is 9 (3 * 3), and so on.

**Modulo** returns the remainder of division. For example, 25 % 7 would be 4, since 7 goes into 25 3 times with **4 left over**.

**Instructions**

Do a little math practice in the editor. When you're ready, click Save & Submit Code to move on to the next exercise.

A :

	5**3 = 125

---

## 'puts' and 'print'

The **print** command just takes whatever you give it and prints it to the screen. 
**puts** (for "put string") is slightly different: it adds a new (blank) line after the thing you want it to print. You use them like this:

puts "What's up?"
print "Oxnard Montalvo"

No parentheses or semicolons needed!

Instructions
In the editor, use at least one print statement and at least one puts statement. You can print out any strings you like! (Make sure to put your strings between quotes, like this: "Hello!".)

---

## Everything in Ruby is an Object

Because everything in Ruby is an object (more on this later), **everything in Ruby has certain built-in abilities called methods**. You can think of methods as **"skills"** that certain objects have. For instance, strings (words or phrases) have built-in methods that can tell you the **length** of the string, reverse the string, and more.

We also promised to tell you more about the interpreter. **The interpreter is the program that takes the code you write and runs it**. You type code in the editor, the interpreter reads your code, and it shows you the result of running your code in the console (the bottom window on the right).

---

## The '.length' Method

Methods are summoned using a .. If you have a string, "I love espresso", and take the .length of it, Ruby will return the length of the string (that is, the number of characters—letters, numbers, spaces, and symbols). Check it out:

	"I love espresso".length
	# ==> 15

Taking the length of input can be useful if, for example, you want to make a website that takes credit card payments. Ruby can check to make sure the credit card number appears to be valid.

**Instructions**

Call the .length method on your name (remember to use quotes around your name).

A :

	dyomedio.length

---

## The '.reverse' Method

The **.reverse** method is called the same way .length is, but instead of asking Ruby to tell you how long a string is, it spits out a backwards version of the string you gave it. For instance,

	"Eric".reverse

will result in

	"cirE"

Reversing input can be useful if you want to sort a list of values from highest to lowest instead of lowest to highest. (We'll get to sorting in later lessons.)

**Instructions**

Call the .reverse method on your name. Don't forget those quotation marks around your name to make it a string!	

A :

	"Dyo Medio".reverse

	-> "oideM oyD"

---

## '.upcase' & '.downcase'

Let's try one more method (er, two methods). As you might have guessed, the .upcase and .downcase methods convert a string to ALL UPPER CASE or all lower case, respectively.

**Instructions**

Call .upcase on your name to make your name ALL CAPS and use puts to print it to the screen, like this:

	puts "eric".upcase
	# ==> ERIC
	
On the next line, call .downcase to make your name all lower case. Make sure to use puts so you can see it printed out!	

A :

	puts "Dyo Medio".upcase
	puts "Dyo Medio".downcase

	DYO MEDIO
	dyo medio
	nil

---

## Single-Line Comments

You probably saw us use the # sign a few times in earlier exercises. The # sign is for comments in Ruby. A comment is a bit of text that Ruby won't try to run as code: it's just for humans to read. Writing good comments not only clarifies your code for other people who may read it, but helps remind you of what you were doing when you wrote the code days, months, or even years earlier.

The # sign should come before your comment and affects anything you write after it, so long as you're on a single line. (We'll show you how to do multi-line comments in a second.) Check out these 

examples:

	# I'm a full line comment!
	"Eric".length # I'm a comment, too!

The second example will return 4, since the comment comes after the code that Ruby will execute.

**Instructions**

Write a comment in the editor. It can be anything you like!

A :

	# ini adalah comment
	"Dyo Medio".length # menghitung panjang karakter

	-> 9

---

## Multi-Line Comments

You can write a comment that spans multiple lines by starting each line with a #, but there's an easier way. If you start with =begin and end with =end, everything between those two expressions will be a comment. Take a look at this example:

	=begin
	I'm a comment!
	I don't need any # symbols.
	=end

Don't put any space between the = sign and the words begin or end. You can do that with math (2 + 5 is the same as 2+5), but in this case, Ruby will get confused. =begin and =end also need to be on lines all by themselves, just as shown above.

**Instructions**

Create a multi-line comment in the editor to the right. Make sure =begin and =end are on their own lines!	

A :

	=begin

	ini adalah komentar
	saya sudah komentar
	sekali lag komentar
	akhirnya komentar

	=end

---

## Naming Conventions

There are many different kinds of variables you'll encounter as you progress through these courses, but right now we're **just concerned with regular old local variables**. By convention, these variables should start with a **lowercase letter and words should be separated by underscores**, like counter and masterful_method. Ruby won't stop you from starting your local variables with other symbols, such as capital letters, $s, or @s, but by convention these mean different things, so it's best to avoid confusion by doing what the Ruby community does.

**Instructions**

Create a variable name in the editor and set it equal to your name as a string (between quotes, like this: "Eric"). Your string can be capitalized, but name should be all lower case!

A :

	name = "Dyo Medio"

---

## Strings and String Methods

In Ruby, you can do this two ways: each method call on a separate line, or you can chain them together, like this:

	name.method1.method2.method3

Example: 

	name = "widyo bumi".downcase.reverse.upcase

	-> "IMUB OYDIW"

---

## What You'll Be Building

This project will help you create a small program that will read a user's input and correct his or her capitalization. Users can provide an almost infinite range of input, so it makes our lives easier as programmers to make their input standard before doing anything with it.

Instructions

Check out the code in the editor—we've added some new things that we'll be teaching you. Can you guess what it does? Click Save & Submit Code to find out!

Answer each question, and hit enter (return on some keyboards).

	print "What's your first name?"
	first_name = gets.chomp
	first_name.capitalize!

	print "What's your last name?"
	last_name = gets.chomp
	last_name.capitalize!

	print "What city are you from?"
	city = gets.chomp
	city.capitalize!

	print "What state or province are you from?"
	state = gets.chomp
	state.upcase!

	puts "Your name is #{first_name} #{last_name} and you're from #{city}, #{state}!"

---

## Prompting the User

First, let's write the code we're already familiar with. In order to get input from the user, we'll first need to print a prompt on the screen.

Instructions

print the question "What's your first name?" to the screen. Feel free to peek back at the first exercise if you need a syntax reminder.

A :

	print "what is your first name?"

---

## Getting Input

Good! Now let's try something new. You may have noticed this weird little line of code repeated in our example:

	variable_name = gets.chomp

**gets is the Ruby method that gets input from the user**. When getting input, Ruby automatically adds a blank line (or newline) after each bit of input; chomp removes that extra line. (Your program will work fine without chomp, but you'll get extra blank lines everywhere.)

**Instructions**

Declare a variable first_name and set it equal to gets.chomp.

A :

	print "what is your first name?"
	first_name = gets.chomp

## Repeat for More Input

All right! Now we need to repeat what we've done for last_name, city, and state.

Instructions

Add print prompts, variables, and gets.chomps for the user's last name, city, and state/province. Use last_name as the variable for the user's last name, city for their city, and state for their state or province. (Hint: prompt the user to provide an abbreviation for their state or province, such as "NY" for New York. This will naturally lead us to use .upcase later!)

A :

	print "what is your first_name?"
	first_name = gets.chomp
	print "what is your last_name?"
	last_name = gets.chomp
	print "what is your city?"
	city = gets.chomp
	print "what is your state?"
	state = gets.chomp

---

## Printing the Output

As you might have noticed, Ruby's not really returning any feedback to us. We want to be able to see our string formatting in action! For this, we'll need one more new piece of syntax.

If you define a variable monkey that's equal to the string "Curious George", and then you have a string that says "I took #{monkey} to the zoo", Ruby will do something called string interpolation and replace the #{monkey} bit with the value of monkey—that is, it will print "I took Curious George to the zoo". We can do the same thing here! For example:

	first_name = "Kevin"
	puts "Your name is #{first_name}!"

will print "Your name is Kevin!"

**Instructions**

Let's use this syntax to print out the values of first_name, last_name, city, and state using #{} syntax.

A:

	print "what is your first_name?"
	first_name = gets.chomp
	print "what is your last_name?"
	last_name = gets.chomp
	print "what is your city?"
	city = gets.chomp
	print "what is your state?"
	state = gets.chomp

	puts "#{first_name}, #{last_name}, #{city}, #{state}"

---

## Formatting with String Methods

Great! Now we've got our output, but as you can see, we haven't used string methods to properly capitalize everything yet.

	print "This is my question?"
	answer = gets.chomp
	answer2 = answer.capitalize 
	answer.capitalize!

First we introduce one new method, **capitalize**, here. It capitalizes the first letter of a string and makes the rest of the letters lower case. We assign the result to answer2

The next line might look a little strange, we don't assign the result of capitalize to a variable. Instead you might notice the ! at the end of capitalize. This modifies the value contained within the variable answer itself. The next time you use the variable answer you will get the results of answer.capitalize

**Instructions**

After each variable assignment: first_name, last_name, and city add the .capitalize! method
For state use the .upcase! method.

	print "what is your first_name?"
	first_name = gets.chomp.capitalize!
	print "what is your last_name?"
	last_name = gets.chomp.capitalize!
	print "what is your city?"
	city = gets.chomp.capitalize!
	print "what is your state?"
	state = gets.chomp.upcase!

	puts "#{first_name}, #{last_name}, #{city}, #{state}" 	 			

---

## How It Works

You may have noticed that the kinds of programs we've written so far in Ruby aren't very flexible. Sure, they can take user input, but they always produce the same result based on that input; they don't change their behavior in reaction to the environment (the collection of all variables and their values that exist in the program at a given time).

Control flow gives us the flexibility we're looking for. We can select different outcomes depending on information the user types, the result of a computation, or the value returned by another part of the program.

**Instructions**

Check out the code in the editor. There's some new syntax there, but we'll bet you can guess what it does. Click Save & Submit Code to see the program in action! (Go ahead and give Ruby an integer—that is, a positive or negative number with no decimal bit.)

	print "Integer please: "
	user_num = Integer(gets.chomp)

	if user_num < 0
	  puts "You picked a negative integer!"
	elsif user_num > 0
	  puts "You picked a positive integer!"
	else
	  puts "You picked zero!"
	end	

---

## If

Ruby's if statement takes an expression, which is just a fancy word for something that has a value (like 4, true, or pants). If that expression is true, Ruby executes the block of code that follows the if. If it's not true (that is, false), Ruby doesn't execute that block of code: it skips it and goes on to the next thing.

Here's an example of an if statement in action:

	if 1 < 2
	  print "I'm getting printed because one is less than two!"
	end

Ruby doesn't care about whitespace (spaces and blank lines), so the indentation of the print statement isn't necessary. However, it's a convention that Rubyists (Ruby enthusiasts) follow, so it's good to get in the habit now. The block of code following an if should be indented two spaces.

When you're done with your if, you have to tell Ruby by typing end.

**Instructions**

Write your own if statement in the editor. It can take any expression you want (even just true!), but it should evaluate to true. When it does, it should print a string of your choice to the console (using print or puts).

A :

	if true
	    print "this greater than zero"
	end

---

## Else

The partner to the if statement is the else statement. An if/else statement says to Ruby: "If this expression is true, run this code block; otherwise, run the code after the else statement." Here's an example:

	if 1 > 2
	  print "I won't get printed because one is less than two."
	else
	  print "That means I'll get printed!"
	end

**Instructions**

Try it yourself in the editor! Use any expression you like in your if/else statement, but make sure both branches print a string of your choice to the console.	

A:

	if 0 != 2
	    print "shame on you"
	else
	    print "no better than your thinking"
	end

---

## Elsif

What if you want more than two options, though? It's elsif to the rescue! The elsif statement can add any number of alternatives to an if/else statement, like so:

	if x < y  # Assumes x and y are defined
	  puts "x is less than y!"
	elsif x > y
	  puts "x is greater than y!"
	else
	  puts "x equals y!"
	end

**Instructions**

Add an elsif block to your if/else statement in the editor.

A: 

	if 0 != 2
	    print "shame on you"    
	elsif 0 < 2
	    print "you are kind of get better"
	else
	    print "no better than your thinking"
	end

---	

## Unless

Sometimes you want to use control flow to check if something is false, rather than if it's true. You could reverse your if/else, but Ruby will do you one better: it will let you use an unless statement.

Let's say you don't want to eat unless you're hungry. That is, while you're not hungry, you write programs, but if you are hungry, you eat. You might write that program in Ruby like this:

	unless hungry
	  # Write some sweet programs
	else
	  # Have some noms
	end

**Instructions^^

We've started you off in the editor. Replace the ___s with the correct unless statement code so your program prints out "I'm writing Ruby programs!"

A :

	hungry = false

	unless hungry
	  puts "I'm writing Ruby programs!"
	else
	  puts "Time to eat!"
	end

---

## Equal or Not?

In Ruby, we assign values to variables using =, the assignment operator. But if we've already used = for assignment, how do we check to see if two things are equal? Well, we use ==, which is a comparator (also called a relational operator). == means "is equal to." When you type

	x = 2
	y = 2
	if x == y
	  print "x and y are equal!"
	end

you're saying: "if x equals y, print 'x and y are equal!'" You can also check to see if two values are not equal using the != comparator.

**Instructions**

We've got two variables in the editor: is_true and is_false. Replace the __ with == or != to make is_true evaluate to true and is_false evaluate to false.

A :

	is_true = 2 != 3

	is_false = 2 == 3

---

## Less Than or Greater Than

We can also check to see if one value is less than, less than or equal to, greater than, or greater than or equal to another. Those operators look like this:

	Less than: <
	Less than or equal to: <=
	Georgereater than: >
	Greater than or equal to: >=

**Instructions**

We've set up a few variables in the editor. We want them all to evaluate to true. Your job: replace the __s with <, <=, >, or >= to make the expression for each variable true!

A :

	test_1 = 17 >= 16

	test_2 = 21 < 30

	test_3 = 9 <= 9

	test_4 = -11 < 4

---

## Practice Makes Perfect

Great work so far! You know what they say: practice makes perfect. Let's try a few more comparators to make sure you've got the hang of this.

**Instructions**

For this round, we'll show you the comparators and you set each variable to true or false depending on what value you expect the expression to return. Remember: no quotes around true and false!

A:

	# test_1 = 77 != 77
	test_1 = false

	# test_2 = -4 <= -4
	test_2 = true

	# test_3 = -44 < -33
	test_3 = true

	# test_4 = 100 == 1000
	test_4 = false	

---

## And

Comparators aren't the only operators available to you in Ruby. You can also use logical or boolean operators. Ruby has three: and (&&), or (||), and not (!). Boolean operators result in boolean values: true or false.

The boolean operator and, &&, only results in true when both expression on either side of && are true. Here's how && works:

	true && true # => true
	true && false # => false
	false && true # => false
	false && false # => false

For example, 1 < 2 && 2 < 3 is true because it's true that one is less than two and that two is less than three.

**Instructions**

Let's practice a bit with &&. Check out the boolean expressions and set each variable to true or false depending on what value you expect the expression to return.

A :

	# boolean_1 = 77 < 78 && 77 < 77
	boolean_1 = false

	# boolean_2 = true && 100 >= 100
	boolean_2 = true

	# boolean_3 = 2**3 == 8 && 3**2 == 9
	boolean_3 = true

---

## Or

Ruby also has the or operator (||). Ruby's || is called an inclusive or because it evaluates to true when one or the other or both expressions are true. Check it out:

	true || true # => true
	true || false # => true
	false || true # => true
	false || false # => false

**Instructions**

Set each variable to true or false depending on what value you expect the expression to return.

	# boolean_1 = 2**3 != 3**2 || true
	boolean_1 = true

	# boolean_2 = false || -10 > -9
	boolean_2 = false

	# boolean_3 = false || false
	boolean_3 = false

---

## Not

Finally, Ruby has the boolean operator not (!). ! makes true values false, and vice-versa.

	!true # => false
	!false # => true

**Instructions**

Set each variable to true or false depending on what value you expect the expression to return.

A :

	# boolean_1 = !true
	boolean_1 = false

	# boolean_2 = !true && !true
	boolean_2 = false

	# boolean_3 = !(700 / 10 == 70)
	boolean_3 = false

---

## Combining Boolean Operators

You can combine boolean operators in your expressions. Combinations like

	(x && (y || w)) && z

are not only legal expressions, but are extremely useful tools for your programs.

These expression may take some getting used to, but you can always use parentheses to control the order of evaluation. Expressions in parentheses are always evaluated before anything outside parentheses.

**Instructions**

Last one! Set each variable to true or false depending on what value you expect the expression to return.

A :

	# boolean_1 = (3 < 4 || false) && (false || true)
	boolean_1 = true

	# boolean_2 = !true && (!true || 100 != 5**2)
	boolean_2 = false

	# boolean_3 = true || !(true || false)
	boolean_3 = true

---

## If, Else, and Elsif

All right! You're all on your lonesome. (Well, not quite. We'll just leave this example here.)

	a = 10
	b = 11
	if a < b
	  print "a is less than b!"
	elsif b < a
	  print "b is less than a!"
	else
	  print "b is equal to a!"
	end

**Instructions**

Create an if/else statement in the editor. Make sure to include at least one elsif. Each branch of the statement should print something to the console.

A:

	x = 10
	y = 5

	if x < y
	    print "x lebih kecil dari b"
	elsif x > y
	    print "x lebih besar dari b"
	else
	    print "x sama dengan y"
	end

## Unless

Good! Now let's review the unless statement.

	problem = false
	print "Good to go!" unless problem

Remember, this is basically a short hand if statement. It will do whatever you ask unless the condition is true. In our example, problem is false, so we don't have a problem. We print Good to go!

**Instructions**

Create an unless statement in the editor. The statement should print something to the console.

A:
	sleep = false
	print "Good work!" unless sleep

---

## Dare to Compare

Now let's review comparators / relational operators. We've turned the tables a bit!

Remember, comparators need to compare two values to each other to result in true or false

	10 > 8 // true
	8 > 10 // false
	8 == 10 // false
	8 != 10 // true

**Instructions**

We're letting you know what value (true or false) we want each variable to have, and your job is to add an expression that evaluates to the correct value using comparators.

	# test_1 should be false
	test_1 = 1 == 2

	# test_2 = should be false
	test_2 = 2 > 3

	# test_3 = should be true
	test_3 = 2 < 3

	