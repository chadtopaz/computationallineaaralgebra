Activity - Fundamentals of Linear Systems
================

------------------------------------------------------------------------

When you begin work during class, work with your assigned partner.
Please have only one electronic device open and work on it jointly. When
writing up this assignment, please remember that showing all of your
work and giving your reasoning are critical parts of achieving mastery.
If the course staff cannot tell how you solved a problem or finds leaps
in explanation or logic, the problem is not mastered. Finally, as a
matter of academic integrity, please make sure that you are positioned
to honestly answer yes to these questions:

- Have I disclosed everyone with whom I collaborated on this work? (Even
  if it is only my assigned partner.)

- Have I made a substantive intellectual contribution to the solution of
  every problem?

- Am I making sure not to pass off as my own work any work that belongs
  to someone else?

Whether intentional or unintentional, any potential violations of
academic integrity will be referred to the Honor Committee.

------------------------------------------------------------------------

Load necessary packages:

``` r
library(pracma)
```

### Problem 1

Which of the following sets of vectors are bases for $\mathbb{R}^2$?

- $\{(0, 1), (1, 1)\}$
- $\{(1, 0), (0, 1), (1, 1)\}$
- $\{(1, 0), (-1, 0)\}$
- $\{(1, 1), (1, -1)\}$
- $\{(1, 1), (2, 2)\}$
- $\{(1, 2)\}$

### Problem 1 solution

Your solution goes here.

### Problem 2

What is the dimension of the intersection of the following two planes in
$\mathbb{R}^3$?

$$
x + 2y - z = 0, \ \ \ 3x - 3y + z = 0
$$

### Problem 2 Solution

Your solution goes here.

### Problem 3

Solve (by hand) the system below.

$$
\begin{pmatrix}
1 & 2 & 0 \\
3 & 2 & 4 \\
-2 & 1 & -2
\end{pmatrix} \begin{pmatrix}
x \\
y \\
z
\end{pmatrix} = \begin{pmatrix}
1 \\
7\\
-1
\end{pmatrix}
$$

### Problem 3 Solution

Your solution goes here.

### Problem 4

Put the augmented coefficient matrix for the system of equations

$$
\begin{aligned}
x+y+z&=2\\
x+3y+3z&=0\\
x+3y+6z&=3
\end{aligned}
$$

into row echelon form.

### Problem 4 Solution

Your solution goes here.

### Problem 5

I’ve written a function called `eliminate` that performs Gaussian
elimination in order to transform a matrix to row echelon form.

``` r
eliminate <- function(A, tol = 10^-8) {
  n <- nrow(A)
  for ( j in 1:(n-1) ) {
    pivot <- A[j,j]
    if (abs(pivot) < tol) stop('zero pivot encountered')
    for ( i in (j+1):n ) {
      A[i,] <- A[i,] - A[i,j]/pivot * A[j,]
    }
  }
  return(A)
}
```

Demonstrate $\mathcal{O}(n^3)$ complexity by doing the following. Run
the `eliminate` command on an $n \times n$ random matrix (generated
using the `runif` command) for each
`n <- round(seq(from = 700, to = 1000, length = 10))`, saving the run
time for each value of $n$. To save the run time, you can use something
like

``` r
tic()
2+2 # Just as an example
t1 <- toc(echo = FALSE)
```

Note: the computations will not be instantaneous, and you may have to
wait several minutes for them to finish. I urge you to use the
`cache = TRUE` option in your code block, which will prevent R from
re-running the block each time you knit, so long as the block hasn’t
changed. Instead, R will execute the code on the first knit, but it will
save the answer and just re-use that answer the next time the code is
knit. You should keep this option in mind as a possibility for all
future coding you do in R markdown.

Additionally, you should “seed” the random number generator. This means
that you’ll produce the same random matrices every time, which will
allow the result of the code block to remain the same, which will allow
successful caching. After the three tick marks that start a code block,
you’ll write `{r cache = TRUE}`. Then your next line will seed the
random number generator with `set.seed(123)` where the number 123 is
totally arbitrary. You can use any number you like; just don’t change it
after you choose it.

Finally, use the `lm` command to fit a line to the points
$(\log n,\log t)$ and find the slope.

### Problem 5 solution

Your solution goes here.

### Problem 6

Compute by hand the eigenvalues of the matrices

$$
\mathbf{A}=\begin{pmatrix}
1 & 1000 \\
0 & 1
\end{pmatrix}, \qquad \widetilde{\mathbf{A}}=\begin{pmatrix}
1 & 1000 \\
0.001 & 1
\end{pmatrix}.
$$

Would you say that the problem of computing eigenvalues is
well-conditioned or ill-conditioned? Check the condition number of
$\mathbf{A}$ using the `kappa` command with the option `exact = TRUE`.
For concreteness, use the 2-norm, though there is nothing special about
that choice.

### Problem 6 Solution

Your solution goes here.
