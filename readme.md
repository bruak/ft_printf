# ft_printf

A custom implementation of the C standard library's printf function.

## Table of Contents
- [ft\_printf](#ft_printf)
  - [Table of Contents](#table-of-contents)
  - [Overview](#overview)
  - [Features](#features)
  - [Requirements](#requirements)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Supported Format Specifiers](#supported-format-specifiers)
  - [Function Description](#function-description)
  - [Project Structure](#project-structure)
  - [Examples](#examples)

## Overview

This project recreates the functionality of the standard C library's `printf` function. The ft_printf function produces output according to a format string, writing to the standard output (file descriptor 1). It handles various format specifiers and returns the number of characters printed.

## Features

- Variadic function implementation
- Support for multiple format specifiers
- Proper handling of edge cases
- Error handling for write failures
- Compatible with libft library

## Requirements

- GCC compiler or equivalent
- make utility
- Standard C library

## Installation

1. Clone the repository (if applicable)
```bash
git clone <repository-url>
cd ft_printf
```

2. Compile the library
```bash
make
```

3. The compilation will produce a static library file named `libftprintf.a`.

4. To use in your project, include the header and link with the library:
```bash
gcc -Wall -Wextra -Werror your_program.c -L. -lftprintf
```

## Usage

Include the library in your C file:

```c
#include "ft_printf.h"

int main(void)
{
    ft_printf("Hello, %s!\n", "world");
    return (0);
}
```

## Supported Format Specifiers

- `%c`: Prints a single character
- `%s`: Prints a string
- `%d` or `%i`: Prints a decimal (base 10) integer
- `%u`: Prints an unsigned decimal (base 10) integer
- `%x`: Prints a hexadecimal (base 16) number in lowercase
- `%X`: Prints a hexadecimal (base 16) number in uppercase
- `%p`: Prints a pointer address in hexadecimal format
- `%%`: Prints a percent sign

## Function Description

```c
int ft_printf(const char *format, ...);
```

- **Parameters**:
  - `format`: A string that specifies how subsequent arguments are converted for output
  - `...`: Variable number of arguments to be formatted

- **Return Value**:
  - On success: the number of characters printed (excluding the null byte)
  - On error: -1

## Project Structure

- **ft_printf.c**: Main implementation of the ft_printf function
- **ft_printf.h**: Header file with function prototypes
- **itoa.c**: Functions for converting integers to strings
- **string.c**: Functions for manipulating strings and characters
- **Makefile**: Compilation instructions
- **libft/**: Custom C library with utility functions

## Examples

```c
// Printing different data types
ft_printf("Character: %c\n", 'A');
ft_printf("String: %s\n", "Hello, world!");
ft_printf("Integer: %d\n", 42);
ft_printf("Unsigned: %u\n", 4294967295);
ft_printf("Hexadecimal: %x\n", 255);
ft_printf("Uppercase Hex: %X\n", 255);
ft_printf("Pointer: %p\n", &var);
ft_printf("Percent sign: %%\n");

// Output:
// Character: A
// String: Hello, world!
// Integer: 42
// Unsigned: 4294967295
// Hexadecimal: ff
// Uppercase Hex: FF
// Pointer: 0x7ffeef1b68e0
// Percent sign: %
```

---

*This project is part of the 42 School curriculum.*