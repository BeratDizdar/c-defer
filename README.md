```c
/* simple as that */
void(*fn_list[999])(void);t;
defer(void(*f)(void)){if(t>=999)return-1;fn_list[t++]=f;}
exec_defer(){for(;t>0;)fn_list[--t]();}

/* example */
#include <stdio.h>
void prt(){printf("msg1\n");}
main() {
    defer(prt);
    printf("msg2\n");
    exec_defer();
    printf("msg3\n");
    return 0;
}
```
