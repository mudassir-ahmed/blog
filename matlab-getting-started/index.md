---
title: Getting started with Octave (or MATLAB) for Machine Learning
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

Fun fact: 82% of Fortune 100 companies use MATLAB. Octave allows you to
prototype your Machine Learning experiments faster. The main reason is that it
is a high level programming language. Some people prefer to get their
algorithms working in Octave and then migrate to another language such as
Python, R, Java or C++.

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
| `V = [1; 2; 3]`          | A 3x1 column vector i.e $V \in \mathbb{R}^3$       |
| `help eye`               | Shows man page for eye                             |
| `pwd`                    | Print working directory                            |
| `cd`                     | Change directory                                   |
| `ls`                     | List files                                         |
| `load someData.dat`      | Load data                                          |
| `save filename variable` | Save data                                          |
| `who`                    | Show variables in the current scope                |
| `whos`                   | Show variables in the current scope with more info |

Watch out: in Octave/MATLAB vectors are not zero-indexed i.e. they start at one

## Manipulating data (matrices)

| Command       | Usage                                                                                         |
| :------------ | :-------------------------------------------------------------------------------------------- |
| `A * B`       | Matrix multiplication                                                                         |
| `A .* B`      | Element-wise multiplication                                                                   |
| `abs(V)`      | Element-wise absolute                                                                         |
| `exp(V)`      | Element-wise exponentiation                                                                   |
| `log(V)`      | Element-wise log                                                                              |
| `max(A)`      | Maximum element in $A$                                                                        |
| `a < 2`       | Element-wise comparison                                                                       |
| `find(A < 3)` | Elements that are less than 3                                                                 |
| `sum(A)`      | Sum of $A$                                                                                    |
| `magic(n)`    | Generate a n x n magic matrix                                                                 |
| `A .* eye(n)` | Assuming $A$ is an n x n matrix then this yields the diagonal and all other elements are zero |
| `flipud(A)`   | Flip matrix up-down                                                                           |

## Plotting data

Plot the $\sin$ function.

```matlab
x = [0:0.01:0.98];
y = sin(2*pi*4*x);
plot(x, y);
```

Plot the $\sin$ and $\cos$ function on the same graph.

```matlab
x = [0:0.01:0.98];
y_sin = sin(2*pi*4*x); % Notice the use of x
y_cos = cos(2*pi*4*x);
plot(x, y_sin);
hold on;
plot(x, y_cos, 'r'); % Plot cos function in red
xlabel('x-value')
ylabel('y-value')
legend('sin', 'cos')
title('Plot title')
print -dpng 'plot.png' % Save the plot
```

Use `figure` to create multiple figures. Tip: use `help plot` for more
information on how to use the `plot` command. Use `subplot` to plot side by
side.

Visualise a matrix.

```matlab
% below is using command chaining of commands
imagesc(magic(8)), colorbar % plot an 8x8 matrix with a color map
close % close the plot
```

## Control statements

```matlab
% for loop
for i=1:10,
    A(i) = 2 * A(i); % double each element of matrix A
end;

% while loop
i = 0;
while i <= 10
    i = i + 1;
end;

% if, elseif, else
if i == 5,
    disp('Found a 5');
elseif i == 4
    disp('Found a 4');
else
    disp('Keep searching');
end;
```

## Functions

Functions are defined in files such as `addTwoNumbers.m`. Make sure your
function is in your octave search path or current working directory.

```matlab
% File: addTwoNumbers.m
function y = addTwoNumbers(a, b)
y = a + b;
```

Pro tip: Octave can natively return multiple values.

## Vectorisation

## Further reading

- [GNU Octave Documentation](https://octave.org/doc/v5.2.0/)
