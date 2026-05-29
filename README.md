# Pumpenanalyse – Strömungsmaschinen Zusatzaufgabe 80212

## Beschreibung
Dieses Repository enthält die Auswertung einer industriellen Wasserpumpe (Laufraddurchmesser: 269 mm) für die Zusatzaufgabe im Fach Strömungsmaschinen. 

## Inhalt
* `volume_flow_data.csv`: Bereitgestellte Messdaten des Volumenstroms.
* `Pump_Analysis.ipynb`: Jupyter Notebook mit dem Python-Code.

## Funktionen des Codes
* **Technische Analyse:** Berechnung von elektrischem Gesamtverbrauch (kWh), Verlustenergie (kWh) und der durchschnittlichen Effizienz (%).
* **Wirtschaftliche Analyse:** Berechnung der Stromkosten und der Kosten durch Ineffizienz (Basis: 0,15 €/kWh).
* **Glättung:** durch einen gleitenden 15-Minuten-Mittelwert.
* **Visualisierung:** Erstellung von 5 Diagrammen (Volumenstrom, Histogramm, H-Q-Kennfeld, Leistungsvergleich und Kostenverlauf).

## Anleitung zur Ausführung
Zur Erstellung wurde Google Colab verwendet. 
1. Die Datei `Pump_Analysis.ipynb` herunterladen und in Google Colab öffnen.
2. Die Datei `volume_flow_data.csv` in den `content/sample_data/`-Ordner von Google Colab hochladen.
3. Alle Code-Zellen nacheinander ausführen.
