# NLP Knowledge Pipeline: AI in Healthcare

This project implements a multi-step Natural Language Processing (NLP) pipeline designed to automate the collection, classification, and synthesis of articles related to Artificial Intelligence in the healthcare sector. The project integrates web scraping of dynamic content, zero-shot classification, and a Retrieval-Augmented Generation (RAG) system to transform raw web data into structured, actionable insights.

This project was developed as part of the **NLP and Web Analytics course** at the **Free University of Bozen-Bolzano**.

## Project Overview

The objective is to build an automated system capable of navigating the "Knowledge Pipeline" from data acquisition to evaluation. The key stages of the project are:
* **Web Scraping:** Extracting dynamic content from the Harvard Gazette using Selenium and BeautifulSoup.
* **Text Classification:** Categorizing articles into specific medical AI domains using Zero-Shot techniques.
* **Information Retrieval (RAG):** Creating a vector-based search system using FAISS and SentenceTransformers.
* **Summarization & Evaluation:** Generating AI-driven summaries via GPT-4o and evaluating prompt effectiveness.

## Repository Structure
```
├── ai_healthcare_articles.csv                          # Dataset of scraped articles
├── Assignment-NLP-WebAnalytics_TESSARI_19322.ipynb     # Main Jupyter notebook with code
├── Assignment-NLP-WebAnalytics_TESSARI_19322.html      # Exported HTML version of the notebook
├── Assignment-NLP-WebAnalytics_TESSARI_19322.pdf       # Final project report in PDF
├── embeddings.index                                    # FAISS vector index for RAG
├── evaluated_summaries.json                            # Summaries and evaluations output
├── requirements.txt                                    # Dependencies for the project
├── .gitignore                                          # Files excluded from the repository
└── README.md                                           # Project README file
```

## Key Files

* **Assignment-NLP-WebAnalytics_TESSARI_19322.ipynb**: The main notebook containing the full pipeline: scraping, preprocessing, embedding generation, RAG system, and LLM interaction.
* **Assignment-NLP-WebAnalytics_TESSARI_19322.html**: A web-ready export of the notebook, useful for quick viewing of code and visualizations directly in the browser.
* **ai_healthcare_articles.csv**: The curated dataset generated during the scraping phase, containing titles, URLs, and full text content.
* **embeddings.index**: The binary index file created with FAISS to allow for fast semantic search within the scraped articles.
* **requirements.txt**: The list of Python dependencies required to recreate the environment.

## How to Run

1. **Clone the repository**
```bash
git clone https://github.com/artessari/NLP_KnowledgePipeline_AI-Healthcare
cd NLP_KnowledgePipeline_AI-Healthcare
```

2. **Install Dependencies**
To install the required Python libraries, run:
```bash
pip install -r requirements.txt
```

3. **Set up API Keys**
Create a `.env` file in the root directory and add your OpenAI API key:
```bash
OPENAI_API_KEY=your_api_key_here
```

4. **Run Jupyter Notebook**
Launch the main notebook to explore the pipeline step-by-step.

## NLP Techniques & Models Implemented

* **Dynamic Scraping:** `Selenium` for handling JavaScript-rendered search results from dynamic news sources.
* **Zero-Shot Classification:** Leveraging `facebook/bart-large-mnli` for flexible thematic labeling without task-specific training.
* **Vector Embeddings:** `all-MiniLM-L6-v2` (Sentence-Transformers) for creating efficient and dense semantic vector representations.
* **Vector Store:** `FAISS` (Facebook AI Similarity Search) for high-performance similarity indexing and retrieval.
* **Generative AI:** `OpenAI GPT-4o` for RAG-based Question Answering and context-aware Summarization.

## Results & Conclusions

The project demonstrates that integrating a **RAG (Retrieval-Augmented Generation)** architecture significantly reduces hallucinations in Large Language Models by grounding responses in a specific, verified dataset. 

Key findings from the evaluation phase:
* **Prompt Engineering:** Role-based prompting (e.g., "Act as a Medical Researcher") consistently produces more professional, accurate, and structured medical summaries compared to baseline instructions.
* **Pipeline Efficiency:** The combination of FAISS and lightweight embeddings allows for a responsive knowledge pipeline that scales effectively even with complex article content.

### References

* **Harvard Gazette** - Science & Technology Section. [news.harvard.edu](https://news.harvard.edu/gazette/)
* **OpenAI API** Documentation. [platform.openai.com](https://platform.openai.com/docs/)
* **Hugging Face** Transformers Library. [huggingface.co/docs/transformers](https://huggingface.co/docs/transformers)

