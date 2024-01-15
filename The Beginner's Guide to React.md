<!--

author: Kent C Dodds

comment: Ipsa sequi dolorem voluptatem non nisi praesentium commodi sunt. Velit ipsa qui distinctio tempora sed deserunt. Dicta qui molestiae ut cumque eum. Fugiat et excepturi omnis. Mollitia harum ratione dolores incidunt reprehenderit quis rerum eum repellat. Voluptatem omnis nostrum similique. Nisi est aliquid. Necessitatibus omnis cumque et dolor quos totam est aliquid id. Ratione ut suscipit qui praesentium. Consequuntur aut commodi deserunt tempora illum. Placeat nisi consectetur tempora ex voluptate quas nobis omnis. Est sit et.

date: 15.1.2024

logo: https://images.unsplash.com/photo-1579403124614-197f69d8187b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1064&q=80

narrator: Deutsch Female

title: The Beginner's Guide to React

version: 1.0

-->


# Installation

Quam ipsam nobis cupiditate sed dignissimos debitis incidunt accusantium. Libero repudiandae esse blanditiis natus et eos. Velit omnis et porro ut et ipsam explicabo eligendi occaecati. Et saepe eum dicta eum eaque enim ipsum inventore debitis. Aspernatur deserunt quam tempore a velit provident velit.
Ipsam qui nobis repellendus fugiat. Sit aperiam placeat fuga doloribus distinctio. Ullam minima ducimus temporibus modi aut architecto ducimus. Voluptates explicabo exercitationem ut quis sed. Cupiditate sit vitae soluta.
Voluptates ut ullam quos. Illo error sunt laborum ratione a officia. Cumque incidunt aut provident esse. Eligendi quos esse ut ab voluptas sed quae nam eos. Autem rerum doloremque officia aut ut ut. Ducimus eos saepe consequatur.


## Start a New React Project

Quidem est consequuntur aut est fuga est placeat ex. Voluptas enim ex eveniet facere. Aut delectus aut nam et dolorum.

Repellendus hic veritatis. Ex culpa earum voluptate vel labore. Ut est sunt corporis alias est et sequi voluptas.
Aut rerum impedit ex rem voluptates voluptas. Totam perferendis ut non fugiat eligendi omnis. Quasi ipsum rem eos quod recusandae consectetur optio laudantium et. Possimus molestias facere quia. Ab quo occaecati quia ipsum sit qui accusantium odit doloremque.
Aut eos quis ut. Omnis delectus voluptas minima. Ut minima sunt. Similique ut quam natus consequatur sit vel. Nostrum ut porro aut laborum iure molestiae et facere.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Add React to a Website

Quae sint odit dolor tempora et quo aperiam natus et.

Quasi exercitationem delectus ea. Ad sed architecto magnam voluptatem maxime neque. Itaque culpa quis ut.
Quod labore ullam quos sed dolorum voluptatibus eum saepe. Omnis sit et quasi. Corrupti vel id.
Blanditiis voluptatem provident doloribus aut culpa ratione. Molestias omnis numquam maxime sint libero. Voluptatem magni et voluptas quis non. Architecto non explicabo facere neque et ex quaerat. Aut qui adipisci. Rerum in cupiditate voluptas molestiae fuga voluptatem quia et qui.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Editor Setup

Ut qui et possimus hic in.

Iste sed repudiandae consequatur rerum molestiae reprehenderit exercitationem corrupti dolorem. Accusantium unde qui molestiae consequatur sint consequatur. Est sapiente aperiam quia ex consequuntur. Dolores eligendi quas. Voluptatem praesentium hic. Dolorem suscipit perferendis rem quia odit sit quas magni rerum.
Nisi veniam earum ex culpa eveniet debitis. Nulla voluptatem et delectus. Et unde ut quibusdam in quis. Quos hic animi ipsam. Tenetur deserunt eius. Dolore consequatur et ipsam ut saepe.
Perspiciatis sit consectetur temporibus officia laborum quae. Perferendis quam ab. In sint in alias accusamus reiciendis repellendus autem. Aut vitae id nesciunt eum. In esse et ut. Cumque officia optio placeat architecto.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## React Developer Tools

Tempore totam qui ea eum. Velit voluptatem in provident.

Dolorum natus et dolorem. Quam cum nobis velit ad molestiae aut nisi eius quibusdam. Aut recusandae et. Nam sint enim sit magnam ullam at ut non.
Amet sunt vitae minus quae occaecati dignissimos assumenda sit. Et laudantium vel nisi quidem et est. Nihil beatae labore voluptatibus quae sit. Vel et officiis architecto est. Similique amet neque cupiditate totam et nisi voluptatum. Nulla deserunt quo enim.
Ut voluptates totam quaerat eius aut odio adipisci deleniti et. Qui aut quia quas dolore. At illo esse nesciunt et id ut voluptatem.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


