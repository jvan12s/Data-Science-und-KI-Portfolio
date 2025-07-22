# 📊 IMDb Sentiment Analysis – Abschlussbericht

Dieses Projekt behandelt die **automatische Sentiment-Klassifikation von IMDb-Filmkritiken** (positiv oder negativ). Ziel war es, den Einsatz eines **einfachen neuronalen Netzes (Keras)** mit einem **klassischen Machine-Learning-Modell (logistische Regression mit scikit-learn)** zu vergleichen.

---

## 🧠 Zielsetzung

Ziel des Projekts war die Beantwortung der Frage:  
> **Wie stark unterscheiden sich ein einfaches neuronales Netz und ein klassisches ML-Modell bei der Textklassifikation anhand von IMDb-Kritiken?**

---

## 🛠️ Verwendete Bibliotheken

- [`pandas`](https://pandas.pydata.org/) – Datenverwaltung und -vorverarbeitung  
- [`scikit-learn`](https://scikit-learn.org/) – Datenaufteilung, TF-IDF-Vektorisierung, Label-Encoding, logistisches Regressionsmodell  
- [`tensorflow` / `keras`](https://www.tensorflow.org/) – Aufbau und Training des neuronalen Netzes  
- [`matplotlib`](https://matplotlib.org/) & [`seaborn`](https://seaborn.pydata.org/) – Visualisierungen

---

## 🧹 Datenvorbereitung & Preprocessing

1. **Datenimport & Cleaning**:
   - Laden der IMDb-Daten
   - Entfernen unnötiger Felder
2. **Label Encoding**:
   - Zielvariable „Stimmung“ (positiv = 1, negativ = 0)
3. **Text-Vektorisierung**:
   - Transformation des Textes in numerische Vektoren mit `TfidfVectorizer`
4. **Train-Test-Split**:
   - Aufteilung im Verhältnis 80/20 mit **stratifizierter Verteilung** zur Wahrung der Klassenbalance

---

## 🧠 Modellarchitektur & Training

### 🔹 Neuronales Netz (Keras)

- Architektur:  
  - `Dense(64, activation='relu')`  
  - `Dense(1, activation='sigmoid')`
- Optimizer: `Adam`  
- Loss: `BinaryCrossentropy`  
- Training: `5 Epochen`, standardmäßige Batch Size

### 🔸 Logistische Regression (scikit-learn)

- Klassisches ML-Modell ohne tieferes Hyperparameter-Tuning
- Nutzung des default `LogisticRegression()`-Objekts auf TF-IDF-Vektoren

---

## 📈 Evaluation & Ergebnisse

| Modell                  | Accuracy |
|-------------------------|----------|
| Neuronales Netz (Keras) | **0.8900** |
| Logistische Regression  | **0.8929** |

- Beide Modelle erreichen eine sehr gute Genauigkeit (~89 %)
- Die **logistische Regression ist leicht besser**, obwohl das neuronale Netz grundsätzlich flexibler ist

---

## 🖼️ Visualisierung

- **Trainingsverlauf (Loss & Accuracy)** mit `matplotlib`
- **Vorhersageverteilung** mittels `seaborn` als Balkendiagramm
- Fokus auf **Accuracy** als Hauptmetrik

Beispielgrafiken:
- Trainingsverlauf als Liniengrafik
- Histogramm der Klassenvorhersagen

---

## 🧾 Fazit

- Klassische Modelle wie **logistische Regression** liefern bei der **Textklassifikation mit TF-IDF**-Vektoren oft **sehr starke Ergebnisse**.
- Tiefe neuronale Netze **sind nicht immer notwendig**, vor allem bei kleinen / mittleren Textdatenmengen.
- Für viele Probleme im NLP („Natural Language Processing“) lohnt sich frühzeitig ein **Modellvergleich verschiedener Klassen**.

---

## 🚀 Weiterentwicklung

- **Fortschrittlichere Architekturen** (z. B. LSTM, CNNs) ausprobieren
- **Pre-trained Embeddings** (z. B. Word2Vec, GloVe, BERT)
- **Größere Datensätze** für das volle Potenzial neuronaler Modelle nutzen
- Einbindung von **Explainability Tools** (z. B. SHAP, LIME)

