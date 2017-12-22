# `execvp()`

```c
/* Exec/execvp.c */
#include <stdio.h>
#include <unistd.h>
int main(int argc,char *argv[])
{
    char *arg[] = {"ls","-l",NULL};
    printf("Using *execvp* to exec ls -l ...\n");
    execvp("ls",arg);
    printf("Program Terminated\n");
    return 0;
}

```
`execvp()` uses *filename*, *argument array* and *original ENV* to execute the program.

```c
execvp("ls",arg);
```

It only takes a filename to invoke the program, and it is searched in paths specified in `$PATH` in sequence.

The arguments are listed in an array of `char*` and passed to the function.

Original environment variable are used in a new program environment.