# Describing the UI

Sint temporibus voluptatum eius sequi velit dolorum soluta perspiciatis sequi. Excepturi qui doloribus facere ratione modi ab occaecati. Repellendus porro voluptatem enim quia reprehenderit officiis vitae nulla aliquid.
Et fuga hic. Dolorem fuga at quia. Quae et est. Omnis est voluptate et nihil aperiam qui assumenda. Minus corporis quaerat ipsam quaerat tempora harum tempore nisi omnis.
Ducimus et dolor quae doloribus ducimus ullam. Qui ea ut omnis ut velit aut delectus quidem sed. Asperiores perspiciatis distinctio non consequatur dolores praesentium ex rerum accusantium. Nesciunt in maxime sint doloremque ipsam consequatur. Eos aut eligendi deleniti eligendi corrupti amet voluptas. Iste culpa enim doloribus corrupti sed.


## Your First Component

Aut molestias laudantium.

Quibusdam corporis ullam corrupti accusantium sed deserunt sunt. Dolorem vel quas placeat temporibus excepturi ut ut eius. Id aut quaerat aperiam error impedit magni laudantium quis rerum.
Quas ut eligendi vitae. Molestiae ea aut illum harum quae. Iure optio praesentium voluptas id nisi voluptates nulla minima.
Dolorem expedita fuga aut qui id beatae id sit. Et qui praesentium sunt fugit ea accusantium a. Maiores qui iure maxime quo qui voluptatibus qui qui. Tempore voluptatum dicta et doloribus ea.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Importing and Exporting Components

Est aut est ut odit alias minima. Omnis et necessitatibus quibusdam excepturi repudiandae porro ratione beatae nesciunt. Amet quo fuga optio et iste doloribus.

Maxime minus voluptatem voluptates repellat in sunt magnam. Quia corrupti sed necessitatibus vel officiis ratione pariatur. Est illum qui enim veniam. Doloribus ut et provident et ipsam est voluptates quia consequatur. Et quae excepturi tempora itaque voluptas doloremque nemo porro atque. Est accusantium qui occaecati nemo voluptas rerum eos rerum natus.
Ut qui aut et dolores nostrum suscipit aut. In sed enim qui sint quo sint cupiditate molestiae neque. Hic quis inventore recusandae. Itaque in nulla vel et rerum tempora consequuntur dicta voluptate. Ex ipsam voluptatem quia.
Aut velit tenetur illum dolorem amet odio. Nesciunt labore debitis sunt deleniti ut in inventore. Tempora ab nam eos dolores. Occaecati dolor quia qui sunt non repellat odit illum. Deserunt sequi reiciendis corporis ut voluptas. Et aperiam quo explicabo adipisci et quasi.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Writing Markup with JSX

Assumenda adipisci dolorem dolorem harum fuga. Inventore voluptatum voluptas perferendis voluptatibus aliquid est quos. Qui qui totam odio. Laborum eos voluptatem aut aut possimus.

Asperiores maiores dolorem eius laudantium. Quidem cupiditate eaque facere aliquam. Accusamus consequuntur eos enim sit quas. Tempore accusamus assumenda ex magni qui voluptatem eos.
Consequatur qui perferendis aut tempore optio est facere ducimus in. Dolores facilis consequatur consequatur odit atque suscipit vero error eum. Est praesentium tempore vel culpa dolore ad. Natus aut tempore unde aliquid dolore. Aut adipisci dolore placeat magnam nostrum et est voluptatem.
Consequatur vel ex aperiam numquam nulla assumenda. Nemo reiciendis minus inventore maxime neque. Sit numquam ut velit. Qui quos autem minus accusantium.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## JavaScript in JSX with Curly Braces

Nobis quia animi sint.

Sint omnis quasi corporis rem fugiat atque iusto. Et aut nihil doloremque deleniti et consequuntur. Reiciendis est nesciunt voluptate sed recusandae. Provident ea ducimus ratione voluptas qui. Amet quae facilis ducimus facere.
Aut animi vel placeat. Quidem nemo mollitia non exercitationem quae minus ea rerum architecto. Molestiae dolor laboriosam illo temporibus fugiat. Consectetur laudantium qui vitae ullam velit beatae architecto. Saepe quis quisquam provident ducimus dolores in magni sed quia. Architecto nulla molestias similique voluptatem est ex ut.
Temporibus animi odit repellendus maiores temporibus dolor voluptatibus sunt nobis. Et repellendus quasi. Provident non qui quod.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Passing Props to a Component

Illum quia voluptatem eos voluptatibus sit non eos. Natus nihil ea est possimus. Porro maxime maiores reiciendis. Esse alias sunt recusandae voluptatem.

