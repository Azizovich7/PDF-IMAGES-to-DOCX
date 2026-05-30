An automated pipeline designed to extract text from PDFs and photos, filter vocabulary to focus on the A2+ (upper-elementary/lower-intermediate) level, translate words, and output a structured, clean, and styled Microsoft Word (`.docx`) book organized by units.

It utilizes **PyMuPDF** and **Tesseract OCR** for text extraction (even from scanned documents) and integrates with **OpenRouter** to process content using cost-free, open-source Language Models (LLMs).

---

## 🚀 Features

*   **📂 Structured by Units:** Automatically treats every document or image in the input directory as a distinct "Unit".
*   **🔍 Hybrid Extraction:** Reads digital text PDFs, handles scanned/image-only PDFs, and extracts text from PNG, JPG, and JPEG files.
*   **🤖 AI-Powered CEFR Filtering:** Uses free open-source models (via OpenRouter) to filter words specifically to the A2+ level.
*   **🌐 Trilingual Output:** Generates definitions in English, alongside translations into **Russian** and **Uzbek**.
*   **🎨 Clean Word Styling:** Produces formatted tables with styled header rows, bold keywords, and uniform layouts, complete with a title page and automatic page breaks between units.

---

## 🛠️ Project Structure

Your project directory will look like this:

```text
vocabulary-book-generator/
├── inputs/             # Place your source PDFs/Images here (e.g., Unit_1.pdf, Unit_2.png)
├── outputs/            # The generated .docx book will be saved here
├── generator.py        # Main execution script
└── README.md           # Documentation
