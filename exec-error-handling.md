# Exec Error Handling

If errors occur while executing `exec*()`, it **will return ** to the program and continue execution. The return value is `-1`, and *errno* is set to indicate the error.

```c
/* Exec/exec_error.c */
#include <stdio.h>
#include <unistd.h>
#include <errno.h>
int main(int argc,char *argv[])
{
    printf("Try to execute lss\n");
    execl("/bin/lls","lls",NULL);
    printf("execl returned! errno is [%d]\n",errno);
    perror("The error message is :");
    return 0;
}


```
In this program, you can see the line `execl returned!...` is printed, indicating that `execl()` returns to the main function and the execution continues. `errno` is a global variable that stores the error number. You can check the manual for the error reason, however, you can print in a human-friendly way by using `perror()`.