#`waitpid()`

`waitpid()` is an advanced version of `wait()` system call. You can specify more in the parameters.

```c
pid_t waitpid(pid_t pid, int *status, int options);
```   

Take a note of the following code to see how does it work:

```c
#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>#include <stdlib.h>

int main(int argc,char *argv[])
{
    int pid;
    int status;
    if(!(pid = fork()))
    {
        printf("My PID: %d\n",getpid()); 
        exit(0); 
    }
    waitpid(pid,&status,WUNTRACED);
    if(WIFEXITED(status)) 
    { 
        printf("Exit Normally\n");
        printf("Exit status: %d\n",WEXITSTATUS(status)); 
    } 
    else 
    { 
        printf("Exit NOT Normal\n"); 
    } 
    return 0;}


```

`waitpid()` takes 3 parameters. The *first* one is child pid, therefore this is more specific than the previous `wait()`. 

The second one stores the status of the child. Whenever the child terminates/suspends, it will store the status code in the middle parameter. Note that it accepts a **pointer** only.

The third is the options for `waitpid()`. You can change various behaviour, for example, returns immediately if no child has exited: `WNOHANG`; also returns if the child is stopped (eg: by Ctrl-Z): `WUNTRACED`.

There are macros to further tell you more information about the child. You can use `WIFEXITED(status)` to check if the child is returned normally (i.e. by `return` or `exit()`). In addition you even can know the exit code (Only least significant 8 bits of status code is available to parents) by using `WEXITSTATUS(status)`.

