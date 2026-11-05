---
date: 2026-10-15
tags:
  - prednaska
---

# Indukce
je metoda dokazovani tvrzeni $V(n)$ ktere zavisi na $n$
$V(n), n; n \geq 1$ 
chceme dokazat ze Vn plati pro veskera cisla

1. $n = 1; V(1)$
2. $k \geq 1; V(k)$
3. $k +1$
4. $V(n) = V(k+1); n \geq 1$

## Příklad: důkaz indukcí
> [!note] Doplněno (Claude), není z přednášky. Příklady jsou stejného typu jako v [[Cv-4]] a [[Cv-5]].

Dokažme, že součet prvních $n$ lichých čísel je $n^2$:
$$V(n):\; 1 + 3 + 5 + \dots + (2n-1) = n^2, \quad n \geq 1$$

1. **Základ** $n = 1$: $L = 1$, $P = 1^2 = 1$, tedy $L = P$.
2. **Indukční předpoklad** $k \geq 1$: platí $1 + 3 + \dots + (2k-1) = k^2$.
3. **Indukční krok** $k+1$: k oběma stranám přičteme další liché číslo $2(k+1)-1 = 2k+1$:
$$1 + 3 + \dots + (2k-1) + (2k+1) = k^2 + 2k + 1 = (k+1)^2$$
   To je přesně $V(k+1)$.
4. **Závěr:** základ platí a z $V(k)$ plyne $V(k+1)$, takže $V(n)$ platí pro všechna $n \geq 1$.

# Důkaz sporem
> [!note] Doplněno (Claude), není z přednášky. Teorie je v [[Pr-4]] a [[Teorie]].

Chceme dokázat $X \implies Y$. Implikace je nepravdivá jen v případě $X \land \lnot Y$, takže:

1. Předpokládáme **opak** toho, co dokazujeme: platí $X$ a zároveň $\lnot Y$.
2. Z toho odvodíme **spor**, tedy tvrzení, které neplatí (např. $5 < 3$, nebo $a$ je zároveň sudé i liché).
3. Předpoklad $X \land \lnot Y$ je tedy nepravdivý, a proto platí $X \implies Y$.

**Příklad 1:** $x > 5 \implies x > 3$.
Předpokládejme $x > 5 \land x \leq 3$. Pak $5 < x \leq 3$, tedy $5 < 3$, což je spor.

**Příklad 2:** $\sqrt{2}$ je iracionální.
Předpokládejme opak: $\sqrt{2} = \dfrac{p}{q}$, kde $p, q \in \mathbb{N}$ jsou nesoudělná. Pak $2q^2 = p^2$, takže $p^2$ je sudé, a tedy i $p$ je sudé, $p = 2r$. Dosazením $2q^2 = 4r^2$, tedy $q^2 = 2r^2$ a $q$ je také sudé. Obě čísla $p, q$ jsou sudá, tedy soudělná, což je spor s nesoudělností. Proto $\sqrt{2}$ není racionální.

# Mnozina
souhrn nejakych obj (mnoziny), chapany jako samostatny object (celek).
mnozinu zadavame pomici velkych pismen a prvky pomoci malych pismen.

$x \in X$
$x \notin X$
$X \subseteq Y \iff a \in X \implies a \in Y$ 

| x   | y   | $a \in X \implies a \in Y$ |
| --- | --- | -------------------------- |
| 1   | 1   | 1                          |
| 1   | 0   | 0                          |
| 0   | 1   | 1                          |
| 0   | 0   | 1                          |

## Zpusoby zadavani mnozin
1. Pomoci prvku
	1. $X = \{ a_1, a_2, \dots, a_n \}$
2. Pomoci vlastnoti 
	1. $X= \{x, P(x)\}$
3. IDK
	1. $X \subset U \iff X \subseteq Y \land X \neq Y$

## Typy mnozin
1. Prazdna
	1. Neobsahuje zadny prvek
	2. $\emptyset$
2. Konecna
	1. Lze zadat vyctem prvku
3. Spocetna
	1. Je takova kde existuje vzajemne jednoznacne zobrazeni mezi touto mnozinou a mnozinou prirozeny cisel 
4. Nekonecna

## Operace
1. Rovnost 2 mnozin
	1. $A = B \iff A \subseteq B \land B \subseteq A$
2. Prunik (obrazek)
	1. $x \in A \cap B \iff x \in A \land x \in B$
3. Sjednoceni (obrazek)
	1. $x \in A \cup B \iff x \in A \land x \in B$
4. Rozdil (obrazek)
	1. $x \in A-B \iff x \in A \land x \notin B$
5. IDK
	1. $U,A \in U; x \in A^2 \iff x \in U \land x \notin A$

## Potecni mnoziny
Potecni mnouzinu mnoziny A nazivame mnouzinou vsech podmnozin mnoziny A
$$
	P(A) = \{B; B \subseteq A\} \\
	|A| = n; |P(A)| = 2^n \\
	A = \{a;b;c\} \\
	P(A) = \{\emptyset; \{a\}; \{a,b\}; \{a,b,c\}\}
$$
## Karte. soucin
$$
A\times{B} \implies(x;y); x \in A; y\in B 
$$