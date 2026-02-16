```
title: Netzwerkanalyse
authors: de Lorenzo, Ebner, Proksch, Uller
course: Network and Web Science by Prof. Schirgi & Prof. Hatzl
date: WS25
location: FH Campus02
```

# 1. Überblick

Der Datensatz besteht aus 88234 Zeilen, wobei jede Zeile einem Kantentupel **(u, v)** des Netzwerks entspricht. Um Komplexität aus der Aufgabenstellung zu nehmen wurde das Netzwerk auf **5000 Kanten** reduziert. In der zufälligen Auswahl von Kanten, finden sich **2831 Knoten**, welche in weiterer Folge auf deren Eigenschaften analysiert werden.

# 2. Analyse

## 2.1 Erster Plot

![first plot](/plots/first_plot.png "Erster Plot")

Der simple Plot dient dafür eine grobe Vorstellung des Netzwerks zu bekommen und eventuell einen Ausblick auf eventuell spannende Eigenschaften zu erhalten. Auf dem ersten Plot kann man deutlich sechs, mehr oder weniger gut verbundene, Cluster erkennen. Um das "Zentrum" sieht man vor allem kleine Verbindungen, bei denen die meisten Knoten nicht einmal eine Brücke zu einem Cluster vorweisen können. Diesen graphischen Eindruck, kann man auch an der Anzahl an Zusammenhangskomponenten **(158)** wiederfinden. Wir denken es macht für die weitere Analyse Sinn, die Inseln, welche durch **keine** Brücke mit den zentralen Komponenten im Zentrum verbunden sind, auszuschließen. Diese kleinen Inseln entstanden wahrscheinlich durch die zufällige Auswahl an Kanten zu Beginn des Projekts.

## 2.2 Reduzierung des Netzwerks

**Hinweis**: Wird in weiterfolgendem Text von Netzwerk oder Graphen geschrieben, wird auf reduzierten Teilgraphen Bezug genommen!

### 2.2.1 Identifizierung der relevanten Komponenten

Aus dem ursprünglichen Netzwerk werden alle Knoten entfernt die in Komponenten liegen, welche aus weniger als 10 Knoten bestehen.

```python
components = list(nx.connected_components(G)) # Liste der Komponenten

large_components = [c for c in components if len(c) >= 10] # Komponenten >= 10

nodes_in_large_components = set().union(*large_components) # Liste zu Menge

H = G.subgraph(nodes_in_large_components) # Teilgraph aus den großen Komponenten
```

Von den ursprünglichen 2831 Knoten des Netzwerks wurden 374 entfernt.

Der Teilgraph H besteht aus **2457 Knoten und 4780 Kanten.**

Der Teilgraph H hat **4 Zusammenhangskomponenten.**

### 2.2.2 Plot des Teilgraphen

![subgraph](/plots/subgraph.png "Teilgraph")

Wie man erkennen kann, wurden die irrelevanten Knoten entfernt.


## 2.3 Eigenschaften des Netzwerks

[] Todo


# 3. Schlussfolgerung

[] Todo

# 4. Aufwand

~ 2