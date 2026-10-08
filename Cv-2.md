
# Vyrokova logika
vyrokem nazyvame vetu konkterniho jazyka ktere je mozno priradit prave jednu pradivnostni hodnotu: True / False

### Priklad
- cislo  2 je sude -> True
- cislo 3 je sude -> False
- Zitra bude prset -> neni vyrok

## Operace s vyroky

| X   | Y   | $\lnot X$ | $X \land Y$ | $X \lor Y$ | $X \implies Y$ | $X \iff Y$ |
| --- | --- | --------- | ----------- | ---------- | -------------- | ---------- |
| 1   | 1   | 0         | 1           | 1          | 1              | 1          |
| 1   | 0   | 0         | 0           | 1          | 0              | 0          |
| 0   | 1   | 1         | 0           | 1          | 1              | 0          |
| 0   | 0   | 1         | 0           | 0          | 1              | 1          |
($\neg$) negace, ($\land$) Disjunkce, ($\lor$) Konjunkce, ($\implies$) Implikace,( ) Ekvivalence 


## Implikace
### $\neg Y \implies \neg X, X \implies Y$ 
- Danna implikace a jeji negace maji stejnou hodnotu
- $X \implies Y \equiv \neg Y \implies \neg X$

| X   | Y   | $\neg Y$ | $\neg X$ | $X \implies Y$ | $\neg Y \implies \neg X$ |
| --- | --- | -------- | -------- | -------------- | ------------------------ |
| 1   | 1   | 0        | 0        | 1              | 1                        |
| 1   | 0   | 1        | 0        | 0              | 0                        |
| 0   | 1   | 0        | 1        | 1              | 1                        |
| 0   | 0   | 1        | 1        | 1              | 1                        |
- $Y \implies X$ - obraceni implikace
Obe implikace nemusi mit stejne hodnoty

## Ekvivalence
### $X \iff Y \equiv \neg X \iff  \neg Y$ 
- maji stejnou hodnotu


## Dukaz platnosti implikace a ekvivalence
### Implikace
1. Primy dukaz
	- Se provade tak ze se sestavi tzv. retez platnych implikaci
	- $X\implies Y, X \implies Y_1 \implies Y_2 \implies \dots \implies Y$
2. Neprimy dukaz
	- $X \implies Y \iff \neg Y \implies \neg X$
3. Dukaz sporem 
	- $(X \land \neg Y) \implies Z$; $Z$ je nepravda

### Ekvivalence
- $Y \iff X$; $X \implies Y \land Y \implies X$
- $(X \iff Y) \iff X \implies Y_n \land Y \implies X$

## Vyrokove formule (brum)
> [!info] Je zapis sestaveny z pismen, log spojek a zavorek, takovy ze dosadime li za pismena vyroky dostaname vyrok.
## Tautologie
> [!info] Je vyrokova formule ktera ma takovou vlastnost dosadime li vyroky ze pismena dostaneme vzdy pravdivy vyrok

> [!info] Dve vyrokove formule se naz. ekvivalentni, jestlize obsahuji stejna pismena a jestlize po dosazeni jakykoliv pravdivostnich hodnot se z obou formuli stanou vyroky totoznych pravdivostnich hodnot.


## Vyrokove formy
> [!info] Veta urciteho jaz. ktera obashuje promennou (nebo nekolik promennych) se naz. vyrokova formule


## $D$ definicni obor
$\forall (c) \in D$; je (Vc) vyrok

Mnozina vsech prvky ktere jsou v def oboru.
Mnozina vsech x z def oboru pro ktere je **TBD** naz. oborem pravdivosti V(x) 


## Kvantifikatory

$\forall , \exists , \exists !$ 


