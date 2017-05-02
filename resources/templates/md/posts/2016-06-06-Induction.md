{:title "Mathematical Induction"
  :layout :post
  :tags ["discrete mathematics"]}

## WHAT?

Is a tool that allows us to prove properties about a program, it is also a principle and a proof technique that is based on the use of a propositional function $P$, where
if we prove that $P((1))$ is true,  and $\forall k.(P (k) \implies P (k + 1))$ are true for positive integers,
then $\forall n . P(n)$ is true.

Sometimes the base case can be 0 or 1, the important thing is that
it correspond to the minimal case of the sequence we want to prove.
We are going to look at some cases where the base case is 8. For instance, if you want to prove that $2^n \geq n^2$, for all integers $n \geq 8$, the base case should look like $2^8 \geq 4^8$

Properties are the same kind you will find in property based testing, which comes from an important area of Mathematics and
Phylosophy called Logic. A property is an assertion about a something, that can be true or false. In our case we are going to look at properties about programs or computations.

Mathematical induction can be used only to prove results obtained in some other way.
It is not a tool for discovering formulae or theorems.

## WHY?

It is extremely important in the field of computer science because it is a tool that allows us
to prove the correctness of programs.
Computation can be performed recursively over the structure of the data, and as
good hackers, we can exploit the inductive nature of a computation process using induction
to prove results about a large variety of discrete objects. In practice, it is used to prove results about complexity
of algorithms, the correctness of certain types of computer programs, or theorems about graphs and trees.

Originally, the method is used to establish statements about natural numbers, but as many resources in mathematics, it can be generalized to work on any recursive data structure, such lists or trees.


## The principle of mathematical induction

provides us with a very powerful technique to prove  several mathematical regards. You show that the first case is true, and show if any case is true, the following case is also true.

A statement, a predicate which depends on
we can prove a statement like $P(k) \Rightarrow x > 5$ then
assuming that $k$ is true, we can prove that the statement
is also true for $k + 1$

1. $P ((1))$ is true
2. $\forall k \>= 1, P(k) \Rightarrow P(k + 1)$

$P((1)) true \Rightarrow P((2)) true \Rightarrow P((3)) true \Rightarrow ...$

## How?

### Proofs using the principle of mathematical induction

A proof by mathematical induction has two parts: a **basis step** or base case, where we
show that P is true for the minimum value of the result to be proved, and an **inductive step**, wherewe show that for all integers k, if $P(k)$ is true, then $P (k + 1)$ is also true.

Three steps!. Two Parts

1. **basis of induction:** proof that $P(n)$ is true for the minimal case, generally 0 or 1.
2. **Induction hypothesis:**. Asume that $P(k)$ is true
3. **Inductive step:** show that $P(k +1)$ is true for the basis of the induction
   hypothesis



### Proof by induction's Hello World

Usually the literature [^1] [^2] [^3] use the following  property as an introduction to the subject.

$$
\forall n\left[\sum_{i=0}^n i= \frac{n(n+1)}{2}\right]
$$
where $n >= 1$ in a finite integer

1. Basis of induction n = 1 , 1 ( 1 + 1) / 2 = 1

so $S(1) = n (n + 1) / 2$ is true for 1

2. Induction hypothesis
Suppose for $k >= 1$
$S(k) = k (k + 1) / 2$ is true

3.Inductive step
$S(k + 1) = 1 + 2 + 3 + 4 + ... + k + (k + 1)$

$= (k ( k + 1) /2) + (k + 1)$


### Example 2

We want to prove the following:

$$1²+2²+3²+...+n² = \frac{n(n+1)(2n+1)}{6}$$

for any $n \geq 1$ such that $n \in \mathbb{N}$

**1. Inductive case:**

$$ 1² = 1 \wedge \frac{1(1+1)(2+1)}{6}= 1$$

it is clear that pluging $1$ to the equation gives us 1 as expected, which is also equal to $1^2$.

**2. Induction hypothesis. We asume that the following is true:**

$$\frac{k(k+1)(2k+1)}{6}$$

or in other words, that $P(k)$ is true.

**3. Inductive step:**

Then, if $P(k)$ is true, we are going to prove that $P(k+1)$ is also true.

