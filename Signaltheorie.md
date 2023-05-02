## Information und Enropie

#### Informationsgehalt

>[!NOTE] Definition 
>
>Der Informationsgehalt eines Zeichens (oder Symbols) drückt aus, wieviel Informationen durch das Zeichen übertragen werden.

<br>

##### Eigenschaften

- je seltener das Zeichen, desto höher sein Informationsgehalt
- der Informationsgehalt einer Zeichenkette entspricht der Summe der einzelnen Zeichen
- Der Informationsgehalt eines vorhersagbaren Zeichens ist 0

<br>

#### Information

>[!NOTE] Definition
>
>Information besteht in der Unsicherheit, Veränderungen eines Signals vorhersagen zu können.
>
>- Informationsgehalt $I$
>- Zeichen $x$
>- Auftrittswahrscheinlichkeit $p(x)$
>
>Zum Beobachtungszeitpunkt ist die Informationsgehalt definiert als:
>$$I(x)=-log_2\ p(x)\text{ mit } [I]=\text{bit}$$
>
>Dabei ergibt sich die Auftrittswahrscheinlichkeit durch: $\frac{\#\text{Zeichen}}{\#\text{alle Zeichen}}$

<br>

#### Entropie

>[!NOTE] Definition
>
>Den mittleren Informationsgehalt einer Quelle bezeichnet man als Entropie. Die Entropie beschreibt zudem das Maß für Ungewissheit 
>- ist für alle $x\in\chi$ die Auftrittswahrscheinlichkeit gleich, dann ist die Entropie maximal also $1\Rightarrow$ es kann keine Voraussage über das nächste Zeichen getroffen werden
>- der Verlauf der Entropie verhält sich wie eine Glocke für binäre Zeichen
>$$H(X)=\sum_{x\in\chi}p(x)\cdot I(x)$$

<br>

## Signaldarstellung

##### Integration

>[!NOTE] Definition
>
>Für ein beliebiges begrenztes Integral gilt:
>$$\int^a_bf(x)dx\hspace{0.5cm}=\hspace{0.5cm}\Big[F(x)\Big]^a_b\hspace{0.5cm}=\hspace{0.5cm}F(a)-F(b)$$

---

##### Fourierreihe

>[!NOTE] Definition
>
>Falls $s(t)$ periodisch verläuft, lässt sich das Singal sich als Summe gewichteter Sinus- und Konsinus-Schwingungen repräsentieren. Die Reihenentwicklung bezeichnet man als Fourierreihe:
>
>$$s(t)=\frac{a_0}{2}+\sum^\infty_{k=1}(a_k\cdot cos(k\omega t)+b_k\cdot sin(k\omega t))$$
>
>- der Gleichanteil von $s(t)$ lautet $\frac{a_0}{2}$ und steht für die Verschiebung anhand der Ordiante
>- das $k$-te Summengleich bezeichnet man als $k$-te harmonische Glied
>- die Koeffizienten $
>- die Koeffizienten (Gewichte) $a_k$ und $b_k$ lassen sich wie folgt berechnen:
>$$a_k=\frac{2}{T}\int^T_0s(t)\cdot cos(k\omega t)\cdot dt\text{ und }b_k=\frac{2}{T}\int^T_0s(t)\cdot sin(k\omega t)\cdot dt$$

---

##### Fouriertransformation

>[!NOTE] Definition
>
>Falls $s(t)$ nicht periodisch verläuft, lässt sich durch eine Fouriertransformation repräsentieren:
>
>$$S(f)=\frac{1}{\sqrt{2\pi}}\int^\infty_{t=-\infty}s(t)(cos(2\pi ft)-i\cdot sin(2\pi ft))dt$$

<br>

## Abtastung, Rekonstruktion und Quantisierung

>[!NOTE] Definition
>
>Natürliche Werte sind zeitkontinuierlich und wertkontinuiertlich $\Rightarrow$ Problem für Computer
>
>$$\text{Analoges Signal}\Rightarrow\text{Abtastung: zeitdiskretes Signal}\Rightarrow\text{Quantisierung: wertdiskretes Signal}\Rightarrow\text{Digitales Signal}$$

<br>

##### Abtastung

>[!NOTE] Definition
>
>- Dirac Impuls $\widehat\delta[t]$ 
>- Abtastintervall $T_a$
>  
>Diskreditierung des Signals:
>
>$$\widehat{s}(t)=s(t)\sum^\infty_{n=-\infty}\delta[t-n\cdot T_a],\text{ mit }\delta[t-n\cdot T_a]=\begin{cases}1 & t=n\cdot T_a\\ 0 & \text{sonst}\end{cases}$$

<br>

##### Rekonstruktion

>[!NOTE] Definition
>
>Für eine angenäherte Rekonstruktion eines Signals mithile der Abtastwerte $\widehat s[n]$ gilt
>$$s(t)\approx\sum^\infty_{n=-\infty}\widehat{s}[n]\cdot sinc\Big(\frac{t-n\cdot T_a}{T_a}\Big)$$
>
>Das Signal wird am genausten nachgebildet mit $n\rightarrow\infty$

---

##### Verlustfreie Rekonstruktion

Mithilfe des Abtasttheorem von Shannon und Nyquist gilt:

>[!NOTE] Definition
>
>Ein $|f|\le B$ bandbegrenztes Signal $s(t)$ ist vollständig durch Abtastwerte beschrieben, sofern die Distanz zwischen den einzelnen Werten weiter als $$T_a\le\frac{1}{2}\cdot B$$ 
>auseinanderliegen.
>
>Die Abtastfrequenz ist damit mit
>$$f_a>2B$$
>nach unten beschränkt, da sonst periodische Überlappungen (Aliasing) auftreten und die Wertabnahme manipulieren.


<br>

##### Quantisierung

>[!NOTE] Definition
>
>- die Unterscheidung von $M=2^N$ Signalstufen erfordert Codewört von $N$ bit
>- jede Signalstufe wird dabei ein bestimmtes Codewort zugeordnet
>- ein Interval $I_Q=[a,b]$ beschreibt untere und obere Schranke der Analyse
>- Stufenbreite (zwischen einzelnen Identifieren): $$\Delta=\frac{b-a}{2^N}$$
>- Signal orientiert sich immer an nähesten Identifier auf der Ordiante in Relation zum zeitlichen Wert $t\in\mathbb{N}$
>
>Dieser Art der Wertzuweisung wird Gray-Code genannt. Die einzelnen Stufen unterscheiden sich dabei um $\pm 1$ (in Binär)
