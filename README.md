Resume Information Extractor

A Python-based Resume Information Extraction System that extracts structured information from PDF resumes using PDF parsing, regular expressions, and NLP techniques.

Features

The system extracts the following information:

* Name
* Email Address
* Phone Number
* Skills
* Education
* Work Experience
* LinkedIn Profile
* GitHub Profile

Setup Instructions

1. Install Required Packages**

Run the following commands:

pip install pdfminer.six

pip install spacy

pip install pymupdf

2. Download spaCy Model

python -m spacy download en_core_web_sm

3. Upload Resume PDF

Place the resume PDF file in your working directory or update the file path in the notebook/script accordingly.

Execution Instructions

1. Run the Notebook or Script

Execute all cells (Jupyter/Colab) or run the Python script.

2. Provide Resume File

Specify the path to the PDF resume file:

pdf_path = "resume.pdf"

3. View Extracted Information

The system processes the resume and returns structured JSON output containing the extracted details.

Sample Output

{
"Name": "John Doe",
"Email": "[johndoe@gmail.com](mailto:johndoe@gmail.com)",
"Phone": "+91 9876543210",
"Skills": ["Python", "Machine Learning", "SQL"],
"Education": [
{
"Degree": "B.Tech Computer Science",
"Institution": "XYZ University"
}
],
"Experience": [
{
"Role": "Software Engineer",
"Company": "ABC Pvt Ltd"
}
],
"LinkedIn": "https://linkedin.com/in/johndoe",
"GitHub": "https://github.com/johndoe"
}

Technologies Used

* Python
* pdfminer.six
* PyMuPDF (fitz)
* spaCy
* Regular Expressions (Regex)

Project Structure

Resume-Information-Extractor/

├── Resume_Information_Extractor.ipynb

├── resumes/

│   └── sample_resume.pdf

├── README.md

└── requirements.txt
