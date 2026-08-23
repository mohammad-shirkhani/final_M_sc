## Data Preparation & Preprocessing

This section contains the notebooks and scripts used to prepare and preprocess the HotpotQA and 2WikiMultiHopQA datasets. To simulate a realistic open-domain environment, the code maps the dataset questions to a large, fixed corpus of full Wikipedia pages rather than relying on a limited set of pre-selected paragraphs. It ensures the text is cleaned, deduplicated, and properly formatted for the chunking and retrieval stages.

---

## Benchmark Models

This directory implements all the reference methods used to evaluate the primary approach. It includes simpler setups like zero-shot LLM generation and lexical BM25, standard single-step Dense RAG, and advanced multi-hop reasoning frameworks such as CuriousLLM, PyRAG, and LogicRAG. Each section contains its own retrieval, generation, and evaluation scripts to measure metrics like F1 score, Exact Match, and LLM-as-a-judge accuracy.

---

## Core Framework Implementation

This is the heart of the research, implementing the agent-driven, knowledge graph-based system for multi-document Q&A. The scripts handle the offline construction of a heterogeneous knowledge graph by extracting entities, relations, and facts into FAISS and BM25 indexes. It also includes the online traversal agent, which uses hybrid retrieval and beam search to dynamically navigate the graph, gather a minimal yet sufficient set of supporting evidence, and generate highly grounded, traceable answers.

---

## Component Analysis & Testing

This section is dedicated to testing the individual impact and necessity of various components within the developed architecture. It contains modified scripts to run experiments that disable specific retrievers, remove the new entity discovery branch during middle hops, or restrict the beam search parameters like branching factor and search depth.
