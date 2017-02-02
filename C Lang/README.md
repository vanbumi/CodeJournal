# C LANG TUTORIAL

Diciptakan dan dikembangkan oleh Brian Kernighan dan Denis Ritchie di Bell Research Labs.

* [c-tutorial](http://www.cprogramming.com/tutorial/c-tutorial.html)

* [C Programming Examples](https://www.programiz.com/c-programming/examples)

+ [C From Beginner To Expert Programming Tutorial The Complete Tutorial to Learn C ](https://www.youtube.com/watch?v=ot9LoXNSqLU)

+ [ExerciseFiles](http://rcg.group.shef.ac.uk/courses/cic6006/clanguage/ExerciseFiles/)

## Video Tutorial

+ [Video Tutorial Bahasa Indonesia](http://www.pecollege.net/videotutorial.aspx)

### IDE

+ 4:00 - [IDE for C](http://www.codeblocks.org/)

+ 5:00 - [Download for ubuntu](https://launchpad.net/~damien-moore/+archive/ubuntu/codeblocks-stable)

Instal in Ubuntu:

	sudo add-apt-repository ppa:damien-moore/codeblocks-stable

	sudo apt-get update

	sudo apt-get install codeblocks codeblocks-contrib

To open 

	$ codeblocks (enter)	

### Step Video Tutorial

4:00 - IDE

5:00 - Download IDE for ubuntu	

7:23 - Start codeblocks IDE

10:00 - Setup Project

16:00 - C is a language

16:40 - Dummy file 

18:00 - Part of the C language

23:00 - **Processor directive includes definition**

Add on top page

	#include <stdio.h>

24:00 **Basic Input & Output (I/O)**

29:30 **Printf**

	printf output is one line string with no new line

add \n to add new line

	#include <stdio.h>

	int main()
	{
		printf("This is the way the world ends \n");
		printf("Not with a bang but a whimper. \n");

		return(0);
	}

31:40 **Escape Characters**

	#include <stdio.h>

	int main()
	{
		printf("Hello\n my name is \"Dyo\" ");

		return(0);
	}	

35:00 **Placeholder**

%d	Integer (whole number) values
%s	String
%f 	Floating-points values
%c 	Single characters
%%	The percent sign	menampilkan persen sejati.	

Sample 1:

	#include <stdio.h>

	int main()
	{
		printf("You are a %s\n","programmer");

		return(0);
	}

Sample 2:

	#include <stdio.h>

	int main()
	{
	    printf("Aku adalah seorang %c %s \n", 'C', "Programmer");

	    return(0);
	}

Sample 3:

	#include <stdio.h>

	int main()
	{
		printf("I got %d%% on my C exam!\n",98);

		return(0);
	}

41:50 **C Language Variable**







