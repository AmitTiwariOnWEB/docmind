# DocMind – AI-Powered Document Intelligence Platform

## Overview

DocMind is an AI-powered document intelligence platform designed to simplify the process of understanding, searching, and extracting information from large documents.

The platform allows users to upload documents such as PDF files and interact with their content through natural language conversations. Instead of manually searching through multiple pages, users can ask questions and receive relevant, context-aware answers based on the information available in their uploaded documents.

DocMind uses **Retrieval-Augmented Generation (RAG)** to retrieve relevant information from documents and provide it as context to an AI language model. This helps generate answers that are grounded in the uploaded content rather than relying only on the model's general knowledge.

The platform also provides semantic search, conversational interactions, document management, and source citations to make document analysis more efficient and user-friendly.

---

## Key Features

### 1. Document Upload and Management

DocMind provides an interface for uploading and managing documents.

- Upload individual documents.
- Upload multiple documents.
- Support for PDF and other supported document formats.
- View uploaded documents and their processing status.
- Access document information and metadata.
- Delete documents when they are no longer required.

### 2. Automatic Document Processing

Once a document is uploaded, DocMind automatically processes its contents to prepare them for AI-powered searching and question answering.

The processing workflow includes:

- Extracting text from uploaded documents.
- Supporting PDF parsing and other document formats through document parsing libraries.
- Dividing large amounts of text into smaller sections called chunks.
- Associating metadata with each chunk, including document information and source details.
- Generating numerical representations of text called embeddings.
- Storing the generated embeddings for efficient information retrieval.

This process makes large documents easier to search and analyze.

### 3. AI-Powered Question Answering

Users can ask questions about the content of their uploaded documents using natural language.

For example:

- What is this document about?
- Summarize the main points.
- What are the key technical skills mentioned in this resume?
- Explain a particular topic discussed in the document.
- Find information related to a specific subject.

The platform retrieves relevant document content and uses an AI language model to generate meaningful responses based on the retrieved information.

### 4. Retrieval-Augmented Generation (RAG)

DocMind uses Retrieval-Augmented Generation (RAG) to connect document search with AI-generated responses.

The RAG workflow consists of three major stages:

**Retrieval**

When a user asks a question, the system searches the stored document embeddings to identify the most relevant text chunks.

**Augmentation**

The retrieved text chunks are added to the question as contextual information.

**Generation**

The AI language model processes the question along with the retrieved context and generates a relevant response.

This approach helps the application answer questions using information from uploaded documents.

### 5. Semantic Search

DocMind supports semantic search to identify information based on meaning and context rather than relying only on exact keyword matches.

The platform converts document chunks and user questions into vector embeddings.

These embeddings are compared using similarity search to identify relevant document sections.

This allows users to find related information even when their questions use different words from the original document.

### 6. Source Citations and References

DocMind provides source references alongside AI-generated responses.

These references help users identify the document and relevant sections from which the information was retrieved.

Citation information can include:

- Source document name.
- Document identifier.
- Relevant chunk information.
- Page number, where available.
- Retrieved text snippets.

This makes it easier to review the original document and verify the information used in an answer.

### 7. Conversational AI Chat

DocMind provides a conversational interface that allows users to interact with their documents through follow-up questions.

Users can:

- Ask questions about uploaded documents.
- Continue conversations with follow-up questions.
- Receive context-aware AI responses.
- View previous conversations.
- Continue working with existing chat sessions.

The platform maintains conversation history to support ongoing interactions.

### 8. Chat Memory and Conversation History

The application supports conversation memory to maintain context across multiple messages.

Previous conversation messages can be retrieved and used as context when generating subsequent responses.

This helps users ask follow-up questions without repeating all the information from earlier messages.

Conversation information is persisted using the application's database-backed chat memory functionality.

### 9. Streaming AI Responses

DocMind supports streaming responses for AI-powered conversations.

Instead of waiting for the complete response to be generated, users can receive response content progressively as it becomes available.

This improves the responsiveness of the conversational experience, especially when processing longer answers.

### 10. User Authentication and Security

DocMind includes user authentication functionality to provide access to the platform.

Features include:

- User registration.
- User login.
- Password hashing.
- JWT-based authentication.
- Protected application endpoints.
- User-specific document retrieval and filtering.

Authentication and authorization mechanisms help protect access to application resources.

---

## Document Processing Workflow

The document processing pipeline prepares uploaded files for semantic search and AI-powered question answering.

1. **Document Upload:** The user uploads a document through the application.
2. **Text Extraction:** The backend extracts readable content from the document.
3. **Text Chunking:** The extracted content is divided into smaller text sections.
4. **Metadata Enrichment:** Information such as document ID, filename, user ID, and chunk details is associated with the extracted sections.
5. **Embedding Generation:** Each text chunk is converted into a numerical vector representation.
6. **Vector Storage:** The generated embeddings and associated metadata are stored for future retrieval.
7. **Document Indexing:** Once processing is successful, the document becomes available for semantic search and question answering.

---

## Question Answering Workflow

When a user submits a question, DocMind follows a retrieval and generation workflow.

1. The user submits a natural language question.
2. The system generates an embedding representation of the question.
3. Semantic similarity search identifies relevant document chunks.
4. Relevant results are retrieved using configured retrieval parameters and applicable document/user filters.
5. The retrieved content is added to the AI prompt as contextual information.
6. The AI language model generates a response using the supplied context.
7. The application returns the generated answer along with available source citations.

---

## Technology Stack

### Frontend

- React
- TypeScript
- Vite
- Tailwind CSS
- Zustand
- Axios
- React Router

### Backend

- Java 21
- Spring Boot
- Spring AI
- Spring Security
- Spring Data JPA
- Maven

### Database and Vector Search

- PostgreSQL
- pgvector
- HNSW Vector Indexing
- Cosine Distance Similarity Search

### Artificial Intelligence

- OpenAI API
- OpenAI Embedding Model
- Large Language Models (LLMs)
- Retrieval-Augmented Generation (RAG)
- Semantic Search
- Conversational AI

### Document Processing

- Apache Tika
- PDF Parsing
- Token-Based Text Chunking
- Document Metadata Extraction

### Development Tools

- Docker
- Docker Compose
- Git
- GitHub

---

## Application Modules

DocMind is organized around the following functional modules:

| Module | Responsibility |
|---|---|
| Authentication | User registration and login |
| Document Management | Uploading, viewing, and deleting documents |
| Document Parsing | Extracting text from supported files |
| Document Ingestion | Chunking content and generating embeddings |
| Vector Search | Retrieving semantically relevant document sections |
| RAG Processing | Combining retrieved context with AI generation |
| AI Chat | Handling document-related conversations |
| Chat Memory | Maintaining conversation context and history |
| Citation Management | Providing references to retrieved document content |

---

## Project Goal

The primary goal of DocMind is to make information stored in large documents more accessible through natural language interaction.

By combining document processing, semantic search, vector databases, and generative AI, DocMind provides an interactive way to explore documents, discover relevant information, and obtain context-aware answers without manually reading every page.

**DocMind transforms static documents into searchable, conversational knowledge sources.**
