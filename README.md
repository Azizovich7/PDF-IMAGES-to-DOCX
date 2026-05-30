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


📋 Prerequisites & Installation
1. Python Libraries
Install the required dependencies using pip:
code
Bash
pip install python-docx openai pillow pytesseract pymupdf
2. Tesseract OCR (Required for Scanned PDFs & Images)
Because the script reads text from images, you must install the Tesseract OCR engine on your computer:
Windows:
Download the installer from the Tesseract at UB-Mannheim repository.
Run the installer (it typically installs to C:\Program Files\Tesseract-OCR).
Make sure the path in generator.py points to your tesseract.exe location.
Mac: Install via Homebrew:
code
Bash
brew install tesseract
Linux:
code
Bash
sudo apt-get install tesseract-ocr
3. OpenRouter API Key
The script uses free models available on OpenRouter to translate and format the text.
Sign up for a free account at OpenRouter.
Create an API key in your settings dashboard.
⚙️ Configuration
Before running the script, open generator.py and configure your API key and Tesseract installation path:
code
Python
# 1. Update your Tesseract location (mostly for Windows users)
pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract.exe'

# 2. Add your OpenRouter API key
OPENROUTER_API_KEY = "your_openrouter_api_key_here"

# 3. Optional: Change the target model (Default uses Llama-3-8b-Instruct)
MODEL_NAME = "meta-llama/llama-3-8b-instruct:free"
📖 How to Use
Clone or download this repository to your machine.
Put the files you want to convert (images, digital PDFs, or scanned PDFs) into the inputs folder.
Tip: Name your files in order, e.g., 01_lifestyle.pdf, 02_travel.png. The script sorts files alphabetically to build the units.
Open your terminal or command prompt inside the project folder.
Run the script:
code
Bash
python generator.py
Check the outputs folder for your compiled and formatted A2_Vocabulary_Book.docx.
