[libft.pdf](https://github.com/user-attachments/files/24056884/libft.pdf)

# Libft – 42 Common Core Project  
A custom implementation of essential C standard library functions.

---

# 📌 Table of Contents
- [📖 Introduction](#-introduction)
- [📁 Repository Structure](#-repository-structure)
- [⚙️ Compilation](#️-compilation)
- [🧰 Usage](#-usage)
- [📚 Mandatory Functions](#-mandatory-functions)
  - [1️⃣ Character Checks](#1️⃣-character-checks)
  - [2️⃣ Memory Functions](#2️⃣-memory-functions)
  - [3️⃣ String Functions](#3️⃣-string-functions)
  - [4️⃣ Safe String Ops (BSD)](#4️⃣-safe-string-ops-bsd)
  - [5️⃣ Conversions & Allocation](#5️⃣-conversions--allocation)
  - [6️⃣ Advanced String Manipulation](#6️⃣-advanced-string-manipulation)
  - [7️⃣ File Descriptor Output](#7️⃣-file-descriptor-output)
- [🌿 Bonus Functions (Linked Lists)](#-bonus-functions-linked-lists)

---

# 📖 Introduction

**Libft** is the first project in the 42 cursus.  
Its purpose is to reimplement essential parts of the C standard library **from scratch**, gaining a deep understanding of low-level programming, memory manipulation, and data structures.

You will:
- Recreate many libc functions (`memcpy`, `strchr`, `atoi`, etc.)
- Implement safer alternatives (`strlcpy`, `strlcat`)
- Handle dynamic memory allocation
- Write higher-order string functions
- Build your own **linked list library** (bonus)

The final output is your own static library:

```
libft.a
```

---

# 📁 Repository Structure

```
libft/
 ├── Makefile
 ├── libft.h
 ├── ft_*.c
 ├── ft_*_bonus.c
 └── libft.a   (generated after compilation)
```

---

# ⚙️ Compilation

```bash
make          # compile mandatory part
make bonus    # compile bonus (linked lists)
make clean    # remove .o files
make fclean   # clean + remove libft.a
make re       # full rebuild
```

All files must compile with:

```
Wall -Wextra -Werror
```

---

# 🧰 Usage

Include the header:

```c
#include "libft.h"
```

Compile your program with:

```bash
cc main.c -L./libft -lft -I./libft -o program
```

---

# 📚 Mandatory Functions

---

# 1️⃣ Character Checks

## `int ft_isalpha(int c);`
Checks if character is alphabetical.

## `int ft_isdigit(int c);`
Checks if character is a digit (0–9).

## `int ft_isalnum(int c);`
Checks if character is alphanumeric.

## `int ft_isascii(int c);`
Checks if value is within ASCII range.

## `int ft_isprint(int c);`
Checks if character is printable.

## `int ft_toupper(int c);`
Converts lowercase to uppercase.

## `int ft_tolower(int c);`
Converts uppercase to lowercase.

---

# 2️⃣ Memory Functions

## `void ft_bzero(void *s, size_t n);`
Sets `n` bytes to zero.

## `void *ft_memset(void *b, int c, size_t len);`
Fills memory with a byte value.

## `void *ft_memcpy(void *dst, const void *src, size_t n);`
Copies `n` bytes from `src` to `dst`.  
Does **not** handle overlap.

## `void *ft_memmove(void *dst, const void *src, size_t len);`
Safe copy even if the memory areas overlap.

## `void *ft_memchr(const void *s, int c, size_t n);`
Searches for byte `c` in the first `n` bytes of memory `s`.

## `int ft_memcmp(const void *s1, const void *s2, size_t n);`
Compares first `n` bytes of memory.

---

# 3️⃣ String Functions

## `size_t ft_strlen(const char *s);`
Returns the length of a string.

## `char *ft_strchr(const char *s, int c);`
Finds first occurrence of character.

## `char *ft_strrchr(const char *s, int c);`
Finds last occurrence of character.

## `int ft_strncmp(const char *s1, const char *s2, size_t n);`
Compares strings.

## `char *ft_strdup(const char *s1);`
Duplicates a string.

## `char *ft_strnstr(const char *haystack, const char *needle, size_t len);`
Searches substring with length restriction.

---

# 4️⃣ Safe String Ops (BSD)

## `size_t ft_strlcpy(char *dst, const char *src, size_t dstsize);`
Safe copy with null-termination.

## `size_t ft_strlcat(char *dst, const char *src, size_t dstsize);`
Safe concatenation preserving buffer size.

---

# 5️⃣ Conversions & Allocation

## `int ft_atoi(const char *str);`
Converts string to integer.

## `void *ft_calloc(size_t count, size_t size);`
Allocates zero-initialized memory.

## `char *ft_itoa(int n);`
Converts integer to string.

---

# 6️⃣ Advanced String Manipulation

## `char *ft_substr(char const *s, unsigned int start, size_t len);`
Extracts substring.

## `char *ft_strjoin(char const *s1, char const *s2);`
Concatenates two strings.

## `char *ft_strtrim(char const *s1, char const *set);`
Trims characters from both ends.

## `char **ft_split(char const *s, char c);`
Splits string by delimiter.

## `char *ft_strmapi(char const *s, char (*f)(unsigned int, char));`
Maps function over string, returns new string.

## `void ft_striteri(char *s, void (*f)(unsigned int, char *));`
Applies function to each character in place.

---

# 7️⃣ File Descriptor Output

## `void ft_putchar_fd(char c, int fd);`
Writes character `c` to fd.

## `void ft_putstr_fd(char *s, int fd);`
Writes string to fd.

## `void ft_putendl_fd(char *s, int fd);`
Writes string with newline.

## `void ft_putnbr_fd(int n, int fd);`
Writes integer `n` to fd.

---

# 🌿 Bonus Functions (Linked Lists)

### Linked List Structure

```c
typedef struct s_list
{
    void            *content;
    struct s_list   *next;
}   t_list;
```

---

## `t_list *ft_lstnew(void *content);`
Creates a new node with given content.

---

## `void ft_lstadd_front(t_list **lst, t_list *new);`
Adds a node at the beginning of the list.

---

## `int ft_lstsize(t_list *lst);`
Returns number of nodes in the list.

---

## `t_list *ft_lstlast(t_list *lst);`
Returns last node of list.

---

## `void ft_lstadd_back(t_list **lst, t_list *new);`
Adds node to the end of list.

---

## `void ft_lstdelone(t_list *lst, void (*del)(void *));`
Deletes a single node using `del` to free content.

---

## `void ft_lstclear(t_list **lst, void (*del)(void *));`
Deletes entire list and frees memory.

---

## `void ft_lstiter(t_list *lst, void (*f)(void *));`
Applies function `f` to each node’s content.

---

## `t_list *ft_lstmap(t_list *lst, void *(*f)(void *), void (*del)(void *));`
Creates a new list by applying `f` to each node of the original.  
Uses `del` to handle memory on error.

---

# ✅ Summary

Libft teaches:
- Memory and pointer manipulation  
- String handling  
- Safe low-level programming  
- Data structures (linked lists)  
- Building static libraries  
- Clean modular C development  

It becomes the base for future 42 projects like:  
`get_next_line`, `ft_printf`, `push_swap`, `minishell`, and more.
