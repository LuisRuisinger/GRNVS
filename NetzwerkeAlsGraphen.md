## Pfade in Netzwerken

>[!NOTE] Definition
>
>Eine Sequenz an Knotentupel entspricht einem Pfad von $s$ nach $t$ falls jedes Tupel innerhalb dieser Sequenz paarweise verschieden ist.
>Eine Sequenz kann dabei innerhalb gerichteter bzw. ungerichteter Graphen bestehen.
>
>---
>
>Die Pfadkosten entsprechen der Summe der Kantenkosten:
>$$c(P_{st}):=\sum_{(i,j)\in P_{st}}c_{ij}$$
>
>---
>
>Die Pfadlänge entspricht der Anzahl der Kanten auf dem Pfad:
>$$I(P_{st}):=|P_{st}|$$

<br>

## Netzwerktopologien

>[!NOTE] Definition
>
>DIe Topologie beschreibt die Struktur, wie Knoten miteinander verbunden sind. Man unterscheidet zwischen
>
>- physikalischer Topologie
>- logischer Topologie
>
>---
>
>**wichtige Topologien**:
>
>- Baum
>- Vermaschung
>- Bus
>- Stern
>- Kette
>- P2P

---

<br>

### Adjazenz- und Distanzmatrix

Die Adjazenzmatrix gibt an ob zwischen $2$ Knoten eine Kante existiert.

- eine Zeile $n$ beschreibt die Kanten zwischen $n$ und allen anderen Knoten
- $1\Leftrightarrow\exists (n,n_{other})\in A$ mit $n\equiv\text{source}$ und $n\in N$ sonst $0$ 

---

Die Distanzmatrix gibt die Kosten zwischen allen Knoten ausgehend von jedem Knoten zeilenweise an:

- $c_{i,j}\Leftrightarrow\exists (i,j)\in A$
- $0\Leftrightarrow i=j$
- $\infty\Leftrightarrow\not\exists(i,j)\in A$

---

<br>

### Kürzeste Distanz

- die Matrix $D^n$ enthält die Länge eines jeweils kürzesten Pfades über $n$ Hops
- für ein endliches $n$ konvergiert die Potenzreiche nach $D^*$
- der längste einfache Pfad ist durch die Anzahl $N$ der Knoten beschränkt

$\Rightarrow$ die Matrix $D^*$ enthält die Kosten eines jeweils kürzesten Pfades zwischen zwei Knoten und löst damit das **All-pair-shortest-distance-Problem**
