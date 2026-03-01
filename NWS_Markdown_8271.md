# Analysebericht: Facebook Social Network Analysis

<small>Autoren: Michael de Lorenzo, Stefan Ebner, Thomas Proksch, Victoria Uller</small>

## 1. Einleitung und Methodik

In dieser Untersuchung wird ein ungerichteter Graph analysiert, der auf einem Datensatz von Facebook-Verbindungen basiert.

* **Datengrundlage:** Aus dem Gesamtdatensatz wurde eine repräsentative Stichprobe von **5000 Kanten** extrahiert.
* **Reproduzierbarkeit (Random State):** Als Zufallswert (`random_state`) wurde die Zahl **8271** gewählt. Diese Nummer wurde aus der Summe der Matrikelnummern unserer Gruppe generiert, um sicherzustellen, dass die gezogene Stichprobe für unsere Gruppe einzigartig und das Ergebnis nachvollziehbar bleibt.
* **Netzwerkgröße:** Der resultierende Graph umfasst **2831 Knoten**.

---

## 2. Netzwerkanalyse: Kennzahlen & Interpretation

### 2.1 Netzwerkdichte (Density)

* **Ergebnis:** ~0.00125
* **Interpretation:** Die Dichte ist extrem gering. In einem sozialen Netzwerk bedeutet dies, dass nur ein Bruchteil der theoretisch möglichen Verbindungen tatsächlich existiert.
* **Begründung:** Das Netzwerk ist "sparse" (dünn besiedelt). Dies ist charakteristisch für große soziale Medien: Nutzer sind meist in lokalen Clustern vernetzt, kennen aber nicht die gesamte Population. Trotz der geringen Dichte bleibt das Netzwerk durch "Small World"-Effekte effizient.

### 2.2 Zentrale Akteure (Hubs)

* **Wichtigster Knoten:** ID **107** mit einem Grad von **57**.
* **Interpretation:** Dieser Knoten fungiert als einflussreichster „Super-Connector“.
* **Bedeutung:** Solche Hubs sind entscheidend für die strukturelle Integrität. Sie dienen als Brücken zwischen weit entfernten sozialen Kreisen und sind für die Geschwindigkeit der Informationsverbreitung (Viralität) unerlässlich.

### 2.3 Clustering-Koeffizient (Cliquenbildung)

* **Durchschnittswert:** ~0.0176
* **Interpretation:** Ein Wert von ca. 1,7 % ist relativ niedrig. Er beschreibt, wie stark die Freunde eines Nutzers auch untereinander vernetzt sind.
* **Begründung:** Dies deutet darauf hin, dass in dieser Stichprobe die lokale Cliquenbildung schwach ausgeprägt ist. Das Netzwerk besteht hier eher aus losen Bekanntschaften als aus dichten, geschlossenen Freundeskreisen.

---

## 3. Struktur, Resilienz und Gleichartigkeit

### 3.1 Zusammenhangskomponenten und Isolation

* **Analyse:** Das Netzwerk besteht aus **158 Komponenten**.
* **Interpretation:** Es existiert eine große Hauptkomponente (Giant Component), in der die meisten Nutzer verbunden sind. Die restlichen 157 Komponenten sind isolierte Kleingruppen oder Einzelpersonen (Knoten-IDs siehe Code-Output).
* **Bedeutung:** Dies zeigt die Fragmentierung sozialer Medien. Viele Nutzer existieren in abgeschotteten digitalen Inseln ohne Verbindung zum globalen Diskurs des Hauptnetzwerks.

### 3.2 Resilienz und Brücken

* **Lokale Brücken:** Die identifizierten Brücken sind die kritischen Pfade des Netzwerks. Sie verbinden unterschiedliche soziale Cluster.
* **Resilienz-Theorie:** Das Netzwerk folgt einer skalenfreien Logik. Das bedeutet:
* **Robustheit:** Gegenüber zufälligen Ausfällen (Nutzer werden inaktiv) ist das Netzwerk stabil.
* **Fragilität:** Bei gezielten Ausfällen von Hubs (wie Knoten 107) bricht die Struktur schnell zusammen. Das Netzwerk ist also robust gegenüber Zufall, aber anfällig für gezielte Entfernung zentraler Akteure.

### 3.3 Entfernen von Komponenten
* **Interpretation**:
Das untersuchte Netzwerk weist eine klassische Core-Periphery-Struktur auf. Während die "Giant Component" mit 2046 Akteuren das kommunikative Zentrum bildet, existiert eine signifikante Anzahl von 157 isolierten Kleingruppen (insg. 785 Personen), die vom Hauptinformationsfluss abgeschnitten sind. Die geringe Dichte innerhalb des Kerns (0,2 %) bei gleichzeitig hoher Vernetzung zeigt, dass das Netzwerk effizient, aber fragil ist: Es gibt kaum Redundanz.



