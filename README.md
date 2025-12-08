# Fact-Checking-Agent

A voice-enabled fact-checking agent that takes a spoken or typed claim, retrieves relevant evidence, and returns a fact-check verdict with a short, source-backed explanation.

The project aims to combine:

- A supervised classifier trained on public misinformation datasets (e.g. LIAR, LIAR-2)
- Retrieval-augmented generation (RAG) over news and fact-checking corpora
- Speech-to-text (STT) so users can speak claims directly
- A simple web UI for interactive demos

> Status: Early development. Repo currently focuses on project skeleton and environment setup.

---

## Planned Features

- Text input: type a short factual claim and receive:
  - A label (e.g. True / Mostly True / Mixed / Mostly False / False / Not Enough Info)
  - A short explanation
  - Links to supporting/contradicting sources
- Voice input: record a claim using your microphone, transcribed via STT
- Retrieval: retrieve relevant articles / fact-checks from a local corpus
- RAG reasoning: generate verdicts by combining retrieved evidence with an LLM
- Evaluation: benchmark on public misinformation datasets (e.g. LIAR, LIAR-2, CoAID, FakeNewsNet)

---

## Tech Stack (planned)

- **Language:** Python (3.10+)
- **Core:** `pandas`, `scikit-learn`, `sentence-transformers` or similar
- **STT:** Whisper or equivalent speech-to-text model
- **RAG / LLM:** API-based or local LLM backend
- **Web UI:** Streamlit or Gradio

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/Fact-Checking-Agent.git
cd Fact-Checking-Agent
```

### 2. Create and Activae a Python Environment

You can use the built-in venv module (recommended for a simple setup).
Using venv (Windows)

```bash
# From the project root
py -3 -m venv .venv

# Activate the virtual environment
.\.venv\Scripts\activate
```
Using venv (macOS / Linux)

```bash
# From the project root
python3 -m venv .venv

# Activate the virtual environment
source .venv/bin/activate
```

### 3. Install Dependencies

Once the environment is active:

```bash
pip install --upgrade pip

# When requirements.txt is added:
pip install -r requirements.txt

```
Until requirements.txt is finalised, you can install packages incrementally as they are introduced into the codebase.

Planned Project Structure

This structure is indicative and will be filled in as development progresses:

```Fact-Checking-Agent/
  data/
    raw/          # Original datasets (not committed)
    processed/    # Cleaned / transformed data (not committed)
  models/         # Saved models / checkpoints (ignored by git)
  index/          # Vector indexes for retrieval (ignored by git)
  logs/           # Application and evaluation logs (ignored by git)
  src/
    __init__.py
    config.py
    data_prep.py
    features.py
    classifier.py
    retriever.py
    rag_reasoner.py
    stt.py
    tts.py
    app.py        # Streamlit/Gradio UI
  notebooks/
    01_eda_liar.ipynb
    02_train_classifier.ipynb
  docs/
    architecture.md
    references.md
  .gitignore
  README.md
  requirements.txt
```
Note: data/, models/, index/, and logs/ will typically be listed in .gitignore to avoid committing large or sensitive files.

Datasets (planned)

This project is intended to use the following public datasets for training and evaluation:

LIAR: “Liar, Liar Pants on Fire: A New Benchmark Dataset for Fake News Detection.”

LIAR-2: A multimodal extension of LIAR for fine-grained fake news detection.

CoAID: COVID-19 healthcare misinformation dataset.

FakeNewsNet: Repository of news content with social context and temporal information.

Exact dataset usage, splits, and preprocessing steps will be documented in [docs/datasets.md] and [docs/references.md] as the project develops.
