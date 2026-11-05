---
date: 2026-10-22
tags:
  - prednaska
---

> [!warning] Sestaveno zpětně z `Cv-4.md`
> Z této přednášky nemám vlastní poznámky. Obsah je odvozen z látky, kterou procvičuje [[Cv-4]] (cvičení bylo po přednášce), a navazuje na [[Pr-2]] a [[Pr-3]]. Co na přednášce opravdu zaznělo, může být jinak, a podle PDF z Downloads se probíral i disjunktní rozklad, třídy ekvivalence a zobrazení, které tu nejsou.

# Důkaz implikace $X \implies Y$

Implikace $X \implies Y$ je nepravdivá jen v jediném případě: $X$ platí a $Y$ neplatí.

| $X$ | $Y$ | $X \implies Y$ |
| --- | --- | -------------- |
| 1   | 1   | 1              |
| 1   | 0   | 0              |
| 0   | 1   | 1              |
| 0   | 0   | 1              |

Dokazovat lze třemi způsoby: přímo, nepřímo (obměnou) a sporem.

## Tranzitivní zákon
Relace $>$ je tranzitivní:
$$a > b \land b > c \implies a > c$$

Příklad: $n > 5 \implies n > 3$ plyne z $n > 5 > 3$ (dosadíme $a = n$, $b = 5$, $c = 3$ a $5 > 3$ platí vždy). Indukce tu není potřeba.

## Přímý důkaz
1. Předpokládáme, že platí $X$.
2. Řadou správných kroků (definice, již dokázaná tvrzení, např. tranzitivní zákon) z $X$ odvodíme $Y$.
3. Tím je dokázáno $X \implies Y$.

$$X \implies X_1 \implies X_2 \implies \dots \implies Y$$

Příklad: $n \in \mathbb{N}$, $n$ sudé $\implies n^2$ sudé.
$n = 2k$, tedy $n^2 = 4k^2 = 2 \cdot (2k^2)$, což je sudé číslo.

## Nepřímý důkaz (obměnou)
Implikace je ekvivalentní své obměně:
$$X \implies Y \;\equiv\; \lnot Y \implies \lnot X$$

| $X$ | $Y$ | $\lnot X$ | $\lnot Y$ | $X \implies Y$ | $\lnot Y \implies \lnot X$ |
| --- | --- | --------- | --------- | -------------- | -------------------------- |
| 1   | 1   | 0         | 0         | 1              | 1                          |
| 1   | 0   | 0         | 1         | 0              | 0                          |
| 0   | 1   | 1         | 0         | 1              | 1                          |
| 0   | 0   | 1         | 1         | 1              | 1                          |

Poslední dva sloupce se shodují, proto stačí dokázat obměnu.

Příklad: $x > 5 \implies x > 3$. Obměna: $x \leq 3 \implies x \leq 5$, a to platí, protože $x \leq 3 \leq 5$.

## Důkaz sporem
Implikace $X \implies Y$ je nepravdivá jen v případě $X \land \lnot Y$, takže stačí ukázat, že tento případ nemůže nastat.

1. Předpokládáme opak toho, co chceme dokázat: platí $X$ a zároveň $\lnot Y$.
2. Odvodíme spor, tedy tvrzení, které neplatí (např. $5 < 3$).
3. Předpoklad $X \land \lnot Y$ je nepravdivý, a proto platí $X \implies Y$.

| $X$ | $Y$ | $\lnot Y$ | $X \land \lnot Y$ | $\lnot(X \land \lnot Y)$ | $X \implies Y$ |
| --- | --- | --------- | ----------------- | ------------------------ | -------------- |
| 1   | 1   | 0         | 0                 | 1                        | 1              |
| 1   | 0   | 1         | 1                 | 0                        | 0              |
| 0   | 1   | 0         | 0                 | 1                        | 1              |
| 0   | 0   | 1         | 0                 | 1                        | 1              |

Příklad: $x > 5 \implies x > 3$. Předpokládejme $x > 5 \land x \leq 3$. Pak $5 < x \leq 3$, tedy $5 < 3$, což je spor.

# Matematická indukce
Používá se, když tvrzení $V(n)$ závisí na $n \in \mathbb{N}$ a dokazujeme ho pro **všechna** $n \geq 1$, např. u součtu s proměnným počtem sčítanců. Na rozdíl od nerovnosti $n > 5 \implies n > 3$ tady indukci opravdu potřebujeme.

1. **Základ:** ověříme $V(1)$.
2. **Indukční předpoklad:** předpokládáme $V(k)$ pro nějaké $k \geq 1$.
3. **Indukční krok:** z $V(k)$ dokážeme $V(k+1)$.
4. **Závěr:** $V(n)$ platí pro všechna $n \geq 1$.

Příklad: $1 + 2 + \dots + n = \dfrac{n(n+1)}{2}$. Základ: $1 = \dfrac{1 \cdot 2}{2}$. Krok: k oběma stranám předpokladu přičteme $k+1$:
$$\frac{k(k+1)}{2} + (k+1) = \frac{(k+1)(k+2)}{2}$$

Podrobně, včetně všech kroků: [[Cv-4]] a [[Cv-5]].
