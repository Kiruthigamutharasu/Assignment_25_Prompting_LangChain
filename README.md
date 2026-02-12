

# Assignment 25 – Prompting and LangChain Implementation

## Overview

This assignment demonstrates practical implementation of prompt engineering and LangChain workflows using Ollama-based local language models. The notebook covers structured prompting, output parsing, conditional logic, parallel chains, LCEL pipelines, and Retrieval-Augmented Generation (RAG).


## Objectives

The following concepts are implemented and demonstrated:

1. PromptTemplate usage with dynamic variable injection
2. ChatPromptTemplate with role-based messaging
3. Structured output generation using Pydantic
4. Validation handling and safe parsing
5. LCEL-based chaining
6. Conditional routing logic
7. Parallel chain execution
8. Runnable pipelines
9. Retrieval-Augmented Generation (RAG) using FAISS
10. Observations and practical insights



## Technologies Used

* LangChain (core and community modules)
* LCEL (LangChain Expression Language)
* Ollama (local LLM execution)
* FAISS (vector database)
* Sentence Transformers (embeddings)
* Pydantic (structured schema validation)



## Model Configuration

The assignment was executed using locally hosted Ollama models:

* llama3.2:1b

Embeddings model:

* sentence-transformers/all-MiniLM-L6-v2

No external API (e.g., OpenAI) was used.



## Project Structure

```
Assignment_25_Prompting_LangChain/
│
├── assignment_25.ipynb
├── data/
│   └── sample.txt
├── requirements.txt
└── README.md
```



## Task Breakdown

### Task 0 – Environment Setup

* Configured Ollama LLM
* Initialized embedding model
* Imported required LangChain modules

### Task 1 – PromptTemplate

* Created dynamic prompt template
* Injected user input
* Generated model response

### Task 2 – ChatPromptTemplate

* Implemented role-based messaging
* Demonstrated structured conversational prompting

### Task 3 – Pydantic Structured Output

* Defined schema using Pydantic
* Integrated PydanticOutputParser
* Injected formatting instructions
* Demonstrated structured response attempt

### Task 4 – Validation Handling

* Implemented safe parsing logic
* Added fallback mechanism for schema mismatch
* Ensured application robustness

### Task 5 – LCEL Chain

* Created runnable pipeline using:
  PromptTemplate → LLM
* Demonstrated modern chain architecture

### Task 6 – Conditional Chain

* Implemented question-based routing logic
* Used chain for specific query types
* Used direct LLM invocation otherwise

### Task 7 – Parallel Chain

* Generated answer
* Generated summary
* Generated follow-up questions
* Demonstrated multi-output orchestration

### Task 8 – Runnable Basics

* Demonstrated RunnablePassthrough
* Showed functional LCEL chaining

### Task 9 – Retrieval-Augmented Generation (RAG)

* Loaded documents
* Split text into chunks
* Created FAISS vector store
* Built retriever
* Implemented RAG pipeline using RunnableMap



## RAG Implementation Details

The RAG pipeline follows:

1. Document loading (with fallback handling)
2. Text splitting using RecursiveCharacterTextSplitter
3. Embedding generation
4. FAISS vector index creation
5. Retriever integration
6. Prompt construction with contextual injection

Fallback handling ensures the notebook runs even if external files are missing.



## Key Learnings

* Small local models may not strictly follow structured output formats.
* Pydantic parsing requires validation safeguards.
* LCEL provides a cleaner and more modular alternative to deprecated LLMChain.
* Conditional routing improves flexibility in real-world applications.
* RAG significantly enhances factual grounding by injecting retrieved context.



## Execution Instructions

1. Install dependencies:

```
pip install -r requirements.txt
```

2. Ensure Ollama is running locally:

```
ollama run llama3.2:1b
```

3. Open the notebook:

```
jupyter notebook assignment_25.ipynb
```

4. Run all cells sequentially.



## Conclusion

This assignment demonstrates a complete LangChain workflow including prompt engineering, structured outputs, validation, chaining logic, and retrieval augmentation using modern best practices.

