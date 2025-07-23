# 🩺 Herzstillstand-Vorhersage – Abschlussbericht (Data Science Projekt)

## 📌 Projektbeschreibung

In diesem Data-Science-Projekt wurde untersucht, ob es durch maschinelles Lernen möglich ist, **Herzstillstände (Cardiac Arrest)** bei Patient:innen zuverlässig vorherzusagen.  
Die zugrunde liegenden medizinischen Daten enthalten verschiedene Messgrößen und Merkmale. Die **Zielvariable** gibt an, ob ein Patient oder eine Patientin in der Zukunft von einem Herzstillstand betroffen sein wird (`1`) oder nicht (`0`).

### 🎯 Zielsetzung

- Entwicklung und Vergleich zweier Klassifikationsmodelle.
- Analyse der **Praxistauglichkeit und Interpretierbarkeit** dieser Modelle in medizinischem Kontext.
- Formulierung einer Empfehlung für Mediziner:innen zur **anwendbaren Risikoeinschätzung** basierend auf ML-Techniken.

---

## 🧾 Projektinhalt

### ✅ Datenaufbereitung

- **Reinigung der Daten**: Behandlung fehlender Werte, fehlerhafter Einträge und Ausreißer.
- **Transformation**: Einheitliche Skalierung und Typisierung der Variablen.
- **Explorative Datenanalyse (EDA)**: Statistik, Histogramme, Korrelationen, Zielverteilung.

### 🧠 Feature Engineering

- Untersuchung von Zusammenhängen der Merkmale zur Zielvariable.
- Ausschluss unbrauchbarer und irrelevanter Variablen.
- Visualisierung der wichtigsten Korrelationen.

---

## 🤖 Modellierung

Zwei verschiedene Klassifikationsalgorithmen wurden getestet und bewertet:

### 1. Logistische Regression

- **Beschreibung**: Einfache, erklärbare Methode für binäre Klassifikation.
- **Vorteile**:
  - Gut interpretierbar (Merkmalsgewichtungen)
  - Transparente Entscheidungsregeln
- **Nachteile**:
  - Begrenzte Modellkomplexität
- **Erzielte Genauigkeit**: **ca. 80 %**

### 2. Random Forest

- **Beschreibung**: Komplexes Ensemble-Modell (viele Entscheidungsbäume).
- **Vorteile**:
  - Sehr hohe Genauigkeit
  - Robust gegenüber Ausreißern und Korrelationen
- **Nachteile**:
  - Kaum interpretierbar („Black Box“)
- **Erzielte Genauigkeit**: **ca. 99 %**

---

## 🧪 Modellvergleich

| Modell               | Präzision   | Interpretierbarkeit     | Empfehlung                                           |
|----------------------|-------------|--------------------------|------------------------------------------------------|
| Logistische Regression | ca. 80 %  | Sehr gut                 | Ideal für medizinische Anwendungen mit Fokus auf Nachvollziehbarkeit |
| Random Forest          | ca. 99 %  | Gering („Black Box“)     | Maximale Erkennungsleistung bei reduzierter Transparenz |

📝 **Interpretation:**

- Die Logistische Regression erlaubt **direkte Rückschlüsse auf Einflussfaktoren**.
- Der Random Forest erzielt extrem hohe Werte, eignet sich jedoch weniger für **erklärbare medizinische Entscheidungen**.

---

## 🧠 Fazit & Empfehlung

Für Anwendungen in der Medizin, wo **Transparenz, Erklärbarkeit und Vertrauenswürdigkeit** entscheidend sind, **empfiehlt sich die Logistische Regression**.

Wenn jedoch die **höchste Modellperformance** (Accuracy) im Vordergrund steht – etwa bei datengetriebener Risikoanalyse – kann der **Random Forest** ebenso sinnvoll sein.

---

## 🔄 Weiterentwicklung

- Kombination beider Modelle: Logistische Regression zur Begründung, Random Forest zur Validierung.
- Einsatz erklärbarer KI-Methoden wie **SHAP** für Random Forest Interpretationen.
- Erweiterung des Datensatzes mit **Langzeitverläufen** oder **klinischen Zusatzdaten**.