### 3.4 Gleichartigkeit

* **Interpretation:** Wir können davon ausgehen, dass innerhalb der gefundenen Communities eine hohe Gleichartigkeit herrscht. Nutzer verbinden sich bevorzugt mit Menschen, die ähnliche Merkmale aufweisen (gleiche Interessen, Wohnort). Dies begünstigt die Bildung von „Echo-Kammern“, in denen Informationen schnell zirkulieren, aber selten nach außen dringen.

---

## 4. Visualisierung

Bei 2831 Knoten ist ein Standard-Plot oft unübersichtlich („Haarknäuel“). Um die Struktur erkennbar zu machen, wurden folgende Strategien gewählt:

1. **Layout-Algorithmus:** Nutzung eines Force-Directed-Layouts (Spring-Layout), um vernetzte Gruppen räumlich zu gruppieren.
2. **Fokussierung:** Durch die Stichprobenbildung auf 5000 Kanten wird das „Skelett“ des Netzwerks sichtbar, ohne die Lesbarkeit durch zu viele Kantenüberkreuzungen zu verlieren.
3. **Interpretation:** 
Die Visualisierung der Hauptkomponente bestätigt die Ergebnisse der Community-Analyse. Man erkennt deutlich, dass das Netzwerk kein ungeordnetes Chaos ist, sondern sich in spezifische Subzentren (die Farbwolken) unterteilt.
Besonders auffällig sind die dichten Cluster in Orange und Braun: Hierbei handelt es sich um hochgradig vernetzte Kerngruppen, die fast wie geschlossene Einheiten fungieren. 
Die lose verteilten Punkte am Rand zeigen hingegen die Peripherie des Netzwerks. 
Die wenigen Verbindungen, die zwischen den großen Farbwolken verlaufen, markieren die strategischen Schnittstellen des Netzwerks. 
Diese Visualisierung macht deutlich, warum das System so empfindlich auf das Entfernen von Einzelpersonen reagiert: Der Zusammenhalt zwischen den großen Clustern hängt buchstäblich an seidenen Fäden – den wenigen Brücken zwischen den Communities.

---

## 5. Übergreifende Interpretation und finales Resümee

Die Analyse des Facebook-Teilgraphen offenbart eine Netzwerkarchitektur, die prototypisch für moderne, digitale Kommunikationsstrukturen ist.

### 5.1 Die Effizienz der „Small World“-Struktur

Trotz der geringen Netzwerkdichte ist das System hocheffizient. Während der Großteil der Nutzer nur spärlich vernetzt ist, garantieren zentrale Hubs, dass die durchschnittliche Distanz zwischen zwei Personen kurz bleibt. Informationen diffundieren nicht gleichmäßig, sondern „springen“ über diese Super-Connectoren in Rekordzeit durch das gesamte Netzwerk.

### 5.2 Strukturelle Fragilität und das „Robust-yet-Fragile“-Paradigma

Das Netzwerk weist eine ambivalente Resilienz auf. Gegenüber zufälligen Ausfällen ist es extrem stabil. Es ist jedoch hochgradig verwundbar gegenüber gezielten Eingriffen: Würden die zentralen Hubs oder die identifizierten lokalen Brücken entfernt, würde die „Giant Component“ kollabieren. Das soziale Gefüge würde in seine Fragmente zerfallen, was den globalen Informationsfluss schlagartig stoppen würde.

### 5.3 Soziale Implikationen: Echo-Kammern vs. Informationsbrücken

Das geringe Clustering in Kombination mit der hohen Anzahl an Komponenten deutet auf eine soziale Fragmentierung hin. Nutzer bewegen sich in relativ homogenen, isolierten Clustern. Der Austausch von neuem Wissen hängt fast ausschließlich an den Brücken (Bridges). Ohne diese kritischen Verbindungen neigt das Netzwerk zur Bildung von „Echo-Kammern“, in denen Informationen nur innerhalb der eigenen Blase zirkulieren.

### 5.4 Beurteilung

Zusammenfassend lässt sich das untersuchte Netzwerk als ein **„optimiertes, aber belastungsarmes Distanz-Netzwerk“** charakterisieren. Es ist perfekt auf die schnelle, virale Verbreitung von Informationen ausgelegt (hohe Reichweite durch Hubs), bietet jedoch wenig strukturelle Redundanz. Es ist ein hocheffizientes Informationssystem, das jedoch in seiner sozialen Tiefe zu wünschen übrig bleibt.