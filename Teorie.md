# TZI – sjednocená teorie

Souhrn všech přednášek na jednom místě, ve stejném pořadí jako v semestru. Vaše původní poznámky (`Pr-*.md`, `Cv-*.md`) jsem nechal beze změny.

**Zdroje:** poznámky z přednášek a cvičení, scan *TZI teorie* (PDF, kap. 2, 3, 4) a tabule z fotek.
**Značení:** věci označené **(doplněno)** nejsou ve vašich poznámkách ani na fotkách, jsou to standardní doplnění z hlavy. Na konci je sekce [Opravy v původních poznámkách](#opravy-v-původních-poznámkách).

Obsah: [1 Číselné soustavy](#1-číselné-soustavy) · [2 Výroková logika](#2-výroková-logika) · [3 Kvantifikátory a věty](#3-kvantifikátory-a-matematické-věty) · [4 Důkazy](#4-důkazy) · [5 Indukce](#5-matematická-indukce) · [6 Množiny](#6-množiny) · [7 Kartézský součin](#7-kartézský-součin) · [8 Relace](#8-relace) · [9 Kombinační čísla](#9-kombinační-čísla) · [10 Automaty a jazyky](#10-konečné-automaty-a-jazyky)

---

## 1 Číselné soustavy
(*Pr-1*)

**Číselná soustava** je způsob reprezentace čísel. Čísla se tvoří z uspořádané množiny symbolů (číslic). Dělí se na **poziční** a **nepoziční**.

**Poziční soustava** je určena kladným číslem $Z$ (základ), které udává počet číslic v soustavě.

| $Z$ | název | číslice |
| --- | ----- | ------- |
| 2 | binární (dvojková) | $\{0,1\}$ |
| 8 | oktalová (osmičková) | $\{0,\dots,7\}$ |
| 10 | dekadická (desítková) | $\{0,\dots,9\}$ |
| 16 | hexadecimální (šestnáctková) | $\{0,\dots,9,A,B,C,D,E,F\}$ |

Každé číslo zapsané číslicemi $a_n a_{n-1} \dots a_1 a_0$ v soustavě o základu $Z$ má hodnotu
$$a = a_n Z^n + a_{n-1} Z^{n-1} + \dots + a_1 Z^1 + a_0 Z^0$$

**Nepoziční soustava** nemá základ, hodnota číslice nezávisí na její poloze (např. římské číslice). **(doplněno)**

### Převody
- **Binární → dekadická:** sečtou se mocniny dvou u jedniček.
  $11010_2 = 16 + 8 + 2 = 26_{10}$ (váhy $32\;16\;8\;4\;2\;1$)
- **Binární ↔ hexadecimální:** po čtveřicích bitů (váhy $8\,4\,2\,1$).
  $0001\;1010_2 = 1A_{16}$, $1111\;0010_2 = F2_{16} = 242_{10}$
- **Dekadická → jiná soustava:** opakované dělení základem se zbytkem, zbytky se čtou odzadu. **(doplněno)**
  $262342_{10}$: $262342 = 4\cdot 16^4 + 0\cdot 16^3 + 0\cdot 16^2 + 12\cdot 16 + 6$, tedy $262342_{10} = 400C6_{16}$ (v poznámkách bylo zadání bez výsledku, předpokládám dekadické číslo).

---

## 2 Výroková logika
(*Pr-2*, *Cv-4*)

**Výrok** je věta konkrétního jazyka, které lze přiřadit právě jednu pravdivostní hodnotu: pravda (1) / nepravda (0).
- „Číslo 2 je sudé“ → pravda
- „Číslo 3 je sudé“ → nepravda
- „Zítra bude pršet“ → není výrok (nelze určit)

### Logické spojky
| symbol | název |
| ------ | ----- |
| $\lnot$ | negace |
| $\land$ | konjunkce („a“) |
| $\lor$ | disjunkce („nebo“) |
| $\implies$ | implikace |
| $\iff$ | ekvivalence |

| $X$ | $Y$ | $\lnot X$ | $X \land Y$ | $X \lor Y$ | $X \implies Y$ | $X \iff Y$ |
| --- | --- | --------- | ----------- | ---------- | -------------- | ---------- |
| 1 | 1 | 0 | 1 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 0 | 1 | 1 | 0 |
| 0 | 0 | 1 | 0 | 0 | 1 | 1 |

Implikace $X \implies Y$ je nepravdivá **jen** když $X$ platí a $Y$ neplatí.

### Implikace, obměna, obrácení
- **Obměna** (kontrapozice): $X \implies Y \;\equiv\; \lnot Y \implies \lnot X$ (vždy stejná pravdivostní hodnota)
- **Obrácená implikace**: $Y \implies X$ (nemusí mít stejnou hodnotu jako původní)
- **Negace implikace:** $\lnot(X \implies Y) \equiv X \land \lnot Y$

**Ekvivalence:** $X \iff Y \;\equiv\; (X \implies Y) \land (Y \implies X)$. Také platí $X \iff Y \equiv \lnot X \iff \lnot Y$.

### Formule, tautologie
- **Výroková formule** je zápis z písmen, logických spojek a závorek; po dosazení výroků za písmena dostaneme výrok.
- **Tautologie** je formule, která je po dosazení libovolných výroků vždy pravdivá.
- Dvě formule jsou **ekvivalentní**, obsahují-li stejná písmena a po dosazení libovolných hodnot mají vždy stejnou pravdivostní hodnotu.
- **De Morganova pravidla (doplněno):** $\lnot(X \land Y) \equiv \lnot X \lor \lnot Y$, $\lnot(X \lor Y) \equiv \lnot X \land \lnot Y$

### Výroková forma
Věta určitého jazyka obsahující proměnnou (nebo několik proměnných), která se stane výrokem po dosazení hodnoty.
- **Definiční obor** $D$: množina všech hodnot, pro které je $V(c)$ výrok.
- **Obor pravdivosti** $V(x)$: množina všech $x \in D$, pro které je výrok pravdivý.

---

## 3 Kvantifikátory a matematické věty
(*Pr-2*, *PDF kap. 2*)

### Kvantifikátory
- $\forall$ – obecný („pro všechna“)
- $\exists$ – existenční („existuje alespoň jedno“)
- $\exists!$ – „existuje právě jedno“

### Matematická věta
**Věta** je tvrzení, které má tvar pravdivého úsudku:
$$(K x)\; x \in D_x \implies V(x)$$
- $K$ – kvantifikátor
- $D_x$ – množina přípustných hodnot
- $V(x)$ – výroková forma závislá na $x$

Obvykle má $V(x)$ tvar implikace $P(x) \implies Z(x)$:
- $P(x)$ – **předpoklad** (postačující podmínka, premisa)
- $Z(x)$ – **závěr** (nutná podmínka, konsekvent)

Příklad: „Jestliže je přirozené číslo dělitelné šesti, pak je dělitelné třemi.“
$$(\forall x \in \mathbb{N})\; 6 \mid x \implies 3 \mid x$$
Číslo $a$ je dělitelné 6 právě tehdy, když existuje $b \in \mathbb{N}$ takové, že $a = 6b$.

**Vymezení věty** s více proměnnými: $(K_x\, x \in D_x) \land (K_y\, y \in D_y) \land \dots \implies (P(x) \implies Z(x))$.

### Negace věty
Negace mění kvantifikátor a negace implikace dává konjunkci:
$$\lnot\big[(\forall x \in D_x)\; P(x) \implies Z(x)\big] \;\equiv\; (\exists x \in D_x)\; P(x) \land \lnot Z(x)$$
Příklad: negace věty $\forall x\,(6 \mid x \implies 3 \mid x)$ je $\exists x\;(6 \mid x \land 3 \nmid x)$.

Platí: $\forall \leftrightarrow \exists$ při negaci (**doplněno** jako pravidlo): $\lnot\forall \equiv \exists\lnot$, $\lnot\exists \equiv \forall\lnot$.

### Obrácená věta
$$(K x \in D_x)\; Z(x) \implies P(x)$$
- **Nemění se kvantifikace.**
- Z pravdivosti původní věty **nelze usoudit** na pravdivost obrácené věty.

Příklad: $\forall x\in\mathbb{N}$: $3 \mid x \implies 6 \mid x$ je nepravdivá. Protipříklad: $x = 9$ ($3 \mid 9 \land 6 \nmid 9$). Její negace $\exists x\,(3 \mid x \land 6 \nmid x)$ je pravdivá.

Pythagorova věta: $\triangle$ = množina trojúhelníků, $Pr(x)$ = „$x$ je pravoúhlý“, $j, p$ odvěsny, $k$ přepona.
- $(\forall x \in \triangle)\; Pr(x) \implies j^2 + p^2 = k^2$ (platí)
- obrácená $(\forall x \in \triangle)\; j^2 + p^2 = k^2 \implies Pr(x)$ (platí také, tedy platí ekvivalence $Pr(x) \iff j^2+p^2=k^2$)

### Obměna věty
$$V(x):\; (K x \in D_x)\; P(x) \implies Z(x) \qquad\Longleftrightarrow\qquad \overline{V}(x):\; (K x \in D_x)\; \lnot Z(x) \implies \lnot P(x)$$
Obměna je vždy **ekvivalentní** původní větě (sloupce $a \implies b$ a $\lnot b \implies \lnot a$ mají v pravdivostní tabulce stejné hodnoty).

Příklad: $\forall x \in \mathbb{N}$: $6 \mid x \implies 3 \mid x$ má obměnu $\forall x \in \mathbb{N}$: $3 \nmid x \implies 6 \nmid x$.

---

## 4 Důkazy
(*PDF kap. 2*, *Cv-4*)

### Přímý důkaz
Věta $(K x \in D_x)\; P(x) \implies Z(x)$.
Přímý důkaz je **implikační posloupnost** tvrzení $T_1, T_2, \dots, T_n$, kde $T_1 = P(x)$, $T_n = Z(x)$ a každé $T_i$ ($i = 2,\dots,n-1$) je jedno z:
- přijaté tvrzení dané struktury (**axiom**),
- již dokázaná věta,
- závěr odvozovacího pravidla.

**Axiom** je tvrzení, které v dané struktuře (systému, teorii) nedokazujeme a předpokládáme, že je pravdivé.

$$P(x) \implies T_2 \implies T_3 \implies \dots \implies T_{n-1} \implies Z(x)$$

Příklad: $(\forall y \in \mathbb{N})\; y \geq 2 \implies 6y + 3 > 13$
$$y \geq 2 \implies 6y \geq 12 \implies 6y + 1 \geq 13 \implies (6y+1)+2 > 13 \implies 6y + 3 > 13$$
Konec důkazu se značí **QED** / **CBD** / ∎ (Q.E.D. = quod erat demonstrandum, „což bylo dokázat“).

> [!warning] Důkaz musí být s kvantifikátorem
> Ověřit větu pro jedno číslo (např. $x := 7$) ani pro několik čísel důkaz není. V důkazu s kvantifikátorem se za proměnnou dosazuje **obecný** prvek (zde $y$), ne konkrétní hodnota. Zápis „$x \geq 2 \implies 6x+3 > 13$“ bez kvantifikátoru je nesprávný.

### Nepřímý důkaz
Nepřímý důkaz věty je **přímý důkaz její obměny**:
$$(\forall x \in D_x)\; P(x) \implies Z(x) \quad\text{dokazujeme jako}\quad (\forall x \in D_x)\; \lnot Z(x) \implies \lnot P(x)$$

Příklad: $(\forall x \in \mathbb{N})\; x \geq 2 \implies 6x + 3 > 13$. Dokazujeme obměnu: $6x + 3 \leq 13 \implies x < 2$.
$$6x + 3 \leq 13 \implies 6x \leq 10 \implies x \leq \tfrac{10}{6} \implies x < \tfrac{12}{6} \implies x < 2$$

### Důkaz sporem
Věta $X \implies Y$ je nepravdivá jen v případě $X \land \lnot Y$. Předpokládáme $X \land \lnot Y$ a odvodíme spor (tvrzení, které neplatí). Tedy $X \land \lnot Y$ nemůže nastat a platí $X \implies Y$.
$$(X \land \lnot Y) \implies Z,\quad Z \text{ je nepravda}$$

Příklad (*Cv-4*): $x > 5 \implies x > 3$. Předpoklad $x > 5 \land x \leq 3$ dává $5 < x \leq 3$, tedy $5 < 3$, spor.

### Důkaz ekvivalence
$X \iff Y$ se dokazuje jako dvě implikace: $X \implies Y$ a $Y \implies X$.

### Důkaz tranzitivitou (*Cv-4*)
$a > b \land b > c \implies a > c$. Tvrzení $n > 5 \implies n > 3$ plyne z $n > 5 > 3$, indukce není potřeba.

---

## 5 Matematická indukce
(*Pr-3*, *Cv-4*, *Cv-5*)

Metoda dokazování tvrzení $V(n)$ závislého na $n \in \mathbb{N}$, $n \geq 1$, pro **všechna** přirozená čísla.

1. **Základ:** ověříme $V(1)$ (nejmenší $n$).
2. **Indukční předpoklad:** předpokládáme $V(k)$ pro nějaké $k \geq 1$.
3. **Indukční krok:** z $V(k)$ dokážeme $V(k+1)$.
4. **Závěr:** $V(n)$ platí pro všechna $n \geq 1$.

Příklad (*Cv-5*): $1 + 2 + \dots + n = \dfrac{n(n+1)}{2}$. Základ $1 = \frac{1 \cdot 2}{2}$. Krok: přičteme $k + 1$:
$\frac{k(k+1)}{2} + (k+1) = \frac{(k+1)(k+2)}{2}$.

Indukci používáme, když tvrzení závisí na proměnném počtu sčítanců apod. Nerovnost jako $n > 5 \implies n > 3$ indukci nepotřebuje.

---

## 6 Množiny
(*Pr-3*)

**Množina** je souhrn nějakých objektů (prvků), chápaný jako samostatný celek. Množiny značíme velkými, prvky malými písmeny.

- $x \in X$ – prvek patří do množiny, $x \notin X$ – nepatří
- **Podmnožina:** $X \subseteq Y \iff (a \in X \implies a \in Y)$
- **Vlastní podmnožina:** $X \subset Y \iff X \subseteq Y \land X \neq Y$

### Způsoby zadání
1. Výčtem prvků: $X = \{a_1, a_2, \dots, a_n\}$
2. Vlastností: $X = \{x;\; P(x)\}$ (prvky, pro které platí $P(x)$)

### Typy množin
1. **Prázdná** $\emptyset$ – neobsahuje žádný prvek
2. **Konečná** – lze zadat výčtem prvků
3. **Spočetná** – existuje vzájemně jednoznačné zobrazení mezi ní a množinou přirozených čísel
4. **Nekonečná**

### Operace
| operace | definice |
| ------- | -------- |
| rovnost | $A = B \iff A \subseteq B \land B \subseteq A$ |
| průnik | $x \in A \cap B \iff x \in A \land x \in B$ |
| sjednocení | $x \in A \cup B \iff x \in A \lor x \in B$ |
| rozdíl | $x \in A \setminus B \iff x \in A \land x \notin B$ |
| doplněk | $A \subseteq U$: $x \in A' \iff x \in U \land x \notin A$ |

### Potenční množina
$P(A) = \{B;\; B \subseteq A\}$ – množina všech podmnožin. Pro $|A| = n$ je $|P(A)| = 2^n$.

$A = \{a, b, c\}$:
$$P(A) = \{\emptyset, \{a\}, \{b\}, \{c\}, \{a,b\}, \{a,c\}, \{b,c\}, \{a,b,c\}\}\quad (2^3 = 8 \text{ prvků})$$

---

## 7 Kartézský součin
(*Pr-3*, *PDF kap. 3*)

Mějme množiny $A, B$. **Kartézský součin** $A \times B$ (v daném pořadí) je množina
$$A \times B = \{[a,b];\; a \in A \land b \in B\}$$

### Uspořádaná dvojice
$[a,b]$ (též $(a,b)$, $\langle a,b\rangle$) má **první prvek** $a$ a **druhý prvek** $b$. Pořadí rozhoduje:
$$\{a,b\} = \{b,a\}, \qquad [a,b] \neq [b,a]\ (\text{pro } a \neq b)$$

**Definice:** uspořádaná dvojice je množina $[a,b] = \{\{a\}, \{a,b\}\}$.
Pro $a = b$ je $[a,a] = \{\{a\}\}$.

**Uspořádaná $n$-tice:** $[a_1, a_2, \dots, a_n] = [[a_1, \dots, a_{n-1}], a_n]$, $n \in \mathbb{N}$, $n \geq 1$.

**Kartézský součin $n$ množin:** $A_1 \times \dots \times A_n = (A_1 \times \dots \times A_{n-1}) \times A_n$.
**Kartézská mocnina řádu $n$:** $M^n = \underbrace{M \times \dots \times M}_{n}$, např. $\mathbb{R}^2 = \mathbb{R} \times \mathbb{R}$.

Příklad: $A = \{1,2,3\}$, $B = \{2,4,6,8\}$:
$$A \times B = \{[1,2],[1,4],[1,6],[1,8],[2,2],[2,4],[2,6],[2,8],[3,2],[3,4],[3,6],[3,8]\}$$
Je-li $|A| = m$, $|B| = k$, pak $|A \times B| = m \cdot k = |B \times A|$ (ale $A \times B \neq B \times A$ obecně).

**Znázornění:** kartézským grafem (body v mřížce) nebo uzlovým orientovaným grafem (šipky z prvků $A$ do prvků $B$). $A^2$ se kreslí jako graf na jedné množině uzlů se smyčkami.

---

## 8 Relace
(*PDF kap. 4*)

**Relace v množině $M$** je libovolná podmnožina $M^2$.
**Relace mezi množinami $A, B$** (v daném pořadí) je libovolná podmnožina $A \times B$.

Počet relací: pro $|A| = 3$ je $|A \times A| = 9$ a relací na $A$ je $|P(A \times A)| = 2^9 = 512$. Obecně $|P(n)| = 2^k$, kde $|n| = k$.

Příklady na $A = \{1,2,3\}$: $R_1 = \{[1,1],[2,2],[3,3]\}$, $R_2 = \{[1,2],[2,3]\}$.

### Obory relace
Pro $R \subseteq M \times M$:
- **První obor** (definiční obor): $\mathrm{D}(R) = \{x \in M;\; \exists y \in M: (x,y) \in R\}$
- **Druhý obor** (obor hodnot): $\mathrm{H}(R) = \{y \in M;\; \exists x \in M: (x,y) \in R\}$
- Pro $a, b \in M$: $\{x \in M;\; (x,a) \in R\}$ jsou prvky ve vztahu s $a$ zleva, $\{y \in M;\; (b,y) \in R\}$ prvky ve vztahu s $b$ zprava.

Příklad $R_2 = \{[1,2],[2,3]\}$: první obor $\{1,2\}$, druhý obor $\{2,3\}$.

### Vlastnosti binárních relací na $M$ ($R \subseteq M^2$)
| vlastnost | definice |
| --------- | -------- |
| **reflexivní** | $(\forall x \in M)\; [x,x] \in R$ |
| **antireflexivní** | $(\forall x \in M)\; [x,x] \notin R$ |
| **symetrická** | $(\forall x,y \in M)\; [x,y] \in R \implies [y,x] \in R$ |
| **antisymetrická, silně** | $(\forall x,y \in M)\; [x,y] \in R \implies [y,x] \notin R$ |
| **antisymetrická, slabě** | $(\forall x,y \in M)\; [x,y] \in R \land [y,x] \in R \implies x = y$ |
| **tranzitivní** | $(\forall x,y,z \in M)\; [x,y] \in R \land [y,z] \in R \implies [x,z] \in R$ |

Zápis $x R y$ znamená $[x,y] \in R$, $x \not R y$ znamená $[x,y] \notin R$.

**(doplněno) Důležité typy relací**
- **Ekvivalence:** reflexivní + symetrická + tranzitivní (např. „má stejný zbytek po dělení 3“).
- **Uspořádání:** reflexivní + (slabě) antisymetrická + tranzitivní (např. $\leq$, $\subseteq$).

---

## 9 Kombinační čísla
(*Cv-5*)

$$\binom{n}{k} = \frac{n!}{k!\,(n-k)!},\qquad 0 \leq k \leq n$$

- $0! = 1$ (ne $0$)
- $\binom{n}{0} = \binom{n}{n} = 1$, $\binom{n}{k} = \binom{n}{n-k}$ **(doplněno)**
- Krácení faktoriálů: $\binom{19}{16} = \dfrac{19 \cdot 18 \cdot 17}{3!} = 969$

Příklad ze cvičení: najděte $x \in \mathbb{N}$, pro které $\binom{x+1}{2} + \binom{x}{2} = 4\binom{5}{5}$.
Podmínka $x \geq 2$. Pravá strana $= 4$. Levá: $\frac{(x+1)x}{2} + \frac{x(x-1)}{2} = x^2$, tedy $x^2 = 4$, $x = 2$ (záporné $-2$ nevyhovuje). Zkouška: $\binom{3}{2} + \binom{2}{2} = 4$.

---

## 10 Konečné automaty a jazyky
(*Pr-4*, *Pr-5*)

Podrobně, včetně příkladů a diagramů: [[Pr-4]] (automat) a [[Pr-5]] (slova a jazyky).

### Abeceda, slova, jazyky
- **Abeceda** $\Sigma$ – neprázdná konečná množina symbolů, např. $\{0,1\}$, $\{a,b,c\}$.
- **Slovo** nad $\Sigma$ – konečná posloupnost symbolů; $\varepsilon$ je prázdné slovo, $|\varepsilon| = 0$, $|abcd| = 4$.
- $\Sigma^+$ – všechna **neprázdná** slova; $\Sigma^* = \Sigma^+ \cup \{\varepsilon\}$.
- **Zřetězení:** $uv = a_1\dots a_n b_1 \dots b_m$, $\varepsilon u = u\varepsilon = u$ ($\varepsilon$ je neutrální prvek).
- **Mocnina slova:** $u^0 = \varepsilon$, $u^1 = u$, $u^{i+1} = u^i u$.
- **Jazyk** nad $\Sigma$ – libovolná podmnožina $\Sigma^*$, $L \subseteq \Sigma^*$.

### Konečný automat
$$A = (Q, \Sigma, \delta, q_0, F)$$
- $Q$ stavy, $\Sigma$ vstupní abeceda, $\delta \colon Q \times \Sigma \to Q$ přechodová funkce
- $q_0 \in Q$ počáteční stav, $F \subseteq Q$ koncové stavy

Způsoby zadání: přechodová funkce, tabulka, stavový diagram, stavový strom.

**(doplněno)** Zobecněná přechodová funkce $\delta^* \colon Q \times \Sigma^* \to Q$: $\delta^*(q, \varepsilon) = q$, $\delta^*(q, wa) = \delta(\delta^*(q,w), a)$.
Slovo $w$ je přijato, když $\delta^*(q_0, w) \in F$. **Jazyk automatu** $L(A) = \{w \in \Sigma^* \mid \delta^*(q_0,w) \in F\}$.

### Spojitost s ostatními kapitolami
- **Kartézský součin:** $\delta$ je funkce $Q \times \Sigma \to Q$, tedy zvláštní relace mezi $Q \times \Sigma$ a $Q$ (každé dvojici je přiřazen právě jeden stav).
- **Množiny:** jazyk je množina slov, takže na něj lze použít sjednocení, průnik a doplněk.
- **Indukce:** vlastnosti slov (např. $|uv| = |u| + |v|$) se dokazují indukcí podle délky slova. **(doplněno)**

---

## Opravy v původních poznámkách
Vaše soubory jsem neměnil. Tady je seznam míst, která bych opravil.

**`Pr-2.md` (výroková logika)**
- U spojek jsou názvy prohozené: $\land$ je **konjunkce**, $\lor$ je **disjunkce** (v poznámkách je to naopak). U ekvivalence chybí symbol $\iff$.
- Nadpis „$\neg Y \implies \neg X$“: tvrzení „daná implikace a její *negace* mají stejnou hodnotu“ má znít „implikace a její **obměna**“.
- „Výroková formule“ u výrokové formy: věta s proměnnou se jmenuje **výroková forma**, ne formule.
- Obor pravdivosti: „pro které je **TBD**“ doplnit: pro které je $V(x)$ pravdivý výrok.
- Důkaz ekvivalence: $(X \iff Y) \iff (X \implies Y) \land (Y \implies X)$ (v zápisu je překlep $Y_n$).

**`Pr-3.md` (množiny)**
- Sjednocení: $x \in A \cup B \iff x \in A \lor x \in B$ (v poznámkách je $\land$, to je průnik).
- Podmnožina: $X \subseteq Y \iff x \in X \implies x \in Y$ (v poznámkách je písmeno $a$).
- Doplněk: $x \in A'$ (ne $A^2$).
- $P(A)$ pro $\{a,b,c\}$ má mít **8** prvků, chybí $\{b\}, \{c\}, \{a,c\}, \{b,c\}$.
- Způsob zadání množiny „IDK“ je vlastní podmnožina.
- Kartézský součin: $A \times B = \{[x,y];\; x \in A \land y \in B\}$.

**`Pr-1.md`** – úvod o poziční soustavě: místo $10^n$ má být obecný základ $Z^n$, indexy ($a_m$ vs. $a_n$) sjednotit.
