# 📄 LLM Document Structuring Pipeline

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Gemini](https://img.shields.io/badge/Google%20Gemini-LLM-orange?logo=google&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)
![Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)

> Converts unstructured PDF documents into a clean, structured Excel sheet using Google Gemini LLM — fully automated, zero manual parsing.

---

## 🧠 What This Does

Most real-world documents (invoices, reports, forms) are messy, unstructured PDFs. This pipeline:

1. Reads any PDF using `PyPDF2`
2. Sends the extracted text to **Google Gemini LLM** with a structured extraction prompt
3. Parses the LLM's response into a clean tabular format
4. Exports the result as a formatted **Excel sheet** using `pandas` + `openpyxl`

No manual regex. No hardcoded rules. Just AI-driven extraction.

---

## 🔁 Pipeline Flow
PDF File → PyPDF2 (text extraction) → Google Gemini LLM (structuring) → Pandas → Excel Output
---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.8+ | Core language |
| Google Gemini API | LLM for intelligent data extraction |
| PyPDF2 | PDF text extraction |
| Pandas | Data manipulation and structuring |
| OpenPyXL | Excel file generation |
| Jupyter Notebook | Interactive pipeline execution |

---

## 📁 Project Structure
llm-document-structuring-pipeline/
│
├── soln.ipynb          # Main pipeline notebook
├── Data_Input.pdf      # Sample input PDF
├── Output.xlsx         # Sample structured output
├── requirements.txt    # Python dependencies
├── .env.example        # API key template (never commit real keys)
└── README.md---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/sunilraj180805/llm-document-structuring-pipeline.git
cd llm-document-structuring-pipeline
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Set Up Your API Key

Create a `.env` file in the root directory:
GOOGLE_API_KEY=your_gemini_api_key_here

> ⚠️ **Never hardcode or commit your API key.** The `.env` file is already in `.gitignore`.

Get your free Gemini API key at [Google AI Studio](https://makersuite.google.com/app/apikey).

### 4. Run the Notebook
```bash
jupyter notebook soln.ipynb
```

Open `soln.ipynb`, set your input PDF path, and run all cells.

### 5. Get Your Output

The structured data will be saved as `Output.xlsx` in the project root.

---

## 📊 Sample Input → Output

**Input:** An unstructured PDF with scattered fields like name, date, amounts, etc.

**Output:** A clean Excel sheet with properly labeled columns and rows — ready for analysis.

| Field | Extracted Value |
|---|---|
| Name | John Doe |
| Date | 2024-01-15 |
| Amount | $5,200 |
| Category | Invoice |

*(Actual fields depend on your PDF content — Gemini adapts automatically.)*

---

## ⚠️ Limitations

- Works best with **text-based PDFs** — scanned/image PDFs require OCR preprocessing (e.g., `pytesseract`)
- Extraction quality depends on the clarity and consistency of the PDF content
- Very large PDFs may hit Gemini's token limits — consider chunking for long documents
- Output structure is inferred by the LLM and may vary slightly between runs

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙋 Author

**Sunilraj D**  
[GitHub](https://github.com/sunilraj180805)

