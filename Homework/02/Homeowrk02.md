## Homework 2

> enum
```
enum { 
  Num = 128, Fun, Sys, Glo, Loc, Id,
  Char, Else, Enum, If, Int, Return, Sizeof, While, Do,
  Assign, Cond, Lor, Lan, Or, Xor, And, Eq, Ne, Lt, Gt, Le, Ge, Shl, Shr, Add, Sub, Mul, Div, Mod, Inc, Dec, Brak
};
```

>  compile
```
int compile(int fd) {
  int i, *t;

  p = "char else enum if int return sizeof while do "
      "open read write close printf malloc free memset memcmp exit void main";
  i = Char; while (i <= Do) { next(); id[Tk] = i++; }
  i = OPEN; while (i <= EXIT) { next(); id[Class] = Sys; id[Type] = INT; id[Val] = i++; } // add library to symbol table
  next(); id[Tk] = Char; // handle void type
  next(); idmain = id; // keep track of main

  if (!(lp = p = malloc(poolsz))) { printf("could not malloc(%d) source area\n", poolsz); return -1; }
  if ((i = read(fd, p, poolsz-1)) <= 0) { printf("read() returned %d\n", i); return -1; }
  p[i] = 0;

  return prog();
}
```
> Result
```
./c6.exe dowhile.c
11
exit(0) cycle = 195
```

```
./c6.exe -s dowhile.c
1: #include <stdio.h>
2:
3: int main()
4: {
5:     int n;
6:     int i;
7:     n=0;
    1:660054     ENT  2
    3:66005C     LEA  -1
    5:660064     PSH
    6:660068     IMM  0
    8:660070     SI
8:     i=10;
    9:660074     LEA  -2
   11:66007C     PSH
   12:660080     IMM  10
   14:660088     SI
9:     do {
10:         n = n + 1;
   15:66008C     LEA  -1
   17:660094     PSH
   18:660098     LEA  -1
   20:6600A0     LI
   21:6600A4     PSH
   22:6600A8     IMM  1
   24:6600B0     ADD 
   25:6600B4     SI
11:     } while (n <= i);
   26:6600B8     LEA  -1
   28:6600C0     LI
   29:6600C4     PSH
   30:6600C8     LEA  -2
   32:6600D0     LI
   33:6600D4     LE
   34:6600D8     BZ   38:6600E8
   36:6600E0     JMP  15:66008C
12:     printf("%d\n",n);
   38:6600E8     ADDR 0:6A0058
   40:6600F0     PSH
   41:6600F4     LEA  -1
   43:6600FC     LI
   44:660100     PSH
   45:660104     PRTF
   46:660108     ADJ  2
13:     return 0;
   48:660110     IMM  0
   50:660118     LEV
```