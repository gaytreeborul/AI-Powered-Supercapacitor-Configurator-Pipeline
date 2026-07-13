# AI-Powered Electronic Component Data Extraction & Configurator

## Project Overview
This project involves the development of an automated, AI-driven data extraction pipeline designed to process electronic component datasheets (specifically supercapacitors). The system replaces manual data entry by utilizing Large Language Models (LLMs) to intelligently parse complex engineering PDFs, extract critical physical parameters, and populate a structured relational database. 

This clean data acts as the foundational layer for an AI-based hardware configurator engine that uses evolutionary algorithms to optimize component selection.

> **Note:** The source code for this project is proprietary to the company and cannot be shared publicly. This repository serves as an architectural overview and case study of the system designed and developed during this project.

## Architecture & Tech Stack
* **Language:** Python
* **AI / LLMs:**  Open-Source Local LLMs (Ollama), Prompt Engineering
* **Data Processing:** strict JSON parsing, PDF text extraction
* **Database:** MariaDB (SQL)
* **Optimization:** Genetic Algorithms (NSGA-II)
* **External Integrations:** Digikey API

## System Workflow

### 1. Data Ingestion & API Integration
* Automated the fetching of initial component metadata using the Digikey API.
* Engineered Python scripts to manage API rate limits and structure the raw incoming data for pipeline processing.

### 2. AI-Driven Parameter Extraction (The Middle Layer)
* Developed a pipeline that feeds complex, unstructured PDF datasheets into an LLM.
* Designed strict system prompts that force the LLM to output highly specific, standardized JSON structures.
* Successfully extracted key physical parameters (e.g., Capacitance, Voltage, ESR, Physical Dimensions, Operating Temperature ranges) from varying manufacturer formats.

### 3. Database Integrity & Management
* Designed an ingestion script to map the LLM-generated JSON directly into a MariaDB SQL database.
* Diagnosed and repaired database integrity issues, including resolving AUTO_INCREMENT gaps and re-sequentializing database IDs.
* Audited the database schema to ensure high-performance querying for the downstream configurator engine.

### 4. Component Optimization Engine
* Transitioned the workflow from static, traditional industry calculators to a predictive, AI-simulated hardware design model.
* The populated database feeds into a Genetic Algorithm (NSGA-II), allowing the system to automatically calculate and suggest the optimal combination of supercapacitors based on strict engineering constraints (e.g., cost, physical footprint, thermal limits).

## Key Achievements
* **Automated Data Entry:** Drastically reduced manual engineering hours by reliably extracting technical parameters via LLMs instead of manual datasheet review.
* **Structured Unstructured Data:** Successfully bridged the gap between non-deterministic AI models and strict relational databases by enforcing JSON structures.
* **Scalable Foundation:** Built a robust, clean database pipeline that successfully powers advanced evolutionary algorithms for automated hardware component selection.
