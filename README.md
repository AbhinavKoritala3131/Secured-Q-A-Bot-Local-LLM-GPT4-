# Secured-Q&A-Bot-Local-LLM
A local, offline solution for question-answering based on a large language model (LLM). This project does not rely on any online LLM APIs. Instead, it leverages GPT4All’s Meta-Llama-3-8B-Instruct.Q4_0.gguf model and HuggingFace’s all-MiniLM-L6-v2 Sentence Transformer embedder to provide high-quality answers to user queries.

# Our Approach
We are developing a fully local LLM application where all operations, including query processing and answer generation, take place on your local machine. We do not integrate any online LLM APIs. Instead, we use the GPT4All Meta-Llama-3-8B-Instruct.Q4_0.gguf model and HuggingFace’s all-MiniLM-L6-v2 Sentence Transformer embedder for processing the input queries and generating accurate answers.

# How It Works (Flow)
1. User Query Input:
The user types a question in the Streamlit UI.
2. Query Processing:
The input query is encoded into an embedding using the Sentence Transformer.
Relevant documents are retrieved from the FAISS index.
3. Context Preparation:
The relevant documents are combined into a "context" that helps provide a meaningful answer.
The context is then formatted into a prompt for the LLM.
4. Answer Generation:
The formatted prompt is sent to the GPT4All model (Meta-Llama-3-8B-Instruct.Q4_0.gguf).
The model generates an answer based on the provided context.
5. Output Display:
The generated answer is displayed in the Streamlit chat UI.
Citations for the answer are shown below the response to give the source of the information.
Access the Q&A Bot:
You can access the Q&A Bot locally at:
http://192.168.0.11:8501

# Installation
To run the Q&A Bot locally, follow these steps:

Step 1: Clone the repository
-> git clone https://github.com/your-repository/q-a-bot-local-llm.git
-> cd q-a-bot-local-llm '

Step 2: Set up a Virtual Environment
Create and activate a virtual environment:
-> python -m venv venv

For Windows:
-> venv\Scripts\activate

For macOS/Linux:
-> source venv/bin/activate

Step 3: Install Requirements
Install the necessary requirements:
-> pip install -r requirements.txt

Step 4: Run the Application
Once the requirements are installed, you can start the application using Streamlit:
-> streamlit run app.py

This will launch the Q&A Bot in your local browser at # http://192.168.0.11:8501.

# Usage
Enter your question in the Streamlit interface.
The query is processed and relevant information is retrieved from the FAISS index.
The GPT4All model generates a response based on the context.
The generated response is displayed with citations for the source of information.

# Requirements
streamlit: Framework for creating the web UI.
sentence-transformers: Library for generating text embeddings.
faiss-cpu: Efficient similarity search library for retrieving relevant documents.
gpt4all: Local large language model (LLM) for generating answers.
pymupdf: For reading PDF files and extracting text.
