# Wait!

After we learnt about running other program using `exec`, you may find one problem: the parent died before the child. We would like to suspend the parent and wake it after the child is terminated.

In this section, you will learn:

1. `wait` system call
2. `waitpid` system call