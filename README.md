# Natural-Language-Processing-for-Legal-Documents

# Introduction
This project focuses on generating summaries of legal documents using advanced natural language processing techniques, specifically leveraging transformer-based models. The aim is to automatically condense complex legal judgments into concise summaries while retaining critical information.

# Datasets
Location: The dataset is stored in Google Drive at https://drive.google.com/drive/folders/1Mlh_USXgXTi4uvVCF-OtDUviarO5G33D?usp=sharing

Structure:
Judgment Files: These are located in subdirectories named judgement under train-data and test-data. Each file contains the full text of legal judgments.
Summary Files: Corresponding summary files are located in the summary subdirectories, providing reference summaries.
Statistics File: A file named stats-IN-test.txt provides the required summary lengths for test documents.

# Tools and Libraries Used
Python Libraries:
transformers: Used to load pre-trained models and tokenizers.
torch: Facilitates deep learning operations and computations on GPUs.
nltk: Used for tokenization of text into sentences.
pandas and numpy: Utilized for data manipulation and numerical operations.
Model: nsi319/legal-pegasus from Hugging Face's Transformers library, specifically designed for summarizing legal documents.
Platform: Google Colab for cloud-based execution and GPU acceleration.

# Process Overview
Data Preparation:
Mount Google Drive and set paths for datasets and outputs.
Retrieve documents and summaries from specified directories.
Parse a statistics file to determine required summary lengths.

Text Processing:
Tokenize documents into sentences using nltk.
Chunk documents into nested sentences to fit model input requirements (max 512 words per chunk).

Summarization:
Utilize the Pegasus model to generate summaries for each chunk of the document.
Adjust the length of generated summaries based on the required length from the statistics file.
Concatenate chunk summaries and ensure sentence boundaries are respected.

# Output:
Save each generated summary as a text file in the specified output directory.
Output containing summary of 5 legal text https://drive.google.com/drive/folders/1FjsjU7I7xylm_4wccJKTf2EXH4hcwSic?usp=sharing

# Conclusion
The process successfully automates the summarization of legal documents, providing an efficient way to handle large volumes of text. By employing the Pegasus model, the summaries are generated with an emphasis on retaining essential information while reducing verbosity.

# Future Work
Model Optimization: Experiment with different models and fine-tune parameters to improve summarization quality.

Evaluation Metrics: Implement automatic evaluation metrics (e.g., ROUGE scores) to assess the quality of generated summaries against reference summaries.

Expanded Dataset: Use a larger and more diverse dataset to test the model's generalization capabilities across various types of legal documents.

Real-Time Summarization: Develop a real-time summarization tool with a user-friendly interface for legal practitioners.

Multi-lingual Support: Extend the model to support legal documents in multiple languages, catering to a global audience.
