# Couple limits

**Theorem**

```math
\lim_{x \to \infty} (1 + \frac{1}{x})^{x} = e
```

**Proof**

Let's expand $(1 + \frac{1}{x})^{x}$ using Newton's binom.

```math
\lim_{x \to \infty} (1 + \frac{1}{x})^{x} = \sum_{k = 0}^{x} \binom{x}{k} 1^{k}(\frac{1}{x})^{x - k} = \sum_{k = 0}^{x} \binom{x}{k} (\frac{1}{x})^{x - k}
```

We can rewrite the last one as

```math
\lim_{x \to \infty} \sum_{k = 0}^{x} \frac{x!}{k!(x - k)!}(\frac{1}{x})^{k} = \sum_{k = 0}^{x} \frac{x!}{k!(x - k)!}(\frac{1}{x^{k}}) = \sum_{k = 0}^{x} \frac{1}{k!}\frac{x(x - 1)(x - 2) \dots (x - k + 1)}{x^{k}}
```

We can label the last one as

```math
\lim_{x \to \infty} \sum_{k = 0}^{x} \frac{1}{k!}\frac{x_{1} \cdot (x - 1)_{2} \cdot (x - 2)_{3} \cdot \dots \cdot (x - (k - 1))_{k}}{x_{1} \cdot x_{2} \cdot \dots \cdot x_{k}} = \sum_{k = 0}^{x} \frac{1}{k!}\frac{x_{1}}{x_{1}} \cdot \frac{(x - 1)_{2}}{x_{2}} \cdot \frac{(x - 2)_{3}}{x_{3}} \dots \cdot \frac{(x - k + 1)_{k}}{x_{k}}
```

Finally, synthetizing for $k = \\{ 0, 1, 2, \dots \\}$ we get

```math
\lim_{x \to \infty} \sum_{k = 0}^{x} \frac{1}{k!}\frac{x_{1}}{x_{1}} \cdot \frac{(x - 1)_{2}}{x_{2}} \cdot \frac{(x - 2)_{3}}{x_{3}} \dots \cdot \frac{(x - k + 1)_{k}}{x_{k}} = \frac{1}{0!} + \frac{1}{1!}\frac{x_{1}}{x_{1}} + \frac{1}{2!}\frac{x_{1}}{x_{1}} \cdot \frac{(x - 1)_{2}}{x_{2}} + \frac{1}{3!}\frac{x_{1}}{x_{1}} \cdot \frac{(x - 1)_{2}}{x_{2}} \cdot \frac{(x - 2)_{3}}{x_{3}} + \dots =
```
```math
= 1 + 1 + \frac{1}{2} \cdot \frac{(x - 1)_{2}}{x_{2}} + \frac{1}{3!} \cdot \frac{(x - 1)_{2}}{x_{2}} \cdot \frac{(x - 2)_{3}}{x_{3}} + \dots = 1 + 1 + \frac{1}{2} \cdot (\frac{x_{2}}{x_{2}} - \frac{1}{x_{2}}) + \frac{1}{3!} \cdot (\frac{x_{2}}{x_{2}} - \frac{1}{x_{2}}) \cdot (\frac{x_{3}}{x_{3}} - \frac{1}{x_{3}}) + \dots =
```
```math
= 1 + 1 + \frac{1}{2} \cdot (1 - \frac{1}{x_{2}}) + \frac{1}{3!} \cdot (1 - \frac{1}{x_{2}}) \cdot (1 - \frac{2}{x_{3}}) + \dots = 1 + 1 + \frac{1}{2} \cdot (1 - \frac{1}{x}) + \frac{1}{3!} \cdot (1 - \frac{1}{x}) \cdot (1 - \frac{2}{x}) + \dots
```

where this last one is the one you can find on Stackexchange. Now, we apply the limit, obtaining

```math
\lim_{x \to \infty} 1 + 1 + \frac{1}{2} \cdot (1 - \frac{1}{x}) + \frac{1}{3!} \cdot (1 - \frac{1}{x}) \cdot (1 - \frac{2}{x}) + \dots = 1 + 1 + \frac{1}{2} \cdot (1 - 0) + \frac{1}{3!} \cdot (1 - 0) \cdot (1 - 0) + \dots = 1 + 1 + \frac{1}{2} + \frac{1}{3!} + \frac{1}{4!} + \dots = e
```
```math
\square
```

This is the only real proof of the former identity. Fuck every other corposloppy fake proof.

**Theorem**

```math
\lim_{y \to \infty} (1 + \frac{a}{y})^{y} = e^{a}
```

**Proof**

Setting

```math
t = \frac{y}{a} \rightarrow y = at
```

we can rewrite the previous as

```math
\lim_{t \to \infty} (1 + \frac{1}{t})^{at}
```

because $y \to \infty$ causes $t \to \infty$. Now

```math
\lim_{t \to \infty} (1 + \frac{1}{t})^{at} = [(1 + \frac{1}{t})^{t}]^{a} = e^{a}
```
```math
\square
```

**Theorem**

```math
\lim_{y \to \infty} (1 - \frac{a}{y})^{y} = e^{- a}
```

**Proof**

Setting

```math
t = - \frac{y}{a} \rightarrow y = - at
```

we can rewrite the previous as

```math
\lim_{t \to \infty} (1 + \frac{1}{t})^{- at}
```

The sign behaviour is subtle. The best way to think about it I found is to focus on the application of the minus sign. What we are really doing in the substitution is

```math
t = \frac{y}{- a} \rightarrow y = (- a)t
```

This somehow justify why $y \to \infty$ doesn't cause $t \to - \infty$. The whole sign behaviour is completely held by the $a$ constant and we simply declare $t$ to flip its sign. Thinking about it deeply quite makes sense. If we are declaring $t$ to be sign flipped compared to $y$, then it wouldn't make sense to evaluate $t \to - y$, because we'd lose the meaning we want to express. This reasoning is particularly not intuitive because $(y, t) \to \infty$ in reality means we are considering two equivalent forms of the same identity with signs flipped: **(1)** the one between addends inside parentheses and **(2)** the exponent one. Now we can finally obtain

```math
\lim_{t \to \infty} (1 + \frac{1}{t})^{- at} = [(1 + \frac{1}{t})^{t}]^{- a} = e^{- a}
```

and therefore

```math
\lim_{y \to \infty} (1 - \frac{a}{y})^{y} = e^{- a}
```
```math
\square
```

**We can observe that we can make an approximation of this last formula.** Whenever $y$ makes $\frac{a}{y}$ very small, then

```math
\lim_{y \to \infty} (1 - \frac{a}{y})
```

```math
\diamond\diamond\diamond
```
