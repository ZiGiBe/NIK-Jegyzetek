a.
$$
\sum^\infty_{k=0}{(-1)^k}{x^k} = 1 - x + x^2 - x^3 + \dots = \frac{1}{1+x}
$$
b.
$$
\sum^\infty_{k=0}{x^{2k}} = 1 + x^2 + x^4 + x^6 + \dots = \frac{1}{1-x^2}
$$
c.
$$
\sum^\infty_{k=0}x^{2k+1} = x + x^3 + x^5 + \dots = \frac{x}{1-x^2}
$$
d.
$$
\sum^\infty_{k=0}{(-1)^k \cdot x^{2k}} = 1 - x^2 + x^4 - x^6 + \dots = \frac{1}{1+x^2}
$$
e.
$$
\sum^\infty_{k=1}kx^{k-1} = 1 + 2x + 3x^2 + \dots = (\frac{x}{1-x})' = \frac{1}{(1-x)^2}
$$
f.
$$
\sum^\infty_{k=1}(-1)^k\cdot kx^{k-1} = -1 + 2x - 3x^2 + \dots = (\frac{x}{1+x})' = -\frac{1}{(1+x)^2}
$$g.
$$
\sum^\infty_{k=1}2kx^{2k-1} = 2x + 4x^3 + 6x^5 + \dots = (x^2 + x^4 + x^6 + \dots)' = (\frac{x^2}{1-x^2})'  = \frac{2x(1-x^2) - x^2(-2x)}{(1-x^2)^2} = \frac{2x}{(1-x^2)^2}
$$
h.
$$
\sum_{k=1}^\infty \frac{x^k}{k} = x + \frac{x^2}{2} + \frac{x^3}{3} \dots = \int 1 + x + x^2 + x^3 \dots =\int \frac{1}{1-x} dx = -\ln|1-x| + C
$$


## Hatványsorok konvergenciatartományai

$$
r = \lim_{k\rightarrow\infty}|\frac{c_k}{c_{k+1}}|
$$
$$
r = \lim_{k\rightarrow\infty}\frac{1}{\sqrt[k]{|c_k|}}
$$
a.
$$
\sum^\infty_{k=1} k!x^k
$$
$$
r = \lim_{k\rightarrow\infty} |\frac{k!}{(k+1)!}| = |\frac{1}{(k+1)}| = 0
$$
b.
$$
\sum^\infty_{k=1}2^{2k}\cdot x^{2k}
$$
$$
r = \lim_{k\rightarrow\infty} |\frac{1}{\sqrt[k]{2^{2k}}}| \rightarrow \frac{1}{2^2} = \frac{1}{4}
$$
$$
\sum_{k=1}^\infty2^{2k}\cdot (\frac{1}{4})^{2k} = (\frac{2}{4})^{2k}
$$
$$
\sum_{k=1}^\infty2^{2k}\cdot(-\frac{1}{4})^{2k} = (-\frac{1}{2})^{2k}
$$
$$
D_s = [-\frac{1}{4};\frac{1}{4}]
$$
g.
$$
\sum_{k=1}^\infty\frac{k!}{k^k}(x-1)^k
$$
$$
r =\lim_{n\rightarrow\infty} \frac{\frac{k!}{k^k}}{\frac{(k+1)!}{(k+1)^{k+1}}} \rightarrow \frac{k!}{k^k} \cdot \frac{(k+1)^{k+1}}{(k+1)!} = (\frac{k+1}{k})^k = \infty
$$
## Fourier
