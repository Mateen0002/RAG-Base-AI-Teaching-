# RAG-Based AI Teaching Assistant

This project is an end-to-end **Retrieval Augmented Generation (RAG)** based AI Teaching Assistant designed to answer course-related questions using video lecture content.

The system processes educational videos, converts them into text, intelligently chunks the content, generates vector embeddings, and retrieves the most relevant lecture segments to produce **accurate, context-aware answers** using a local Large Language Model (LLM).

The assistant behaves like a real teaching assistant by guiding users to the **exact video number and timestamps** where a topic is taught.

---

## Why This Project?

- Helps students quickly revise concepts from long video courses
- Avoids manual searching across multiple lectures
- Works completely **offline** after initial setup
- Demonstrates real-world usage of **RAG + LLMs**
- Built with scalability in mind for any course content

---

## System Architecture & Workflow

The project follows a structured RAG pipeline:

1. **Video → Audio** conversion  
2. **Audio → Text** transcription using Whisper  
3. **Text Chunking** with timestamps  
4. **Chunk Merging & Cleaning** to remove noise  
5. **Text → Vector Embeddings**  
6. **User Query → Vector**  
7. **Similarity Search (Cosine Similarity)**  
8. **Prompt Construction**  
9. **LLM Response Generation (Ollama)**  

This ensures accurate retrieval and reliable answers.

---

## How to Use This RAG AI Teaching Assistant on Your Own Data

### Step 1 – Collect Course Videos
Place all your lecture video files inside the `video/` folder.

### Step 2 – Process Videos and Run RAG Pipeline
Convert videos to audio, transcribe audio to text, merge and clean chunks, generate embeddings, and run the RAG pipeline using the following commands:

### Step 2 – Process Videos and Run RAG Pipeline

```bash
python video_to_mp3.py
python mp3_to_json.py
python merge_chunk.py
python main.py
```

**User Query:**  
> Where is the box model taught?

**Assistant Response:**  
> The CSS Box Model is explained in **Video 18**, between **00:40 and 02:20**, where margin, padding, and borders are discussed in detail.


##  Technologies Used
- Python
- Whisper (Speech-to-Text)
- Ollama (Local LLM Inference)
- bge-m3 (Text Embeddings)
- Pandas & NumPy
- Scikit-learn (Cosine Similarity)
- Joblib (Embedding Storage)

## Offline Capability

- Models are downloaded only once
- Fully functional without internet connection
- Suitable for low-connectivity environments
- All inference runs locally using Ollama


## Project Structure

RAG base AI/
│
├── audio/
├── chunk_json/
├── group_json/
│
├── video_to_mp3.py
├── mp3_to_json.py
├── merge_chunk.py
├── main.py
│
├── embeddings.joblib
├── prompt.txt
├── response.txt
└── README.md

## Future Improvements

- Web-based UI (Streamlit / FastAPI)
- Vector database integration (FAISS)
- Multi-language support
- Automatic topic detection
- Student progress tracking

## Author
**Mateen Ajmat**  
Final-Year Computer Science Engineering Student  
Specialization: AI, Machine Learning & Data Analytics

## License
This project is licensed under the MIT License.
