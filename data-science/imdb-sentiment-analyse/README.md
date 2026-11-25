# 🎬 IMDb Sentiment-Analyse: Neuronales Netz vs. logistische Regression

Automatische Klassifikation von 50.000 IMDb-Filmkritiken in **positiv** oder **negativ**. Die Leitfrage: Bringt ein neuronales Netz bei Textklassifikation einen Vorteil gegenüber einem klassischen ML-Modell?

**Tech:** Python · pandas · scikit-learn · TensorFlow/Keras · matplotlib · seaborn
**Notebook:** [`sentiment_keras.ipynb`](sentiment_keras.ipynb)

---

## Daten

- [IMDB Dataset of 50K Movie Reviews](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews) (Kaggle), 25.000 positive und 25.000 negative Kritiken
- Wegen der Dateigröße (~66 MB) nicht im Repo enthalten. Zum Ausführen herunterladen und als `data/IMDB Dataset.csv` ablegen.

## Vorgehen

1. **Label Encoding:** `positive` → 1, `negative` → 0
2. **Text-Vektorisierung:** TF-IDF mit den 5.000 häufigsten Begriffen
3. **Train-Test-Split:** 80/20, stratifiziert
4. **Modell 1: Neuronales Netz (Keras)**
   - `Dense(64, relu)` → `Dense(1, sigmoid)`, Optimizer Adam, Loss Binary Crossentropy, 5 Epochen
5. **Modell 2: Logistische Regression (scikit-learn)** mit Standardparametern auf denselben TF-IDF-Vektoren

## Ergebnisse

| Modell | Accuracy (Testset, 10.000 Kritiken) |
|---|---|
| Neuronales Netz (Keras) | 0,886 |
| Logistische Regression | **0,893** |

- Beide Modelle liegen bei **knapp 89 %**. Die einfache logistische Regression ist sogar leicht besser.
- Der Trainingsverlauf des neuronalen Netzes zeigt **Overfitting**: Die Trainings-Accuracy steigt von Epoche 2 bis 5 von 0,91 auf 0,93, während der Validierungs-Loss bereits nach der ersten Epoche wieder ansteigt (0,25 → 0,29). Mehr Epochen helfen hier nicht.

## Fazit

- Auf TF-IDF-Vektoren liefern klassische Modelle bei Textklassifikation oft genauso gute Ergebnisse wie ein einfaches neuronales Netz und sind schneller und leichter zu erklären.
- Ein neuronales Netz spielt seine Stärken eher mit Modellen aus, die Wortreihenfolge und Kontext nutzen (z. B. LSTM, Transformer/BERT).

## Bekannte Einschränkungen

- Der TF-IDF-Vektorisierer wird auf dem **gesamten** Datensatz angepasst, also vor dem Split. Sauberer wäre es, ihn nur auf den Trainingsdaten anzupassen. Bei 50.000 Texten ist der Effekt gering, methodisch ist es aber ein kleines Leck.
- Das Testset dient beim neuronalen Netz zugleich als Validierungsset. Für eine saubere Bewertung bräuchte es ein separates Validierungsset (z. B. für Early Stopping).
- Beim `classification_report` der logistischen Regression sind die Argumente vertauscht (`y_pred, y_test`). Die Accuracy stimmt, Precision und Recall pro Klasse sind dadurch aber gegeneinander vertauscht.

## Weiterentwicklung

- Early Stopping bzw. Dropout gegen Overfitting
- Vortrainierte Sprachmodelle (z. B. BERT) als Vergleich
- Erklärbarkeit der Vorhersagen mit LIME oder SHAP

## Ausführen

```bash
pip install pandas scikit-learn tensorflow matplotlib seaborn jupyter
# Datensatz von Kaggle laden und als data/IMDB Dataset.csv ablegen
jupyter notebook sentiment_keras.ipynb
```
