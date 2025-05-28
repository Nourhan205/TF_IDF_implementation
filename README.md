# PDF Text Analysis with TF-IDF

This project demonstrates a workflow for extracting text from PDF documents, preprocessing the text, and applying the Term Frequency-Inverse Document Frequency (TF-IDF) algorithm to identify the most significant words within each document. It utilizes several Python libraries for PDF manipulation, natural language processing, and numerical computation.

## Description

The primary goal of this project is to analyze the content of PDF files by identifying key terms based on their TF-IDF scores. The process involves reading text directly from PDF files, cleaning and preparing the text data by removing irrelevant elements like punctuation and common words (stopwords), and then calculating TF-IDF values. TF-IDF is a statistical measure used to evaluate how important a word is to a document in a collection or corpus. The importance increases proportionally to the number of times a word appears in the document but is offset by the frequency of the word in the corpus.

## Features

- **PDF Text Extraction:** Leverages the `PyPDF2` library to read and extract textual content from PDF files page by page.
- **Text Preprocessing:** Implements text cleaning techniques using `nltk` (Natural Language Toolkit), including converting text to lowercase, removing punctuation, tokenizing the text into individual words, and filtering out common English stopwords.
- **TF-IDF Calculation:** Computes TF (Term Frequency) and IDF (Inverse Document Frequency) scores for words across a collection of documents. It then combines these scores to calculate the final TF-IDF value for each word in each document.
- **Top Keyword Identification:** Identifies and ranks the most important words (keywords) within each document based on their calculated TF-IDF scores.
- **Sample PDF Generation:** Includes functionality using the `reportlab` library to create sample PDF documents for demonstration and testing purposes.

## Requirements

This project requires Python 3 and the following libraries:

- `PyPDF2`: For reading and extracting text from PDF files.
- `nltk`: For natural language processing tasks like tokenization and stopword removal.
- `reportlab`: For generating sample PDF documents.

Additionally, specific `nltk` data packages need to be downloaded:

- `punkt`: Used for tokenization.
- `stopwords`: Contains a list of common English stopwords.

## Setup

1.  **Install Python Libraries:**
    You can install the required libraries using pip:
    ```bash
    pip install pypdf2 nltk reportlab
    ```

2.  **Download NLTK Data:**
    Run the following Python commands to download the necessary `nltk` data:
    ```python
    import nltk
    nltk.download('punkt')
    nltk.download('stopwords')
    ```

## Usage

The provided Jupyter Notebook (`Untitled (1).ipynb`) contains the complete code implementation. It demonstrates the workflow as follows:

1.  **Initialization:** Installs dependencies and imports necessary modules.
2.  **Function Definitions:** Defines functions for text preprocessing (`preprocess_text`), PDF text extraction (`extract_text_from_pdf`), TF calculation (`compute_tf`), IDF calculation (`compute_idf`), TF-IDF calculation (`compute_tfidf`), and identifying top words (`get_top_words`).
3.  **Sample Data Generation:** Creates four sample PDF files (`doc1.pdf` to `doc4.pdf`) containing text related to artificial intelligence and machine learning using the `create_sample_pdf` function.
4.  **Analysis:** Processes the generated PDF files by:
    - Extracting text from each PDF.
    - Preprocessing the extracted text.
    - Computing TF-IDF scores for the collection of documents.
    - Identifying and printing the top 5 most significant words for each document based on their TF-IDF scores.

You can adapt the code to process your own PDF files by modifying the `pdf_files` list to include the paths to your target documents.

## Code Structure

- **`preprocess_text(text)`:** Cleans and tokenizes the input text.
- **`extract_text_from_pdf(pdf_path)`:** Reads a PDF and returns its text content.
- **`compute_tf(document_tokens)`:** Calculates TF for a tokenized document.
- **`compute_idf(documents)`:** Calculates IDF across a list of tokenized documents.
- **`compute_tfidf(documents)`:** Calculates TF-IDF scores for a list of tokenized documents.
- **`get_top_words(tfidf_scores, top_n=5)`:** Returns the top N words for each document based on TF-IDF scores.
- **`create_sample_pdf(file_name, text)`:** Generates a simple PDF file.

The main part of the script demonstrates how to use these functions together to analyze a set of sample PDFs.

