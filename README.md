# AI Medical Prescription Verifier - Prototype

This is a runnable prototype for the "AI Medical Prescription Verification" system.
It includes:
- FastAPI backend (`app.py`)
- Streamlit frontend (`ui.py`)
- Simple NER wrapper (`ner_model.py`) using a Hugging Face model
- Utility functions for RxNorm/openFDA lookups and mock interaction checks (`drug_utils.py`)

## How to run (local)

1. Create a virtual environment and install requirements:
```
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

2. Start the FastAPI backend:
```
uvicorn app:app --reload
```

3. In another terminal, start the Streamlit UI:
```
streamlit run ui.py
```

4. Open the Streamlit UI in your browser (typically http://localhost:8501) and use the app.

## Notes
- `ner_model.py` uses a public Hugging Face model for demo inference. For production you should fine-tune a clinical NER model with labelled prescriptions.
- Interaction checks are mocked in `drug_utils.py`. Replace with DrugBank or other licensed DDI sources for production use.
- openFDA and RxNav calls are live HTTP calls; ensure internet access when running locally.
