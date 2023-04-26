## Idee des Schichtenmodells

Unterteilung des komplexen Kommunikationsvorgangs:
- niedrigere Schichten bieten höheren Schichten Dienste an
- höhere Schichten nehmen DIenste der jeweiligen niedrigeren Schicht in Anspruch

Abstraktion von der Implementierung einer Schicht:
- Festlegung, welche Dienste angeboten werden, aber nicht wie sie erfüllt werden (Interface)
- Austauschbarkeit einzelner Implementierungen

<br>

## Das ISO/OSI-Modell

>[!NOTE] Definition
>
>Das Open Systems Interconnection model unterteilt die Architektur des Systems, das die Kommunikationsfunktionalität erbringt in 7 Schichten.
>
>- jede Schicht erbringt bestimmte Dienste
>- keine Aussage, wie diese Dienste zu erbingen sind

---

##### Horizontale Kommunikation

Kommunikation zwischen Schichten der selben Stufe in unterschiedlichen Systemen.

---

##### Vertikale Kommunikation

Kommunikation zwischen Schichten verschiedener Stufen im gleichen System.

<br>

##### Schichten

Von der niedrigsten Schicht beginnend:

1. Physikalische Schicht
2. Sicherungsschicht
3. Vermittelungsschicht
4. Transportschicht
5. Sitzungsschicht
6. Darstellungsschicht
7. Anwendungsschicht

Die physikalische Schicht kommuniziert dabei mit anderen physikalischen Schichten über einen Kanal (aus Kuper, Lichtwellenleiter, Funk).

<br>

##### Datenaustausch zwischen Schichten

>[!NOTE] Definition des Datenaustausches
>
>- Kommunikation zwischen $(N+1)$-Schicht, $N$-Schicht und $(N-1)$-Schicht
>- Dienstanspruchname $\Rightarrow N$-Schicht enthält IDU von $(N+1)$-Schicht

<br>

$N$-IDU enthält:

- Nutzdaten SDU
- Kontrollinformation ICI (notwendig zum Erbringen des Dienstes)

$$\Downarrow$$

$N$-Schicht:

- erbringt azf der $N$-SDU die angeforderten Dienste
- fügt PCI für die $N$-Schicht der Gegenseite hinzu
- erzeugt aus PCI und SDU die PDU

$$\Downarrow$$

$N$-Schicht nutzt Dienst der $(N-1)$-Schicht:

- erzeugt $(N-1)$-ICI
- übergibt diese zusammen mit $N$-PDU als $(N-1)$-IDU der $(N-1)$-Schicht

<br>

##### PDU

>[!NOTE] Definition
>
>Die PDU bezeichnet:
>
>- die Nutzdaten der darüberliegenden Schicht, d.h. die SDU
>- die Protokollsteuerinformationen (PCI) ihrer Schicht
>- die PCI wird häufig in Form eines Headers den Nutzdaten vorangestellt
>
>PDUs einiger Schichten haben eigene Bezeichnungen:
>
>- Segmenten auf der Transportschicht
>- Paketen auf der Vermittelungsschicht
>- Rahmen auf der Sicherungsschicht
