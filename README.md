# LangChain Text Splitters

A collection of examples demonstrating different text splitting techniques using LangChain. Text splitting is essential for processing large documents in LLM applications, RAG pipelines, and vector databases.

## Overview

This project showcases five different text splitting approaches:

| File | Splitter Type | Use Case |
|------|---------------|----------|
| `length_based.py` | CharacterTextSplitter | Split by character count (PDF documents) |
| `text_structure_based.py` | RecursiveCharacterTextSplitter | Smart splitting with multiple separators |
| `markdown_splitting.py` | RecursiveCharacterTextSplitter (Markdown) | Preserve markdown structure |
| `python_code_splitting.py` | RecursiveCharacterTextSplitter (Python) | Preserve code structure |
| `semantic_meaning_based.py` | SemanticChunker | Split by semantic similarity |

## Requirements

- Python 3.10+
- LangChain
- OpenAI API key (for semantic splitting)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/LangChain-Text-Splitters.git
   cd LangChain-Text-Splitters
   ```

2. Install dependencies:
   ```bash
   pip install langchain langchain-community langchain-experimental langchain-openai pypdf python-dotenv
   ```

3. Set up environment variables (for semantic splitting):
   ```bash
   # Create a .env file
   echo "OPENAI_API_KEY=your-api-key-here" > .env
   ```

## Usage

### 1. Length-Based Splitting
Splits text by a fixed character count. Good for simple documents.

```bash
python length_based.py
```

**Parameters:**
- `chunk_size`: Maximum characters per chunk (default: 200)
- `chunk_overlap`: Overlapping characters between chunks
- `separator`: Character to split on

### 2. Text Structure-Based Splitting
Recursively splits text using multiple separators (`\n\n`, `\n`, ` `, etc.).

```bash
python text_structure_based.py
```

### 3. Markdown Splitting
Preserves markdown structure (headers, lists, code blocks).

```bash
python markdown_splitting.py
```

### 4. Python Code Splitting
Preserves Python code structure (classes, functions, methods).

```bash
python python_code_splitting.py
```

### 5. Semantic Meaning-Based Splitting
Uses embeddings to split text by semantic similarity. Requires OpenAI API key.

```bash
python semantic_meaning_based.py
```

**Parameters:**
- `breakpoint_threshold_type`: Method to determine split points (`standard_deviation`, `percentile`, `interquartile`)
- `breakpoint_threshold_amount`: Sensitivity threshold

## Notes

- For `length_based.py`, ensure you have a `dl-curriculum.pdf` file in the project directory
- Adjust `chunk_size` and `chunk_overlap` based on your LLM's context window
- Semantic splitting provides the best results for mixed-topic documents but requires API calls

## License

MIT
