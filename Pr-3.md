# Indukce
je metoda dokazovani tvrzeni $V(n)$ ktere zavisi na $n$
$V(n), n; n \geq 1$ 
chceme dokazat ze Vn plati pro veskera cisla

1. $n = 1; V(1)$
2. $k \geq 1; V(k)$
3. $k +1$
4. $V(n) = V(k+1); n \geq 1$

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