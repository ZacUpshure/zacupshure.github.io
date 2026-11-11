# Übersicht

## Titel
> **Entwicklung und implementierung von Algorithmen zur Optimierung von Durchlaufzeiten 
> einer Automobilfertigungslinien.** 

Ist der Titel der Arbeit. Eingegrenzt auf (SALBP-2).

## SALBP-2
Bei SALBP-2 betrachtet man eine vereinfachte Fertigungslinie mit einer festen **Anzahl Stationen (m)**. Und es gibt **(n) Arbeitsvorgänge** mit Bearbeitungszeit und Vorrängen. Das Ziel ist es dabei die Arbeitsvorgänge auf die Stationen zu verteilen, so dass die **Taktzeit ( c) minimiert wird**. Die Taktzeit ist die Zeit der am stärksten ausgelasteten Station.

Auf einer getakteten Linie gilt: 

> Durchlaufzeit ≈ Taktzeit X Stationsanzahl

Da die Taktzeit ein Faktor ist wird die Durchlaufzeilt unmittelbar kürzer sobald die Taktzeit selbst kürzer wird. (Damit wird die Eingrenzung gegenüber dem Titel gerechtfertigt)

## SALBP-1
Anders als bei SALBP-1 wo die Taktzeit fest ist und die Zahl der Stationen minimiert wird.

## Daten
### Herkunft
Der Datensatz der im Rahmen der Arbeit für das Experiment verwendet wird sind die Otto & Scholl Benchmarks von 2013. Referenziert aus ihrem Beitrag "Otto, A.; Otto, C.; Scholl, A. (2013): Systematic data generation and test design for solution algorithms on the example of SALBPGen for assembly line balancing. European Journal of Operational Research 228/1, 33-45.". 

Auf der webseite [assembly-line-balancing.de](https://assembly-line-balancing.de/) die von einer kleinen Gruppe Wissenschaftler*innen in dem Feld geführt wird:

- Prof. Dr. Nils Boysen, University of Jena
- Prof. Dr. Malte Fliedner, University of Hamburg
- Prof. Dr. Robert Klein, University of Augsburg
- Prof. Dr. Armin Scholl, University of Jena

gibt es auf der Seite [Benchmark Data Sets by Otto et al. (2013)](https://assembly-line-balancing.de/salbp/benchmark-data-sets-2013/) Den Datensatz selbst sowie eine Beschreibung des Formats und ein Paper mit Ergebnissen `Results of BBR by Morrison et al. (2014, Appendix A)` wo der Benchmark verwendet wurde. 

### Format
Die einzelnen Insanzen haben ein eigenes Dateiformat `.alb` und sind nach der Anzahl der Aufgaben in einer Linie strukturiert. Es gibt umfangreiche Instanzen zu n=5, 20, 50, 100, 1000. Für das Experiment wären 5 zu wenig gewesen, weil man die den Unterschied in den Ergebnissen kaum sinvoll vergleichen könnte. 100 bis 1000 wäre nicht umsetzbar gewesen im Rahmen der Arbeit, da zum Vergleich auch ein Simplex Algorithmus als exaktes verfahren verwendet wird. Da dies ein NP (`nichtdeterministisch polynomielle Zeit`) hartes Problem ist, wird die Lösung des Problems für exakte Verfahren schnell untragbar und verbraucht zu viele Resourcen. `n=50` ist also eine Mitte die sowohl eine brauchbare Auswertung zulässt als auch eine für die verfügbaren Resourcen tragbare Lösung des Exakten Verfahrens ermöglicht. 

```bash
<number of tasks>
50

<cycle time>
1000

<order strength>
0.196


<task times>
1 73
2 125
3 172
...
48 228
49 163
50 27

<precedence relations>
1,33
2,8
2,9
...
38,48
43,49
46,50

<end>
```

### Besonderheiten
Die Daten waren urspünglich für SALBP-1 gedacht. Wenn aber die Startlösung, also die Anzahl der Stationen (m), in die jeweilige Instanz hinzugefügt wird, werden daraus SALBP-2 fähige Daten. Das ist relevant für die Forschungsfrage, da die im Rahmen der Arbeit vor allem untersucht wird ob es einen Vorteil gibt dabei ob die Startlösung (m) vorsortiert oder zufällig ist. Was das bedeutet, wird klarer wenn man sich die Verfahren ansieht die in dem Experiment verwendet werden.

## Forschungsfrage

## Verfahren

## Eigenleistung