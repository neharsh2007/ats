# ATS Resume Expert

ATS Resume Expert is a Streamlit-based application that analyzes resumes against job descriptions (JDs) using AI and natural language processing (NLP). It provides insights such as JD match percentage, missing skills, and an overall summary to help users optimize their resumes for specific job applications.
![alt text](./Ats.jpg)

## How the ATS Resume Expert Works

The ATS Resume Expert application is designed to help users optimize their resumes for specific job descriptions by analyzing the compatibility between the two. Below is a detailed breakdown of the steps performed by the application:

### 1. **Resume and Job Description Upload**

- The user uploads their **resume** and **job description (JD)** in PDF format using the file uploaders provided in the Streamlit app interface.
- The application extracts text from the uploaded PDF files using the

PyPDF2

library.

### 2. **Text Preprocessing**

- The extracted text from both the resume and the job description is cleaned and preprocessed. This includes:
  - Removing special characters, numbers, and extra spaces.
  - Converting text to lowercase for uniformity.
  - Tokenizing the text into individual words or phrases.

### 3. **Keyword Extraction**

- The application uses `scikit-learn`'s

CountVectorizer

to extract keywords from the job description.

- These keywords represent the essential skills, qualifications, and requirements for the job.

### 4. **JD Match Percentage Calculation**

- The application compares the keywords extracted from the job description with the content of the resume.
- It calculates the **JD Match Percentage**, which indicates how well the resume aligns with the job description based on keyword overlap.

### 5. **Skills Gap Analysis**

- The application identifies **missing skills** or keywords in the resume that are present in the job description.
- This helps the user understand which specific skills or qualifications they need to add to their resume to improve compatibility.

### 6. **Position Match Assessment**

- Using OpenAI's GPT model (via LangChain), the application performs a deeper analysis of the resume and job description.
- It generates a **Position Match Assessment**, which provides insights into how well the resume aligns with the overall requirements of the job.
- This assessment includes qualitative feedback, such as strengths and areas for improvement.

### 7. **AI-Powered Insights**

- The GPT model is also used to generate a detailed **summary** of the analysis, including:
  - Key strengths of the resume.
  - Suggestions for improvement.
  - Recommendations for tailoring the resume to better match the job description.

### 8. **Results Display**

- The analysis results are displayed in the Streamlit app, including:
  - **JD Match Percentage**: A numerical score indicating the alignment between the resume and the job description.
  - **Missing Skills**: A list of skills or keywords that are present in the job description but missing from the resume.
  - **Overall Summary**: A detailed AI-generated summary of the analysis.
  - **Position Match Assessment**: A qualitative evaluation of the resume's fit for the job.

### 9. **User Guidance**

- Based on the analysis, the application provides actionable recommendations to the user, such as:
  - Adding specific skills or keywords to the resume.
  - Tailoring the resume to better highlight relevant experience and qualifications.

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/ApplicationTrackingSystem.git
   cd ApplicationTrackingSystem
   ```

2. Install the required dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Create a `.env` file in the root directory and add your OpenAI API key:

   ```
   OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxx
   ```

4. Run the Streamlit app:
   ```bash
   streamlit run ats.py
   ```

## Usage

1. Upload a **Job Description (PDF)** and a **Resume (PDF)** using the file uploaders in the app.
2. Click the **Analyze Resume** button.
3. View the analysis results, including:
   - JD Match Percentage
   - Missing Skills
   - Overall Summary
   - Position Match Assessment

## Requirements

- Python 3.8 or higher
- Dependencies listed in requirements.txt

## Technologies Used

- **Streamlit**: For building the web application interface.
- **LangChain**: For integrating OpenAI's GPT model.
- **OpenAI GPT**: For generating AI-powered insights.
- **scikit-learn**: For text vectorization and keyword extraction.
- **PyPDF2**: For extracting text from PDF files.

## File Structure

```
.
├── ats.py                         # Main application script
├── .gitignore                     # Specifies files and directories to ignore in version control
├── requirements.txt               # List of dependencies
├── .env                           # Environment variables (not included in repo)
└── README.md                      # Project documentation
```

## License

This project is licensed under the MIT License.

## Acknowledgments

- OpenAI for providing the GPT model.
- Streamlit for the interactive app framework.
- scikit-learn for text processing utilities.
