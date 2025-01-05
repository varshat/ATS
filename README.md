Smart ATS

Overview

Smart ATS is a web-based application built using Streamlit and Google Generative AI (Gemini) to help users optimize their resumes for applicant tracking systems (ATS). The tool evaluates resumes against a provided job description, highlighting the matching percentage, missing keywords, and a summary of the profile.

You can access the app here: Smart ATS on Hugging Face

Features

Resume Evaluation:

Upload a resume in PDF format.

Input a job description (JD) for analysis.

Matching Percentage:

Calculates how well the resume aligns with the job description.

Missing Keywords:

Identifies keywords missing in the resume based on the job description.

Profile Summary:

Generates a summary of the resume profile.

User-Friendly Interface:

Simple and interactive design powered by Streamlit.

Prerequisites

To run this application, ensure you have the following installed:

Python 3.8+

Streamlit: For building the web interface.

PyPDF2: For extracting text from PDF files.

dotenv: For managing environment variables.

google-generativeai: For leveraging Google's Generative AI models.

Installation

Clone the repository:

git clone <repository-url>
cd <repository-folder>

Set up a virtual environment:

python -m venv venv
source venv/bin/activate # For Linux/Mac
venv\Scripts\activate   # For Windows

Install dependencies:

pip install -r requirements.txt

Set up the .env file:

Create a file named .env in the project root.

Add your Google API key:

GOOGLE_API_KEY=your_google_api_key

How to Run

Start the Streamlit app:

streamlit run app.py

Open the application in your browser (default: http://localhost:8501).

Use the app:

Paste the job description into the provided text area.

Upload your resume (PDF format).

Click the Submit button to get the analysis results.

How It Works

Input Handling:

Job descriptions are input directly into the text area.

Resumes are uploaded as PDF files.

Text Extraction:

Uses PyPDF2 to extract text from the uploaded PDF.

Generative AI Analysis:

The job description and resume text are passed to the Google Gemini API using a structured prompt.

The response includes:

Matching percentage.

Missing keywords.

A summary of the profile.

Results Display:

Results are displayed on the web interface for user review.

Example Prompt

The tool sends the following prompt to the Google Generative AI API:

Hey Act Like a skilled or very experience ATS(Application Tracking System)
with a deep understanding of tech field,software engineering,data science ,data analyst
and big data engineer. Your task is to evaluate the resume based on the given job description.
You must consider the job market is very competitive and you should provide 
best assistance for improving the resumes. Assign the percentage Matching based 
on JD and
the missing keywords with high accuracy
resume:{text}
description:{jd}

I want the response in one single string having the structure
{"JD Match":"%","MissingKeywords:[]","Profile Summary":""}

Dependencies

Streamlit: For building the UI.

google-generativeai: For leveraging Gemini models.

PyPDF2: For extracting text from PDF files.

dotenv: For loading API keys securely.

Install these dependencies using the requirements.txt file.

Future Enhancements

Support for additional file formats (e.g., .docx).

More detailed feedback on resume structure and formatting.

Customizable prompts for industry-specific analysis.

Integration with other generative AI models for comparison.

Troubleshooting

API Key Error:

Ensure the .env file is set up correctly with your Google API key.

PDF Text Extraction Issues:

Verify that the uploaded PDF is text-based (not an image-based scan).

Consider adding OCR capabilities for scanned PDFs.

Streamlit Not Running:

Ensure all dependencies are installed.

Check for typos in the command: streamlit run app.py.

Author

This Smart ATS tool was developed to simplify resume optimization for competitive job markets. Feel free to suggest improvements or report issues through the repository.

License

This project is licensed under the MIT License.

