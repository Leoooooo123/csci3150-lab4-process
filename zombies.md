#Problem 2: Zombies!

The following code simulates a shell that executes `ls` in each round. 
```c
/* Wait/problematic2.c */
#include <stdio.h>
#include <unistd.h>
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
            sleep(1);
         }
    }
    return 0;
}

```

The program will run without *apparent* problems. However, if you look at the system process...

![](/assets/zombies.png)

Zombies appear!!

This is the consequence of the mishandling in the parent process- the parent ignores the `SIGCHLD` signal.
