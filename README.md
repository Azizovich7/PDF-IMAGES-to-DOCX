# 📚 A2+ Vocabulary Book Generator

An automated pipeline for transforming PDFs and images into a professionally formatted **A2+ vocabulary textbook**.

The generator extracts text from digital documents, scanned PDFs, and images, identifies vocabulary at the **A2+ (Upper-Elementary / Lower-Intermediate)** CEFR level, generates English definitions, translates words into **Uzbek** and **Russian**, and compiles everything into a clean, publication-ready Microsoft Word (`.docx`) book.

Powered by **PyMuPDF**, **Tesseract OCR**, and free open-source language models through **OpenRouter**, this tool makes vocabulary-book creation fast, accurate, and fully automated.

---

# ✨ Features

### 📂 Unit-Based Organization

Each file placed in the input directory is automatically treated as a separate learning unit.

### 🔍 Hybrid Text Extraction

Supports multiple content sources:

* Digital PDFs
* Scanned PDFs
* PNG images
* JPG images
* JPEG images

### 🤖 AI-Powered Vocabulary Processing

Uses free open-source LLMs via OpenRouter to:

* Extract vocabulary
* Filter words to the A2+ CEFR level
* Generate concise English definitions
* Create multilingual translations

### 🌍 Trilingual Vocabulary Output

Each vocabulary entry includes:

* 🇬🇧 English Word
* 📖 English Definition
* 🇺🇿 Uzbek Translation
* 🇷🇺 Russian Translation

### 🎨 Professional DOCX Formatting

Automatically generates a polished textbook featuring:

* Cover page
* Unit headings
* Styled vocabulary tables
* Bold keywords
* Consistent formatting
* Automatic page breaks between units

---

# 🗂️ Project Structure

```text
vocabulary-book-generator/
│
├── inputs/                 # Source PDFs and images
├── outputs/                # Generated vocabulary book
├── generator.py            # Main application
└── README.md               # Documentation
```

---

# 📋 Prerequisites & Installation

## 1. Install Python Dependencies

Install all required packages:

```bash
pip install python-docx openai pillow pytesseract pymupdf
```

---

## 2. Install Tesseract OCR

This project relies on **Tesseract OCR** to extract text from scanned documents and image files.

### Windows

1. Download the installer from the Tesseract OCR (UB-Mannheim) release page.
2. Run the installer.

Default installation location:

```text
C:\Program Files\Tesseract-OCR
```

3. Update the Tesseract path in `generator.py`.

### macOS

Install using Homebrew:

```bash
brew install tesseract
```

### Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install tesseract-ocr
```

---

## 3. Obtain an OpenRouter API Key

The project uses OpenRouter to access free open-source language models.

### Steps

1. Create a free OpenRouter account.
2. Generate an API key from your dashboard.
3. Copy the key for configuration.

---

# ⚙️ Configuration

Open `generator.py` and update the following settings:

```python
# Tesseract OCR location (mainly required on Windows)
pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"

# OpenRouter API Key
OPENROUTER_API_KEY = "your_openrouter_api_key_here"

# Optional: Select a different model
MODEL_NAME = "openrouter/free"
```

---

# 📖 Usage

## Step 1 — Prepare Your Files

Place all source materials into the `inputs` directory.

Supported formats:

* 📄 PDF
* 📄 Scanned PDF
* 🖼️ PNG
* 🖼️ JPG
* 🖼️ JPEG

### Recommended Naming Convention

For proper unit ordering, name files numerically:

```text
01_lifestyle.pdf
02_travel.pdf
03_education.png
04_environment.jpg
```

Files are processed alphabetically.

---

## Step 2 — Run the Generator

Open a terminal inside the project folder and execute:

```bash
python generator.py
```

---

## Step 3 — Retrieve the Generated Book

After processing completes, the vocabulary textbook will be saved in the `outputs` directory:

```text
outputs/A2_Vocabulary_Book.docx
```

---

# 📘 Generated Output

The resulting document includes:

* ✅ CEFR A2+ vocabulary
* ✅ English definitions
* ✅ Uzbek translations
* ✅ Russian translations
* ✅ Unit-based organization
* ✅ Professional table formatting
* ✅ Cover page
* ✅ Automatic page breaks
* ✅ Publication-ready DOCX layout

---

# 🚀 Example Workflow

```text
PDFs / Images
        │
        ▼
Text Extraction
(PyMuPDF + OCR)
        │
        ▼
Vocabulary Filtering
(OpenRouter LLM)
        │
        ▼
Definitions & Translations
        │
        ▼
DOCX Generation
        │
        ▼
A2_Vocabulary_Book.docx
```

---

# 🧠 Technologies Used

| Technology    | Purpose                  |
| ------------- | ------------------------ |
| PyMuPDF       | PDF text extraction      |
| Pillow        | Image processing         |
| Tesseract OCR | OCR for scanned files    |
| OpenRouter    | Access to free LLMs      |
| python-docx   | Word document generation |

---

# 📄 License

This project is provided as-is for educational and personal use.

Feel free to modify, improve, and adapt it to your own learning materials and vocabulary projects.
