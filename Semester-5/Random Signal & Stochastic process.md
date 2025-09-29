# Random Variables:

## Exponential:

PDF:
$$
f(x; \lambda) =
\begin{cases}
\lambda e^{-\lambda x}, & x \geq 0 \\
0, & x < 0
\end{cases}
$$
$$
\text{Mean: } \mathbb{E}[X] = \frac{1}{\lambda}
$$

$$
\text{Variance: } \text{Var}(X) = \frac{1}{\lambda^2}
$$

$$
\text{Moment Generating Function (MGF): } M_X(t) = \mathbb{E}[e^{tX}] = \frac{\lambda}{\lambda - t}, \quad t < \lambda
$$

$$
\text{Characteristic Function (CF): } \phi_X(t) = \mathbb{E}[e^{itX}] = \frac{\lambda}{\lambda - it}
$$



## Gaussian or Normal:

- If mean = 0 , var =1 $\;\Rightarrow\;$ Standard Gaussian
  $$
  X \sim \mathcal{N}(\mu, \sigma^2)
  $$
- PDF
  $$
  f(x) = \frac{1}{\sqrt{2 \pi \sigma^2}}
  \exp\!\left( -\frac{(x-\mu)^2}{2\sigma^2} \right),
  \quad -\infty < x < \infty
  $$
- CF:
  $$
  \varphi_X(w) = \mathbb{E}\!\left[e^{j w X}\right]
  = \exp\!\left(j \mu w - \tfrac{1}{2}\sigma^2 w^2 \right).
  $$
- Z-Score: Convert any normal distribution into the standard normal distribution
- Transform $X \rightarrow Z = \frac{X-\mu}{\sigma}$
$$
\text{Mean: } \mathbb{E}[X] = \mu
$$

$$
\text{Variance: } \text{Var}(X) = \sigma^2
$$

$$
\text{Moment Generating Function (MGF): } M_X(s) = \mathbb{E}[e^{sX}] = \exp\left(\mu s + \frac{1}{2}\sigma^2 s^2\right)
$$

$$
\text{Characteristic Function (CF): } \phi_X(\omega) = \mathbb{E}[e^{i \omega X}] = \exp\left(i \mu \omega - \frac{1}{2} \sigma^2 \omega^2 \right)
$$


## Rayleigh Distribution:

- PDF
  $$
  f(x; \sigma) =
  \begin{cases}
  \dfrac{x}{\sigma^2} \exp\!\left(-\dfrac{x^2}{2\sigma^2}\right), & x \geq 0 \\
  0, & x < 0
  \end{cases}
  $$
- CDF
  $$
  F(x; \sigma) =
  \begin{cases}
  1 - \exp\!\left(-\dfrac{x^2}{2\sigma^2}\right), & x \geq 0 \\
  0, & x < 0
  \end{cases}
  $$
  $$
 \mathbb{E}[X] = \sigma \sqrt{\tfrac{\pi}{2}},
\qquad \text{Var}(X) = \Big(2 - \tfrac{\pi}{2}\Big)\sigma^2
$$
## Rician Distribution:

$$
f(r; \nu, \sigma) =
\begin{cases}
\dfrac{r}{\sigma^2} \exp\!\left(-\dfrac{r^2 + \nu^2}{2\sigma^2}\right)
I_0\!\left(\dfrac{r\nu}{\sigma^2}\right), & r \geq 0 \\
0, & r < 0
\end{cases}
$$

## Nakagami:

- PDF
  $$
  f_X(x; m, \Omega) =
  \begin{cases}
  \frac{2 m^m}{\Gamma(m) \, \Omega^m} \, x^{2m-1} e^{-\tfrac{m}{\Omega} x^2}, & x \geq 0 \\
  0, & x < 0
  \end{cases}
  $$
## Gamma:

- Gamma Function:
  $$
  \Gamma(z) = \int_{0}^{\infty} t^{z-1} e^{-t} \, dt
  $$
  $$
  \Gamma(z+1)= z \Gamma(z)
  $$
- If $z$ is an integer
  $$
  \Gamma(z)= (z-1)!
  $$
- PDF:
  $$
  f(x; \alpha, \beta) =
  \begin{cases}
  \dfrac{1}{\Gamma(\alpha)\beta^\alpha} x^{\alpha-1} e^{-x/\beta}, & x > 0 \\
  0, & x \leq 0
  \end{cases}
  $$
  $\alpha : \text{shape parameter}$  
  $\beta : \text{scale parameter}$

- MGF
  $$
  M_X(t) = (1 - \beta t)^{-\alpha}, \quad t < \tfrac{1}{\beta}
  $$

