# Asymptotic Equivalences

In the lectures, we said that logarithms with different bases don't affect the
asymptotic complexity of an algorithm. Prove that $O(\log_{2} n)$ is the same as
$O(\log_{5} n)$. Use the mathematical definition of $O$ -- do a formal proof,
not just the intuition.

I have started with the formal definition of $O$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$T(n) \in O(f(n)) \iff \exists c, n_0: T(n) \leq c \cdot f(n) \forall n \geq n_0$

## Answer

The goal is to show that $O(\log_{2} n) = O(\log_{5} n)$.

Let $T(n) \in O(\log_{2} n)$. By definition:

$\exists c_1, n_0: T(n) \leq c_1 \cdot \log_{2} n \forall n \geq n_0$

Using the change of base formula, we know that:
$\log_{2} n = \frac{\log_{5} n}{\log_{5} 2}$

Now, $T(n) \leq c_1 \cdot \log_{2} n = c_1 \cdot \frac{\log_{5} n}{\log_{5} 2} = (\frac{c_1}{\log_{5} 2}) \cdot \log_{5} n$

Let $c_2 = \frac{c_1}{\log_{5} 2}$. Since this is just a constant, we have shown that $T(n) \in O(\log_{5} n)$.

The proof that $O(\log_{5} n) = O(\log_{2} n)$ follows the same steps, just using $\log_{5} n = \frac{\log_{2} n}{\log_{2} 5}$ instead.

Therefore, $O(\log_{2} n) = O(\log_{5} n)$.