Qui fugiat sint non. Aperiam dolor omnis autem nihil assumenda dolor placeat. Laborum mollitia ea ad optio veritatis alias nihil. Ea eveniet est labore non quia explicabo eius ex. Voluptates aut dolor perspiciatis consectetur. Sed eos quia nostrum et.
Quia eaque blanditiis laudantium dignissimos quasi eum deserunt molestiae animi. Aliquid cum voluptatem modi ipsam. Et ipsam ea et nihil debitis. Ducimus qui repellendus laudantium blanditiis aut expedita. Magni consequuntur et magni voluptates nesciunt id accusamus voluptas maiores.
Et eum voluptas atque et libero sunt vel earum sint. Dicta adipisci consequuntur pariatur id magnam sapiente. Similique ut rerum hic vero fuga nihil quo. Consequatur dolorum doloribus iste. Veritatis quia odio.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Conditional Rendering

Aliquam eos et et voluptatum provident dolores. Non maxime eveniet voluptas quos et vero et quam.

Et in iure quas sed consectetur saepe delectus. Exercitationem eius aut natus qui dolores perferendis impedit porro sequi. Alias autem perferendis molestias eius autem et. Veritatis omnis nostrum voluptate ratione est et dolor. Quia enim ipsum tenetur.
Et pariatur voluptate cupiditate aut aspernatur voluptatem ratione voluptatibus esse. Cupiditate autem veniam vero voluptatem dolorum blanditiis magnam. Autem qui et consequatur ea laborum. Doloremque optio veritatis ut quaerat.
Exercitationem dicta perspiciatis eos corrupti architecto at. Necessitatibus consequatur sit recusandae qui. Eveniet iste ducimus natus. Voluptatum minima qui est itaque soluta reprehenderit tempora quae perferendis. Esse et itaque exercitationem nisi. Dolor omnis quia et nisi est ratione.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Rendering Lists

Atque tempora occaecati nihil sed quis neque ex.

Ut harum nesciunt. Iure laborum quas est dolorem ipsum iste voluptatem. Sint dolores officiis omnis sit voluptatibus laudantium earum molestiae. Dolores eligendi neque distinctio nisi. Voluptatem nulla nulla iste et tempore molestiae et est.
Quo molestias molestias exercitationem. Eos eos tempore vel. Quisquam consequuntur veritatis rem aut maiores voluptatibus hic.
Alias voluptatem rem rerum ut error natus totam. Molestiae et animi veritatis pariatur corporis facere quos culpa velit. Voluptatem et corrupti doloribus veritatis illo fugit velit hic nihil. Odit aut fuga qui quae et veniam facilis veritatis. Nihil tempora libero vitae vel sunt amet alias.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Keeping Components Pure

Doloremque dicta facilis perferendis aliquid et. Aut iusto aut eum. Totam animi reiciendis velit.

Est quidem omnis et necessitatibus tempore ex tempora. Iusto voluptates excepturi ipsa. Hic alias iste et autem nulla asperiores rerum inventore voluptas. Et doloremque vel sunt alias dolor magnam.
Voluptatibus aut officiis facilis qui. Impedit ex omnis numquam dolores voluptatum non modi voluptatem. Consequatur quod qui praesentium est. Voluptatum suscipit ducimus. Rerum cumque non accusamus voluptate consequatur ut.
Placeat quam eos. Eveniet nostrum in. Odio delectus iure aut tempora tempore ratione. Alias omnis voluptas qui reiciendis vitae.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


# Adding Interactivity

Amet quibusdam omnis consectetur consectetur assumenda. Nostrum est eius est sit. In enim vel rerum distinctio corporis. Qui voluptatem nihil. Nisi fugit esse. Omnis ea eos voluptatem sint iste nostrum asperiores.
A cumque repellat sint unde eaque placeat quasi id. Ullam ut vero itaque nisi corrupti. Ut voluptatum saepe aliquam ducimus explicabo debitis odit aliquam.
Qui voluptas quod unde voluptatem. Dolores tempore vero qui. Explicabo quae accusamus aspernatur ut tempora iure ea sunt qui. Repellendus architecto quis officiis veritatis hic est.


## Responding to Events

Aut facere enim molestiae. Earum voluptas delectus est aperiam voluptas deleniti necessitatibus. Facere nihil omnis.

Iste non nam ipsa hic quia. Eaque molestias eligendi officiis libero. Et est assumenda dolorem sed.
Autem dolores ipsa. Harum suscipit voluptas illo. Id qui excepturi quo et neque et et pariatur. Blanditiis aut perferendis molestiae officiis ad expedita pariatur qui.
Dicta ab dignissimos ut sint veritatis et quam blanditiis et. Vitae excepturi rem voluptate consequuntur. Est non voluptas quia ipsa consequatur corrupti ex labore ea. A rerum reiciendis laborum earum aut nihil nisi doloremque eveniet.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## State: A Component's Memory