- Expectation
  $$
  \mathbb{E}[X] = \alpha \beta
  $$

- Variance
  $$
  \text{Var}(X) = \alpha \beta^2
$$
$$
\text{Characteristic Function (CF): } \phi_X(\omega) = (1 - i \beta \omega)^{-\alpha}
$$

## Poisson:

- PMF
  $$
  P(X = k; \lambda) =
  \begin{cases}
  \dfrac{e^{-\lambda} \lambda^k}{k!}, & k = 0,1,2,\dots \text{ and } \lambda > 0 \\
  0, & \text{otherwise}
  \end{cases}
  $$
- PGF
  $$
  G_X(s) = e^{-\lambda} \cdot e^{\lambda s} = e^{\lambda(s-1)}.
  $$
- CF 
  $$
  \varphi_X(w) = \exp\!\big(\lambda(e^{j w} - 1)\big).
  $$
$$
\text{Mean: } \mathbb{E}[X] = \lambda
$$

$$
\text{Variance: } \text{Var}(X) = \lambda
$$
## Cauchy Distribution:

- MGF does not exist
  $$
  f_{X}(x) = \frac{1}{\pi (1+x^{2})}, \quad  -\infty < x < \infty
  $$

## Bernoulli:

- A single trial
- PMF
  $$
  P(X = x) =
  \begin{cases}
  p, & x = 1 \\
  1-p, & x = 0 \\
  0, & \text{otherwise}
  \end{cases}
  $$
- CDF
  $$
  F(x) =
  \begin{cases}
  0, & x < 0 \\
  1-p, & 0 \leq x < 1 \\
  1, & x \geq 1
  \end{cases}
  $$
- CF
  $$
  \varphi_X(\omega) = (1-p) + p e^{i\omega}
  $$

## Binomial:

- No. of successes in $n$ independent Bernoulli trials
- PMF
  $$
  P(X = k) =
  \begin{cases}
  \binom{n}{k} p^k (1-p)^{n-k}, & k = 0,1,2,\dots,n \\
  0, & \text{otherwise}
  \end{cases}
  $$
- CDF
  $$
  F_{X}(k) = P(X \leq k) = \sum_{i=0}^k \binom{n}{i} p^i (1-p)^{n-i},
  \quad k = 0,1,2,\dots,n
  $$

$$
\text{Mean: } \mathbb{E}[X] = n p
$$

$$
\text{Variance: } \text{Var}(X) = n p (1 - p)
$$

$$
\text{Moment Generating Function (MGF): } M_X(s) = (1 - p + p e^s)^n
$$

$$
\text{Characteristic Function (CF): } \phi_X(\omega) = (1 - p + p e^{i \omega})^n
$$


## Geometric:

- Number of trials until first success
- PMF
  $$
  P(X = k) =
  \begin{cases}
  (1-p)^{k-1} p, & k = 1,2,3,\dots \\
  0, & \text{otherwise}
  \end{cases}
  $$
- CF
  $$
  \varphi_X(\omega) = \sum_{k=1}^{\infty} e^{i\omega k}(1-p)^{k-1}p
  = \frac{pe^{i\omega}}{1 - (1-p)e^{i\omega}}, \quad |(1-p)e^{i\omega}| < 1
  $$
$$
\text{Mean: } \mathbb{E}[X] = \frac{1}{p}
$$

$$
\text{Variance: } \text{Var}(X) = \frac{1 - p}{p^2}
$$

$$
\text{Moment Generating Function (MGF): } M_X(s) = \frac{p e^s}{1 - (1 - p) e^s}, \quad e^s < \frac{1}{1 - p}
$$

## Negative Binomial:

- No. of trials until $r$th success  
- $r = 1 \Rightarrow$ Geometric
- PMF
  $$
  P(X = k) =
  \begin{cases}
  \binom{k-1}{r-1} p^r (1-p)^{k-r}, & k = r, r+1,\dots \\
  0, & \text{otherwise}
  \end{cases}
  $$
- CDF
  $$
  F(k) = \sum_{j=r}^{k} \binom{j-1}{r-1} p^r (1-p)^{j-r},
  \quad k = r, r+1,\dots
  $$
- CF
  $$
  \varphi_X(\omega) = \left( \frac{p e^{i\omega}}{1 - (1-p)e^{i\omega}} \right)^r, \quad 0<p\leq1
  $$
$$
\text{Mean: } \mathbb{E}[X] = \frac{r (1 - p)}{p}
$$

$$
\text{Variance: } \text{Var}(X) = \frac{r (1 - p)}{p^2}
$$

---

# Formulas:

## PMF:
$$
P_X(k) = P\{X=k\}
$$

