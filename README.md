# Student Affairs Analysis for UET

Welcome to the **Student Affairs Analysis** project! This repository contains a Jupyter Notebook that dives deep into the `Quries_in_English.csv` dataset, providing insights into student affairs processes at the University of Engineering and Technology (UET), Lahore. From obtaining Detailed Marks Certificates (DMCs) to degree issuance, fee structures, and hostel inquiries, this project uncovers patterns in student queries. Additionally, it leverages **Word2Vec** and **GloVe** models to explore semantic relationships in the dataset, paving the way for applications like a UET chatbot or knowledge base.

## 🎯 Project Purpose

This project aims to:
1. Analyze student queries to identify common concerns (e.g., DMC issuance, degree applications, hostel allotments).
2. Visualize key metrics like fees and processing times to streamline administrative understanding.
3. Use NLP models (Word2Vec and GloVe) to explore semantic similarities, supporting future chatbot development.
4. Provide a foundation for improving student services at UET through data-driven insights.

## 📂 Dataset Description

The dataset (`Quries_in_English.csv`) contains questions and answers related to student affairs at UET, Lahore. It covers topics such as:
- **DMC/Transcript**: Procedures, fees, and documents for obtaining Detailed Marks Certificates.
- **Degree**: Application processes, fees, and timelines for degree issuance.
- **Hostel**: Allotment, fees, and facilities.
- **Admission**: Entry tests, merit lists, and document requirements.
- **Fees**: Payment methods, challans, and refund policies.
- **Grades/CGPA**: Minimum requirements and grade impacts.
- **Certificates**: Bonafide, percentage equivalence, and provisional certificates.
- **Clearance**: Departmental and dues clearance processes.

The dataset is a CSV file with two columns: `Questions` and `Answers`. It includes detailed procedural information and is ideal for both statistical analysis and NLP tasks.

##  Setup Instructions

### Prerequisites
- Python 3.9

### Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/anonduke/EmbeddingClusteringVectorizationWorkshop.git
   ```

2. **Set Up a Virtual Environment** (optional but recommended):
   ```bash
   python -m venv .venv
   On Windows: .venv\Scripts\activate
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Download NLTK Data**:
   ```python
   import nltk
   nltk.download('punkt')
   ```

5. **Download GloVe Embeddings**:
   - Download the `glove.6B.50d.txt` file from [GloVe's official site](https://nlp.stanford.edu/projects/glove/) or another source.
   - Place it in a `glove.6B` folder in the project directory.

6. **Place the Dataset**:
   - Ensure `Quries_in_English.csv` is in the `data` folder of the project directory.

7. **Run the Notebook**:
   ```bash
   jupyter notebook Student_Affairs_Analysis.ipynb
   ```

## Notebook Structure

The Jupyter Notebook (`EmbeddingClusteringVectorizationWorkshop.ipynb`) is organized as follows:

1. **Importing Libraries**:
   - Loads `pandas`, `matplotlib`, `seaborn`, `gensim`, and `nltk` for data processing and visualization.

2. **Loading and Preprocessing Data**:
   - Reads the CSV file and cleans it by removing empty rows, standardizing column names, and normalizing text.

3. **Categorizing Queries**:
   - Categorizes questions into groups (e.g., DMC/Transcript, Degree, Hostel) using keyword-based rules.
   - Visualizes category frequencies with a bar plot.

4. **Analyzing Fee Structures**:
   - Extracts fee amounts using regex and visualizes their distribution across categories with a box plot.

5. **Processing Times Analysis**:
   - Extracts processing times (in days) and visualizes them with a bar plot.

6. **Document Requirements Analysis**:
   - Identifies common documents required for processes and visualizes the top 10 with a bar plot.

7. **NLP Analysis with Word2Vec and GloVe**:
   - Trains a Word2Vec model (Skip-gram) on the dataset to find semantic similarities (e.g., words similar to "DMC").
   - Loads pretrained GloVe embeddings (50d) to compare similarities.
   - Evaluates similarity for domain-specific word pairs (e.g., "dmc-form", "challan-fee").
   - Compares Word2Vec and GloVe performance in a table.

8. **Interesting Fact**:
   - Highlights the most frequently required document (e.g., DMC form).

9. **Conclusion**:
   - Summarizes findings and suggests extensions for further analysis.

## Key Findings

- **Query Distribution**: DMC/Transcript and Degree-related queries dominate, reflecting their importance in student affairs.
- **Fee Insights**: Fees range from Rs. 300 (incomplete DMC) to Rs. 10,000 (loan clearance for final DMC). The box plot reveals outliers in certain categories.
- **Processing Times**: Most processes (e.g., DMC, certificates) take 3-4 days, while degrees require 40 days.
- **Document Requirements**: The DMC form is the most frequently required document, appearing in multiple processes.
- **NLP Insights**:
  - Word2Vec (Skip-gram) captures domain-specific relationships well (e.g., "dmc" is highly similar to "form" with a score of 0.959).
  - GloVe struggles with niche terms like "dmc" due to its general-purpose vocabulary but performs well for common terms like "student-account" (score: 0.427).
  - Word2Vec is better suited for a UET-specific chatbot due to its ability to learn from the dataset directly.

## NLP Component

The notebook includes an NLP analysis to explore semantic relationships in the dataset, useful for building a chatbot or knowledge base:
- **Word2Vec (Skip-gram)**: Trained on the dataset to capture context-specific word relationships. For example, "dmc" is closely related to "form" (0.959) and "fee" (0.945).
- **GloVe (50d)**: Uses pretrained embeddings to compare general-purpose word similarities. It performs less effectively for UET-specific terms like "dmc" but is robust for broader terms.
- **Comparison**: A table compares similarity scores for word pairs (e.g., "dmc-form", "challan-fee"). Word2Vec outperforms GloVe for this dataset due to its domain-specific training.