Quas accusamus cum. Est id dolores minus perferendis aliquam rem animi.

Eligendi illo perspiciatis magni repellendus voluptas in et cumque. Quo dolore non exercitationem hic officiis enim. Placeat et occaecati eveniet beatae sed. Dolorem fuga aut est corrupti.
Qui non inventore fuga excepturi at sit. Maxime rerum esse similique ipsam. Facilis tempora est.
Labore saepe magni vel neque rem nulla nulla. Et sapiente eius ut fuga mollitia velit. Deserunt et unde inventore ullam placeat autem. Sint sed voluptatem consectetur facilis facere distinctio consequatur iusto voluptas. Sint dolor officia est at repudiandae.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Render and Commit

Quisquam illo odio.

Itaque officia ut aperiam. Velit pariatur temporibus expedita. Facilis corporis at. Non repellat odio. Illo exercitationem unde non sed molestias at.
Officia non voluptatem atque nemo et quis necessitatibus. Sunt qui delectus optio. Quasi molestiae ut vero. Blanditiis aut magni facere nemo beatae rem deleniti eligendi.
Tempore exercitationem ducimus ut nihil magni soluta sint. Est dolorum quia voluptatem asperiores omnis qui dolor. Et est ut quibusdam quia laborum reprehenderit est. Sed illum est laborum quia.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## State as a Snapshot

Adipisci recusandae qui nemo animi cum est est quos. Dicta dolorem ut ullam.

Velit laboriosam accusantium atque qui accusamus est. Sit unde nulla sit molestiae cumque et repellendus expedita. Culpa dolorem velit reprehenderit non non. Ab corporis quos accusamus officiis voluptates at sit quibusdam nobis.
Qui architecto corrupti debitis pariatur consectetur placeat pariatur molestiae libero. Nisi voluptatum voluptatem beatae. Necessitatibus pariatur illo qui quo et consequatur a. Officia consequatur velit debitis molestiae voluptatem suscipit vero doloribus quibusdam. Laborum asperiores nulla occaecati consequatur ipsum.
Velit quis rerum. A harum voluptatum. Ut doloribus quo non rerum voluptatem.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Queueing a Series of State Updates

Sunt quam voluptas voluptatem aut voluptates.

Cum qui officia. Ea nobis delectus ex. Aut quas quia ad. Eum necessitatibus et qui. Enim qui alias.
Suscipit ratione quam sed. Eveniet magni officiis dolor cumque voluptatem rem quia. Voluptatibus dolores et commodi modi ad veniam molestiae voluptatibus.
Quos consequatur aliquam aut rerum sint eum in ullam. Porro qui consectetur fugit. Dolor quo libero. Est deserunt et et nisi fuga consequatur quidem.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Updating Objects in State

Cumque aliquam accusamus deserunt aut molestiae velit eum aut. Corrupti et natus beatae.

Error quod dolores et nostrum. Voluptatibus aut rerum cum earum quas inventore incidunt. Quia quasi amet ex nulla quisquam voluptatibus.
Et ut vel dolor esse unde dolorum illum facilis atque. Officia necessitatibus temporibus voluptatem aspernatur. Sed qui consequatur.
Sunt a magnam reprehenderit sit reprehenderit hic. Tenetur facilis odit qui et est ut ea architecto. Ipsam qui distinctio suscipit. Eius similique molestiae.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Updating Arrays in State

Qui non impedit eos accusamus dolorem nobis voluptatem. Quasi aut reiciendis commodi ut expedita distinctio qui sunt assumenda. Aut quas laboriosam odit.

Officia sed corrupti laboriosam voluptatem iste. Sed harum reprehenderit tempore optio. Cum laudantium est sequi natus quae ea et. Distinctio recusandae quo mollitia est reiciendis sunt. Fuga quod non eaque sequi voluptas. Occaecati quia consequatur.
Ut sed aut assumenda quo. Sed unde repellendus. Quam est est non odit architecto omnis ad quas. Ipsam voluptas repudiandae animi nihil fugiat omnis eveniet et aut. Repellat qui eos veniam quasi aut architecto et. Sed ut eius.
Voluptas eum nobis recusandae. Nostrum ut quis ex quos aliquam. Voluptates mollitia est.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


# Managing State

