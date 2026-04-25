[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23702494&assignment_repo_type=AssignmentRepo)
# Codelab 03: The Multi-Modal Minefield

**Student Name**: Nguyen Minh Hieu

**Student ID**: 2A202600180

**GithubName**: nmhieuhieuhieu

**Email**: minhhieutrumhoa1@gmail.com

**Team**: 1 member
**Topic**: Data Pipeline Engineering - Unstructured Data Orchestration

## Overview
In this lab, I acted as a full-stack Data Engineer to ingest messy, unstructured data from two different sources (PDFs and Videos), normalize it, and unify it into a single, high-quality Knowledge Base for an AI Agent.

This project focuses on **Schema Harmonization** and **Semantic Observability**.

## The Roles Fulfilled
I completed the tasks of all 4 roles in the `starter_code/` directory:

### 1. Lead Data Architect (`schema.py`)
- Defined the `UnifiedDocument` Pydantic model with fields: `document_id`, `source_type`, `author`, `category`, `content`, `timestamp`.
- Ensured both Group A (PDF) and Group B (Video) data fit into this schema.

### 2. ETL/ELT Builder (`process_unstructured.py`)
- Parsed the messy JSON outputs from the "OCR/Speech-to-Text" services.
- Translated varying key names into the unified schema.
- Cleaned up "noise" (e.g., removing `HEADER_PAGE_X` and `FOOTER_PAGE_X` from PDF text using Regex).

### 3. Observability & QA Engineer (`quality_check.py`)
- Wrote the "Quality Gates".
- Detected and filtered out extracted documents that contained very short content or corrupt content (e.g., "Null pointer exception", "OCR Error", "Traceback").

### 4. DevOps & Integration Specialist (`orchestrator.py`)
- Glued the entire pipeline together.
- Read data from `raw_data/`, passed it through processing and semantic checks, and output the final `processed_knowledge_base.json`.

## Instructions to Run
1. Navigate to the root directory.
2. Ensure you have installed the requirements: `pip install -r requirements.txt`.
3. Run `python starter_code/orchestrator.py` to execute the pipeline.
4. Run `python tests/test_lab.py` to run the automated grading suite.

**Final Score:** 100/100
