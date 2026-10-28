# Cybersecurity Learning Assistant (RAG)

A beginner-friendly Streamlit chatbot that retrieves relevant passages from Markdown knowledge files and uses OpenRouter to generate grounded answers. The app displays the source filename and retrieved text for transparency.

## Features
- Loads every `.md` file in `knowledge_base/` automatically.
- Retrieval-augmented generation (RAG) with embeddings and cosine similarity.
- Shows the source excerpts used for each answer.
- Supports English and Roman Urdu responses.
- Focuses on defensive security, secure configuration, incident response, and authorized lab learning.
- Keeps API credentials in a local `.env` file (excluded from Git).

## Requirements
- Python 3.10 or newer
- An OpenRouter API key
- An OpenRouter chat model and an embeddings-compatible model enabled for your account

## Windows setup (PowerShell)

1. Extract the ZIP and open the `cybersecurity_rag_chatbot` folder in VS Code.
2. Open **Terminal → New Terminal**.
3. Create and activate a virtual environment:

   ```powershell
   py -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

   If PowerShell blocks activation, for this terminal session only run:

   ```powershell
   Set-ExecutionPolicy -Scope Process -ExecutionPolicy RemoteSigned
   .\.venv\Scripts\Activate.ps1
   ```

4. Install packages:

   ```powershell
   python -m pip install -r requirements.txt
   ```

5. Create your local `.env` file from the example:

   ```powershell
   Copy-Item .env.example .env
   ```

6. Open `.env` and replace the placeholder with your own OpenRouter API key. Keep the key private. Do not paste it into source code or upload `.env` to GitHub.
7. Start the chatbot:

   ```powershell
   streamlit run app.py
   ```

8. Open the local URL Streamlit prints, usually `http://localhost:8501`.

## Add your fifth Markdown knowledge file later

You do not need to edit Python code.

1. Save/download your fifth `.md` file on your computer.
2. In VS Code Explorer, right-click the `knowledge_base` folder and choose **Reveal in File Explorer** (or open that folder normally).
3. Copy the fifth `.md` file into `knowledge_base/`, beside the other four files. Keep the `.md` extension.
4. Stop Streamlit with `Ctrl+C` in the terminal.
5. Start it again with `streamlit run app.py`.
6. The app automatically loads all `.md` files in `knowledge_base/` and rebuilds embeddings on startup. This uses your configured embeddings API and may incur API usage costs.

You should then see **Loaded 5 Markdown knowledge files** in the sidebar. If it still says four, confirm the new file is directly inside `knowledge_base/` and ends in `.md`.

## Troubleshooting
- **Missing API key:** confirm `.env` exists next to `app.py` and the key is valid.
- **Embedding model error:** use an embeddings-compatible model available to your OpenRouter account, such as `openai/text-embedding-3-small` if available.
- **New Markdown file not loaded:** ensure it is inside `knowledge_base/`, then stop and restart Streamlit.
- **API errors/costs:** embeddings are created at startup and question embeddings are requested during retrieval. Check your OpenRouter usage and model access.

## Safety note
Use this assistant for learning and defensive security. Only assess systems you own or have explicit permission to test. The knowledge base is the primary source for source-grounded answers; the model may still make mistakes, so verify important security decisions.