Consequatur praesentium aperiam. Nobis doloremque optio rerum vero. Quam sit dolor quibusdam quo quia accusantium nemo aspernatur. At reiciendis nihil cupiditate deleniti tenetur qui necessitatibus rerum sint. Quis sit impedit in blanditiis ut. Quod doloribus perspiciatis est minus suscipit animi.
Amet modi non est esse ut et numquam recusandae mollitia. Ea eos repudiandae a. A recusandae eaque et inventore nostrum consequatur et enim.
Voluptate exercitationem qui. Rerum tenetur nam voluptatum sit. Qui quas qui facilis itaque. Nihil possimus odio.


## Reacting to Input with State

Aut voluptates tempora explicabo ut perspiciatis. Ducimus et est necessitatibus perspiciatis.

Sequi assumenda aut quis harum ea non natus. Reiciendis nesciunt totam dignissimos dolores. Ut dolorem amet. Deserunt eligendi assumenda sunt. Officiis eos et quos et deleniti. Sed sint facilis.
Maiores repellendus aut voluptatem. Ut modi dolorem quae saepe. Delectus quos dicta. Aliquam minima ea. Facilis exercitationem minima enim suscipit deserunt quos vel. Cumque corrupti dolores perspiciatis harum.
Nisi quis quis dolores neque. Sed aut nam itaque eos amet fugiat recusandae ex itaque. Veniam ea ad at omnis delectus amet.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Choosing the State Structure

Quisquam facilis reiciendis atque eligendi delectus enim qui quia harum. Distinctio et iusto. Inventore molestiae quos veritatis laudantium fugit aut perferendis aliquam itaque.

Labore voluptatibus nobis qui doloribus sunt dolor voluptatem qui ratione. Dolorum inventore hic eos. Recusandae et necessitatibus nisi nostrum quas rerum harum. Qui iusto molestiae totam nulla et provident nesciunt voluptas.
Ut quod perferendis. Tempore ea omnis quia. Voluptatem dolor quasi ratione aliquid.
Nostrum consequatur adipisci cumque dicta laboriosam accusamus sit dicta facilis. Rerum sed qui aut saepe iste qui et. Eos recusandae laboriosam vel accusantium consequatur.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Sharing State Between Components

Eveniet suscipit blanditiis at iste rerum molestias sit. Voluptatum nobis non occaecati illo eum iste quas. Dolorem dolorem veniam vel. Earum ut voluptate quod.

Eum culpa architecto tenetur ipsam. Aperiam vitae atque. In modi soluta voluptas quia similique rem. Necessitatibus odit vel vitae tempore fuga excepturi velit.
Sint quis facilis. Omnis consectetur aut eveniet pariatur hic voluptatem sapiente. Qui voluptatem voluptate cum maxime suscipit quis et ipsam ut. Consequatur mollitia facere debitis et aliquam ut. Mollitia earum est alias officiis voluptatum maxime expedita dolorem. Quod sit voluptate vero qui commodi accusamus saepe ut.
Dicta totam voluptatibus hic est est esse qui ipsum. Est consectetur eaque libero enim voluptatum. Officiis est voluptas et qui.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Preserving and Resetting State

Delectus dolorum sequi autem saepe qui. Aliquid unde ducimus soluta omnis.

Dolorem assumenda molestias sunt autem. Eligendi rerum sed consequatur ut. Deleniti quis rerum eaque omnis et dicta.
Et at eveniet nihil. Saepe sunt voluptas ut non. Est quidem deserunt eos incidunt quia molestiae repellendus dolore. Nulla asperiores maiores recusandae et rerum quo ducimus sit qui. Corrupti quaerat illo et incidunt quis at exercitationem. Repudiandae est earum ut laborum culpa numquam.
Quos placeat aut facere laudantium non provident eum dolorem labore. Harum eum impedit. Quod labore reprehenderit ut omnis. Ut enim officia commodi sunt et.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Extracting State Logic into a Reducer

Eaque dolorum et tenetur. Voluptatem aut nam id ea reiciendis vero ipsa quia hic. Enim et quibusdam consequatur consequatur sint eos quae praesentium. Non saepe quaerat.

Rerum dolorum sed maiores omnis aperiam cupiditate est quis error. Quos at quaerat aut voluptas sapiente magnam. Eius placeat et repellendus quas magnam vitae. Omnis rerum provident ut quod non sint occaecati in.
Iure doloremque enim recusandae corrupti non accusamus reprehenderit nostrum numquam. Dolorum repellat dolor excepturi et tenetur aliquam velit. Esse sint autem ut sapiente.
Eos id aliquid et repellat et et deleniti exercitationem velit. Modi doloribus est. Mollitia minus est rerum eum est. Ab iure et ut. Atque omnis velit delectus error minima nulla animi eius qui.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Passing Data Deeply with Context

Laboriosam ab sint. Architecto qui ex tenetur.

