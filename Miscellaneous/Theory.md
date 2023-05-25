## Run time vs Compile time?

Run time and compile time are programming terms that refer to different stages of software program development. After a developer writes ***a source code, this code must be compiled into machine code in order to become an executable program***. This is referred to as **compile time**.

***A compiled program can be opened and run by a user. When the application is running, it is called run time.***



## What is Interpreted language?

*‘What static and dynamic typing are?’, also ‘What static and dynamic binding is?’*
Static indicates that resolution takes place at the time a program is constructed — **compile time**. Dynamic indicates that resolution takes place at the time a program is run — **run time**.



## What static and dynamic typing is?

Static typing means that the executable form of a program generated at compile time will vary depending upon the types of data values found in the program. Dynamic typing means that the generated code will always be the same irrespective of the type — any differences in execution will be determined at run time.

In dynamic typing, value can change from its first declarations type to another type at any time for example int to string, but in statically typing value cannot be changed from one type to another easily. You have to convert them.


## What static and dynamic binding is?

Binding refers to the association of names in program text to the storage locations to which they refer. In static binding, this association is predetermined at compile time. With dynamic binding, this association is not determined until run time.

Example:

If someone attempts to invoke a method like MyClass.foo(), a static binding system will verify at build time that there is a class called MyClass and that class has a method called foo. A dynamic binding system will wait until run time to see whether either exists.



## What is Interpreted language?. 

With a compiled language, the code you enter is reduced to a set of machine-specific instructions before being saved as an executable file — at compile time. With an Interpreted language, most of its implementations execute instructions directly and freely, without previously compiling a program into machine language instructions. Interpreted languages must be reduced to machine instructions.— at run time. You can write dynamically typed interpreted language. 