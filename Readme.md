# Green Finance Optimization Platform

This document explains the architecture and workflow of the Green Finance Optimization Platform. The platform is designed to analyze and rank green finance projects using environmental, social, and governance (ESG) scores, ensuring a transparent and data-driven approach to decision-making.

---

## System Components and Workflow

The system consists of four main modules:

### 1. **Ingestion**
   - **Purpose:** Collect reports and data from various sources such as government and NGO reports.
   - **Process:**
     - A Python-based web scraper hosted on AWS S3 gathers the required reports.
     - The collected data is stored on Amazon S3 for further processing.

### 2. **Data Warehouse**
   - **Purpose:** Serve as the central repository for all collected and processed data.
   - **Components:**
     - **Firebase Storage:** Used to store raw and processed data files.
     - **Firebase Realtime Database:** Serves as a NoSQL database for managing structured data.
   - **Data Flow:**
     - Data from AWS S3 is transferred to Firebase Storage.
     - Structured data is organized and stored in the Firebase Realtime Database.

### 3. **Analytics Engine**
   - **Purpose:** Extract, process, and analyze data to generate ESG scores.
   - **Process:**
     1. **Text and Data Extraction:**
        - Extract relevant information from collected reports.
     2. **LLM Inference:**
        - Use Large Language Models (LLMs) to process extracted data.
        - Perform reasoning and generate ESG estimations.
     3. **Output:** ESG scores for the analyzed projects.

### 4. **Visualization Engine**
   - **Purpose:** Present data insights and rankings to the end-users.
   - **Process:**
     - **Power BI:** Visualize ESG scores and related insights.
     - **Project Ranking System:** Use ESG scores to rank projects and display the results in an intuitive format.

---

## Data Flow and Communication
- **Mass Data Flow (Orange Arrows):** Used for transferring large datasets between the modules.
- **Internal Data Exchange (Green Arrows):** Handles communication between components within a module.

---

## Final Output
The platform provides:
- ESG scores for green finance projects.
- A ranking system that highlights top-performing projects based on ESG metrics.

---

## Technology Stack
- **AWS S3:** For initial data collection and storage.
- **Firebase:**
  - Storage for unstructured and structured data.
  - Realtime Database for NoSQL storage.
- **Power BI:** For creating interactive visualizations and dashboards.
- **Python:** For web scraping, data extraction, and integration.
- **LLMs:** For reasoning and ESG estimation.

---

## Architecture Diagram
![Architecture Diagram](image/architecture.png)

---

## Documentation
For more details, refer to the documentation:
- [AlphaScout.pdf](docs/Alphascout.pdf)

---

## Future Enhancements
- Incorporate more data sources for diverse insights.
- Use advanced AI models for better ESG estimations.
- Implement automation for the ingestion process.

---
