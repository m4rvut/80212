# Pumpenanalyse – Strömungsmaschinen Zusatzaufgabe 80212

## Projektbeschreibung
Dieses Repository beinhaltet die Auswertung von Betriebsdaten einer industriellen Wasserpumpe mit einem 269 mm Laufrad. Das Verhalten der Anlage wird technisch undauch wirtschaftlich betrachtet. 

## Enthaltene Dateien
* `volume_flow_data.csv`: Die rohen Messdaten der Sensoren (Volumenstrom und Zeitstempel).
* `Kennlinie_Pumpe`: Datenblatt des Pumpenherstellers. (Vorsicht! auf französisch)
* `Pump_Analysis.ipynb`: Das Jupyter Notebook, welches die vollständige Berechnung, Datenbereinigung und grafische Auswertung enthält.

## Methodik und Berechnungen
Das Skript führt vollautomatisch folgende Schritte durch:

1. **Datenaufbereitung mit Glättung:** Da die Sensordaten große Schwankungen enthalten, wurde zusätzlich der gleitende Mittelwert berechnet (15-Minuten-Fenster). Durch diesen werden die Daten geglättet und der Betriebstrend besser sichtbar gemacht zur Visualisierung.
2. **Technische Auswertung:** Basierend auf der interpolierten Herstellerkennlinie werden für jeden Messpunkt die Förderhöhe und der Wirkungsgrad ermittelt. Daraus berechnet sich die elektrische Leistungsaufnahme, die hydraulische Nutzleistung und schließlich die ungenutzte Verlustenergie in Kilowattstunden (kWh).
3. **Wirtschaftliche Auswertung:** Um die Ineffizienz zu verdeutlichen, werden die Energiewerte mit einem angenommenen Industriestrompreis (0,15 € / kWh) multipliziert. So wird exakt aufgeschlüsselt, welche Kosten durch tatsächliche Nutzung und welche durch Verluste entstehen.

## Grafische Auswertung
Zur besseren Nachvollziehbarkeit generiert der Code fünf Diagramme:
* **Volumenstrom-Verlauf:** Gegenüberstellung der rohen Sensordaten und des geglätteten Trends.
* **Histogramm:** Darstellung der Häufigkeit einzelner Betriebspunkte.
* **H-Q-Kennfeld:** Abgleich der real gemessenen Betriebspunkte mit der theoretischen Herstellerkennlinie.
* **Leistungsvergleich:** Visualisierung von Stromaufnahme, Nutzleistung und den dazwischenliegenden Verlusten über den Tag.
* **Kostenverlauf:** Ein Flächendiagramm, das die stündlichen Stromkosten in Nutz- und Verlustkosten unterteilt.

## Ausführung des Codes
Der Code wurde mit Google Colab erstellt.
1. Die Datei `Pump_Analysis.ipynb` herunterladen oder direkt in Google Colab öffnen.
2. Die beiliegende Datei `volume_flow_data.csv` in das Dateiverzeichnis (`/content/sample_data/`) von Google Colab hochladen.
3. Die Code-Zellen im Notebook nacheinander von oben nach unten ausführen.