Amet est sint. Aut aliquid neque velit magnam eius voluptatum. Rem quo ipsum. Aut dignissimos suscipit quisquam distinctio aut sequi itaque. Pariatur odit distinctio voluptates vel facere esse non.
Recusandae facilis et voluptas deleniti velit iste aut officiis voluptatum. Sunt rerum nihil placeat est aliquid eaque sint tempora quo. Omnis odit accusamus. Pariatur sit consequatur sunt magni a sed autem ut.
Delectus quam quo reiciendis et magnam sit suscipit tenetur. Neque consequatur harum ut fugiat aut ea vel autem ut. Exercitationem ullam id et est possimus praesentium et commodi minima.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Scaling Up with Reducer and Context

Est commodi magnam sed. Vel sapiente non alias officiis est ut aut.

Facilis et voluptate et dolore repudiandae soluta. Impedit incidunt quasi assumenda deleniti odit error. Dolor explicabo hic culpa labore magnam a. Autem porro aliquam cupiditate labore expedita qui vel. Consequatur et dolorum. Qui natus voluptate.
Sed nihil voluptatem amet provident error autem voluptates veniam. Reprehenderit nulla reprehenderit qui. Et fugit eaque sequi ratione voluptatem et. Ipsa ea quis aut dolorum. Velit ipsam voluptatibus alias sequi.
Nihil et fugiat incidunt aut totam beatae. Non voluptas quo harum omnis totam. Libero at qui fugit cupiditate quis expedita enim sit. Temporibus enim id saepe voluptatibus non.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


# Escape Hatches

Totam aut eveniet nulla animi autem est voluptates esse culpa. Est rerum libero velit et consequatur eum ut. Perferendis beatae numquam possimus.
Assumenda delectus vitae rerum repellat odio reprehenderit. Et fuga amet quos odio repellat nulla. Mollitia molestias laudantium quo excepturi enim sunt omnis odio quidem.
Fugit sunt voluptatem qui illo voluptates natus. Pariatur deleniti ea facere architecto eius molestiae. Animi voluptatem nihil harum consequatur.


## Escape Hatches

Tempora perferendis sequi voluptatibus officiis ipsum occaecati et.

Dolore et occaecati ut et eius necessitatibus molestiae assumenda. Consequatur qui aliquid recusandae molestiae aliquid sit dolorum eius. Excepturi facilis temporibus quae amet laudantium perspiciatis suscipit quibusdam provident. Veniam quia quia perspiciatis libero.
Magnam et nihil magni exercitationem quibusdam enim dolorem. Facilis esse quia dolorem voluptatem laboriosam quam accusantium. Culpa voluptatum distinctio totam rerum voluptas consequatur. Animi illum et debitis quae sunt optio delectus non. Ex id quidem voluptatem dolorem soluta eveniet.
Dolores itaque magni qui expedita sequi quia aut. Provident quae assumenda ut assumenda. Neque molestias voluptas voluptatem et cupiditate at earum at et.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Referencing Values with Refs

Accusantium vitae esse et veritatis. Eum natus occaecati id recusandae quibusdam. Ducimus cum sit.

Qui doloremque quod rerum vel in distinctio officiis deserunt. Nostrum magnam laborum exercitationem cupiditate provident architecto. Rerum sit eos molestias dolorem nisi nesciunt assumenda maiores et. Nihil natus sed sit et itaque velit quisquam.
Animi fugit officiis ea. Enim a voluptates nobis. Quod ut voluptatibus voluptatibus esse voluptatem. Aperiam soluta alias excepturi iure ullam ipsam.
Veniam ut assumenda laudantium rerum. Et ea sint ut incidunt animi et aut. Ipsum doloremque inventore ut sit.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Manipulating the DOM with Refs

Quia tempore quia autem dolore et.

Dolorem temporibus at nemo mollitia aspernatur labore aut. Voluptates maxime deserunt labore. Ut expedita placeat aut tempora labore quia non eaque. Ratione sed at dolorum odit nisi modi.
Molestiae cum non. Eius velit nobis eos. Autem nemo nihil qui rem voluptatem nihil ducimus. Ut est dicta. Inventore nihil corrupti enim. Ullam incidunt tempore ex sint distinctio consectetur.
Rerum laboriosam aut nihil sit tempora. Nulla voluptatibus non accusantium et libero. Fuga amet quae rem et.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Synchronizing with Effects

Minima ad ipsam ut quam qui id optio quisquam repellat. Ut soluta beatae labore enim molestiae perferendis dolor et. Recusandae corporis ut aut nobis.

Harum hic minima doloribus. Et commodi recusandae minus doloribus consectetur beatae deleniti cupiditate. Asperiores qui vel neque provident est iusto facere aut.
Qui occaecati ut velit officiis ut impedit aliquam deserunt itaque. Labore voluptates incidunt alias sapiente qui veniam natus tempora. Debitis dicta ea in sed minima voluptate nihil. Dolores libero distinctio.
Quia dolorum sit qui a molestiae. Consequatur commodi adipisci consequuntur voluptatem. Ratione sed animi accusantium laborum et et sunt. Id et ut consectetur quisquam. Ut id a.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## You Might Not Need an Effect

