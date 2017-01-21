---
layout: post
title: "Wonders Of Static Linking"
date: 2017-01-21 20:37:00
author: lordPoseidon
---

Hi, this is Nimit Bhardwaj, a student of Computer Science, we all in the journey of computer science got the chance to learn the C Programming language, yes we all, not all although, learning C as out first programming language taught us many things, many things which are related to the working of the basics of the programming.

We are taught how to compile a program, yes very easy process, most of us think its just pressing the **Compile** button or pressing the **Compile and Execute** button for those who use Dev-C/C++ or just use `gcc` who use linux. Its a good defination for a layman, but for a programmer, yes for us, its not enough. For the coders(some basic coders), like us, there are 4 steps of the compilation these are

* Preprocessing
* Compilation
* Assembling
* Linking

The preprocessing is easy for C/C++ languages, it just replace the pre-program directive, the lines starting with `#`, like `#include <stdio.h>` with the file which has the **prototypes** of the functions which will be used or replace the Macros with their expansions like `#define POSEIDON 7`, this line will replace the occurence of POSEIDON with 7, pretty basic huh.

Then is compilation, which checks the possiblities of the syntax and sementic errors if possible and then will initilize the assembling phase of the process.

Then is the assembling, this will convert the language, the high level language which is C to the Assembly language, a low level language, which is hardware dependent. The C code after the preprocessing and compilation will be converted to the assembly language of the given hardware, which will be the .obj file, the object file.

Then is the linking phase, the whole program even from small "Hello World" program to the big Windows like Operating systems, at some phase requires linking. So, what is linking, we usually understand or got some idea of the other processes but getting linking can be difficult for begineers, but I bet it is not difficult, what it is, is very simple concept. Now take the example, you make the "Hello World" program, 
{% highlight c %}
#include <stdio.h>

int main()
{
    printf("Hello World\n");
    return 0;
}
{% endhighlight %}

During the compilation of this program, first `#include <stdio.h>` will be replaced by the content of the stdio.h file, which contains the prototypes of the functions like `int printf(const char *, ...);` which we used now, and the implementation of the file will be complied, yes we will have the compiled file of the functions of the stdio.h which are then **linked** with this hello.c file, so linking put together the different pieces of the like different functions together in a single file so the piece of the code for the printf will be linked with this hello world program.

So this was the basic of the compilation, I hope the reader will understand whats linking, so it will be cool or HOT if we could also link our files which we made. There are two types of linking static and dynamic in this post I will discuss the static in this post.

So whats static linking, its just a hot thing, in this form of linking, the file with main function or any source files which are compiled and linked together by static linking will attach the copies of the libraries, which we linked, like if suppose for a sec, if printf was a statically linked function(which is possible may be) then in a.out formed from hello.c(above), will have the copy of the libprintf, the static library in it, the a.exe (for windows) or a.out (for linux) will actually contain the file for printf implementation, which is not same as dynamic linking, which I will tell in a later post, we can relate it with an aircraft, the aircraft has many components like wings, like seat, like gears etc (though I am not a mechanical engineer please mind my knowledge), aircraft actually has these things, they are combined together, so a whole big aircraft is made, same is the case for a program with static linking.

So lets make an illustration, a program to make the static library. This very simple program will teach you the basics. So ppack youself.

Consider we want to make a very simple library the math library, not so hifi, very low level ;-), which just has 4 operations add, sub, multi and div.

So for this we will need a name for library, let it be poseidonMath, lets make poseidonMath.h first

{% highlight c %}
int add(int, int);
int sub(int, int);
int multi(int, int);
int div(int, int);
{% endhighlight %}

and this is the header file of the poseidonMath library, now we make the files for the functions we make add.c, sub.c, multi.c and div.c

so here are

add.c

{% highlight c %}
int add(int a, int b)
{
    return a + b;
}
{% endhighlight %}

sub.c

{% highlight c %}
int sub(int a, int b)
{
    return a - b;
}
{% endhighlight %}

multi.c

{% highlight c %}
int multi(int a, int b)
{
    return a * b;
}
{% endhighlight %}

div.c

{% highlight c %}
int div(int a, int b)
{
    return a / b;
}
{% endhighlight %}

Now we have the files we can now the compile them, **JUST COMPILE** them, just compiling will make the .o or .obj files, these will have just the assembly code of the files, these will not be able to run as they don't have the main, they are just the piece of the code in assembly, nothing else, just the parts of aircraft made separately in different industries, nothing else, so how to compile them, just do the following, I hope in linux this following command is self explainary, -c tells just compile.

{% highlight bash %}

$ gcc -c add.c
$ gcc -c sub.c
$ gcc -c multi.c
$ gcc -c div.c
{% endhighlight %}

Now, they will output the add.o, sub.o, multi.o and div.o files, the object files like parts(object codes) made from the blueprints(source codes). Its time to make the file for the main function, so here it is,

main.c

{% highlight c %}

#include <poseidonMath.h>
#include <stdio.h>
int main()
{
    int a = 10, b = 2;
    printf("%d %d %d %d\n", add(a, b), sub(a, b), multi(a, b), div(a, b));
    return 0;
}
{% endhighlight %}

The output will be clear for just begineer, for clearity it will `12 8 20 5` , but wait I tell this will be the output, sorry I was wrong, we first have to compile it, now how to do it.

Its easy, remember we had the .o files??, yes I remember that, ok we had the parts that were **separate**, now we will convert them to a single file which will be a single library, ok how to do it, lets see following

{% highlight bash %}
$ ar rs libposeidonMath.a add.o sub.o multi.o div.o
{% endhighlight %}

whats libposeidonMath.a its a static libray, .a tells the archive, `ar` is command which means archieve, the commandline options which will check if there is occurence of the duplicate then it will ignore the duplicates and s tells it will put these object files serially, and the libposeidonMath.a is the name of the library which will be made, this will appear after those command line args, and after it, we will provide the list of the object files which will be merged together to a single file or "archieved" to form a static library.

OK now we have the main.c, poseidonMath.h and libposeidonMath.a we only need these 3 things only, now you don't like the other files except them, you can delete them without any second thought.

so by these files how can we make the a.out or a.exe file, howwwww????

{% highlight bash %}
$ gcc -o lordPoseidon -I . -L . main.c -lposeidonMath
{% endhighlight %}

this will create the output file, which can be executed by ./lordPoseidon on linux.

But wait, how this above command work, -o arg, easy, it just set the name of the file which will be output in our case its lordPoseidon instead of a.out.

-I . :  this part searches the header files, . tell to search the header files in the present directory, which explains we were able to use `#include <poseidonMath.h>` instead of using `#include "poseidonMath.h"`.

-L . : this part tells that the linking will take place in the present directory, the file that needs to be linked is present in the present directory, the file libposeidonMath.a is in the present dir so we used -L .

and then there is name of the the file with main function and atlast we provide the linking we link using -lposeidonMath which links the libposeidonMath.a with the with the compiling output of main.c.

Pretty simple hah, hope you will like it.
