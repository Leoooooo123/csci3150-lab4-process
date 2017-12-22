# `execle()`

```c
/* Exec/execle.c */
#include <stdio.h>
#include <unistd.h>
int main(int argc,char *argv[])
{ 
    char *env[] = {"LS_COLORS=fi=04;33;44",NULL}; 
    printf("Using *execle* to exec ls -l\n"); 
    execle("/bin/ls","ls","-l","--color",NULL,env); 
    printf("Program Terminated\n");
    return 0;
}
```
`execlp()` uses *pathname*, *argument list* and *provided ENV* to execute the program.

```c
execle("/bin/ls","ls","-l","--color",NULL,env); 

```

You need to provide the exact location (pathname) in order to execute it.

For the arguments, they are specified directly in the `execle()` function.

You can define new environment variables in the function. The environment variables are in a `char*` array.  In this example, the behaviour of `ls` can be changed by the variables. In this case, the colors for displaying files and directories are changed.
