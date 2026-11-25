# Data Science & KI Portfolio

Hallo, ich bin Jan 👋 – Wirtschaftsinformatiker und Associate Consultant Data Analytics aus Bonn.

Beruflich arbeite ich an Datenselektionen und Kampagnenmanagement im CRM-Umfeld (SAS Viya, SQL). In diesem Repository zeige ich Projekte aus den Bereichen **Machine Learning**, **NLP** und **KI-Agenten/Automatisierung**, die ich neben dem Beruf umgesetzt habe.

🌐 Mehr über mich: [cv.jvan12s.work](https://cv.jvan12s.work)

---

## Projekte

### 🤖 KI-Anwendungen & Agenten

| Projekt | Worum geht's? | Tech-Stack |
|---|---|---|
| [**Recherche-Agent (Telegram → Notion)**](ki-anwendungen/n8n-recherche-agent) | Thema per Telegram schicken, der Agent recherchiert mit Perplexity und legt eine strukturierte Notion-Seite an | n8n, Groq (Qwen3-32B), Perplexity, Notion API, Telegram |
| [**RAG-Agent mit Vektordatenbank**](ki-anwendungen/n8n-rag-agent) | Chat-Agent beantwortet Fragen auf Basis eines PDF-Dokuments, inkl. Chunking nach Abschnitten und Reranking | n8n, Pinecone, Cohere Embeddings & Reranker, Groq |
| [**News-Agent**](ki-anwendungen/n8n-news-agent) | Erstellt jeden Morgen um 7 Uhr eine HTML-Nachrichtenübersicht (DE/International) und verschickt sie per E-Mail | n8n, Groq (Qwen3-32B), Perplexity, Gmail |
| [**RAG-PDF-Assistent in Python**](ki-anwendungen/rag-pdf-assistent-python) | Frage-Antwort-App für hochgeladene PDFs mit Gradio-Oberfläche (Projekt aus dem IBM Data Science Professional Certificate) | Python, LangChain, Chroma, IBM watsonx, Gradio |

### 📊 Data Science & Machine Learning

| Projekt | Worum geht's? | Tech-Stack |
|---|---|---|
| [**Herzkrankheit-Klassifikation**](data-science/herzkrankheit-klassifikation) | Logistische Regression vs. Random Forest: Data Leakage durch Duplikate erkannt und behoben, Modellvergleich per Kreuzvalidierung | Python, pandas, scikit-learn, seaborn |
| [**IMDb Sentiment-Analyse**](data-science/imdb-sentiment-analyse) | Klassifikation von 50.000 Filmkritiken: neuronales Netz (Keras) vs. logistische Regression auf TF-IDF | Python, scikit-learn, TensorFlow/Keras |

---

## Schwerpunkte

- **Machine Learning:** Klassifikation, Modellvergleich, Evaluation (Kreuzvalidierung, ROC-AUC), Erkennen von Data Leakage
- **NLP & LLMs:** TF-IDF, Retrieval-Augmented Generation (RAG), Embeddings, Reranking, Prompt Design
- **KI-Automatisierung:** Agenten-Workflows mit n8n, Tool-Anbindung (Perplexity, Notion, Telegram, Gmail, Google Drive)
- **Daten & Analytics im Beruf:** SAS Viya, SQL, Databricks, Power BI

---

<details>
<summary>🇬🇧 <b>English summary</b></summary>

I'm Jan, a business informatics graduate working as an Associate Consultant in Data Analytics (CRM campaign management, SAS Viya, SQL) based in Bonn, Germany. This repository collects side projects in **machine learning**, **NLP** and **AI agents/automation**:

- **AI agents (n8n):** a Telegram-to-Notion research agent, a RAG chat agent backed by Pinecone with Cohere reranking, and a daily news briefing agent.
- **RAG PDF assistant (Python):** LangChain + IBM watsonx + Gradio (project from the IBM Data Science Professional Certificate).
- **Heart disease classification:** logistic regression vs. random forest, including detecting and fixing data leakage caused by duplicate rows.
- **IMDb sentiment analysis:** Keras neural network vs. logistic regression on TF-IDF features.

Project documentation is written in German.
</details>
