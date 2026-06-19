 📄 Resume Information Extractor: Approach & Design

 🎯 Overview

The **Resume Information Extractor** is a rule-based system designed to extract structured information from PDF resumes **without using Large Language Models (LLMs) or Generative AI services**. The solution combines PDF parsing, Regular Expressions, and Natural Language Processing (NLP) techniques to identify and organize key resume information.



 🔍 Approach
 
📌 Step 1: PDF Text Extraction

The resume PDF is processed using **pdfminer.six** to extract textual content. Additionally, **PyMuPDF** is used to retrieve embedded hyperlinks, enabling accurate detection of LinkedIn and GitHub profiles.


 🧹 Step 2: Text Preprocessing

The extracted text is cleaned and standardized by:

* Removing unnecessary whitespace
* Normalizing line breaks
* Standardizing formatting

This preprocessing step improves the accuracy of downstream extraction tasks.


⚙️ Step 3: Information Extraction

 📧 Contact Information

* Email addresses are extracted using **Regular Expressions (Regex)**.
* Phone numbers are identified through pattern matching techniques.

 👤 Name Extraction

The candidate's name is extracted using a combination of:

* Position-based heuristics
* Regular Expressions
* spaCy Named Entity Recognition (NER)

💡 Skills Extraction

* Resume content is matched against a predefined skill dictionary.
* Detected skills are returned as a structured list.

🎓 Education Extraction

* The Education section is identified using common section headers.
* Institution names and degree information are extracted using keyword-based rules.

 💼 Experience Extraction

Experience-related sections are located using headers such as:

* Experience
* Work Experience
* Professional Experience

Relevant content is extracted until another major section begins.

 🔗 Social Profile Extraction

* LinkedIn and GitHub profiles are first extracted from embedded PDF hyperlinks.
* If hyperlinks are unavailable, regex-based URL extraction is used as a fallback mechanism.


📦 Step 4: Structured Output Generation

All extracted information is consolidated into a Python dictionary and exported as **JSON**, making it easy to integrate with databases, ATS systems, and other applications.


 📋 Assumptions

The system operates under the following assumptions:

* Resumes are provided in **PDF format**.
* PDFs contain selectable text and are not scanned images.
* Resume content is primarily written in **English**.
* Standard section headers such as **Education**, **Experience**, and **Skills** are present.
* Contact information follows common formatting conventions.
* LinkedIn and GitHub profiles are available either as hyperlinks or plain text.



⚠️ Limitations

While the system performs effectively on standard resumes, the following limitations apply:

* Scanned PDFs requiring OCR are not currently supported.
* Skill extraction is limited to the predefined skill dictionary.
* Highly customized resume layouts may reduce extraction accuracy.
* Education and experience extraction rely on section headers and keyword-based parsing.
* Non-standard social profile URLs may not always be detected.
* The system does not perform deep semantic understanding of resume content.

 🚀 Key Technologies

* Python
* pdfminer.six
* PyMuPDF (fitz)
* spaCy
* Regular Expressions (Regex)
* JSON
