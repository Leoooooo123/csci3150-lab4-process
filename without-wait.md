#Without Wait?

Below it is a typical problem to print something in child. 

```c
/* Wait/problematic.c */
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
    printf("After fork..\n");
    return 0;
}

```

We expect the output to be:

```
Before fork...
Hello World!
After fork... 
```
However,  the actual output may become

```
Before fork...
After fork...
Hello World!

```

We would like to **suspend** the parent and let the child finish execution.