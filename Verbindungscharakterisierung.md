EIne Verbindung zwischen zwei Knoten kann hinsichtlich einiger grundlegender Eigenschaften charakterisitert werden:

- Übertragungsrate
- Übertragungsverzögerung
- Übertragungsrichtung
- Mehrfachzugriff (Multiplexing)

<br>

## Übertragungsrate

>[!NOTE] Definition
>
>Die Übertragungsrate $r$ in $bit/s$ beschreibt die notwendige Zeit um $L$ Datenbtis zu übertragen. Wir auch Serialisierungszeit genannt.
>$$t_s=\frac{L}{r}$$

<br>

## Ausbreitungsgeschwindigkeit

>[!NOTE] Definition
>
>Die Ausbreitungsverzögerung über eine Distanz $d$ wird bestimmt von der endlichen Ausbreitungsgeschwindigkeit im Vakuum $c_0$ die durch einen Faktor $v$ gestaucht wird.
>$$t_p=\frac{d}{v\cdot c_0}$$
>
>- für typische Kupferleitungen nehmen wir $v\approx\frac{2}{3}$ an
>- die Distanz $d$ wird in $m/s$ angegeben

---

Die Gesamtverzögerung $t_d$ ergibt sich daraus folglich aus $t_s+t_p$ und beschreibt den Zeitraum vom Senden des ersten Bits bis zum fertigen Serialisieren.

<br>

## Bandbreitenbverzögerungsprodukt

>[!NOTE] Definition
>
>Als Bandbreitenverzögerungsprodukt bezeichnet man die Anzahl an Bits die sich in einer Senderichtung gleichzeitig auf der Leitung befinden können.
>$$C=t_p\cdot r=\frac{d}{v\cdot c_0}\cdot r$$
>
>Die Bandbreite $r$ der Leitung wird dabei in $bit/s$ angegeben

<br>

## Mehrfachzugriff

Nachrichten unterschiedlicher Teilnehmer können gemeinsam über eine Leitung übertragen werden. Dabei muss man einen Standard für die strikte Trennung der Kommunikationspartner definieren.

---

### synchrones TDMA

- statische Aufteilung des Kanals zwischen den Teilnehmern
- Datenverkehr erfolgt stossartig $\Rightarrow$ für kurze Zeit sendet immer ein Teilnehmer, dann ein anderer, usw.

$\Rightarrow$ Lösungsansatz: keine statische Aufteilung $\Rightarrow$ keine Ruhezeiten $\Rightarrow$ zufälliger, konkurrierender oder dynamisch geregelter Medienzugriff

<br>

### ALOHA

##### Funktionsweise

- jede Station sendet an eine Zentrale Station (Vergleich: WLAN), sobald Daten vorliegen
- senden zwei Stationen gleichzeitig kommt es zu Kollision
- erfolgreich übertragende Nachrichten werden vom Empfänger auf anderer Sequenz quittiert

$\Rightarrow$ Quittierung erfolgt "out-of-band" und kann somit nicht für Kollisionen sorgen

---

<br>

##### Erreichbarer Durchsatz

- Betrachtung eines Zeitintervalls $[t,t+T)$ indem ein beliebiger Knoten $n$ senden kann
- $\forall n\in N: Pr[n]=\frac{1}{|N|}$
- dasselbe Bernoulli-Experiment wird $|N|$ mal wiederholt
- Approximierung durch eine **Poisson-Verteilung** möglich
- die mittlere Anzahl an Nachrichten pro Intervall wird beschrieben mit $Np=\lambda$

Das Ereignis $X_t$, dass im Intervall $[t,t+T)$ genau $k$ Knoten senden ist poisson-verteilt:
$$Pr[X_t=k]=\frac{\lambda^k\cdot e^{-k}}{k!}$$

---

$\Rightarrow$ die Übertragung ist erfolgreich

$\hspace{0.65cm}\Leftrightarrow$ innerhalb von $[t_0,t_0+T)$ genau eine Übertragung stattfindet
$\hspace{0.65cm}\Leftrightarrow$ innerhalb von $(t_0-T,t_0)$ keine Übertragung begonnen hat

---

>[!NOTE] Definition
>
>Die Dichtefunktion der Poisson-Verteilung beschreibt die Wahrscheinlichkeit $p_0$ für eine erfolgreiche Übertragung
>$$p_0=Pr[X_{{t_0}-T}=0]\cdot Pr[X_{t_0}=1]=e^{-\lambda}\lambda e^{-\lambda}=\lambda\cdot e^{-2\cdot\lambda}$$
>
>---
>
>Die Anzahl $S$ der erfolgreichen Nachrichten pro Intervall entspricht somit $Pr[X_t=1]$, da maximal eine Nachricht geschickt werden kann.
>
>---
>
>Bei einem optimalen Verfahren würde die Anzahl erfolgreicher Nachrichten $S$ linear mit der Senderate ansteigen bis die maximale Anzahl Nachrichten pro Intervall erreicht ist.

---

<br>

### Slotted Aloha

Zeitdiskretisierung $\Rightarrow$ Nachrichtenübertragungen dürgen nurnoch an den Zeitpunkten
$$t=n\cdot T, n\in\mathbb{N_0}$$
geschehen.

$\Rightarrow$ kritischer Zeitpunkt nurnoch $T$ anstatt von $2\cdot T$
$\Rightarrow p_0=\lambda\cdot e^{-\lambda}$

---



