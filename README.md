# LangChain Practice Repository

A comprehensive learning repository for mastering **LangChain** and **Retrieval-Augmented Generation (RAG)** concepts. This project contains 30 Jupyter notebooks organized in a progressive learning sequence, from fundamental LLM API usage to building production-ready RAG systems.

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Environment Setup](#environment-setup)
- [Project Structure](#project-structure)
- [Learning Progression](#learning-progression)
- [Notebooks Guide](#notebooks-guide)
- [Getting Started](#getting-started)
- [Key Concepts](#key-concepts)
- [RAG Architecture](#rag-architecture)

---

## 🎯 Project Overview

This repository demonstrates:

- **Direct LLM API Integration** with OpenAI/Ollama
- **LangChain Fundamentals** - message types, prompts, and templating
- **Output Parsing** - structuring and extracting LLM responses
- **LCEL (LangChain Expression Language)** - composing complex workflows
- **RAG Implementation** - indexing, retrieval, and generation pipelines
- **Production Patterns** - batching, streaming, and optimization

**Target Audience:** AI engineers and ML practitioners learning LangChain ecosystem

---

## 🔧 Environment Setup

### Prerequisites

- **Python:** 3.10
- **Package Manager:** Conda
- **GPU Support (Optional):** For embedding models via Ollama

### Installation

1. **Clone or navigate to the repository:**

```bash
cd /Users/sakilkhan/Documents/Development/AI/AI_Engineer/langchain_practice
```

2. **Create and activate conda environment:**

```bash
# Create environment with Python 3.10
conda create -n langchain_practice python=3.10 -y

# Activate environment
conda activate langchain_practice
```

3. **Install dependencies:**

```bash
# Install LangChain and core libraries
pip install langchain langchain-openai langchain-community langchain-chroma

# Install document processing
pip install PyPDF2 python-docx pymupdf

# Install embedding and retrieval
pip install chromadb ollama

# Install additional utilities
pip install jupyter ipykernel

# Jupyter kernel registration (optional but recommended)
python -m ipykernel install --user --name langchain_practice --display-name "LangChain (Python 3.10)"
```

4. **Environment Variables:**

Create a `.env` file in the project root (recommended):

```bash
# OpenAI/Ollama Configuration
OPENAI_API_KEY=your_api_key_here
OLLAMA_BASE_URL=http://localhost:11434  # If using local Ollama

# Model Configuration
LLM_MODEL=mistral  # or llama2, neural-chat, etc.
EMBEDDING_MODEL=nomic-embed-text  # or all-minilm, etc.
```

---

## 📁 Project Structure

```
langchain_practice/
├── 1. openai_api/                          # OpenAI Direct API Usage (1 notebook)
├── 2. model_inputs/                        # LangChain Message Types & Prompts (6 notebooks)
├── 3. output_parser/                       # Response Parsing & Structuring (3 notebooks)
├── 4. lcel/                                # LangChain Expression Language (9 notebooks)
├── 5. rag/                                 # Retrieval-Augmented Generation (11 notebooks)
│   ├── Introduction-to-Data-and-Data-Science.pdf
│   ├── Introduction-to-Data-and-Data-Science.docx
│   ├── Introduction-to-Data-and-Data-Science-2.docx
│   └── intro-to-ds-lectures/              # Sample data for RAG examples
├── .env                                    # Environment configuration (create this)
├── .gitignore                              # Git ignore file
├── README.md                               # This file
└── .vscode/                                # VS Code settings
```

**Total:** 30 Jupyter notebooks (.ipynb) + supporting documents

---

## 📚 Learning Progression

The repository follows a **bottom-up learning progression**:

```
Layer 1: Foundation
├─ OpenAI API (Direct LLM calls)
└─ Model Inputs (Messages & Templating)
         ↓
Layer 2: Prompt Engineering & Output
├─ Few-shot Learning (in-context examples)
└─ Output Parsers (Structured responses)
         ↓
Layer 3: Composition & Orchestration
└─ LCEL (Piping, Parallel, Streaming, Batching)
         ↓
Layer 4: Advanced Applications
└─ RAG (Complete knowledge-augmented systems)
```

---

## 📖 Notebooks Guide

### 1️⃣ OpenAI API (1 notebook)

**Direct LLM API Integration**

| Notebook                     | Focus                                                 |
| ---------------------------- | ----------------------------------------------------- |
| Creating a Sarcastic Chatbot | OpenAI client usage, streaming, temperature & seeding |

**Concepts:** Direct API calls, streaming responses, model parameters

---

### 2️⃣ Model Inputs (6 notebooks)

**LangChain Message Types & Prompt Engineering**

| #   | Notebook                               | Focus                                                     |
| --- | -------------------------------------- | --------------------------------------------------------- |
| 2.1 | Chat OpenAI                            | LangChain ChatOpenAI wrapper, Ollama integration          |
| 2.2 | System and Human Messages              | SystemMessage, HumanMessage, role-based prompting         |
| 2.3 | AI Messages                            | AIMessage, multi-turn conversations, context building     |
| 2.4 | Prompt Templates and Prompt Values     | PromptTemplate, variable substitution, reusable templates |
| 2.5 | Chat Prompt Templates                  | ChatPromptTemplate, role-specific templates               |
| 2.6 | Few-Shot Chat Message Prompt Templates | FewShotChatMessagePromptTemplate, in-context learning     |

**Key Concepts:**

- Message types: SystemMessage, HumanMessage, AIMessage
- Template variables and dynamic prompts
- Few-shot learning for behavior guidance
- Message composition for complex conversations

---

### 3️⃣ Output Parser (3 notebooks)

**Structuring & Parsing LLM Responses**

| #   | Notebook                      | Focus                                            |
| --- | ----------------------------- | ------------------------------------------------ |
| 3.1 | String Output Parser          | StrOutputParser, basic text extraction           |
| 3.2 | Comma-Separated Output Parser | CommaSeparatedListOutputParser, list formatting  |
| 3.3 | Datetime Output Parser        | DatetimeOutputParser, structured date extraction |

**Key Concepts:**

- Format instructions in prompts
- Response parsing strategies
- Type-specific parsers (strings, lists, dates)
- Output validation and error handling

---

### 4️⃣ LCEL - LangChain Expression Language (9 notebooks)

**Building Complex Workflows with Composable Components**

| #   | Notebook                 | Focus                                              |
| --- | ------------------------ | -------------------------------------------------- |
| 4.1 | Piping a Prompt          | Pipe operator (\|), component chaining             |
| 4.2 | Batching                 | Batch processing multiple inputs efficiently       |
| 4.3 | Streaming                | Token-by-token streaming output                    |
| 4.4 | Runnable Passthrough     | Identity routing, variable passing                 |
| 4.5 | Graphing Runnables       | Visualizing chain structure and execution flow     |
| 4.6 | Runnable Parallel        | Parallel execution of independent chains           |
| 4.7 | Piping Runnable Parallel | Combining parallel outputs into sequential steps   |
| 4.8 | Runnable Lambda          | Wrapping custom Python functions as runnables      |
| 4.9 | The @chain Decorator     | Declarative chain definition with decorator syntax |

**Key Concepts:**

- **Pipe Operator (|):** `template | model | parser` composition
- **Execution Patterns:** Sequential, parallel, branching flows
- **Performance:** Batching, streaming, async execution
- **Debugging:** Chain visualization and tracing
- **Custom Logic:** Lambda functions and decorators

**Example LCEL Chain:**

```python
chain = (
    {"question": RunnablePassthrough()}
    | retriever  # Get context
    | prompt_template  # Format for LLM
    | model  # Call LLM
    | output_parser  # Parse response
)

# Use it:
result = chain.invoke("What is RAG?")
results = chain.batch(["Query 1", "Query 2"])
for token in chain.stream("Query"):
    print(token, end="", flush=True)
```

---

### 5️⃣ RAG - Retrieval-Augmented Generation (11 notebooks)

**Complete Knowledge-Augmented LLM Systems**

#### Phase 1: Indexing (5 notebooks)

| #   | Notebook                 | Focus                           | Libraries                  |
| --- | ------------------------ | ------------------------------- | -------------------------- |
| 5.1 | Document Load - PyPDF    | PDF text extraction             | PyMuPDFLoader              |
| 5.2 | Document Load - DOCX2TXT | Word document processing        | Docx2txtLoader             |
| 5.3 | Character Text Split     | Chunking by character count     | CharacterTextSplitter      |
| 5.4 | Markdown Header Split    | Semantic splitting by hierarchy | MarkdownHeaderTextSplitter |
| 5.5 | Ollama Embedding         | Vector embeddings generation    | OllamaEmbeddings           |

**Concepts:**

- Document loading from multiple formats
- Smart chunking strategies (overlap, separators)
- Semantic preservation through metadata
- Embedding generation and similarity metrics

#### Phase 2: Storage (1 notebook)

| #   | Notebook           | Focus                           |
| --- | ------------------ | ------------------------------- |
| 5.6 | Chroma Vectorstore | Persistent vector DB management |

**Concepts:**

- Vectorstore creation and persistence
- CRUD operations on indexed documents
- Similarity indexing and retrieval optimization

#### Phase 3: Retrieval (3 notebooks)

| #   | Notebook                         | Focus                            |
| --- | -------------------------------- | -------------------------------- |
| 5.7 | Similarity Search                | Semantic document ranking        |
| 5.8 | Maximal Marginal Relevance (MMR) | Relevance + diversity balancing  |
| 5.9 | Vectorstore-Backed Retriever     | Standardized retriever interface |

**Concepts:**

- Vector similarity search (cosine, dot product)
- Diversity in retrieval results
- Filtering and metadata-based retrieval
- Standardized retriever patterns for LCEL

#### Phase 4: Generation (2 notebooks)

| #    | Notebook             | Focus                          |
| ---- | -------------------- | ------------------------------ |
| 5.10 | Stuffing Documents   | Context injection into prompts |
| 5.11 | Generating Responses | End-to-end RAG pipeline        |

**Concepts:**

- Context window management
- Prompt engineering with retrieved documents
- Complete RAG chain composition
- Quality and latency optimization

**RAG Pipeline Diagram:**

```
Query
  ↓
[Retriever] ← Vectorstore (Chroma)
  ↓ (retrieved documents + query)
[Prompt Template] ← System prompt
  ↓ (formatted prompt with context)
[LLM] (OpenAI/Ollama)
  ↓ (response)
[Output Parser]
  ↓
Answer with Citations
```

---

## 🚀 Getting Started

### Option 1: Run Individual Notebooks

```bash
# Start Jupyter Lab
jupyter lab

# Or Jupyter Notebook
jupyter notebook

# Navigate to desired notebook and run cells
```

### Option 2: Run from Command Line

```bash
# Run a specific notebook
jupyter nbconvert --to notebook --execute --inplace "1. openai_api/1. creating_a_sarcastic_chatbot.ipynb"
```

### Recommended Learning Order

**Phase 1: Fundamentals (Start here)**

1. `1. openai_api/creating_a_sarcastic_chatbot.ipynb`
2. `2. model_inputs/chat_openai.ipynb`
3. `2. model_inputs/system_and_human_messages.ipynb`

**Phase 2: Prompting & Output** 4. `2. model_inputs/prompt_templates_and_prompt_values.ipynb` 5. `2. model_inputs/chat_prompt_templates_and_chat_prompt_values.ipynb` 6. `3. output_parser/string_output_parser.ipynb`

**Phase 3: Composition** 7. `4. lcel/piping_a_prompt.ipynb` 8. `4. lcel/batching.ipynb` 9. `4. lcel/streaming.ipynb`

**Phase 4: Advanced** 10. `4. lcel/runnable_parallel.ipynb` 11. `4. lcel/runnable_lambda.ipynb`

**Phase 5: RAG (Capstone)** 12. `5. rag/indexing_document_load_pypdf.ipynb` 13. `5. rag/indexing_char_text_split.ipynb` 14. `5. rag/indexing_chroma_vectorstore.ipynb` 15. `5. rag/retrieval_similarity_search.ipynb` 16. `5. rag/generation_response.ipynb` (Complete RAG pipeline)

---

## 🔑 Key Concepts

### Core Abstractions

| Concept       | Purpose                              | Example                                         |
| ------------- | ------------------------------------ | ----------------------------------------------- |
| **Message**   | Container for conversational content | SystemMessage, HumanMessage, AIMessage          |
| **Runnable**  | Executable component in LCEL         | LLM, Retriever, Prompt Template                 |
| **Chain**     | Composition of runnables             | `template \| llm \| parser`                     |
| **Retriever** | Interface for knowledge lookup       | Vectorstore-backed retriever                    |
| **Parser**    | Response structuring                 | StrOutputParser, CommaSeparatedListOutputParser |

### LCEL Operations

```python
# Piping: Sequential composition
chain = component1 | component2 | component3

# Parallel: Simultaneous execution
parallel = RunnableParallel({"output1": chain1, "output2": chain2})

# Passthrough: Identity and variable routing
passthrough = RunnablePassthrough()

# Lambda: Custom Python functions as runnables
custom = RunnableLambda(lambda x: x.upper())

# Batch: Process multiple inputs efficiently
results = chain.batch([input1, input2, input3])

# Stream: Token-by-token output
for token in chain.stream(input):
    print(token, end="", flush=True)
```

### RAG Concepts

| Concept          | Definition                                                    |
| ---------------- | ------------------------------------------------------------- |
| **Indexing**     | Converting documents to embeddings and storing in vectorstore |
| **Retrieval**    | Finding relevant documents using semantic search              |
| **Augmentation** | Incorporating retrieved context into prompts                  |
| **Generation**   | Using LLM to answer based on augmented prompt                 |
| **Chunking**     | Splitting documents into manageable pieces                    |
| **Embedding**    | Converting text to vector representations                     |

---

## 🏗️ RAG Architecture

### Complete RAG System

```
┌─────────────────────────────────────────────────────┐
│                  INDEXING PHASE                      │
│  (Run once, typically offline/batch)                │
├─────────────────────────────────────────────────────┤
│                                                     │
│  Documents → Load → Split → Embed → Store           │
│   (PDF,      PyPDF  Text   Ollama  Chroma          │
│    DOCX)    Docx2txt Split        Vectorstore      │
│                                                     │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│                 RETRIEVAL PHASE                      │
│        (Run for each query, real-time)              │
├─────────────────────────────────────────────────────┤
│                                                     │
│  Query → Embed → Search → Retrieve (top-k)         │
│         Ollama Chroma  Similarity or MMR           │
│                     Vector DB                       │
│                                                     │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│                  GENERATION PHASE                    │
│              (Real-time response)                    │
├─────────────────────────────────────────────────────┤
│                                                     │
│  Query + Context → Format → LLM → Parse → Answer   │
│                   Prompt  OpenAI/  Output          │
│                  Template Ollama   Parser          │
│                                                     │
└─────────────────────────────────────────────────────┘
```

### Data Flow Example

```
User Query: "What is data science?"
    ↓
[Retrieve] Find related documents from Chroma
    ↓
Context: "Data science combines statistics, programming, ..."
    ↓
[Format] Create prompt:
    System: "You are a helpful assistant"
    User: "Based on: {context}, answer: {query}"
    ↓
[Generate] LLM processes formatted prompt
    ↓
Response: "Data science is the practice of..."
```

---

## 📦 Dependencies

### Core LangChain Libraries

- `langchain` - Core framework
- `langchain-openai` - OpenAI integration
- `langchain-community` - Community integrations
- `langchain-chroma` - Chroma vectorstore support

### Document Processing

- `PyPDF2` - PDF reading
- `python-docx` - DOCX file support
- `pymupdf` - Enhanced PDF processing

### Embeddings & Vectorstore

- `chromadb` - Vector database
- `ollama` - Local LLM & embeddings

### Utilities

- `jupyter` - Notebook environment
- `ipykernel` - Jupyter kernel support

---

## 📝 Notes

- **Ollama Required:** Notebooks use Ollama for local LLM/embedding inference
- **Document Examples:** Sample PDFs and DOCX files in `5. rag/` directory
- **Vector DB:** Chroma data stored in `intro-to-ds-lectures/` directory
- **API Keys:** Modify `.env` or notebook cells for OpenAI API keys
- **Performance:** LCEL chains optimize for latency using streaming and batching

---

## 🎓 Learning Outcomes

After completing this repository, you will understand:

✅ How LLMs work and how to call them via APIs  
✅ LangChain fundamentals and message types  
✅ Prompt engineering techniques (templates, few-shot)  
✅ Output parsing and response structuring  
✅ LCEL for composing complex workflows  
✅ Building and optimizing LCEL chains  
✅ RAG architecture and implementation  
✅ Document processing and semantic search  
✅ Production patterns (batching, streaming)  
✅ End-to-end AI application development

---

## 📚 Additional Resources

- [LangChain Documentation](https://python.langchain.com/)
- [LangChain Expression Language (LCEL)](https://python.langchain.com/docs/expression_language/)
- [RAG Best Practices](https://python.langchain.com/docs/use_cases/question_answering/)
- [Ollama Models](https://ollama.ai/library)
- [Chroma Vectorstore](https://docs.trychroma.com/)

---

## 💡 Tips for Success

1. **Start Linear:** Follow the learning progression order
2. **Experiment:** Modify notebooks and try different parameters
3. **Run Locally:** Use Ollama for free GPU-accelerated inference
4. **Debug Chains:** Use `.get_graph().print_ascii()` to visualize workflows
5. **Profile Performance:** Compare batch, streaming, and sequential execution
6. **Extend:** Build your own RAG system with your own documents

---

## 🤝 Contributing

This is a personal learning repository. Improvements and corrections are welcome!

---

**Last Updated:** April 2026  
**Python Version:** 3.10  
**Environment:** Conda  
**Framework:** LangChain

Happy Learning! 🚀
