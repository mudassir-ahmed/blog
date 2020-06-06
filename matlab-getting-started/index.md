---
title: Getting started with Octave for Machine Learning
excerpt: excerpt
hero: https://cdn.dribbble.com/users/169093/screenshots/624424/f_x_.jpg
alt: alt
date: "2020-06-06 21:41:48"
og:
  image:
    url: /assets/blog/hello-world/cover.jpg
tags:
  - Machine Learning
  - Octave
---

Octave allows you to prototype your Machine Learning experiments faster. The
main reason is that it is a high level programming language. Some people prefer
to get their algorithms working in Octave and then migrate to another language
such as Python, R, Java or C++.

## Installation

On Ubuntu 20.04

```bash
sudo apt update
sudo apt install octave
```

For other distributions, please consult [GNU Octave
download](https://www.gnu.org/software/octave/#install) website.

## The basics

| Command(s)               | Usage                                              |
| :----------------------- | :------------------------------------------------- |
| `+, -, \\, *`            | Elementary math operations                         |
| `==`                     | Logical equal to                                   |
| `~=`                     | Logical not equal to                               |
| `&&`                     | Logical AND                                        |
| `||`                     | Logical OR                                         |
| `xor(a, b)`              | Logical XOR                                        |
| `eye(n)`                 | n x n identity matrix                              |
| `ones(n, m)`             | n x m matrix of ones                               |
| `rand(n, m)`             | n x m matrix of randoms                            |
| `size(A)`                | Dimensions of matrix $A$                           |
| `clear A`                | Remove variable $A$                                |
| `A'`                     | Transpose of matrix $A$                            |
| `A(1,2)`                 | Get element $A_{1,2}$                              |
| `A(2,:)`                 | Get the 2nd row of $A$                             |
| `pinv(A)`                | Pseudo inverse of matrix $A$                       |
| `a = 3`                  | Variable assignment                                |
| `a = 3;`                 | Variable assignment - semicolon suppresses output  |
| `pi`                     | Constant PI                                        |
| `A = [1 2; 3 4; 5 6]`    | A 3x2 matrix with denoted elements                 |
| `V = [1; 2; 3]`          | A 3x1 column vector i.e $V \in \mathbf{R}^3$       |
| `help eye`               | Shows man page for eye                             |
| `pwd`                    | Print working directory                            |
| `cd`                     | Change directory                                   |
| `ls`                     | List files                                         |
| `load someData.dat`      | Load data                                          |
| `save filename variable` | Save data                                          |
| `who`                    | Show variables in the current scope                |
| `whos`                   | Show variables in the current scope with more info |

## Further reading

- [GNU Octave Documentation](https://octave.org/doc/v5.2.0/)
