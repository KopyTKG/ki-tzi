# Indukce
Dokazujeme tvrzení $V(m): 1 + 2 + \dots + m = \dfrac{m(m+1)}{2}$ pro všechna $m \geq 1$.

1. Základ: $m = 1; V(1)$
	Ověříme tvrzení pro nejmenší $m$.
$$
 L = 1 \\
 P = \frac{1 \cdot (1+1)}{2} = 1 \\
 L = P
$$
2. Indukční předpoklad: $k \geq 1; V(k)$
	Předpokládáme, že tvrzení platí pro nějaké $k$.
$$
 1 + 2 + \dots + k = \frac{k(k+1)}{2}
$$
3. Indukční krok: $k + 1; V(k+1)$
	Z $V(k)$ chceme dokázat $V(k+1)$. K oběma stranám předpokladu přičteme $k+1$.
$$
 1 + 2 + \dots + k + (k+1) = \frac{k(k+1)}{2} + (k+1) \\
 = \frac{k(k+1) + 2(k+1)}{2} \\
 = \frac{(k+1)(k+2)}{2} \\
 = \frac{(k+1)((k+1)+1)}{2}
$$
4. Závěr: $V(m); m \geq 1$
	Základ platí a z $V(k)$ plyne $V(k+1)$, takže $V(m)$ platí pro všechna $m \geq 1$.

# Kombinační číslo
Obecný vzorec: $\dbinom{n}{k} = \dfrac{n!}{k!\,(n-k)!}; \, 0 \leq k \leq n$

Vypočítáme $\dbinom{19}{16}$.
$$
 \binom{19}{16} = \frac{19!}{16! \cdot (19-16)!} \\
 = \frac{19!}{16! \cdot 3!} \\
 = \frac{19 \cdot 18 \cdot 17 \cdot 16!}{16! \cdot 3!} \\
 = \frac{19 \cdot 18 \cdot 17}{3 \cdot 2 \cdot 1} \\
 = \frac{5814}{6} \\
 = 969
$$
otazka v testu(ukazka): Ktere prirozene cislo $x$ vyhovuje
$$
\begin{align}
	\dbinom{x+1}{2} + \dbinom{x}{2}&=4\dbinom{5}{5} \\
	\frac{(x+1)!}{2! *(x-1)!} + \frac{x!}{2! * (x-2)!} &= 4 * \frac{5!}{5! * {0}}\\
	\frac{(x+1)!}{2! *(x-1)!} + \frac{x!}{2! * (x-2)!} &= 4
\end{align}
$$
## Řešení
Podmínka: kombinační číslo $\dbinom{x}{2}$ je definované pro $x \geq 2$, tedy $x \in \mathbb{N}, x \geq 2$.

Pravá strana: $\dbinom{5}{5} = \dfrac{5!}{5! \cdot 0!} = 1$, protože $0! = 1$ (ne $0$). Pravá strana je tedy $4 \cdot 1 = 4$.

Levá strana rozepíšeme a zkrátíme faktoriály:
$$
\begin{align}
	\binom{x+1}{2} + \binom{x}{2} &= 4 \binom{5}{5} \\
	\frac{(x+1)!}{2! \cdot (x-1)!} + \frac{x!}{2! \cdot (x-2)!} &= 4 \\
	\frac{(x+1) \cdot x}{2} + \frac{x \cdot (x-1)}{2} &= 4 \\
	\frac{x\,(x + 1 + x - 1)}{2} &= 4 \\
	\frac{x \cdot 2x}{2} &= 4 \\
	x^2 &= 4 \\
	x &= 2 \;\lor\; x = -2
\end{align}
$$
Podmínce $x \geq 2$ vyhovuje jen $x = 2$.

Zkouška:
$$
 \binom{3}{2} + \binom{2}{2} = 3 + 1 = 4 = 4 \binom{5}{5}
$$
Odpověď: $x = 2$.