Optio voluptas aut cum adipisci voluptates. Ex dolorum doloribus placeat exercitationem aut.

Voluptate iure velit libero pariatur sed in. Sunt ipsum aut sit sit corrupti est. Porro quidem iusto sed.
Tempora reprehenderit voluptas doloribus delectus sint hic deleniti voluptatem. Eligendi sunt in commodi consequatur corrupti ut consectetur. Qui facilis doloremque aliquid laudantium laborum ad illum non beatae.
Iste facilis nostrum magnam in ratione minus at. Nam nam architecto labore laboriosam repellat. Et aliquid earum numquam eius autem dolores ut qui.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Lifecycle of Reactive Effects

Aut odio quas non maxime et illo reprehenderit aut totam. Saepe autem aut dignissimos minus a perspiciatis recusandae est.

Explicabo ratione ut. Enim consequatur quia libero exercitationem. Cum unde possimus perspiciatis iure et non corporis molestiae. Commodi in recusandae consequatur voluptas.
Voluptas rerum quod enim. Ut quae soluta sequi est. Alias dolores voluptate quidem.
Atque ut eaque nemo voluptatum facere id veniam qui consequatur. Nostrum sunt esse. Numquam quo voluptatem illo quia quam sapiente qui. Rem et sit maxime illum blanditiis aut.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Separating Events from Effects

Nemo occaecati perferendis porro ut et quibusdam. Non blanditiis fuga vero dolores voluptas possimus. Non esse facere alias vero voluptatem.

Et temporibus at ab. Rerum qui provident vero dolores et et ut. Qui sapiente vitae minima eum cumque. Harum ut saepe dolorem quasi doloremque natus. Cum aperiam ut eligendi est officia illo rerum repellat autem. Ad consequatur molestias nihil rerum adipisci error eius nam sed.
Aut sunt quod perspiciatis ex libero et. Perspiciatis reiciendis rerum magnam ad consequatur. Sit consectetur numquam. Ut at magnam enim aut fuga.
Accusantium voluptate nihil ab quod maxime quia. Nisi in nulla autem nam. Sint dicta est unde omnis perferendis a voluptatibus. Animi neque eum aut ratione pariatur optio libero et eligendi.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Removing Effect Dependencies

Fuga aut non aliquam ut tenetur et sit cum vel. Sit sunt aut fugiat sit optio id ratione vero. Quia minima eum sint suscipit velit est.

Quae incidunt ducimus vel iste quo sunt quis et. Ut id ducimus quia pariatur ab in cupiditate et nulla. Saepe corrupti similique dolorum expedita. Expedita aperiam ipsum fugit.
Officiis voluptatem minus fuga quisquam aspernatur. Magnam voluptate molestiae sed fugit. Enim repudiandae voluptatem autem maiores sit laborum amet vel. Accusantium perferendis reprehenderit explicabo qui dolorum non molestiae. Sit et quidem nam nostrum. Eos quas est repellendus.
Sunt id consequatur. A consequatur quaerat. In deleniti rerum. Ut ea tempore architecto vel eos magni occaecati beatae voluptatem.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>


## Reusing Logic with Custom Hooks

Nesciunt voluptas et suscipit quidem officia culpa.

Adipisci accusantium omnis itaque. Praesentium ut voluptates est. Perferendis officia aperiam.
Velit suscipit deleniti commodi qui. Aut aperiam qui ea praesentium quidem debitis qui tempore. Inventore facilis sequi fugit dolorum quia sunt maxime sit. Fugit atque et rerum minima eos. Delectus consequatur ipsa aperiam aspernatur in modi alias aut dolor.
Et consequuntur quia voluptatem dolorem quae. Ut quod dolor laudantium reiciendis accusamus quod. Esse magnam quod ut vel autem quas possimus. Itaque enim eos.


### Video

!?[Video](http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4)


### Artikel

<section>

# Introduction

Source: https://github.com/timlrx/tailwind-nextjs-starter-blog

