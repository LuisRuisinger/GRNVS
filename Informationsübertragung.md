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

---

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

---

##### Leitungskodierung

>[!NOTE] Definition
>
>Leitungscodes definieren die Abfolge von einer bestimmten Art von Grundimpulsen, welche Bits oder Gruppen von Bits repräsentieren
