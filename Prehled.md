---
tags:
  - prehled
---

# Přehled poznámek a vztahů

> [!note] Jak číst
> Plné šipky ukazují, **na co co navazuje** (látka). Čárkované ukazují, **co se cvičilo** z které přednášky. Vztahy jsou odvozené z obsahu poznámek, ne od učitele. Nahlédnutí do grafu Obsidianu: `Ctrl+G` (graf se opírá o odkazy `[[...]]` níže).

## Graf vztahů
```mermaid
flowchart LR
    subgraph P["Přednášky (čtvrtky)"]
        P1["Pr-1 · 1.10<br/>číselné soustavy"]
        P2["Pr-2 · 8.10<br/>výroková logika"]
        P3["Pr-3 · 15.10<br/>indukce, množiny"]
        P4["Pr-4 · 22.10<br/>důkazy"]
        P5["Pr-5 · 29.10<br/>konečný automat"]
        P6["Pr-6 · 5.11<br/>slova, jazyky, δ*"]
    end
    subgraph C["Cvičení"]
        C1["Cv-1 · 1.10<br/>info"]
        C4["Cv-4 · 22.10<br/>důkazy, indukce"]
        C5["Cv-5 · 29.10<br/>indukce, kombinační čísla"]
        C6["CV-6 · 5.11<br/>kombinatorika"]
    end
    T["Teorie<br/>sjednocený souhrn"]

    P1 --> P2
    P2 --> P3
    P2 --> P4
    P3 --> P4
    P3 --> P5
    P5 --> P6

    P4 -.-> C4
    P3 -.-> C5
    C4 --> C5
    C5 --> C6
    P1 -.-> C1

    P1 --> T
    P2 --> T
    P3 --> T
    P4 --> T
    P5 --> T
    P6 --> T
```

## Vztahy slovy
| odkud | kam | proč |
| ----- | --- | ---- |
| Pr-2 → Pr-4 | výroková logika → důkazy | důkaz implikace, obměna a spor vychází z pravdivostních tabulek |
| Pr-3 → Pr-5 | množiny → automat | $Q$, $\Sigma$, $F$ jsou množiny, $\delta$ je funkce na kartézském součinu $Q \times \Sigma$ |
| Pr-5 → Pr-6 | automat → slova, jazyk | $\delta^*$ a $L(A)$ jsou postavené na $\delta$ a $\Sigma^*$ |
| Pr-4 → Cv-4 | důkazy → cvičení | přímý důkaz, spor, indukce |
| Pr-3 → Cv-5 | indukce → cvičení | součet $1+2+\dots+n$ |
| Cv-5 → CV-6 | kombinační čísla → variace a permutace | faktoriál a krácení |

## Odkazy (pro graf Obsidianu)
**Přednášky:** [[Pr-1]] · [[Pr-2]] · [[Pr-3]] · [[Pr-4]] · [[Pr-5]] · [[Pr-6]]
**Cvičení:** [[Cv-1]] · [[Cv-4]] · [[Cv-5]] · [[CV-6]]
**Souhrn:** [[Teorie]]
