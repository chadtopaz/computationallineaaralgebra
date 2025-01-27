Activity - Eigenvalues I
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

Let $\mathbf{A}$ be an $n \times n$ matrix. As a reminder, to perform
power iteration, we select any vector $\mathbf{x}^{(0)}$ in
$\mathbb{R}^n$, then compute
$\mathbf{x}^{(1)}=\frac{\mathbf{A}\mathbf{x}^{(0)}}{||\mathbf{A}\mathbf{x}^{(0)}||}$,
then compute
$\mathbf{x}^{(2)}=\frac{\mathbf{A}\mathbf{x}^{(1)}}{||\mathbf{A}\mathbf{x}^{(1)}||}$,
and so forth. From direct (repeated) substitution into the definition of
power iteration, one can find that the iterates satisfy
$\mathbf{x}^{(k)}=c_k \mathbf{A}^k \mathbf{x}^{(0)}$, where the sequence
of constants $\{c_k\}$, $k=0,1,\ldots$, is defined as

$$
c_k=\prod_{i=0}^{k-1} \frac{1}{ ||\mathbf{A}\mathbf{x}^{(i)}||}.
$$

(You can check this if you want.)

a\. Let $\mathbf{A} \mathbf{v}=\lambda\mathbf{v}$. For
$k \in \mathbb{Z}^+$, what is $\mathbf{A}^k\mathbf{v}$?

b\. An orthonormal basis for $\mathbb{R}^3$ is

$$
\mathbf{v}_1 = \begin{pmatrix}-\frac{4}{9}, -\frac{7}{9}, \frac{4}{9} \end{pmatrix}^T,\quad
\mathbf{v}_2 = \begin{pmatrix} \frac{1}{9},\frac{4}{9}, \frac{8}{9} \end{pmatrix}^T,\quad
\mathbf{v}_3 = \begin{pmatrix} \frac{8}{9},-\frac{4}{9}, \frac{1}{9} \end{pmatrix}^T.
$$

Consider a starting vector $\mathbf{x}^{(0)} = (-1, -2, -3)^T$. Find
$a_1$, $a_2$, and $a_3$ such that
$\mathbf{x}^{(0)}=a_1 \mathbf{v}_1 + a_2 \mathbf{v}_2 + a_3 \mathbf{v}_3$.

c\. The orthonormal vectors $\mathbf{v}_1$, $\mathbf{v}_2$, and
$\mathbf{v}_3$ are actually eigenvectors of

$$
\mathbf{A}=\frac{1}{9} \begin{pmatrix}
83 & 296 & -128 \\
296 & 473 & -152 \\
-128 & -152 & 335
\end{pmatrix},
$$

and they are ordered so that their associated eigenvalues are in order
of decreasing magnitude: $|\lambda_1| > |\lambda_2| \geq |\lambda_3|$.
Let’s use this and put together with what we know from having worked
through this problem this far:

$$
\begin{align*}
\mathbf{x}^{(k)}&=c_k \mathbf{A}^k \mathbf{x}^{(0)} \\
&=c_k \mathbf{A}^k (a_1 \mathbf{v}_1 + a_2 \mathbf{v}_2 + a_3 \mathbf{v}_3) \\
&=c_k (a_1 \mathbf{A}^k \mathbf{v}_1 + a_2 \mathbf{A}^k \mathbf{v}_2 + a_3 \mathbf{A}^k \mathbf{v}_3)\\
&=c_k (a_1 \lambda_1^k \mathbf{v}_1 + a_2 \lambda_2^k \mathbf{v}_2 + a_3 \lambda_3^k \mathbf{v}_3)\\
&=c_k \lambda_1^k \left[a_1 \mathbf{v}_1 + a_2 \left(\frac{\lambda_2}{\lambda_1}\right)^k \mathbf{v}_2 + a_3 \left(\frac{\lambda_3}{\lambda_1}\right)^k \mathbf{v}_3\right]
\end{align*}
$$

Explain what happens as $k$ increases, meaning, as we continue
performing power iteration Note: we need $a_1 \neq 0$. Give a geometric
explanation of when that condition is met.

d. Now write code to perform power iteration using the
$\mathbf{x}^{(0)}$ and $\mathbf{A}$ defined above. In each iteration of
your loop, also compute and print out

$$
\lambda^{(k)}=\frac{\left(\mathbf{x}^{(k)}\right)^T \mathbf{A} \mathbf{x}^{(k)}}{\left(\mathbf{x}^{(k)}\right)^T \mathbf{x}^{(k)}}.
$$

This is called the Rayleigh quotient, and it is the estimate for the
eigenvalue. What vector does your power iteration converge to? What
value does your Rayleigh quotient converge to?

### Problem 1 Solution

a\. Your solution goes here.

b\. Your solution goes here.

c\. Your solution goes here.

d\. Your solution goes here.