## PDF:
$$
\int_{S_c}{f_X(x)}\, dx  = 1
$$

## CDF:
$$
F_X(x) = \int_{-\infty}^x f_X(x) \,dx = \sum_{-\infty}^x P_X(k)
$$

## Mean:
$$
\mu_X = \int_{-\infty}^{\infty}x f(x) \, dx = E[X]
$$
$$
\mu_X = \sum_k kP_X(k)
$$

## Variance:
$$
\sigma_X^2 = \int_{-\infty}^{\infty} (x-\mu_X)^2 f(x) \, dx
$$
$$
\sigma_X^2 = E[X^2] - \mu_X^2
$$

## Covariance:
$$
\mathrm{Cov}(X,Y) = \mathbb{E}\!\left[(X - \mu_X)(Y - \mu_Y)\right]
$$

## Median:
$$
P\{X \leq m \} \geq \tfrac{1}{2}
$$

## Mode:
- Value of $x$ where probability is highest.
- Where PDF is maximum. 

## MGF:
$$
M_X(s) = E[e^{sX}]
$$
$$
E[X^n] = \frac{d^nM_X(s)}{ds^n} \bigg|_{s= 0}
$$

## Probability Generating Function (PGF):
$$
G_X(s) = \mathbb{E}[s^X] = \sum_{k=0}^\infty P(X=k) \, s^k, \quad |s|\leq 1
$$

- Normalization: $G_X(1) = 1$  
- $G_X(0) = P(X=0)$  
- $\mathbb{E}[X] = G_X'(1)$  
- $\text{Var}(X) = G_X''(1) + G_X'(1) - (G_X'(1))^2$

Examples:
$$
\begin{aligned}
\text{Bernoulli}(p): & \quad G_X(s) = (1-p) + ps \\
\text{Binomial}(n,p): & \quad G_X(s) = \big((1-p) + ps\big)^n \\
\text{Poisson}(\lambda): & \quad G_X(s) = \exp\!\big(\lambda(s-1)\big)
\end{aligned}
$$

## Characteristic Function:
$$
\phi_X(\omega) = E[e^{j\omega X}]
$$
$$
E[X^k] =\frac{1}{j^k}\frac{d^k\phi_X(\omega)}{d\omega^k} \Big|_{\omega=0}
$$

## Q-function:
$$
Q(x) = \frac{1}{\sqrt{2\pi}} \int_x^\infty e^{-t^2/2} \, dt
$$
Relation:
$$
Q(x) = 1 - \Phi(x), \quad Q(-x) = \Phi(x)
$$

## Memoryless Property:
- Exponential & Geometric
$$
P(X > x+a \mid X > a) = P(X > x)
$$

## Bayes Theorem:
$$
P(A \mid B) = \frac{P(B \mid A)\, P(A)}{P(B)}
$$

---

# Identities:

## Binomial:
$$
\binom{n}{k} = \frac{n!}{k!(n-k)!}, \quad 0 \leq k \leq n
$$

## Maclaurin Series:
$$
e^{\lambda} = \sum_{k=0}^{\infty} \frac{\lambda^k}{k!}
$$
$$
e^{\lambda s} = \sum_{k=0}^{\infty} \frac{(\lambda s)^k}{k!}
$$

## Gaussian Integral:
$$
 \int_{-\infty}^{\infty}e^{-\alpha x^{2}}dx = \sqrt{\frac{\pi}{\alpha}}
$$

## Gamma Function:
$$
\Gamma(z) = \int_{0}^{\infty} t^{z-1} e^{-t} \, dt
$$
$$
\Gamma(z+1)= z \Gamma(z)
$$
If $z$ is an integer: $\Gamma(z)= (z-1)!$  
Also: $\Gamma\!\left( \tfrac{1}{2} \right) = \sqrt{ \pi }$

---

# Other Properties:

## Transform:
For $Y = g(X)$
$$
f_Y(y) = f_X(g^{-1}(y)) \left| \frac{d}{dy} g^{-1}(y) \right|
$$

If $Y = aX+b$:
$$
f_Y(y) = f_X\Big(\frac{y-b}{a}\Big) \cdot \frac{1}{|a|}
$$

For $Z = X+Y$ (independent):
$$
f_Z(z) = \int_{-\infty}^{\infty} f_X(x) f_Y(z - x) \, dx
$$

For $W= X-Y$:
$$
f_W(w) = \int_{-\infty}^{\infty} f_X(x) f_Y(x - w) \, dx
$$

## Markov's Inequality:
$$
\mathbb{P}(X \geq a) \leq \frac{\mathbb{E}[X]}{a}, \quad a > 0, X \geq 0
$$

