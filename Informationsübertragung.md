## Übertragungskanal

##### Einflüsse auf einen Transportkanal

- Dämpfung $\Rightarrow$ Amplitude des Signals am Ausgang ist geringer
- Tiefpassfilterung $\Rightarrow$ höhere Frequenzen werden stärker gedämpft als niedrige
- Verzögerung $\Rightarrow$ die Übertragung benötigt gewisse Zeit
- Rauschen in Form von AWGN

---

Aufgrund der Tiefpasscharakteristik kann man von einer Kanalbrandbreite $B$ sprechen:

- niedrige Frequenzen passieren ungehindert
- hohe Frequenzen werden gedämpft
- ab einer bestimmten Frequenz ist die Dämpfung so stark, dss die betreffenden Signalteile vernachlässigt werden können $\Rightarrow$ nur Frequenzteile $|f|<B$ passieren

<br>

##### Nyquist-Rate

>[!NOTE] Definition
>
>Sei $B$ die Grenzfrequenz eines bandbegrenzten Kanals. Dann ist die Nyquist-Rate $f_N=2B$
>- untere Schranke die für eine vollständige Rekonstruktion erlaubt
>- obere Schranke für die Anzahl an Symbolen je Zeiteinheit die unterscheidbar sind

---

##### Hartleys Gesetz

>[!NOTE] Definition
>
>Auf einem Kanal der Bandbreite $B$ mit $M$ unterscheidbaren Signalstufen ist die Kanalkapazität durch
>$$C_H=2B\cdot log_2(M) bit$$
>
>nach oben begrenzt

<br>

### Rauschen

Rauschen macht es schwer Signalstufen auseinanderzuhalten $\Rightarrow$ je feiner die Signalstufen desto verherender wirkt Rauschen.

>[!NOTE] Definition 
>
>Für das Maß des Rauschens gilt
>$$SNR=\frac{\text{Signalleistung}}{\text{Rauschleistung}}=\frac{P_S}{P_N}$$
>
>- $P_S$ und $P_N$ in Watt
>- Angabe in dB: $SNR_{db}=10\cdot log_{10}(SNR)$

<br>

### Signalleistung

>[!NOTE] Definition
>
>Für die obere Schranke für die erreichebare Datenrate gilt nach Shannon-Hartley:
>$$C_S=B\cdot log_2\Big(1+\frac{P_S}{P_N}\Big)$$
>
>- Kanal der Bandbreite $B$
>- Rauschleistung $P_N$
>- Signalleistung $P_S$

---

##### Vergleich mit Hartleys Gesetz

- $C_S$ berücksichtigt nur additives Rauschen des kanals, aber keine Quantisierungsfehler
- $C_H$ berücksticht nur die Signalstufen und damit das Quantisierungsrauschen aber keine Kanaleinflüsse

2 Faktorbeschränkung durch $C_S$ und $C_H$:
$$C<min\{C_H,C_S\}=min\{2B\cdot log_2(M),\ B\cdot log_2(1+SNR)\}\text{ bit}$$

<br>

## Nachrichtenübertragung

##### Quellcodierung

>[!NOTE] Definition
>
>Ziel der Quellenkodierung ist es durch Abbildung von Bitsequenzen auf Codewörter Redundanz aus den zu übertragenden Daten zu entfernen.

$\Rightarrow$ verlustlose Datenkompression

<br>

##### Kanalcodierung

>[!NOTE] Definition
>
>Ziel der Kanalkodierung ist es, den zu übertragenden Daten gezielt Redundanz hinzuzufügen, sodass
>
>- Bitfehler erkannt werden
>- Bitfehler korrigiert werden

$\Rightarrow$ Lineare Codes für Redundanz und Fehlerkorrektur
$\Rightarrow$ Absinkung der Datenrate als Folge der Sicherheit
$\Rightarrow$ Bei Bedarf muss eine Übertragung wiederholt werden

<br>

##### Leitungskodierung

>[!NOTE] Definition
>
>Leitungscodes definieren die Abfolge von einer bestimmten Art von Grundimpulsen, welche Bits oder Gruppen von Bits repräsentieren

