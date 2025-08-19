# COVID-19 Report QA System  

This project is a **Question-Answering (QA) system** built on top of Malaysia’s COVID-19 Situation Reports. It extracts text from a PDF, splits it into chunks, creates embeddings using **Sentence Transformers**, indexes them with **FAISS**, and uses **Flan-T5** to generate answers. A **Gradio** interface is provided for easy interaction.  

##Features  
- Extract text from PDF reports using **PyPDF2**  
- Split text into manageable chunks for semantic search  
- Generate embeddings with **SentenceTransformers** (`all-MiniLM-L6-v2`)  
- Store and search embeddings using **FAISS** (vector database)  
- Retrieve relevant context for a query  
- Use **Google Flan-T5 Base** for text generation (answers)  
- Interactive web UI built with **Gradio**  

## Project Structure  
```
.
├── Question3TM.ipynb         # Main script with PDF parsing, embeddings, QA pipeline, and Gradio app. Run this on Jupyter Notebook
├── README.md        # Documentation
└── data/
    └── COVID19_sitrep_MYS_w-46--47.pdf   # pdf report used  to extract the text from.
```

##  Requirements  
Install dependencies:  
```
!pip -q install pypdf faiss-cpu sentence-transformers gradio transformers torch hf_xet
```

## Usage  

1. Place your PDF (e.g., `COVID19_sitrep_MYS_w-46--47.pdf`) inside the `data/` folder.  
2. Update the file path in the script (`pdf_path`).  
3. Run the script:  
   ```bash
   python main.py
   ```  
4. Open the Gradio link (local or public `share=True`) to start asking questions.  

##  Example Questions  
- *What was the total number of confirmed COVID-19 cases as of 27 November 2022?*  
- *Which two states had the highest 14-day positivity rates, and what were the rates?*  
- *What are the key findings in this report?*  
- *How many new cases were reported?*  

## How It Works Simplified  
1. **Extract PDF text** → Convrt pages into raw text.  
2. **Text chunking** → Break down text into smaller chunks.  
3. **Embedding & Indexing** → Each chunk is converted into a vector and stored in FAISS.  
4. **Context Retrieval** → Search FAISS for chunks relevant to the query.  
5. **Answer Generation** → Flan-T5 generates a response based on retrieved context.  
6. **User Interaction** → Ask questions through the Gradio UI.  
