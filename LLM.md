

#Watch the demonstration video of the project below:

[![Watch the video](https://img.youtube.com/vi/JYtwnbCWCHA/0.jpg)](https://www.youtube.com/watch?v=JYtwnbCWCHA)

Click the image to watch the video on YouTube.


# Research Paper Question-Answering System with References

This repository contains the implementation details of a Retrieve-Augment-Generate (RAG) pipeline designed to answer questions based on a collection of thousands of brain-related research papers. The system provides highly relevant answers along with references to the specific research papers and page numbers from which the information was extracted. The pipeline also incorporates re-ranking and metadata generation to enhance the accuracy and relevance of responses.

---

## Features

- **Question-Answering System**: Accepts user queries and returns precise answers.
- **Reference Linking**: Includes references to the research paper, page number, and a direct link to the document.
- **Metadata-Enhanced Retrieval**: Uses metadata to improve the relevance of retrieved results.
- **Re-Ranker Integration**: Reranks retrieved results to ensure the highest relevance.
- **Self-Hosted Model**: Uses a self-hosted Mixtral AI for in-house deployment.

---

## Pipeline Overview

### 1. **Data Preparation**
- **Input**: A collection of thousands of research papers (PDFs).
- **Output**: Indexed document repository with metadata.
- **Steps**:
  1. **PDF Parsing**:
     - Extract text and images from PDFs.
     - Tools used: `PyPDF2`, `pdfplumber`, `PDFMiner`.
  2. **Metadata Generation**:
     - Extract titles, authors, abstracts, keywords, and section headers.
     - Tools used: `spaCy`, custom NLP scripts.
  3. **Document Indexing**:
     - Break down documents into smaller chunks (e.g., sections or paragraphs).
     - Assign unique identifiers for each chunk (e.g., document ID, page number).
     - Tools used: `LangChain`, `FAISS`, `Pinecone`.

### 2. **Retrieval-Augmented Generation (RAG)**
- **Input**: User query.
- **Output**: Answer with references.
- **Steps**:
  1. **Query Understanding**:
     - Process the query using a transformer-based model for better understanding.
     - Tools used: `Hugging Face Transformers` (e.g., BERT, T5).
  2. **Document Retrieval**:
     - Use a vector similarity search to retrieve the most relevant document chunks.
     - Tools used: `FAISS`, `Pinecone`.
  3. **Metadata Filtering**:
     - Leverage metadata (e.g., keywords, authors, topics) to filter irrelevant results.
     - Custom metadata indexing and filtering logic.

### 3. **Re-Ranking**
- **Purpose**: Reorder the retrieved results to ensure the highest relevance.
- **Steps**:
  1. **Candidate Scoring**:
     - Score the retrieved chunks based on query-document similarity.
     - Tools used: `Cross-Encoders` (e.g., MiniLM, RoBERTa-based rerankers).
  2. **Top-K Selection**:
     - Retain the top-ranked chunks for the final generation step.

### 4. **Answer Generation**
- **Purpose**: Generate a human-readable answer from the retrieved content.
- **Steps**:
  1. **Context Concatenation**:
     - Combine the top-ranked chunks into a coherent context.
     - Tools used: `LangChain`.
  2. **LLM-Based Generation**:
     - Use Mixtral AI (self-hosted) to generate answers based on the context.
     - Tools used: Self-hosted `Mixtral AI` or equivalent open-source LLMs.

### 5. **Reference Linking**
- **Purpose**: Provide detailed references with the answer.
- **Steps**:
  1. **Mapping References**:
     - Map generated answers back to the source document IDs and page numbers.
  2. **Reference Formatting**:
     - Include references as links, citing the paper title, author, and page number.
     - Tools used: `Custom Python Scripts`.

### 6. **Deployment**
- **Purpose**: Make the system accessible to users.
- **Details**: This project was implemented at the Sudha Gopalakrishnan Brain Centre, IIT Madras, where it was deployed on secure internal servers. Due to institutional policies, the code and deployment specifics are not available for public use or local hosting.

---

## Technologies Used

### **Core Components**
- **Language Models**:
  - Self-hosted Mixtral AI for in-house deployment.
  - Hugging Face Transformers for query understanding and re-ranking.
- **Data Indexing and Search**:
  - FAISS for vector similarity search.
  - Pinecone for scalable vector database.
- **NLP Tools**:
  - spaCy for metadata extraction.
  - LangChain for retrieval and context handling.

### **Additional Tools**
- **PDF Processing**: PyPDF2, pdfplumber.
- **Web Framework**: Flask/FastAPI for the backend; React.js for the frontend.
- **Deployment**: Docker, Nginx for containerization and hosting.
- **Version Control**: Git for managing codebase.

---

## Disclaimer
This project was carried out at the **Sudha Gopalakrishnan Brain Centre, IIT Madras**. Due to confidentiality agreements and institutional policies, the source code and implementation details cannot be shared or reproduced outside the organization. However, the methodology and high-level pipeline details are shared here to provide insights into the work conducted.

---

## Contributions
Feel free to reach out with queries or suggestions for similar projects in other domains.

---

## License
This project is proprietary and adheres to the guidelines set by the Sudha Gopalakrishnan Brain Centre, IIT Madras. Unauthorized use, reproduction, or distribution is prohibited.






# Professional Experience - NeuroVoyager at SGBC, IIT Madras

## AI/ML Engineer
### Brain Research Platform Development

#### AI/ML Development 
- Implemented Data Base Query Engine for natural language interaction with brain research data
- Built NeuroGuardrails system using NemoGuardrails and Meta-Llama-Guard-2-8B for query safety
- Developed Analytics Generator for brain region statistics and visualization
- Integrated with NVIDIA DGX3 infrastructure for high-performance computing

#### Platform Features
- **Database Query Engine**: Natural language interface for querying brain research data
- **NeuroGuardrails**: Safety system for filtering unsafe/irrelevant queries
- **Analytics Generator**: Statistical analysis of brain regions and visualization

#### Technologies Used
- **AI/ML**: Meta-Llama-Guard-2-8B, NemoGuardrails, VLLM
- **Infrastructure**: NVIDIA DGX3

#### Achievements
- Presented NeuroVoyager at IIT Madras Student Fest Paradox 2024
- Received weekly guidance and support from NVIDIA