## Chebyshev's Inequality:
$$
\mathbb{P}(|X - \mu| \geq b) \leq \frac{\text{Var}(X)}{b^2}, \quad b > 0
$$

## IID Random Variables:
Independent:
$$
\mathbb{P}(X \leq x,\, Y \leq y) = \mathbb{P}(X \leq x)\,\mathbb{P}(Y \leq y)
$$
Identically distributed: $X_1, X_2, \dots, X_n \sim F$

## Multivariate Distribution:
- Discrete joint PMF:
$$
p_{X,Y}(x,y) = \mathbb{P}(X = x,\, Y = y), \quad
\sum_x \sum_y p_{X,Y}(x,y) = 1
$$
- Continuous joint PDF:
$$
f_{X,Y}(x,y) \geq 0, \quad
\int_{-\infty}^{\infty}\int_{-\infty}^{\infty} f_{X,Y}(x,y)\, dx\,dy = 1
$$
- Marginals:
$$
f_X(x) = \int_{-\infty}^{\infty} f_{X,Y}(x,y)\,dy, \quad
f_Y(y) = \int_{-\infty}^{\infty} f_{X,Y}(x,y)\,dx
$$
$$
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}
$$
Adjoint:
$$
\operatorname{adj}(A) =
\begin{bmatrix}
d & -b \\
-c & a
\end{bmatrix}
$$

Inverse:
$$
A^{-1} = \frac{1}{ad - bc}
\begin{bmatrix}
d & -b \\
-c & a
\end{bmatrix}
$$
$$
A = \begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix}
$$

Adjoint
$$
\operatorname{adj}(A) = C^T
$$

Inverse:
$$
A^{-1} = \frac{1}{\det(A)} \operatorname{adj}(A)
$$


## Orthogonality:
$$
E[XY] = 0
$$

## Correlation Coefficient:
$$
\rho_{X,Y}= \frac{\mathrm{Cov}(X,Y)}{\sigma_X \sigma_Y}
$$

## Multivariate Gaussian Distribution:
$$
f_{\underline{X}}(\underline{x}) =
\frac{1}{(2\pi)^{n/2} |\mathbf{K}|^{1/2}}
\exp\!\left(
-\tfrac{1}{2} (\underline{x} - \boldsymbol{\mu})^T
\mathbf{K}^{-1}
(\underline{x} - \boldsymbol{\mu})
\right),
\quad
\underline{X} \sim \mathcal{N}(\boldsymbol{\mu}, \mathbf{K})
$$
where $\mathbf{K}$ is covariance matrix.

---

## Law of Large Numbers:
- Sample mean converges to population mean as n grows large
$$
\overline{X}_n \rightarrow \mu \quad \text{as } n \rightarrow \infty
$$
Sample mean:
$$
\overline{X}_n = \frac{1}{n}\sum_{i=1}^n X_i
$$
Weak LLN:
$$
\forall \epsilon > 0,\;\; \lim_{n \to \infty} P(|\overline{X}_n - \mu| \geq \epsilon) = 0
$$
Strong LLN:
$$
P\!\left(\lim_{n \to \infty} \overline{X}_n = \mu \right) = 1
$$

## Central Limit Theorem:
- Defined for sample means 
- let $y_{n}$= $\bar{X}_{25}$
- $E[y_{n}]= \mu_{x}$
- $Var(y_{n}) = \frac{\sigma_{x}^2}{n}$
- Standardizing  
$$
Z_n = \frac{\overline{X}_n - \mu}{\sigma / \sqrt{n}}
\;\;\; \xrightarrow{d} \;\;\; \mathcal{N}(0,1), \quad n \to \infty
$$

---

# Random Variable (Definition)

A **Random Variable** is a real-valued function defined over a sample space, assigning a number to each outcome.

- **Discrete RV (DRV):** described by PMF  
- **Continuous RV (CRV):** described by PDF  

## PMF:
$$
P_X(k) = P\{X=k\}
$$

## PDF:
$$
f_X(x) \geq 0, \quad \int_{S_c}{f_X(x)}\, dx = 1
$$

## CDF:
$$
F_X(x) = \int_{-\infty}^x f_X(x) \,dx = \sum_{-\infty}^x P_X(k)
$$

---

# MGF:
$$
M_X(s) = E[e^{sX}]
$$
$$
E[X^n] = \frac{d^nM_X(s)}{ds^n} \bigg|_{s=0}
$$

---

# Characteristic Function:
$$
\phi_X(\omega) = E[e^{j\omega X}]
$$
$$
E[X^n] = \frac{1}{j^n}\frac{d^n\phi_X(\omega)}{d\omega^n} \Big|_{\omega=0}
$$
