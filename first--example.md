#First `exec` example

```c
/* Exec/execl.c */
#include <stdio.h>
#include <unistd.h>

int main(int argc,char* argv[])
{
    printf("Using *execl* to exec ls -l...\n");
    execl("/bin/ls","ls","-l",NULL);
    printf("Program Terminated\n");
    return 0;
}

```
The above program illustrates the function of `exec()`.
`execl()` is one of the family members of `exec()`, which is responsible for calling external programs.

First the program will print out `Using *execl* to exec ls -l...`

Then the program will execute `/bin/ls` program, with the supplied arguments.

After this step, the code of the process is *changed* to the target program and it **never** returns to the original code. As the result, the line `Program Terminated` is not printed.
