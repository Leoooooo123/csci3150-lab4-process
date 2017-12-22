# `sleep()`

```c
unsigned int sleep(unsigned int seconds);

```

`sleep()` is a system call that can make the process to *sleep* for a specified period.

```c
/* Wait/sleep.c */
#include <stdio.h>
#include <unistd.h>
#include <stdlib.h>


int main(int argc,char *argv[])
{
    printf("Before fork...\n");
    if(fork() == 0)
    {
        printf("Hello World!\n");
        exit(0);
    }
    sleep(1);
    printf("After fork...\n");
    return 0;
}

```

By using `sleep()`, parent can put to a *suspended* state and wait for the child. However, `sleep()` is not desirable (we need to specify the time...).