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

Der simple Plot dient dafür eine grobe Vorstellung des Netzwerks zu bekommen und eventuell einen Ausblick auf eventuell spannende Eigenschaften zu erhalten. Auf dem ersten Plot kann man deutlich sechs, mehr oder weniger gut verbundene, Cluster erkennen. Um das "Zentrum" sieht man vor allem kleine Verbindungen, bei denen die meisten Knoten nicht einmal eine Brücke zu einem Cluster vorweisen können. Diesen graphischen Eindruck, kann man auch an der Anzahl an Zusammenhangskomponenten **(158)** wiederfinden. Wir denken es macht für die weitere Analyse Sinn, die Knoten, welche durch **keine** Brücke mit einem Cluster im Zentrum verbunden sind, auszuschließen.

## 2.2 Reduzierung des Netzwerks

**Hinweis**: Wird in weiterfolgendem Text von Netzwerk oder Graphen geschrieben, wird auf reduzierten Teilgraphen Bezug genommen!

### 2.2.1 Identifizierung der Cluster

[] Todo

### 2.2.2 Identifizierung der Knoten ohne Brücke zu **einem** Cluster

[] Todo

### 2.2.3 Plot des Teilgraphen

[] Todo

## 2.3 Eigenschaften

[] Todo


# 3. Schlussfolgerung

[] Todo

# 4. Aufwand

~ 2