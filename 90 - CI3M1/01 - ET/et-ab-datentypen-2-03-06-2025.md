# AB Datentypen 2
___
```c
int a = 5;
int b = 3;
int c = 5/3; // 1
```

```c
int a = 5;
int b = 4;
int c = 8;
int d = a+b*c; // 37
```

```c
int a = 5;
bool k = false;
bool m = (a > 4); // true
bool n = (a == 4); // false
```

```c
unsigned char a = 7; // char is 1 byte integer
int b = 100;
int c = a * b / b; // 7
int d = 10000;
int e = a * d / d; // 7
```

```c
signed char a = 7;
signed char b = 100;
int c = a * b; // 700
int d = 700;
int e = 100;
long f = d * e; // 70000
```

```c
int a = 5;
int b = 4;
int c = 8;
int d = a + b * c; // 37
```

1. `!`
2. `*, /, %`
3. `>`
4. `==`
5. `&&`
6. `||`

```c
char a = 0x3A; // 58 or 00111010 (:)
char b = 0x76; // 118 or 01110110 (v)
char c = ~a; // 11000101 or 197 (extended ASCII: Å)
	char d = a|b; // 01111110 or 126 (~)
char e = a&b; // 00110010 or 50 (2)
char f = a^b; // 01001100 or 76 (L)
```

