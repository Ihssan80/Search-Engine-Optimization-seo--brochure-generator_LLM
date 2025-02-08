# **Search-Engine-Optimization(SEO) Brochure Generator using LLM (OpenAI) 🚀**

A Python-based tool that **transforms website content into engaging, SEO-optimized brochures** using **web scraping, OpenAI language models, and multilingual support**.

This tool helps businesses create well-structured **Markdown brochures**, complete with:
- **Extracted website content**
- **Dynamic multimedia embedding**
- **SEO-enhanced content generation**
- **Multilingual translation**
- **QR Code sharing support**

---

## **📌 Table of Contents**
1. [Overview](#overview)
2. [Features](#features)
3. [Installation](#installation)
4. [Usage](#usage)
5. [How It Works](#how-it-works)
6. [Code Structure](#code-structure)
7. [Function & Class Documentation](#function--class-documentation)
8. [Future Enhancements](#future-enhancements)
9. [Contributing](#contributing)
10. [License](#license)
11. [Contact](#contact)

---

## **📌 Overview**
The **SEO Brochure Generator** automates **marketing content creation** by:
- Scraping content and links from a company’s website.
- Using **OpenAI LLM** to generate **SEO-optimized** brochures in Markdown.
- Translating the content into multiple **languages**.
- Embedding **YouTube videos** dynamically based on the company name.
- Generating **QR codes** for easy sharing.

This project is perfect for **marketers, content creators, and developers** looking to automate and enhance their **brochure creation process**.

---

## **📌 Features**
✔️ **Web Scraping** – Extracts titles, text, and links from websites.  
✔️ **Language Detection** – Identifies the website’s language for translation.  
✔️ **SEO-Optimized Brochures** – Uses OpenAI's LLM for engaging content generation.  
✔️ **Translation Support** – Converts brochures into multiple languages.  
✔️ **Dynamic Multimedia Embedding** – Fetches related **YouTube videos** automatically.  
✔️ **QR Code Generation** – Creates **QR codes** for quick brochure access.  
✔️ **Markdown Formatting** – Ensures links and email addresses are correctly formatted.  

---

## **📌 Installation**

### **Prerequisites**
- **Python 3.7+**
- **pip** (Python package installer)
- **OpenAI API Key** (Sign up at [OpenAI](https://openai.com/))

### **Used Libraries**
```python
import os
import requests
import json
import qrcode
import langdetect
import re
from typing import List
from dotenv import load_dotenv
from bs4 import BeautifulSoup
from IPython.display import Markdown, display
from openai import OpenAI
```

## **📌 Usage**
### **Step 1: Choose an Option**
- Enter a website URL manually.
- Search for a company name (e.g., "Microsoft" → https://www.microsoft.com).

### **Step 2: Generate the Brochure**
- The tool scrapes the website content.
- Sends it to OpenAI for SEO-optimized content generation.

### **Step 3: Select a Translation Language**
- The tool detects the language of the content.
- Option to translate the brochure into **Spanish, French, German, Chinese, Japanese, Arabic, or English**.

### **Step 4: Get a QR Code**
- A QR code is generated for quick access to the original website.

---

## **📌 How It Works**
The SEO Brochure Generator operates step by step:

1️⃣ **Extract Website Content**  
- Uses web scraping with `requests` and `BeautifulSoup` to fetch:
  - Page Title
  - Main Content
  - Hyperlinks

2️⃣ **Detect Language**  
- Uses `langdetect` to identify the primary language of the extracted content.

3️⃣ **Generate an SEO-Optimized Brochure**  
- Sends the cleaned content to OpenAI's `GPT-4o-mini`.
- The AI generates a structured, engaging, and SEO-friendly Markdown brochure.

4️⃣ **Enhance with Multimedia**  
- Searches YouTube for a related company video.
- Embeds the video link in the brochure.

5️⃣ **Translate the Brochure**  
- Option to translate the brochure into multiple languages while keeping proper formatting.

6️⃣ **Generate a QR Code**  
- A QR code links to the original website, making it easy to share.

---

## **📌 Code Structure**
```
seo_brochure_generator/
│── main.py               # Main script to run the generator
│── website_scraper.py     # Handles web scraping
│── openai_api.py          # Manages OpenAI API calls
│── utils.py               # Helper functions (QR code, formatting)
│── requirements.txt       # Required dependencies
│── README.md              # Documentation
│── .env                   # Stores OpenAI API key
```

---

## **📌 Function & Class Documentation**

### **🔹 Website Class**
```python
class Website:
    """Scrapes website content and extracts links and text."""
```
- Fetches HTML content from a URL.
- Extracts title, main text, and hyperlinks.
- Cleans irrelevant elements (scripts, styles, images).

### **🔹 detect_language Function**
```python
def detect_language(text):
    """Detects the most probable language of the input text."""
    return langdetect.detect(text)
```

### **🔹 generate_qr_code Function**
```python
def generate_qr_code(url):
    """Generates and saves a QR code for the given URL."""
    qr = qrcode.make(url)
    qr.save("brochure_qr.png")
```

### **🔹 create_brochure Function**
```python
def create_brochure(company_name, url):
    """Generates an SEO-optimized brochure in Markdown format."""
```

---

## **📌 Future Enhancements**
✅ Customizable Formatting – Users can tweak content structure.  
✅ More Language Support – Expand to additional languages and dialects.  
✅ Graphical Interface (GUI) – Develop a user-friendly web-based interface.  
✅ Advanced SEO Analysis – Integrate SEO keyword optimization tools.  
✅ Enhanced Multimedia Options – Add support for social media embeds.  

---

## **📌 Contact**
💬 For inquiries or suggestions, reach out at:  
📧 ihssan.alfaqeah@gmail.com  
🌐 GitHub: [Ihssan80](https://github.com/Ihssan80)
