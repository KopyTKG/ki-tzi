---
date: 2026-10-22
tags:
  - cviceni
---

# Tranzitivní zákon
Tvrzení $n > 5 \implies n > 3$ není potřeba dokazovat indukcí, plyne přímo z tranzitivity relace $>$.

Tranzitivní zákon (relace): $a > b \land b > c \implies a > c$

Dosadíme $a = n$, $b = 5$, $c = 3$. Protože $5 > 3$ platí vždy, z $n > 5$ plyne $n > 3$.
$$
 n > 5 \implies n > 3 \\
 5 > 3 \\
 n > 5 > 3 \\
 n > 3 \\
 n > 5 \land 5 > 3 \implies n > 3
$$

# Přímý důkaz
Chceme dokázat implikaci $X \implies Y$.

1. Předpokládáme, že platí $X$.
2. Řadou správných kroků (definice, již dokázaná tvrzení, např. tranzitivní zákon) z $X$ odvodíme $Y$.
3. Tím je dokázáno $X \implies Y$.

$$
 X \implies X_1 \implies X_2 \implies \dots \implies Y
$$

Příklad: pro $n \in \mathbb{N}$ dokažme $n \text{ je sudé} \implies n^2 \text{ je sudé}$.

Předpokládáme, že $n$ je sudé, tedy existuje $k \in \mathbb{N}$ takové, že $n = 2k$. Pak $n^2 = 4k^2 = 2 \cdot 2k^2$, což je sudé číslo.
$$
 n \text{ je sudé} \implies n = 2k \\
 n^2 = (2k)^2 \\
 n^2 = 4k^2 \\
 n^2 = 2 \cdot (2k^2) \\
 n^2 \text{ je sudé}
$$

# Přímý důkaz: $X \implies Y$ pro nerovnosti
Označíme $X \equiv x > 5$ a $Y \equiv x > 3$. Chceme dokázat $X \implies Y$.

Předpokládáme $X$, tedy $x > 5$. Protože $5 > 3$, plyne z tranzitivního zákona $x > 3$, tedy $Y$.
$$
 X \equiv x > 5 \\
 Y \equiv x > 3 \\
 X \implies Y \\
 x > 5 \implies x > 3 \\
 x > 5 \land 5 > 3 \implies x > 3
 
 \\
 \text{obměna: } \lnot Y \implies \lnot X \\
 x \leq 3 \implies x \leq 5 \\
 x \leq 3 \land 3 \leq 5 \implies x \leq 5
$$

# Pravdivostní tabulky
Implikace $X \implies Y$ je nepravdivá jen tehdy, když $X$ platí a $Y$ neplatí.

| $X$ | $Y$ | $X \implies Y$ |
| --- | --- | -------------- |
| 1   | 1   | 1              |
| 1   | 0   | 0              |
| 0   | 1   | 1              |
| 0   | 0   | 1              |

Implikace je ekvivalentní své obměně $\lnot Y \implies \lnot X$ (poslední dva sloupce se shodují).

| $X$ | $Y$ | $\lnot X$ | $\lnot Y$ | $X \implies Y$ | $\lnot Y \implies \lnot X$ |
| --- | --- | --------- | --------- | -------------- | -------------------------- |
| 1   | 1   | 0         | 0         | 1              | 1                          |
| 1   | 0   | 0         | 1         | 0              | 0                          |
| 0   | 1   | 1         | 0         | 1              | 1                          |
| 0   | 0   | 1         | 1         | 1              | 1                          |

Pro $X \equiv x > 5$ a $Y \equiv x > 3$ nastane řádek $X = 1, Y = 0$ nikdy, protože z $x > 5$ plyne $x > 3$.

| $x$ | $X \equiv x > 5$ | $Y \equiv x > 3$ | $X \implies Y$ |
| --- | ---------------- | ---------------- | -------------- |
| 10  | 1                | 1                | 1              |
| 4   | 0                | 1                | 1              |
| 1   | 0                | 0                | 1              |

# Důkaz sporem
Chceme dokázat implikaci $X \implies Y$. Využijeme, že $X \implies Y$ je nepravdivá jen v případě $X \land \lnot Y$, takže stačí ukázat, že $X \land \lnot Y$ nemůže nastat.

1. Předpokládáme opak toho, co chceme dokázat: platí $X$ a zároveň $\lnot Y$.
2. Z těchto předpokladů odvodíme spor, tedy tvrzení, které neplatí (např. $5 < 3$).
3. Předpoklad $X \land \lnot Y$ je tedy nepravdivý, a proto platí $X \implies Y$.

| $X$ | $Y$ | $\lnot Y$ | $X \land \lnot Y$ | $\lnot(X \land \lnot Y)$ | $X \implies Y$ |
| --- | --- | --------- | ----------------- | ------------------------ | -------------- |
| 1   | 1   | 0         | 0                 | 1                        | 1              |
| 1   | 0   | 1         | 1                 | 0                        | 0              |
| 0   | 1   | 0         | 0                 | 1                        | 1              |
| 0   | 0   | 1         | 0                 | 1                        | 1              |

Příklad: $X \equiv x > 5$, $Y \equiv x > 3$. Předpokládejme, že $x > 5$ a zároveň $x \leq 3$. Pak $5 < x \leq 3$, tedy $5 < 3$, což je spor, protože $5 > 3$.
$$
 \text{předpoklad: } X \land \lnot Y \\
 x > 5 \land x \leq 3 \\
 5 < x \leq 3 \\
 5 < 3 \\
 \text{spor, protože } 5 > 3 \\
 \lnot(X \land \lnot Y) \equiv X \implies Y
$$

# Indukce
Dokazujeme tvrzení $V(n): 1 + 2 + \dots + n = \dfrac{n(n+1)}{2}$ pro všechna $n \geq 1$. Na rozdíl od nerovnosti výše tady indukci opravdu potřebujeme, protože $V(n)$ je tvrzení o součtu s proměnným počtem sčítanců.

1. Základ: $n = 1; V(1)$
	Ověříme tvrzení pro nejmenší $n$.
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
4. Závěr: $V(n); n \geq 1$
	Základ platí a z $V(k)$ plyne $V(k+1)$, takže $V(n)$ platí pro všechna $n \geq 1$.
