# Pumpenanalyse – Strömungsmaschinen Zusatzaufgabe 80212

## Projektbeschreibung
Dieses Repository beinhaltet die Auswertung von Betriebsdaten einer industriellen Wasserpumpe mit einem 269 mm Laufrad. Das Verhalten der Anlage wird technisch und auch wirtschaftlich betrachtet. 

## Enthaltene Dateien
* `volume_flow_data.csv`: Die rohen Messdaten der Sensoren (Volumenstrom und Zeitstempel).
* `Kennlinie_Pumpe.pdf`: Datenblatt des Pumpenherstellers. (Vorsicht! auf französisch)
* `Pump_Analysis.ipynb`: Das Jupyter Notebook, welches die vollständige Berechnung, Datenbereinigung und grafische Auswertung enthält.

## Methodik und Berechnungen
Das Skript führt vollautomatisch folgende Schritte durch:

1. **Datenaufbereitung:** Da die Sensordaten große Schwankungen enthalten, wurde zusätzlich der gleitende Mittelwert berechnet (15-Minuten-Fenster). Durch diesen werden die Daten geglättet und der Betriebstrend zur Visualisierung besser sichtbar gemacht.
2. **Technische Auswertung:** Basierend auf der interpolierten Herstellerkennlinie werden für jeden Messpunkt die Förderhöhe und der Pumpenwirkungsgrad ermittelt. Daraus berechnet sich die hydraulische Nutzleistung, die mechanische Wellenleistung und unter Einbezug des Motorwirkungsgrads (93,6 %) die tatsächliche elektrische Leistungsaufnahme. So werden die Energieverluste für Motor und Pumpe (in kWh) detailliert aufgeschlüsselt.
3. **Wirtschaftliche Auswertung:** Um die Ineffizienz zu verdeutlichen, werden die Energiewerte mit einem angenommenen Strompreis (0,15 € / kWh) multipliziert. So wird exakt aufgeschlüsselt, welche Kosten durch tatsächliche Nutzung und welche durch Verluste entstehen.

## Grafische Auswertung
Zur besseren Nachvollziehbarkeit generiert der Code acht Diagramme:
* **Volumenstrom-Verlauf:** Gegenüberstellung der rohen Sensordaten und des geglätteten Trends.
* **Histogramm:** Darstellung der Häufigkeit einzelner Betriebszustände.
* **H-Q-Kennfeld:** Abgleich der real gemessenen Betriebspunkte mit der theoretischen Herstellerkennlinie.
* **Leistungsvergleich:** Visualisierung von Stromaufnahme, Nutzleistung und den dazwischenliegenden Verlusten über den Tag.
* **Kostenverlauf:** Ein Flächendiagramm, das die stündlichen Stromkosten in Nutz- und Verlustkosten unterteilt.
* **Energiebilanz:** Ein Kreisdiagramm zur Darstellung der prozentualen Energieaufteilung
* **Spezifischer Energiebedarf:** Darstellung des Energieaufwands pro Kubikmeter (kWh/m³) im Vergleich zur Idealkurve, um den wirtschaftlichsten Betriebspunkt zu identifizieren.
* **Kumulierte Kosten:** Aufsummierung der gesamten Stromrechnung über den Messzeitraum, aufgeteilt in sinnvolle Ausgaben und reine Verlustkosten.

## Fazit und Interpretation der Ergebnisse
Die Auswertung der Messdaten lässt folgende Rückschlüsse auf das Betriebsverhalten der Anlage zu:

**1. Auslegung und Betriebsverhalten**
Im Messzeitraum arbeitet die Pumpe bei einem mittleren Volumenstrom von ca. 253 m³/h und einer Förderhöhe von rund 19,7 m. Damit trifft die Anlage im Durchschnitt den im Datenblatt geforderten Auslegungspunkt (250 m³/h). Der resultierende mittlere Pumpenwirkungsgrad von 69,6 % entspricht weitestgehend der Herstellervorgabe für diesen spezifischen Lastzustand (71,3 %).

**2. Systemverluste und Wirtschaftlichkeit**
Die Bilanzierung der Gesamtwirkungsgradkette zeigt, dass etwa 35 % der elektrischen Eingangsleistung in Form von Motor- und Hydraulikverlusten abgeführt werden. Bezogen auf die vorliegende Tagesmessung (ca. 24 h) resultiert daraus ein Verlustkostenanteil von rund 65 € pro Tag. Unter der Annahme eines kontinuierlichen Dauerbetriebs (24/7) summiert sich diese systembedingte Ineffizienz auf über 23.000 € pro Betriebsjahr.

**3. Energetische Effizienz und Ursache der Verluste**
Eine Analyse des spezifischen Energiebedarfs verdeutlicht, dass das  Optimum dieser Kreiselpumpe erst im Bereich von 350 bis 400 m³/h erreicht wird. Mit einem durchschnittlichen Betrieb bei 253 m³/h operiert die Anlage lediglich bei etwa 63 % ihres effizientesten Betriebspunktes.

## Ausführung des Codes
Der Code wurde mit Google Colab erstellt.
1. Die Datei `Pump_Analysis.ipynb` herunterladen oder direkt in Google Colab öffnen.
2. Die beiliegende Datei `volume_flow_data.csv` in das Dateiverzeichnis (`/content/sample_data/`) von Google Colab hochladen.
3. Die Code-Zellen im Notebook nacheinander von oben nach unten ausführen.

## Hinweis zur Darstellung auf GitHub
Beim Testen des Github Repository kam es vor, dass GitHub die Jupyter Notebook-Dateien (`.ipynb`) nicht direkt im Browser rendern kann und eine Fehlermeldung ausgibt. In diesem Fall stehen folgende Alternativen zur Verfügung:
* **Externe Ansicht (Jupyter nbviewer):** Die URL der fehlerhaften GitHub-Seite kopieren und auf [nbviewer.jupyter.org](https://nbviewer.jupyter.org/) einfügen.
* **Google Colab:** Die Datei via "Download raw file" herunterladen und direkt in Google Colab hochladen, um den Code betrachten und ausführen zu können.
* **Lokale Ansicht:** Das Repository klonen und die Datei in einer lokalen Umgebung (z. B. VS Code, JupyterLab) öffnen.