---

##### Möglichkeit 1: Coderegelverletzung

- ist das Medium idle können ungültige Basisimpulse gesendet werden
- Präambel: Vor Beginn einer Nachricht kann eine feste Anzahl alternierender Bits gesendet werden
- Beginn der Nachricht wird durch eine zweite Sequenz angezeigt (Start Frame Delimiter)
- funktioniert mit NRZ, RZ und Manchester Code aber nicht mit MLT3

<br>

>[!NOTE] Definition
>
>Die Abfolge wäre:
>$$\text{Idle}\hspace{0.5cm}\Rightarrow\hspace{0.5cm}\text{Präambel}\hspace{0.5cm}\Rightarrow\hspace{0.5cm}\text{SFD}\hspace{0.5cm}\Rightarrow\hspace{0.5cm}\text{Daten}\hspace{0.5cm}\Rightarrow\hspace{0.5cm}\text{Idle}$$
>
>- Präambel ermöglicht Taktsynchronisation
>- SFD am Ende der Präambel signalisiert Beginn der Nachricht
>- Coderegelverletzung zeigt Idle an

---

##### Möglichkeit 2: Steuerzeichen

- definiere Blockcode, welcher Kanalwörter in Gruppen von $k$ bit unterteilt und auf $n>k$ bit abbildet
- Blockcode dient nur zur Bereitstellung von Steuerzeichen und nicht der Fehlerkorrektur
- Abbildung kann so gewählt werden, dass Taktrückgewinnung und Gleichstromfreiheit für NRZ, RZ und MLT3 möglich werden

<br>

###### Modulation

>[!NOTE ] Definition
>
>Ablauf digitaler Modulationsverfahren zur zeitgleichen Kanalnutzung von mehreren Übertragungen - Frequency Division Multiplex:
>
>- die Sendeimpulse $g(t)$ werden mittels Tiefpassfilterung auf eine maximale Frequenz $f_max$ beschränkt $\Rightarrow g_T(t)$
>- das bandbegrenzte Sendesignal $S_T(t)$ wird auf ein Trägersignal der Frequenz $f_0$ aufmoduliert
>  
>$$s(t)=s_T(t)\cdot cos(2\pi\cdot f_0\cdot t)=\Big(\sum^\infty_{n=1}d_n\cdot g_T(t-n\cdot T)\Big)\cdot cos(2\pi\cdot f_0\cdot t)$$
>
>Arten:
>
>- Amplitude Shift Keying $\Rightarrow 2$ bit / Symbol
>- Quadratur-Amplituden-Modulation $\Rightarrow 1$ bit / Symbol

<br>

## Übertragungsmedien

##### Elektromagnetische Wellen

>[!NOTE] Definition
>
>- elektrische Komponente
>- magentische Komponente
>
>Stehen jeweils zueinander orthogonal und zur Ausbreitungsrichtung orthogonal

---

- Ausbreitung im Vakuum mit $c_0\approx 3\cdot 10^8\frac{m}{s}$
- Ausbreitung innerhalb Luft/Wasser mit $c=v\cdot c_0$, wobei $0<v<1$
- kein Medium zur Ausbreitung benötigt
- die Frequenz $f$ ergibt sich aus der Wellenlänge im Medium zu $f=\frac{c}{\lambda}=\frac{c_0}{\lambda_0}$

<br>

##### Koaxialleiter

>[!NOTE] Definition
>
>Eingesetzt u.a für $10$ Mbit/s Ethernet nach IEEE 802.3a, 100 GBit Ethernet auf kurze Distanz.

<br>

##### Twisted-Pair-Kabel

>[!NOTE] Definition
>
>- Verwendung für Lokale Netzwerke, Telefonanschluss
>- Arten: UTP / STP / S/UTP / S/STP

<br>

##### Optische Leiter

>[!NOTE] Definition
>
>- Licht wird innerhalb des Faserkerns weitergebildet
>- sehr hohe Datenraten möglich
>- kein ÜBersprechen
>- Kabelbruch verherrend
