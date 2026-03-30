# 🛡️ DocShield — Universal Document Reader

## Magic-Based File Integrity Verification + Professional Document Viewer

DocShield is a secure, Streamlit-powered document reader that verifies file types using **libmagic** (magic bytes) instead of trusting file extensions. It blocks malicious files disguised as documents and provides a rich viewing experience for PDFs, Office files, images, and plain text formats.

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| Magic Byte Verification | Reads binary signatures (1000+ formats) to detect true file type |
| Threat Blocking | Automatically blocks EXE, ELF, scripts, and other executables |
| Multi-Format Support | PDF, DOCX, XLSX, Images (PNG/JPEG/GIF/BMP/WEBP), JSON, CSV, TXT |
| PDF Power Tools | 200-page limit, per-page tabs, full-text search, text export |
| DOCX Parser | Paragraphs, tables, heading hierarchy |
| XLSX Viewer | Multi-sheet Excel with dataframe views |
| Image Metadata | Shows dimensions, format, and EXIF data where available |
| Hex Dump | Raw binary header inspection for advanced users |
| Session Log | Complete audit trail of all scanned files |
| Download Extracts | Save PDF text as `.txt` file |

---

## 🚀 Quick Start (Local)

### Prerequisites

- Python 3.8 or higher  
- pip package manager  

### Installation

### Linux / macOS / WSL

```bash
# Install system library
sudo apt-get install libmagic1   # Debian/Ubuntu

# OR

brew install libmagic            # macOS

# Install Python packages
pip install -r requirements.txt

# Run the app
streamlit run universal_reader_app.py

Windows

# Install Python package (includes libmagic DLL)
pip install python-magic-bin

pip install -r requirements.txt

# Run the app
streamlit run universal_reader_app.py

The app will open at:

http://localhost:8501


---

## ☁️ Deploy to Streamlit Cloud (FREE)

Share DocShield with anyone — no Python installation required.

Step 1: Create a GitHub Repository

# Go to https://github.com/new
# Create a public repository named: docshield-reader

Upload these three files:

docshield-reader/
├── universal_reader_app.py
├── requirements.txt
└── packages.txt


---

Step 2: Create packages.txt

libmagic1


---

Step 3: Create requirements.txt

streamlit>=1.28.0
python-magic>=0.4.27
pdfplumber>=0.10.0
python-docx>=0.8.11
openpyxl>=3.1.0
pandas>=2.0.0
Pillow>=10.0.0


---

Step 4: Deploy on Streamlit Cloud

1. Go to https://share.streamlit.io
2. Sign in with GitHub
3. Click "New app"
4. Select your repository and universal_reader_app.py
5. Click "Deploy"

Your public URL will look like:

https://yourusername-docshield-reader-xxxx.streamlit.app

Share this link — your users only need a web browser.


---

## 📁 Project Structure

your-project/

├── universal_reader_app.py
├── requirements.txt
└── packages.txt


---

## 🛡️ Security Philosophy

> "Don't trust the extension — trust the magic bytes."



Most file viewers rely on file extensions (e.g., .pdf). DocShield reads the actual binary header (magic bytes) to determine what a file really is.

This prevents:

.pdf.exe malware disguised as a PDF

Renamed script files

Extension spoofing attacks


If a file's magic signature indicates it's executable, DocShield blocks it entirely and alerts the user.


---

# 📚 Supported File Types & Limits

## Format	Magic Detection	Features

PDF	%PDF header	200 pages, search, per-page tabs, text export
DOCX	PK\x03\x04 + Word structure	Paragraphs, tables, heading hierarchy
XLSX	PK\x03\x04 + Excel structure	Multi-sheet, dataframe views
Images	JPEG/PNG/GIF/BMP/WEBP signatures	Metadata, dimensions, format
JSON	Text + structure validation	Syntax highlighting
CSV	Text + delimiter detection	Table view
TXT	Plain text	Raw display with monospace
Blocked	EXE, ELF, Mach-O, scripts	Alert + no access



---

## 🎓 Assignment Information

Subject:      Universal Document Reader (Assignment #2)
Technology:   Python 3.x + Streamlit + libmagic
Core Concept: File extension ≠ file type — magic bytes reveal truth
Submission:   Source code + requirements.txt + packages.txt + README


---

# ❓ Troubleshooting Guide

## Issue	Solution

libmagic not found (Linux)	Run sudo apt-get install libmagic1
python-magic error (Windows)	Run pip install python-magic-bin
PDF won't load	Check file size (<200 pages, <50MB recommended)
EXE not blocked	Verify libmagic is working — check session log
Streamlit Cloud fails	Ensure packages.txt contains libmagic1
ImportError on deployment	Check all packages are in requirements.txt



---

## 🔧 Development Commands

# Install dependencies
pip install -r requirements.txt

# Run locally
streamlit run universal_reader_app.py

# Stop the app
Press Ctrl+C in terminal

# View logs (Streamlit Cloud)
Check "Logs" tab in your app dashboard


---

## 📄 License

This project is created for educational purposes as part of an assignment 
on file integrity verification.


---

## 🙏 Acknowledgments

libmagic — The backbone of file type detection

Streamlit — Rapid UI framework

pdfplumber, python-docx, openpyxl — Document parsing libraries



---

## 📞 Support

For issues related to this assignment:

1. Check the Troubleshooting Guide above


2. Verify your packages.txt contains libmagic1


3. Ensure all files are in the correct structure




---

Built with ❤️ and magic bytes

