# SGBC LLM TEAM
A Reference-based RAG Chatbot for Brain Research

## Data Collection & Processing
- Collected and processed thousands of brain-related research papers
- Implemented chunking to break down research papers into smaller segments for improved semantic search performance

## Pipeline Components
1. **Metadata Extraction**
   - Extracts key information from papers for accurate source referencing

2. **Embedding Generation** 
   - Utilizes sentence transformers to create vector representations of research text
   - Enables semantic understanding of content

3. **Vector Database**
   - Leverages FAISS for efficient storage and retrieval of vector embeddings
   - Optimized for similarity search operations

4. **Semantic Search**
   - Performs similarity-based search to identify relevant paragraphs from research papers matching user queries
   - Enhanced with reranking to improve result quality

5. **Answer Generation**
   - Powered by Mixtral 8x7b model
   - Generates comprehensive responses with reference to retrieved sources
   - Includes source attribution and reference linking in final output