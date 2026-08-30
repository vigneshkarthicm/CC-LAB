# Experiment 2 – Virtual Machine: C Compiler

## Title
Virtual Machine – C Compiler

## Aim
To install a C compiler in the virtual machine created using VirtualBox and execute simple programs.

---

## Requirements
| Item | Details |
|------|---------|
| Virtual Machine | Tiny Core Linux (running in VirtualBox) |
| Compiler | compiletc (installed via tce-load) |
| Program | demo.c – Leap Year Checker |
| Language | C |

---

## Introduction
**Tiny Core Linux** is a minimal Linux distribution ideal for running inside a virtual machine. It uses the `tce-load` package manager to install software including C compilers. Once the compiler is installed, C programs can be compiled with the `cc` command and executed.

---

## Compiler Installation

Boot into Tiny Core Linux inside VirtualBox, then open the terminal and run:

```bash
tce-load -wi compiletc
```

This downloads and installs the GCC-based C compiler toolchain.

---

## Program – Leap Year Checker (`demo.c`)

```c
#include <stdio.h>

int main() {
    int y;

    printf("Enter year: ");
    scanf("%d", &y);

    if ((y % 400 == 0) || (y % 4 == 0 && y % 100 != 0))
        printf("%d is a Leap Year\n", y);
    else
        printf("%d is not a Leap Year\n", y);

    return 0;
}
```

### Logic
- Divisible by 400 → Leap Year
- Divisible by 4 but not 100 → Leap Year
- Otherwise → Not a Leap Year

---

## Compilation

```bash
cc demo.c
```

This compiles `demo.c` and produces the default output binary `a.out`.

---

## Execution

```bash
./a.out
```

---

## Input
```
1991
```

## Expected Output
```
Enter year: 1991
1991 is not a Leap Year
```

---

## Files
| File | Description |
|------|-------------|
| `demo.c` | C source code – Leap Year Checker |
| `output.txt` | Simulated terminal output |

---

## How to Execute
1. Start Tiny Core Linux virtual machine in VirtualBox.
2. Open terminal inside the VM.
3. Install compiler: `tce-load -wi compiletc`
4. Create/copy `demo.c` into the VM.
5. Compile: `cc demo.c`
6. Run: `./a.out`
7. Enter a year when prompted.

---

## Result
The C compiler was installed successfully inside the virtual machine, and the leap year C program was compiled and executed successfully.
