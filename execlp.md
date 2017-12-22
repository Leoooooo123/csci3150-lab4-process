# `execlp()`

```c
/* execlp.c */
#include <stdio.h>
#include <unistd.h>
int main(int argc,char *argv[])
{ 
    printf("Using *execlp* exec ls -l...\n");         
    execlp("ls","ls","-l",NULL); 
    printf("Program Terminated\n"); 
    return 0;
}
```
`execlp()` uses *filename*, *argument list* and *original ENV* to execute the program.

```c

execlp("ls","ls","-l",NULL);

```
we only need to provide the name of the program, it will search accordingly in the locations specified in `$PATH` variable. 

For the program arguments, they are included directly into `execlp()` functions.


Lastly, default environment variables in systm are used.

