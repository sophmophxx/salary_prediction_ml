# Vorhersage von Gehaltsklassen in Stellenausschreibungen

Semesterarbeit im Data-Science-Modul

## Projektziel
Ziel des Projekts ist es, zu untersuchen, ob sich aus Merkmalen von Stellenanzeigen ein Gehaltsniveau mit Machine Learning vorhersagen lässt. Da die verwendeten Stellenanzeigen meist keine direkten Gehaltsangaben enthalten, wird im Hauptsetup eine Proxy-Zielvariable verwendet. Zusätzlich wird eine alternative Datenquelle mit direkteren Gehaltsfeldern untersucht und mit dem Hauptansatz verglichen.

## Projektstruktur

- `00_business_understanding_and_project_structure.ipynb`  
  Business Understanding, Problemdefinition und Sprint-Planung

- `01_sprint_data_acquisition_and_exploration.ipynb`  
  Datenakquise über die API der Bundesagentur für Arbeit, Bereinigung und Exploration

- `02_sprint_proxy_target_construction.ipynb`  
  Verknüpfung mit externen Entgeltdaten und Konstruktion der Zielvariable `gehaltsklasse`

- `03_sprint_modeling_evaluation_and_reflection.ipynb`  
  Modellierung, Evaluation, Cross-Validation, Ablation und Fehleranalyse im BA-Setup

- `04_sprint_direct_salary_data_with_adzuna.ipynb`  
  Prüfung der Adzuna-API als alternative Datenquelle mit direkteren Gehaltsfeldern

- `05_sprint_comparison_and_adzuna_feasibility_model.ipynb`  
  Vergleich des BA- und Adzuna-Ansatzes sowie Machbarkeitstest mit Adzuna

- `07_final_documentation_project_summary.ipynb`  
  Abschließende Gesamtdokumentation des Projekts

## Datengrundlage
Das Projekt verwendet zwei Datenquellen:

1. Stellenanzeigen aus der Jobsuche-API der Bundesagentur für Arbeit  
2. Stellenanzeigen mit Gehaltsfeldern aus der Adzuna-API

Für das Hauptsetup werden die BA-Stellenanzeigen mit externen Entgeltdaten auf Ebene von Berufsgruppe und Region verknüpft. Daraus wird eine Proxy-Gehaltsklasse mit den Klassen `niedrig`, `mittel` und `hoch` erzeugt.

## Zentrale Ergebnisse
- Das BA-Setup liefert die stabilere Hauptlösung für das Projekt.
- Die Modelle übertreffen die Baseline deutlich.
- Die Ablation zeigt, dass ein großer Teil der Vorhersagekraft aus `beruf` und `region` stammt.
- Adzuna ist methodisch näher am eigentlichen Gehaltsproblem, war in diesem Projekt jedoch zu lückenhaft, um das BA-Setup zu ersetzen.

## Reproduzierbarkeit
Die Notebooks sind in Sprint-Reihenfolge aufgebaut und dokumentieren den vollständigen Projektverlauf.  
Für die Reproduzierbarkeit müssen die benötigten CSV-Dateien im `data`-Ordner liegen.  
API-Schlüssel wurden in den exportierten Versionen entfernt bzw. anonymisiert.

## Hinweis
Diese Arbeit verwendet im Hauptsetup keine direkt beobachteten individuellen Gehaltsangaben, sondern eine konstruierte Proxy-Zielvariable. Die Ergebnisse sind daher als Klassifikation eines geschätzten Gehaltsniveaus und nicht als exakte Gehaltsvorhersage zu interpretieren.
