Herzstillstand Vorhersage – Klassifikationsprojekt:

Projektbeschreibung:

In diesem Data-Science-Projekt wurde untersucht, ob es möglich ist, anhand medizinischer Merkmalsdaten vorherzusagen, ob Patient:innen in der Zukunft einen Herzstillstand (Cardiac Arrest) erleiden werden. Die Zielvariable im Datensatz gibt an, ob ein Patient betroffen ist (1) oder nicht (0).
Ziel war es, verschiedene Machine-Learning-Algorithmen zu vergleichen und praktische Empfehlungen auszusprechen, wie zuverlässig und nachvollziehbar eine solche Vorhersage für Mediziner:innen eingesetzt werden kann.

Inhalte des Projekts:

- Datenaufbereitung: Reinigung, Transformation und Analyse medizinischer Datensätze.

- Feature-Auswahl: Korrelationen und Zusammenhänge der Merkmale mit der Zielvariable analysieren.

- Modelltraining: Zwei Modelle wurden verglichen:
Logistische Regression
Random Forest

Bewertung: Beide Modelle wurden bezüglich Präzision und Praxistauglichkeit betrachtet.

Vorgehensweise
1. Datenanalyse & Featurereinigung
Prüfung auf fehlende Werte, fehlerhafte Einträge und Ausreißer.
Features auf ihre Relevanz bezüglich der Zielvariable geprüft (Korrelationen).

2. Modellierung

Logistische Regression:
Transparente, gut interpretierbare Methode. Orientiert sich an Korrelationen und erlaubt Rückschlüsse auf den Einfluss einzelner Merkmale.

Random Forest:
Komplexerer Ensemble-Algorithmus, der sehr hohe Genauigkeit (knapp 99 %) erreicht, jedoch wenig Einblick in die Entscheidungsfindung ermöglicht.

3. Bewertung der Modelle
<table>
<tr>
  <th>Modell</th>
  <th>Präzision (Accuracy)</th>
  <th>Interpretierbarkeit</th>
  <th>Empfehlung</th>
</tr>
<tr>
  <td>Logistische Regression</td>
  <td>ca. 80 %</td>
  <td>Sehr gut</td>
  <td>Praktisch vorteilhaft für medizinische Einsätze</td>
</tr>
<tr>
  <td>Random Forest</td>
  <td>ca. 99 %</td>
  <td>Gering (Black Box)</td>
  <td>Maximale Leistung, aber schwer nachvollziehbar</td>
</tr>
</table>
  
Random Forest erzielt eine fast perfekte Präzision, ist aber weniger gut erklärbar.

Die logistische Regression hat eine etwas niedrigere, aber immer noch gute Genauigkeit. Sie ist jedoch besser verständlich, da ihre Gewichtungen direkt den Einfluss der Merkmale auf das Risiko erklären.

Fazit
Für medizinische Entscheidungen, in denen Transparenz und Vertrauenswürdigkeit besonders wichtig sind, empfiehlt sich meist die Verwendung der logistischen Regression. Kommt es ausschließlich auf höchste Trefferquoten bei der Risikoeinschätzung an, kann der Random Forest ebenfalls eine sinnvolle Wahl sein.

