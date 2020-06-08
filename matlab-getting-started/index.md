---
title: Getting started with GNU Octave (or MATLAB) for Machine Learning
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

82% of Fortune 100 companies use MATLAB; Octave allows you to prototype your
Machine Learning experiments faster, saving you time and money. Since it's a
high level programming language you can do things really fast. Some people
prefer to get their algorithms working in MATLAB and then migrate to another
language such as Python, R, Java or C++. So learning to use MATLAB is a good
investment.

MathWorks provides a free online self-paced [MATLAB
Course](https://matlabacademy.mathworks.com/). You also get a certificate which
you can share to show others you have completed the course. The course is
really well made.

## Installation

Since MATLAB has a price tag, we will use an open source alternative called
[Octave](https://octave.org). Octave is largely compatible with MATLAB - so you
can still follow along if your're a MATLAB user.

On Ubuntu 20.04

```bash
sudo apt update
sudo apt install octave
```

For other distributions, please consult [GNU Octave
download](https://www.gnu.org/software/octave/#install) website.

## MATLAB Basics

Instead of replicating a tutorial, below are commands you will find helpful
when running your machine learning experiments.

| Command(s)               | Usage                                              |
| :----------------------- | :------------------------------------------------- |
| `+, -, \\, *`            | Elementary math operations                         |
| `==`                     | Logical equal to                                   |
| `~=`                     | Logical not equal to                               |
| `&`                      | Logical AND                                        |
| `|`                      | Logical OR                                         |
| `xor(a, b)`              | Logical XOR                                        |
| `eye(n)`                 | n x n identity matrix                              |
| `ones(n, m)`             | n x m matrix of ones                               |
| `rand(n, m)`             | n x m matrix of randoms                            |
| `randi(n, m)`            | n x m matrix of random integers                         |
| `size(A)`                | Dimensions of matrix $A$                           |
| `clear A`                | Remove variable $A$                                |
| `clc` | Clear command window |
| `A'`                     | Transpose of matrix $A$                            |
| `A(1,2)`                 | Get element $A_{1,2}$                              |
| `A(2,:)`                 | Get the 2nd row of $A$                             |
| `A(end, :)` | Get the last row using the end keyword |
| `pinv(A)`                | Pseudo inverse of matrix $A$                       |
| `a = 3`                  | Variable assignment                                |
| `a = 3;`                 | Variable assignment - semicolon suppresses output  |
| `pi`                     | Constant PI                                        |
| `A = [1 2; 3 4; 5 6]`    | A 3x2 matrix with denoted elements                 |
| `V = [1; 2; 3]`          | A 3x1 column vector i.e $V \in \mathbb{R}^3$       |
| `1:4` | Creates a matrix $\begin{bmatrix}1 & 2 & 3 & 4\end{bmatrix}$ |
| `0:2:4` | Creates a matrix $\begin{bmatrix}0 & 2 & 4\end{bmatrix}$ values from 0 to 4 with spacing of 2 |
| `linspace(first, last, num_elements)` | Useful when creating a range of values (no need to calculate spacing yourself) |
| `help eye`               | Shows man page for eye                             |
| `doc eye`                | Open doc page for eye |
| `pwd`                    | Print working directory                            |
| `cd`                     | Change directory                                   |
| `ls`                     | List files                                         |
| `load someData.dat`      | Load data |
| `save filename variable` | Save variables                  |
| `save workspace.mat`     | Save variables in workspace to a MAT-file |
| `load workspace.mat` | Load saved workspace variables |
| `format long` | Increase precision (default is short) |
| `who`                    | Show variables in the current scope                |
| `whos`                   | Show variables in the current scope with more info |

Watch out: in Octave/MATLAB vectors are not zero-indexed i.e. they start at one

Note: All MATLAB variables are arrays. Understand the difference between
matrix, column vector, row vectror and scalar. Fun fact: MATLAB is an
abbreviation for MATrix  LABoratory - makes sense.

Tip: If you only use one index with a matrix, it will traverse down each column
in order. Using one index, try extracting the eighth element of data.

## MATLAB Manipulating data (matrices/vectors)

| Command       | Usage                                                                                         |
| :------------ | :-------------------------------------------------------------------------------------------- |
| `A * B`       | Matrix multiplication                                                                         |
| `A .* B`      | Element-wise multiplication                                                                   |
| `abs(V)`      | Element-wise absolute                                                                         |
| `exp(V)`      | Element-wise exponentiation                                                                   |
| `log(V)`      | Element-wise log                                                                              |
| `max(A)`      | Maximum element in $A$                                                                        |
| `round(A)` | Round each element to the nearest integer |
| `a < 2`       | Element-wise comparison                                                                       |
| `find(A < 3)` | Elements that are less than 3                                                                 |
| `sum(A)`      | Sum of $A$                                                                                    |
| `magic(n)`    | Generate a n x n magic matrix                                                                 |
| `A .* eye(n)` | Assuming $A$ is an n x n matrix then this yields the diagonal and all other elements are zero |
| `flipud(A)`   | Flip matrix up-down                                                                           |
| `A(A > 2)` | Logical indexing. You can use a logical array as an array index, in which case MATLAB extracts the array elements where the index is true. |

## MATLAB Plotting data

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
% More plot ideas at https://uk.mathworks.com/products/matlab/plot-gallery.html
% use xlim([xmin xmax]) to zoom in on an area of interest
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

## MATLAB Control statements

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

## MATLAB Functions

Functions are defined in files such as `addTwoNumbers.m`. Make sure your
function is in your octave search path or current working directory.

```matlab
% File: addTwoNumbers.m
function y = addTwoNumbers(a, b)
y = a + b;
```

Pro tip: Octave can natively return multiple values.

## Vectorisation (advance topic)

By using the vectorised implementation we can take advantage of matrix multiplication provided by the linear algebra library which will be faster than implementing a summation yourself (usually with a for loop). Below is an example.

$$
h_{\theta}(x) = \sum^n_{j=0} \theta_j x_j = \theta^T x
$$

where

$$
\theta =
\begin{bmatrix}
\theta_0 \\
\theta_1 \\
\vdots \\
\theta_n
\end{bmatrix},
x =
\begin{bmatrix}
x_0 \\
x_1 \\
\vdots \\
x_n
\end{bmatrix}
$$

It is easy to see how vectorisation works.

## Further reading

- [GNU Octave Documentation](https://octave.org/doc/v5.2.0/)
