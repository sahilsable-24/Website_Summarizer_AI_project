# 🌐 Website Summarizer AI

A Python-based AI tool that scrapes the content of any website and generates a concise, readable summary using the OpenAI API. Built and explored interactively in a Jupyter Notebook.

---

## ✨ Features

- Fetches and parses website content using `requests` and `BeautifulSoup`
- Strips away noise (scripts, styles, images, inputs) to extract clean text
- Extracts all hyperlinks from a given page
- Sends the cleaned content to OpenAI's API and returns an AI-generated summary
- Environment variables used to keep API keys secure

---

## 🗂️ Project Structure

```
Website_Summarizer_AI_project/
│
├── scrapper.py                  # Web scraping utilities (fetch content & links)
├── website_summarizer_ai.ipynb  # Main Jupyter Notebook (summarization logic)
├── requirements.txt             # Python dependencies
├── .env                         # API key configuration (not committed to VCS)
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/sahilsable-24/Website_Summarizer_AI_project.git
cd Website_Summarizer_AI_project
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Set up your API key

Create a `.env` file in the project root and add your OpenAI API key:

```
OPENAI_API_KEY=your_openai_api_key_here
```

### 4. Run the notebook

Open `website_summarizer_ai.ipynb` in Jupyter and run the cells:

```bash
jupyter notebook website_summarizer_ai.ipynb
```

---

## 🧰 Dependencies

| Package          | Purpose                              |
|-----------------|--------------------------------------|
| `openai`         | OpenAI API client for summarization  |
| `requests`       | HTTP requests to fetch web pages     |
| `beautifulsoup4` | HTML parsing and content extraction  |
| `python-dotenv`  | Load environment variables from `.env` |
| `ipykernel`      | Jupyter Notebook kernel support      |

---

## 🔧 How It Works

1. **`fetch_website_content(url)`** — Sends an HTTP GET request to the target URL, parses the HTML with BeautifulSoup, removes irrelevant tags, and returns up to 2,000 characters of clean body text along with the page title.

2. **`fetch_website_links(url)`** — Extracts all anchor tag `href` values from the page and returns a filtered list of valid links.

3. **Summarization** — The extracted content is passed to the OpenAI API (via the notebook), which generates a concise summary of the page.

---

## ⚠️ Notes
- The scraper currently truncates content to 2,000 characters before sending to the API. You can adjust this limit in `scrapper.py`.
- Some websites may block automated requests or require JavaScript rendering — this tool works best with static HTML pages.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
