---
date: 2026-11-05
tags:
  - cviceni
---

jsou dany cifry ${1,2,3,4,5}$ kolik ruznich 3 cifernych cisel lze sestavit kdy se cifry neopakuji

$$
\begin{align*}
n &= 5 \\
c &= 3 \\
V\binom{n}{c} &= \frac{n!}{(n-c)!} \\
V\binom{5}{3} &= \frac{5!}{(5-3)!} = \frac{5.4.3.2!}{2!} = \frac{5.4.3}{1} = 5.4.3 = 60 
\end{align*}

$$

## Řešení
Čísla vypisujeme systematicky vzestupně: pevná první cifra, pak pevná druhá cifra a třetí cifra probíhá zbývající cifry. Cifry se nesmí opakovat.

První cifra $1$:
- $12x$: $123, 124, 125$
- $13x$: $132, 134, 135$
- $14x$: $142, 143, 145$
- $15x$: $152, 153, 154$

Pro první cifru $1$ je to $4 \cdot 3 = 12$ čísel. Stejně je to pro první cifru $2, 3, 4, 5$.

### Výpočet bez vypisování
- první cifra: $5$ možností
- druhá cifra: $4$ možnosti (jedna cifra je už použitá)
- třetí cifra: $3$ možnosti (dvě cifry jsou už použité)

$$5 \cdot 4 \cdot 3 = 60$$

Jde o **variace bez opakování** ($k = 3$ prvky z $n = 5$, záleží na pořadí):
$$V\binom{5}{3} = \frac{5!}{(5-3)!} = \frac{5!}{2!} = 5 \cdot 4 \cdot 3 = 60$$

**Odpověď:** Lze sestavit $60$ různých trojciferných čísel.


## Jak jsme se dostali k $n = 5$ a $k = 3$

> [!info] Odkud se berou čísla
> Obě čísla jsou přímo ze zadání:
> - **$n = 5$** je velikost „poolu“, tedy z kolika cifer vybíráme: $\{1,2,3,4,5\}$ má 5 prvků.
> - **$k = 3$** je počet pozic v čísle, tedy kolik cifer vybíráme („trojciferná“ čísla).

> [!tip] Proč variace bez opakování
> Vybíráme 3 cifry z 5, cifry se neopakují (**bez opakování**) a záleží na pořadí, protože $123 \neq 132$ (**variace**).
> $$V(n,k)=\frac{n!}{(n-k)!} \quad\Rightarrow\quad V(5,3)=\frac{5!}{(5-3)!}=\frac{5!}{2!}$$
> Čte se: „kolika způsoby naplním $k$ míst z $n$ možností, když žádnou možnost nepoužiju dvakrát“.

> [!example] Proč je to $5 \cdot 4 \cdot 3$
> - 1. cifra: 5 možností
> - 2. cifra: 4 možnosti (jedna už je použitá)
> - 3. cifra: 3 možnosti (dvě už jsou použité)
>
> Počet činitelů v součinu je $k = 3$, začíná se od $n = 5$ a klesá se o jedna.

## Faktoriál

> [!info] Definice
> $$n! = n \cdot (n-1) \cdot (n-2) \cdots 2 \cdot 1$$
> Např. $5! = 120$, $3! = 6$, $2! = 2$. Dohodou $0! = 1$.

> [!tip] Jak funguje zlomek $\dfrac{n!}{(n-k)!}$
> Oba faktoriály mají společný konec a ten se zkrátí:
> $$\frac{5!}{2!}=\frac{5\cdot4\cdot3\cdot\overbrace{2\cdot1}^{2!}}{\underbrace{2\cdot1}_{2!}}=5\cdot4\cdot3=60$$
> Dolní faktoriál $(n-k)!$ „odřízne“ ocas čitatele, zbyde jen prvních $k$ činitelů.

> [!example] Postup
> 1. Rozepsat čitatel, dokud nenarazíme na činitele, který je ve jmenovateli.
> 2. Společný ocas zkrátit.
> 3. Zbytek vynásobit.
>
> Stejný trik jako v `Cv-5.md`: $\binom{19}{16}=\dfrac{19\cdot18\cdot17\cdot16!}{16!\cdot3!}$, zkrátilo se $16!$.

> [!warning] Nepočítat celý faktoriál
> Když se dá zkrátit, celý faktoriál se nepočítá. $19!$ je obrovské číslo, kdežto $19 \cdot 18 \cdot 17 = 5814$.


Kolik presmicek lze vytvorit pouzitim vsech pismen slova "Fyzika" 

$$
m = 6 \\
k = 6 \\
V\binom{6}{6} = 6! = 720
$$

Kolik presmicek lze vytvorit pouzitim vsech pismen slova "Matematika" 

$$
n = 10 \\
M, m \to 2\times,\; a \to 3\times,\; t \to 2\times,\; e, i, k \to 1\times \\
P'(2,3,2,1,1,1) = \frac{10!}{2! \cdot 3! \cdot 2! \cdot 1! \cdot 1! \cdot 1!} = \frac{3628800}{24} = 151'200 \\
$$

> [!info] Rozbor příkladu "Matematika"
> Slovo má **10 písmen**, ale některá se opakují, a proto se nedá použít $10!$. Kdyby byla všechna písmena různá (jako ve "Fyzika"), bylo by to $10!$ přesmyček. Opakující se písmena ale dávají **stejné** slovo, když je prohodíme.
>
> | písmeno | kolikrát |
> | ------- | -------- |
> | m (M a m) | 2 |
> | a | 3 |
> | t | 2 |
> | e | 1 |
> | i | 1 |
> | k | 1 |
> | **celkem** | **10** |
>
> (Velké $M$ a malé $m$ se počítají jako stejné písmeno.)

> [!tip] Proč se dělí faktoriály opakování
> Z $10!$ přesmyček bychom každé slovo napočítali vícekrát: tři písmena $a$ můžeme mezi sebou prohodit $3! = 6$ způsoby, aniž se slovo změní, dvě $t$ $2! = 2$ způsoby a dvě $m$ $2! = 2$ způsoby. Každé slovo je tedy v $10!$ započítáno $2!\cdot3!\cdot2!$ krát, a proto tímto součinem dělíme.
> $$P'(k_1,\dots,k_r) = \frac{n!}{k_1!\cdot k_2!\cdots k_r!}$$
> Jde o **permutace s opakováním**.

> [!example] Výpočet krácením
> $$\frac{10!}{2!\cdot3!\cdot2!} = \frac{10\cdot9\cdot8\cdot7\cdot6\cdot5\cdot4\cdot3!}{2\cdot3!\cdot2} = \frac{10\cdot9\cdot8\cdot7\cdot6\cdot5\cdot4}{4} = 10\cdot9\cdot8\cdot7\cdot6\cdot5 = 151\,200$$
> Faktoriál $3!$ se ze čitatele i jmenovatele zkrátil a čtyřka ($2\cdot2$) se zkrátila s $4$.

**Odpověď:** Z písmen slova "Matematika" lze vytvořit $151\,200$ různých přesmyček.

