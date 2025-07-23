# 📚 Semantic Book Recommender (RAG-Powered with Hugging Face)

This project is a **RAG-based (Retrieval-Augmented Generation)** semantic book recommender system. It takes **free-form natural language queries** from users, embeds them using a Hugging Face transformer model, and **retrieves semantically similar books** from a local vector database.

Books are then **ranked by emotion** (like joy, fear, sadness, etc.) and category to produce emotionally aligned, intelligent recommendations.

---

This system is a **lightweight, domain-specific RAG pipeline**

---

## 🔧 Features

- 🔎 **Semantic Querying**: Match queries with book summaries using vector embeddings.
- 💾 **Chroma Vector Store**: Locally stores book descriptions for fast similarity search.
- 🎯 **Emotion-Aware Recommendations**: Books are ranked by joy, fear, sadness, etc.
- 🧠 **RAG-based Retrieval Layer**: Core recommendation is powered by semantic retrieval.
- 💻 **Gradio Interface**: No frontend coding required — runs as a browser UI.

---

## 📁 Project Structure

<pre> ``` Semantic-Book-Recommender/ ├── app.py # Main Gradio app with RAG-style logic ├── tagged_description.txt # Book descriptions with identifiers ├── books_with_emotions.csv # Book metadata + emotion scores ├── cover-not-found.jpg # Placeholder image for missing thumbnails ├── requirements.txt # Python dependencies └── .env # (optional) dotenv config ``` </pre>

---

## 🚀 How It Works (RAG-style Flow)

1. **User Input**: You enter a query like _“a chilling dystopian novel with hope”_.
2. **Embedding Generation**: The system embeds your query using `sentence-transformers/all-MiniLM-L6-v2`.
3. **Document Retrieval**: It finds similar book summaries from `tagged_description.txt` stored in a **Chroma vector DB** using cosine similarity.
4. **Augmented Matching**: Emotion labels (joy, sadness, anger, etc.) and category filters (e.g., Fiction, Romance) are used to **refine the results**.
5. **Results**: You get thumbnail-rich, emotionally aligned recommendations with brief summaries and authors.

---

## Tech Stack

| Layer           | Tool/Library                              |
| --------------- | ----------------------------------------- |
| Embedding Model | `sentence-transformers/all-MiniLM-L6-v2`  |
| Vector DB       | `ChromaDB (FAISS backend)`                |
| RAG Framework   | Inspired by `LangChain` + semantic search |
| UI              | `Gradio`                                  |