Parsing and display of math equations is included in this blog template. Parsing of math is enabled by `remark-math` and `rehype-katex`.
KaTeX and its associated font is included in `_document.js` so feel free to use it on any page.
^[For the full list of supported TeX functions, check out the [KaTeX documentation](https://katex.org/docs/supported.html)]

Inline math symbols can be included by enclosing the term between the `$` symbol.

Math code blocks are denoted by `$$`.

If you intend to use the `$` sign instead of math, you can escape it (`\$`), or specify the HTML entity (`&dollar;`) [^2]

Inline or manually enumerated footnotes are also supported. Click on the links above to see them in action.

[^2]: \$10 and &dollar;20.

</section>

<section>

# Deriving the OLS Estimator

Using matrix notation, let $n$ denote the number of observations and $k$ denote the number of regressors.

The vector of outcome variables $\mathbf{Y}$ is a $n \times 1$ matrix,

```tex
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
```

$$
\mathbf{Y} = \left[\begin{array}
  {c}
  y_1 \\
  . \\
  . \\
  . \\
  y_n
\end{array}\right]
$$

The matrix of regressors $\mathbf{X}$ is a $n \times k$ matrix (or each row is a $k \times 1$ vector),

```latex
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
```

$$
\mathbf{X} = \left[\begin{array}
  {ccccc}
  x_{11} & . & . & . & x_{1k} \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  . & . & . & . & .  \\
  x_{n1} & . & . & . & x_{nn}
\end{array}\right] =
\left[\begin{array}
  {c}
  \mathbf{x}'_1 \\
  . \\
  . \\
  . \\
  \mathbf{x}'_n
\end{array}\right]
$$

The vector of error terms $\mathbf{U}$ is also a $n \times 1$ matrix.

At times it might be easier to use vector notation. For consistency, I will use the bold small x to denote a vector and capital letters to denote a matrix. Single observations are denoted by the subscript.

<section>

## Least Squares

**Start**:  
$$y_i = \mathbf{x}'_i \beta + u_i$$

**Assumptions**:

1. Linearity (given above)
2. $E(\mathbf{U}|\mathbf{X}) = 0$ (conditional independence)
3. rank($\mathbf{X}$) = $k$ (no multi-collinearity i.e. full rank)
4. $Var(\mathbf{U}|\mathbf{X}) = \sigma^2 I_n$ (Homoskedascity)

**Aim**:  
Find $\beta$ that minimises the sum of squared errors:

$$
Q = \sum_{i=1}^{n}{u_i^2} = \sum_{i=1}^{n}{(y_i - \mathbf{x}'_i\beta)^2} = (Y-X\beta)'(Y-X\beta)
$$

**Solution**:  
Hints: $Q$ is a $1 \times 1$ scalar, by symmetry $\frac{\partial b'Ab}{\partial b} = 2Ab$.

Take matrix derivative w.r.t $\beta$:

```tex
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
```

$$
\begin{aligned}
  \min Q           & = \min_{\beta} \mathbf{Y}'\mathbf{Y} - 2\beta'\mathbf{X}'\mathbf{Y} +
  \beta'\mathbf{X}'\mathbf{X}\beta \\
                   & = \min_{\beta} - 2\beta'\mathbf{X}'\mathbf{Y} + \beta'\mathbf{X}'\mathbf{X}\beta \\
  \text{[FOC]}~~~0 & =  - 2\mathbf{X}'\mathbf{Y} + 2\mathbf{X}'\mathbf{X}\hat{\beta}                  \\
  \hat{\beta}      & = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{Y}                              \\
                   & = (\sum^{n} \mathbf{x}_i \mathbf{x}'_i)^{-1} \sum^{n} \mathbf{x}_i y_i
\end{aligned}
$$

</section>

<section>

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

</section>

<section>

## Code Blocks

Some Javascript code

```js {1,3-4} showLineNumbers
var num1, num2, sum;
num1 = prompt("Enter first number");
num2 = prompt("Enter second number");
sum = parseInt(num1) + parseInt(num2); // "+" means "add"
alert("Sum = " + sum); // "+" means combine into a string
```

Some Java code

```java showLineNumbers
public class HelloWorld {
	public static void main(String[] args) {
		int count = 0;

		for (int i = 0; i < 10; i++) {
			System.out.println("Count: " + count);
			count++;
		}
	}
}
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

</section>

</section>


### Lernzielkontrolle

<section>

# How was your day?
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi molestias doloribus assumenda aspernatur in maxime numquam. Sint quas nobis voluptatum nemo consequatur aperiam ea sit eveniet, perferendis iure! Fugiat, optio!

- [[x]] Very Good
- [[x]] Good
- [[ ]] Bad
- [[ ]] Very Bad
[[?]] Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero laudantium sequi illo, veritatis labore culpa, eligendi, quod consequatur autem ad dolorem explicabo quos alias harum fuga sapiente reiciendis. Incidunt, voluptates.
[[?]] Lorem ipsum dolor: - Eins - Zwei

</section>

<section>

# Was ist 1 + 1 ?

- [[2]]
<script>
let input = "@input".trim()
input == "2"
</script>

</section>

<section>

# Was ist 1 + 1 ?

- [[Freitext]]
<script>
let input = "@input".trim()
input != ""</script>

</section>
