# c-comments

Given a number of source code filenames as arguments this tool scans the files
and outputs only the comments and strings withing double quotes.

Everything else it blanks out, so it outputs the same number of lines as in
the original file. The comments and strings are shown at the same horizontal
position as they were in the original file.

You can use this to for example spell-check comments and strings and not have
it check the actual source code.

Made for C source code and headers.

## intended purpose

Run a spell-checker on the comments strings in the code but make it not
complain on your variable and function names.

## demo

Running the tool on a sample C source file.

~~~sh
$ cat test.c
~~~

~~~c
// comment
#define weird /* like this
                 is odd */
a("hello");

#include "ignore" /* but show this */

/* show */ /* two */ invoke(); // and now

#define something                              \
  "continued"

int code(char *string)
{
  int variable = 3;
  /* it starts */
  return strlen(string) * variable;
}
~~~

~~~sh
$ ./c-comments test.c
~~~

~~~
// comment
              /* like this
                 is odd */
  "hello"  

                  /* but show this */

/* show */ /* two */           // and now

                                                
  "continued"

                      
 
                   
  /* it starts */
                                   
 
~~~
