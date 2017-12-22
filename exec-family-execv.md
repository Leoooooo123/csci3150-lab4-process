#`execv()`

```c
/* Exec/execlv.c */
#include <stdio.h>
#include <unistd.h>
int main(int argc,char *argv[]){ 
    char *arg[] = {"ls","-l",NULL}; 
    printf("Using *execv* to exec ls -l...\n");
    execv("/bin/ls",arg); 
    printf("Program Terminated\n"); 
    return 0;
}
```
`execv()` uses *pathname*, *argument array* and *original ENV* to execute the program.

```c
execv("/bin/ls",arg);
```

You need to specify the absolute path for your target program and array of `char*` for the program arguments.

Lastly `execv()` uses original system enviroment variables for the new program.