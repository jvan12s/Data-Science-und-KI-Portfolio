# IBM Watsonx RAG-Assistent mit Gradio & LangChain

Ein smarter Frage-Antwort-Assistent, der PDF-Dateien versteht – powered by Gradio, LangChain und IBM Watsonx-Modellen im RAG-Framework.

---

## Funktionsweise

1. **Datei-Upload:** Lade eine PDF hoch.
2. **Frage stellen:** Gib eine Frage ein, z.B. „Was steht im Fazit?“
3. **RAG-Workflow:**  
    - Das PDF wird zerlegt, vektorisiert und indiziert  
    - Das LLM sucht relevante Passagen  
    - Eine direkte, faktenbasierte Antwort wird generiert und angezeigt

---

## Architektur auf einen Blick

[Gradio-UI]
|
|--> [PDF-Dokument laden]
|
|--> [Text splitter & Chunking]
|
|--> [Embedding/Vektorisierung mit Watsonx]
|
|--> [Chroma-Vektordatenbank]
|
|--> [Retriever]
|
|--> [LangChain RetrievalQA Chain]
|
|--> [Antwort]

---

## Zentrale Libraries & Frameworks

### Gradio

- Open-Source-Framework für schnelle Web-Interfaces  
- Bereitstellung des Frontends: Datei-Upload & Chat-Eingabe  
- Kein Flask/Django-Aufwand; KI-Demos mit wenigen Zeilen Code

### LangChain

- Toolkit für komplexe KI-Anwendungen, gebaut für LLMs  
- Steuerung des Workflows:  
   - Dokument-Splitting  
   - Embedding-Infrastruktur  
   - Integration externer Sprachemodelle wie Watsonx  
   - Aufbau von QA-Chains mit Retriever

### RAG (Retrieval-Augmented Generation)

- KI-Antworten werden mit externem Wissen (aus PDF) angereichert  
- Funktionsweise:  
   - Retriever: Findet relevante Textstellen im Dokument mit Vektorsearch  
   - Generator (LLM): Formuliert eine natürliche Antwort auf Basis der gefundenen Quellen  
- Ziel: Präzise Antworten, weniger Halluzinationen

## Beispielanwendung

- PDF hochladen  
- Frage eingeben („Was steht über Data Science im Kapitel 2?“)  
- Antwort erscheint nach wenigen Sekunden mit Fakten direkt aus deinem Dokument unter Nutzung von IBM Watsonx-Foundation-Modellen
