# Bangla News Image Summarizer with Cloud Storage
This project reads Bangla newspaper images, converts them into text using OCR, generates concise summaries, and uploads the results to Google Drive for convenient use and collaboration.

## Overview

The Bangla News Image Summarizer is designed to automate the process of reading Bangla newspaper images, extracting textual content using Optical Character Recognition (OCR), cleaning and summarizing the text, and securely saving the summaries to Google Drive.

## Objectives

- Extract readable Bangla text from scanned newspaper images.
- Clean and preprocess extracted text by removing noise and stopwords.
- Generate concise summaries using NLP techniques.
- Store summaries in structured format (CSV/JSON) to Google Drive.

```text
Images (data/) 
    │
    ├─ OCR → Raw Text (output/text/raw/)
    │
    ├─ Cleaning → Clean Text (output/text/clean/)
    │
    ├─ Stopword Removal → No Stopwords (output/text/no_stopwords/)
    │
    ├─ Preprocessing → Preprocessed Text (output/text/preprocessed/)
    │
    └─ Summarization → Summaries (output/summaries/)
           ├─ Individual summary files
           ├─ Combined CSV (summaries.csv)
           └─ Combined JSON (summaries.json)
```

## Directory Structure 

```
BanglaNewsSummarizer/
│
├── data/                              # Original newspaper images (stored in Google Drive)
├── resources/                         # Extra resources like stopword lists
│   └── stopwords-bn.txt
└── output/
    ├── text/
    │   ├── raw/                       # OCR-extracted raw text
    │   ├── clean/                     # Cleaned text
    │   ├── no_stopwords/              # Text without stopwords
    │   └── preprocessed/              # Tokenized & preprocessed text
    ├── summaries/                     # Individual summaries
    ├── summaries.csv                  # Combined summaries CSV (title, link, summary)
    └── summaries.json                 # Combined summaries JSON
```
#### Note:
- Large folders (data/ and output/) are stored in Google Drive.
- Source code and resources are available in GitHub.
- The Google Drive folder contains all images, intermediate text files, and generated summaries.
- Google Drive link: [BanglaNewsSummarizer Drive Folder](https://drive.google.com/drive/folders/1o30kg-7ezd8IYRyrzHp1K1-tHjp7ZKGA?usp=sharing)

## Installation & Setup

Clone this repository:
```
git clone https://github.com/syedirfanx/bangla-news-summarizer.git
cd bangla-news-summarizer
```
Install required Python packages:
```
pip install -r requirements.txt
```
Install Tesseract OCR for Bangla:
```
sudo apt install tesseract-ocr tesseract-ocr-ben
```
Mount Google Drive in Colab to access images and output folders:
```
from google.colab import drive
drive.mount('/content/drive')
```
## Usage

- Open ``bangla_news_summarizer.ipynb`` in Google Colab.
- Set paths for your ``data/`` folder and ``output/`` folders.
- Run the notebook cells in order:
```
OCR → Raw Text
Cleaning → Clean Text
Stopword Removal → No Stopwords
Preprocessing → Preprocessed Text
Summarization → Summaries
```
- Outputs:
```
Individual summary files in output/summaries/
Combined CSV: output/summaries.csv
Combined JSON: output/summaries.json
```

## Key Features
- Full Bangla OCR with preprocessing.
- Bangla stopword removal for cleaner summaries.
- LexRank summarization with frequency-based fallback.
- Saves both individual summary files and combined CSV/JSON.

## References

- [Pytesseract](https://pypi.org/project/pytesseract/) – OCR engine for Python
- [Sumy](https://pypi.org/project/sumy/) – Text summarization library
- [Bangla Stopwords List](https://github.com/stopwords-iso/stopwords-bn/blob/master/stopwords-bn.txt)
