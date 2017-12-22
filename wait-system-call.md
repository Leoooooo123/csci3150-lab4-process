# `wait()` system call

```c
pid_t wait(int *status);
```


In order to suspend the parent and handle the child properly, the `wait` system call is neccssary.

```c
/* Wait/wait.c */
#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>

int main(int argc,char *argv[])
{
    while(1)    
    {
        printf("Press Enter to execute ls");
        while(getchar() != '\n');
        if(!fork())
        { 
            execl("/bin/ls","ls",NULL); 
        } 
        else 
        { 
           wait(NULL); 
        } 
   }
    return 0;
}


```

`wait()` takes one parameter for storing the status of the child process, for example, whether it is terminated or suspended. If you are not interested, just put `NULL` as the parameter.


This is a similar program in [Problem 2](/zombies.md). However, this can get rid of zombies!

    


