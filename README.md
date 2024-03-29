[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/8KYthzwp)
# Recurrent Recurrences

Give big $\Theta$bounds for the following recurrence relations.

1.
$$T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

2.
$$T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

3.
$$T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

### Response

__1. Solve by substitution:__

$T(n) = T(\frac{n}{13}) + 5$<br>
$= (T(\frac{n}{13^2}) + 5) + 5$<br>
$= T(\frac{n}{13^2}) + 10$<br>
$= ...$<br>
$= T(\frac{n}{13^i}) + 5i$<br>
$i = \log{ _{13} }{n}$<br>
$\implies T(\frac{n}{13^{\log{ _{13} }{n}}}) + 5 (\log{ _{13}}{n})$<br>
$= T(1) + 5 (\log{ _{13}}{n})$<br>
$= 5 (\log{ _{13}}{n}) \in \Theta(\log{n})$<br>

Therefore, $T(n)$ exists in $\Theta(\log{n})$.

__2. Solve by substitution:__

$T(n) = 13T(\frac{n}{13}) + 5$<br>
$= 13(13T(\frac{n}{13^2}) + 5) + 5$<br>
$= 169T(\frac{n}{13^2}) + 14 \cdot 5$<br>
$= ...$<br>
$= 13^iT(\frac{n}{13^i}) + 5 \cdot \sum\limits _{j=0}^{i}13^j$<br>
$i = log{ _{13}}{n}$<br>
$\implies 13^{\log{ _{13}}{n}} T(\frac{n}{13^{\log{ _{13}}{n}}})+ 5 \cdot \sum\limits _{j=0}^{\log{ _{13}}{n}} 13^j$<br>$
$= nT(1) + 5 \cdot \sum\limits _{j=0}^{\log{ _{13}}{n}} 13^j$<br>
$= n + 5 \cdot (13^{\log{ _{13}}{n}} + \sum\limits _{j=0}^{\log{ _{13}}{n} - 1} 13^j)$<br>
$n + 5 \cdot (n + \sum\limits _{j=0}^{\log{ _{13}}{n} - 1} 13^j) \in \Theta(n)$<br>

Therefore, $T(n)$ exists in $\Theta(n)$.

__3. Solve by substitution:__

$T(n) = 13T(\frac{n}{13}) + 2n$<br> 
$= 13(13T(\frac{n}{13^2}) + 2(\frac{n}{13})) + 2n$<br>
$= 169T(\frac{n}{13^2}) + 4n$<br>
$= ...$<br>
$= 13^iT(\frac{n}{13^i}) + 2in$<br>
$i = \log{ _{13}}{n}$<br>
$\implies13^{\log{ _{13}}{n}}T(\frac{n}{13^{\log{\_{13}}{n}}}) + 2n (\log{ _{13}}{n})$<br>
$= nT(1) + 2n (\log{ _{13}}{n})$<br>
$= n + 2n (\log{ _{13}}{n})  \in \Theta(n (\log n))$<br>

Therefore, $T(n)$ exists in $\Theta(n (\log n))$.

### Sources:
- https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions
- https://github.blog/2022-05-19-math-support-in-markdown/
- https://latex-tutorial.com/sum-latex/
- https://math.meta.stackexchange.com/questions/22443/how-to-markup-expression-using-sigma-notation-for-sum-in-mathjax
