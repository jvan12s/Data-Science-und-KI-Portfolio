# 🩺 Herzkrankheit-Klassifikation: Logistische Regression vs. Random Forest

Kann man anhand klinischer Messwerte vorhersagen, ob eine Herzkrankheit vorliegt? Und lohnt sich dafür ein komplexes Modell, oder reicht ein erklärbares? Das Projekt vergleicht beide Ansätze und dokumentiert einen typischen Fallstrick: **Data Leakage durch Duplikate**.

**Tech:** Python · pandas · scikit-learn · matplotlib · seaborn
**Notebook:** [`herzkrankheit_klassifikation.ipynb`](herzkrankheit_klassifikation.ipynb)

---

## Fragestellung

- Wie gut lässt sich die Zielvariable (`target`: 1 / 0) mit einer **logistischen Regression** und mit einem **Random Forest** vorhersagen?
- Welches Modell ist für einen medizinischen Kontext empfehlenswert, in dem Entscheidungen **nachvollziehbar** sein müssen?

## Daten

- 13 klinische Merkmale, z. B. Alter, Brustschmerz-Typ (`cp`), Ruhe-Blutdruck, Cholesterin, maximale Herzfrequenz (`thalach`), belastungsinduzierte Angina (`exang`)
- Quelle: Kaggle-Version des [UCI Heart Disease Datensatzes](https://archive.ics.uci.edu/dataset/45/heart+disease) (CC BY 4.0), im Repo unter [`data/heart.csv`](data/heart.csv)
- **1.025 Zeilen, davon nur 302 eindeutig.** 723 Zeilen sind exakte Duplikate.

## Vorgehen

1. **Datenprüfung:** fehlende Werte (keine), **Duplikate (723) entfernt**
2. **Explorative Analyse:** Korrelationen, Heatmap, Verteilung der stärksten Merkmale
3. **Vorverarbeitung:** Standardisierung der numerischen und ordinalen Merkmale. Der Scaler wird in einer Pipeline nur auf den Trainingsdaten angepasst.
4. **Modellierung:** logistische Regression und Random Forest auf demselben stratifizierten 80/20-Split
5. **Evaluation:** Accuracy, Precision/Recall, ROC-AUC, Konfusionsmatrix, Permutation Importance und zusätzlich eine **5-fache Kreuzvalidierung**, weil ein Testset mit 61 Fällen allein stark schwankt

## Ergebnisse

| Modell | Accuracy | ROC-AUC | Recall (target = 1) |
|---|---|---|---|
| Logistische Regression | **0,84** ± 0,03 | **0,91** ± 0,02 | **0,88** ± 0,11 |
| Random Forest | 0,83 ± 0,03 | 0,91 ± 0,01 | 0,85 ± 0,07 |

*Mittelwert ± Standardabweichung über 5 Folds.*

**Empfehlung: logistische Regression.** Sie ist genauso leistungsfähig wie der Random Forest und dabei erklärbar. Die Koeffizienten zeigen direkt, welches Merkmal das Ergebnis in welche Richtung verschiebt.

## 💡 Lessons Learned: Wie aus 99 % realistische 84 % wurden

In der ersten Version dieses Projekts erreichte der Random Forest **ca. 99 % Accuracy**. Bei der Überarbeitung zeigte sich die Ursache:

- 723 der 1.025 Zeilen waren Duplikate.
- Dadurch kamen **199 von 205 Testfällen auch im Trainingsset vor**. Das Modell wurde an Daten geprüft, die es bereits auswendig kannte.
- Ein Random Forest kann Trainingsdaten nahezu perfekt „auswendig lernen“ und profitierte deshalb besonders von diesem Leck.

Nach dem Entfernen der Duplikate liegen beide Modelle gleichauf. Zusätzlich behoben: Der Scaler wurde vorher auf dem gesamten Datensatz angepasst, die Argumente von `classification_report` waren vertauscht (Precision und Recall dadurch verwechselt), und die ROC-Kurve des Random Forest basierte auf 0/1-Vorhersagen statt auf Wahrscheinlichkeiten.

**Takeaway:** Ein auffällig gutes Ergebnis ist zuerst ein Anlass zur Prüfung, nicht zur Freude.

## Grenzen & nächste Schritte

- **Kleine Datenbasis** (302 Fälle): Ergebnisse sind als Tendenz zu verstehen.
- **Plausibilität der Zielvariable:** Eine höhere maximale Herzfrequenz erhöht hier die Wahrscheinlichkeit für `target = 1`, Belastungsangina senkt sie. Medizinisch spricht das dafür, dass `target = 1` in dieser Kaggle-Version eher „geringeres Risiko“ bedeutet. Vor einem echten Einsatz müsste die Kodierung mit der Originalquelle abgeglichen werden.
- **Erweiterungen:** Schwellenwert zugunsten eines höheren Recalls anpassen, Hyperparameter-Tuning, SHAP-Werte zur Erklärung einzelner Vorhersagen.

## Ausführen

```bash
pip install pandas scikit-learn matplotlib seaborn jupyter
jupyter notebook herzkrankheit_klassifikation.ipynb
```
