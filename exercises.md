# Exercises

Take a note of the program below. It has several `fork()` and `printf()`. How many `A`, `B` and `C` will be printed?

```c
/* LetsFork/fork_ex.c */
#include <stdio.h>
#include <unistd.h>
int main(int argc,char *argv[]){
    printf("A\n");
    fork();
    printf("B\n");
    fork();
    printf("C\n");
    return 0;
}


```

<quiz name="Fork Quiz">
    <question>
           <p>How many `A`, `B` and `C` will be printed?</p>
       
       <answer>A: 1 time, B: 2 times, C: 2 times</answer>
        <answer correct>A: 1 time, B: 2 times, C: 4 times</answer>

       <answer>A: 1 time, B: 1 times, C: 2 times</answer>
       <answer>A: 1 time, B: 2 times, C: 3 times</answer>
    </question>
</quiz>

<!--
> In progress

<quiz name="Gitbook Quiz">

 <question multiple>

 <p>What is gitbook used for?</p>

 <answer correct>To read books</answer>

 <answer>To book hotel named git</answer>

 <answer correct>To write and publish beautiful books</answer>

 <explanation>GitBook.com lets you write, publish and manage your books online as a service.</explanation>

 </question>

 <question>

 <p>Is it quiz?</p>

 <answer correct>Yes</answer>

 <answer>No</answer>

 </question>

 <question>

 <p>This is multiple dropdown quiz, in each dropdown select a correct number corresponding to the dropdown's order</p>

 <answer>

 <option correct>First</option>

 <option>Second</option>

 <option>Third</option>

 <option>Fourth</option>

 </answer>

 <answer>

 <option>First</option>

 <option correct>Second</option>

 <option>Third</option>

 <option>Fourth</option>

 </answer>

 <answer>

 <option>First</option>

 <option>Second</option>

 <option correct>Third</option>

 <option>Fourth</option>

 </answer>

 <answer>

 <option>First</option>

 <option>Second</option>

 <option>Third</option>

 <option correct>Fourth</option>

 </answer>

 </question>

</quiz>
-->