$$\begin{align}
\textcolor{limegreen}{
1²+2²+3²+...}+
\textcolor{magenta}{n^2} = \frac{n(n+1)(2n+1)}{6}
\end{align}
$$

the left hand side of the equation is equivalent to $P(k) + P(k+1)$, according to our induction hypothesis. So let's express that, as follows


$$
\begin{align}
\textcolor{limegreen}{    
  \frac{k(k+1)(2k+1)}{6}
}  +
\textcolor{magenta}{
  (k+1)^2
  } = \frac{
       \textcolor{turquoise}{n}
	   (\textcolor{turquoise}{n}+1)(2
	    \textcolor{turquoise}{n}+1)}{6}
\end{align}
$$

On the right hand side we replace every
$\textcolor{turquoise}{n }$ occurence  by $ \textcolor{turquoise}{(k+1)}$

$$
\begin{align}
\textcolor{limegreen}{    
  \frac{k(k+1)(2k+1)}{6}
}  +
\textcolor{magenta}{
  (k+1)^2
  } = \frac{
         \textcolor{turquoise}{(k+1)}
		  (\textcolor{turquoise}{(k+1)}+1)(2
		   \textcolor{turquoise}{(k+1)}+1)}{6}
\end{align}
$$

In order to add the second term on the left hand side,
it has to share the same denominator

$$
\begin{align}
\frac{k(k+1)(2k+1)}{6}+
  \frac{\textcolor{magenta}{6}(k+1)^2}{
    \textcolor{magenta}{6}}
= \frac{(k+1)((k+1)+1)((2k+1)+1)}{6}
\end{align}
$$

by algebra  

$$
\begin{align}
\frac{(k^2+k)(2k+1)+(6k+6)(k+1)}{6}
= \frac{(k+1)((k+1)+1)((2k+1)+1)}{6}
\end{align}
$$

$$
\begin{align}
\frac{(k^2+k)(2k+1)+(6k+6)(k+1)}{6}
= \frac{(k+1)((k+1)+1)((2k+1)+1)}{6}
\end{align}
$$


$$
\begin{align}
\frac{2k^3 + k²+ 2k^2 + k +6k^2 + 6k+ 6k+ 6}{6} =
\frac{2k^3 + 3k^3+ 4k^2+ 6k + 2k^2 + 3k +4k+ 6}{6}
\end{align}
$$

$$
\begin{align}
\frac{2k^3 + 9k^2 + 13k + 6}{6} = \frac{2k^3 + 9k^2 + 13k + 6}{6}
\end{align}
$$



$$
\Box
$$


Recursive Definitions and Structural Induction
==============================================

Hola


Resources
=========

A funny way to get a better grasp about induction is the great book [The Little Prover](https://mitpress.mit.edu/books/little-prover)

Chapter 5 from both books:  [Discrete Mathematics with Applications] and [Discrete Mathematics and its Applications]

Oscar also recomends chapter3 and 4 of [Discrete Mathematics using a computer -John O’Donnell, Cordelia Hall-Springer]

[DTU Podcast: Induktion 1](http://podcast.llab.dtu.dk/feeds/01017-diskret-matematik/?tx_enotepodcast_pi1%5BshowDetails%5D=3570e67cd3fc3d7ca8da4b27cc2a2f7f&cHash=1c6b6d9fa1a4a5eb76f648cb5b6a7667)

[DTU Podcast: Induktion 2](http://podcast.llab.dtu.dk/feeds/01017-diskret-matematik/?tx_enotepodcast_pi1%5BshowDetails%5D=5c3e060620827523c0d70c0d0fed9102&cHash=0312c2e8a34c1002d2024c09be4195d5)

[DTU Podcast: Induktion 3](http://podcast.llab.dtu.dk/feeds/01017-diskret-matematik/?tx_enotepodcast_pi1%5BshowDetails%5D=ace7086958f383bfb786051b9dc53b52&cHash=2a52672448a763990739539b14971769)

### References

[^1]: [Discrete Mathematics with Applications.Sussana S. Epp. Fourth Edition](http://condor.depaul.edu/sepp/DMwA4e.htm)
[^2]: [Discrete Mathematics and its applications. Kenneth H. Rosen, Seventh Edition]()
[^3]: []
