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

#### 4:00 - IDE

#### 5:00 - Download IDE for ubuntu	

#### 7:23 - Start codeblocks IDE

#### 10:00 - Setup Project

#### 16:00 - C is a language

#### 16:40 - Dummy file 

#### 18:00 - Part of the C language

#### 23:00 - **Processor directive includes definition**

Add on top page

	#include <stdio.h>

#### 24:00 **Basic Input & Output (I/O)**

#### 29:30 **Printf**

	printf output is one line string with no new line

add \n to add new line

	#include <stdio.h>

	int main()
	{
		printf("This is the way the world ends \n");
		printf("Not with a bang but a whimper. \n");

		return(0);
	}

#### 31:40 **Escape Characters**

	#include <stdio.h>

	int main()
	{
		printf("Hello\n my name is \"Dyo\" ");

		return(0);
	}	

#### 35:00 **Placeholder**

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

#### 41:50 **C Language Variable**

C language keywords:

* int   --
* float	----- C language keywords 	
* char 	--

**Variable int**

var int bisa digunakan lebih dari 1 kali:

	#include <stdio.h>

	int main()
	{
	    int age;

	    age = 30;
	    printf("Bahasa C sudah berumur lebih dari %d tahun \n", age);

	    age = 40;
	    printf("Umur saya masih dibawah %d tahun lho! \n", age);

	    age = 35;
	    printf("Umur si %s adalah %d \n", "Cungkring",age);
	    printf("Berarti total %d bulan \n", age*12);

	    return(0);
	}

**Variable char**

	#include <stdio.h>

	int main()
	{
	    char x,y,z;

	    x = 'A';
	    y = 'B';
	    z = 'C';

	    printf("Hasilnya adalah %c%c%c \n",x,y,z);

	    x = 'A';
	    y = x + 1;
	    z = y +1;

	    printf("Apakah hasilnya akan sama %c%c%c \n", x,y,z);

	    return(0);
	}

**Var float**

	#include <stdio.h>

	int main()
	{
		float pi;

		pi = 22.00 / 7.0;
		printf("The ancients calculated PI as %f.\n",pi);

		return(0);
	}

#### 49:00 **Character I/O Functions**

* getchar() -> input (mengambil character dari keyboard)
* putchar() -> output (menampilkan character dari variable)

* all those Requires stdio.h header (library)
* Work with int values
* Are stream oriented

Contoh:

	#include <stdio.h>

	int main()
	{
	    int c;

	    printf("Ketik huruf disini: ");

	    c = getchar();
	    printf("Anda sudah mengetik '%c'. \n", c);

	    return(0);
	}

Bila menggunakan putchar() :

	int d;

	printf("Input lagi dong disini: ");
    d = getchar();

    printf("Anda sudah menginput ' ");
    putchar(d);
    printf(" '. \n");

	return(0);

Contoh 2:

	#include <stdio.h>

	int main()
	{
	    int a,b;

	    printf("Ketiklah 2 huruf disini: ");

	    a = getchar();
	    b = getchar();

	    printf("Anda sudah mengetik ' ");
	    putchar(a);
	    printf(" ' dan ' ");
	    putchar(b);
	    printf(" '. \n");

	    return(0);
	}

Contoh 3 string:

	#include <stdio.h>

	int main()
	{
	    char password[] = "rahasia";

	    printf("Tampilkan password: \"%s\" \n", password);

	    return(0);
	}

#### 57:30 **The scanf() Function**

Sintaks nya sbb:

	scanf("format", &variable);

format adalah:

* format adalah berisi text string
* berisi input request
* berisi placeholder %d, %s, %f, %c dsb.

&variable adalah:

* adalah nama dari suatu variable
* diberi awalan "&" (ampersand) di depan variable.
* & bukan awalan dari suatu string atau array.
* "&" adalah menunjuk locasi memeory variable/operator.

Contoh:

	int main()
	{
	    /*
	    int x;

	    printf("Ketik integer disini: ");
	    scanf("%d", &x);
	    printf("Integer %d \n", x);
	    */
	    float x;

	    printf("Ketik float disini: ");
	    scanf("%f", &x);
	    printf("Float %f \n", x);
	}

Contoh penggunaan pada string tidak menggunakan Ampersand (&)

	#include <stdio.h>

	int main()
	{
	    char name[15];

	    printf("Tulis nama anda disini: ");
	    scanf("%s", name);
	    printf("Nama anda adalah: %s \n", name);
	}

Tapi bila anda menuliskan nama dengan 2 kata (Dyo Bumi) maka kata ke 2 tidak terbaca scanf() tidak membaca "**white space**". Untuk itu kita akan menggunakan **fgets()**.

#### 1:02:51 **fgets()**

**fgets(input, 64, stdin)**

	#int main()
	{
	    char input[64];

	    printf("Masukan instruksi anda: ");
	    fgets(input, 64, stdin);
	    printf("Instruksi anda adalah: %s \n", input);

	    // atau seperti ini:

	    printf("Masukan instruksi anda: ");
	    fgets(input, 64, stdin);
	    puts("Terimakasih! Instruksi anda adalah: ");
	    puts(input);
	}

#### 1:03:49 **Math Operators**

Contoh operasi tambah:

#include <stdio.h>

	int main()
	{
	    int a;
	    int b = 5;

	    printf("Input integer a: ");
	    scanf("%d", &a);
	    printf("%d + %d = %d \n", a, b, a + b);

	    return(0);
	}

Contoh operasi pembagian (gunakan float!):

	#include <stdio.h>

	int main()
	{
	    // operasi pembagian
	    float a;
	    float b = 5.0;

	    printf("Masukan nilai bilangan desimal: ");
	    scanf("%f", &a);
	    printf("%f / %f = %f \n", a, b, a / b);

	    return(0);
	}

Contoh operasi penambahan ++

	#include <stdio.h>

	int main()
	{
	    int x = 10;

	    printf("%d \n", x);
	    x = x + 1;
	    printf("%d \n", x);

	    printf("Atau gunakan ini \n");
	    printf("%d \n", x);
	    x++;
	    printf("%d \n", x);

	    printf("Operasi Pengurangan \n");
	    printf("%d \n", x);
	    x--;
	    printf("%d \n", x);

	    return(0);
	}

Contoh lain:

	#include <stdio.h>

	int main()
	{
	    int a;

	    a = 25 / 5 * 2 + 3;
	    printf("Jawabannya adalah a = %d \n", a);

	    printf("\n");

	    a = 25 / 5 * (2 + 3);
	    printf("Jawabannya adalah a = %d \n", a);

	    printf("\n");

	    a = 25 / (5 * (2 + 3));
	    printf("Jawabannya adalah a = %d \n", a);
	}

#### 1:11:00 Math Library

To include math lib:

	#include <math.h>

**sqrt (square root function) akar pangkat dua**

#include <std.io.h>
#include <math.h>

int main()
	{
		int r;

		r = sqrt(2.0);

		printf("Akar pangkat dua dari 2 adalah %f \n", r);

		return(0);

	}

**Power**

#### 1:13:00 C Library Math Function

































