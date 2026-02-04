# Course RAG Chatbot 🎓🤖

A Retrieval-Augmented Generation (RAG) system that allows users to ask questions about a video course and get exact video numbers and timestamps where the topic is taught.

## Problem
Long video courses make it hard to locate specific topics. This project enables semantic search over course transcripts and provides grounded answers using an LLM.

## Tech Stack
- Python
- OpenAI Whisper (speech-to-text)
- Ollama (LLaMA + bge-m3 embeddings)
- Scikit-learn (cosine similarity)
- Pandas, NumPy
- FFmpeg

## Pipeline
1. Convert videos to audio using FFmpeg
2. Transcribe audio with Whisper (Hindi → English supported)
3. Chunk subtitles into semantic segments
4. Generate embeddings using bge-m3
5. Perform similarity search using cosine similarity
6. Use LLM to generate contextual answers with timestamps

## Example Query
**Q:** Where is Flexbox taught in the course?  
**A:** Video 12, timestamp 08:30–14:10 (with explanation)

## Use Cases
- Students revising for exams
- Course creators building search assistants
- RAG and GenAI learning projects

## Learning Outcomes
- Built end-to-end RAG pipeline
- Hands-on experience with embeddings and semantic search
- Practical NLP + LLM integration

## Future Improvements
- Use FAISS or vector DB (Chroma/Pinecone)
- Web UI
- Multi-course support

## Pipeline Overview
Video Files
   ↓
Speech-to-Text (Whisper)
   ↓
Subtitle Chunking
   ↓
Embeddings (bge-m3)
   ↓
Vector Search (Cosine Similarity)
   ↓
LLM Answer (Grounded RAG Response)

## Architecture / Flow
```mermaid
graph TD
    A[Video Files] --> B[Speech-to-Text<br/>Whisper]
    B --> C[Subtitle Chunking]
    C --> D[Embeddings<br/>bge-m3]
    D --> E[Vector Search<br/>Cosine Similarity]
    E --> F[LLM Answer<br/>Grounded RAG Response]
