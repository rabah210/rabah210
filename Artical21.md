# Title
## Sub title
### Sub sub title
 We have many problems that we suffer from in writing our code, including the operating systems, which made the use of certain libraries confined to a specific system. It will not work on another operating system because you are using libraries that will not be compatible, for example, with Linux.  This is a problem, especially in the C programming language. Among these libraries is the windows.h library that works that creates this problem is the Windows OS, but it will not work on another operating system on Linux or Android (phones) and examples of this are this code : 
```c
#include <stdio.h>
#include <windows.h>
void Color(int ForgC){
     WORD wColor;

      HANDLE hStdOut = GetStdHandle(STD_OUTPUT_HANDLE);
      CONSOLE_SCREEN_BUFFER_INFO csbi;

                       //We use csbi for the wAttributes word.
     if(GetConsoleScreenBufferInfo(hStdOut, &csbi))
     {
                 //Mask out all but the background attribute, and add in the forgournd     color
          wColor = (csbi.wAttributes & 0xF0) + (ForgC & 0x0F);
          SetConsoleTextAttribute(hStdOut, wColor);
     }
     return;
 }
int main (){
int i;
for( i = 0  ; i < 15 ; i++){
Color(i);
puts("Hello in my would *-*");
}

}
```
output :
  ```
  Hello in my would *-* 
  Hello in my would *-*  
  Hello in my would *-*
  Hello in my would *-*
  Hello in my would *-*
  Hello in my would *-*
  Hello in my would *-*
  Hello in my would *-*
  Hello in my would *-*
  Hello in my would *-*
  Hello in my would *-*
  Hello in my would *-*
  Hello in my would *-*
  ```


Well, this is a problem that restricts the interaction of our programs with the user and complicates our work more, but this does not mean that it is a problem that has no solution, when we learned to program we were told that you are programmed to solve problems??
