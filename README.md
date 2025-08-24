# ⚡ Recommendify.AI — An AI-Powered YouTube Product Review Analyzer

## 👉 **[Skip the scroll and get instant product verdicts with the power of AI!](https://github.com/Rayan-Farhan/Recommendify.AI)**

This **AI-powered product review analyzer** helps you decide whether to buy a product by analyzing the most relevant **YouTube reviews** — all through intelligent **AI agents** and **LLMs**!

Tired of watching 10+ videos just to figure out if a product is worth it? Let Recommendify.AI do the heavy lifting in seconds.

https://github.com/user-attachments/assets/8fe0d675-7bd6-48cf-8b7c-3b0e78170643

---

## Why Recommendify.AI?

- **Saves Hours** – No more endless video browsing
- **Summarized Insights** – Clear Pros & Cons extracted from video transcripts
- **Smart Filtering** – Uses AI to detect which videos are actual reviews
- **LLM Verdict Engine** – Aggregates review sentiment into a clear "Buy" or "Skip"
- **Simple UI** – Just type in a product name and hit enter
- **LangGraph Agent Flow** – Designed with modular AI workflows

---

## How It Works

The tool workflow is powered by a sequence of intelligent agents:

### 1. Product Specificity Check
- The AI agent determines whether your query refers to a **specific product** (e.g., *iPhone 15 Pro*) or a **generic category** (e.g., *phones*).
- Generic queries are rejected to ensure precise verdicts.

### 2. YouTube Video Search
- Searches for review videos on YouTube using `youtube-search-python`.

### 3. Transcript Fetching
- Automatically fetches video transcripts using the `youtube-transcript-api`.

### 4. Relevance Filtering
- Uses a **Groq + LLaMA3** agent to detect if the video actually reviews the product.
- Filters out irrelevant or clickbait videos.

### 5. Summarization
- Another LLM agent reads the transcript and extracts a **list of pros and cons**.

### 6. Verdict Aggregation
- A final expert agent analyzes all summaries and outputs:
  - **Recommendation**: Recommended or Not Recommended
  - **Reason**: Concise explanation based on review sentiment

---

## Project Structure

```
Recommendify.AI/
├── agents_modules/
│   ├── __init__.py              # Import setup
│   ├── product_checker.py       # Checks product specificity
│   ├── relevance_filter.py      # Filters out non-relevant videos
│   ├── transcript_fetcher.py    # Fetches YouTube transcripts
│   ├── transcript_summarizer.py # Summarizes the pros and cons
│   ├── verdict_aggregator.py    # Gives final verdict
│   └── youtube_search.py        # Searches YouTube
├── graph.py                     # LangGraph AI agent pipeline
├── main.py                      # FastAPI backend
├── app.py                       # Streamlit frontend
├── runme.bat                    # Batch script to run both backend and frontend
├── .env                         # API key (you create this)
├── requirements.txt             # Dependencies
└── README.md                    # You’re reading it!
```

---

## How to Use

### 1. Clone the Repo

```bash
git clone https://github.com/Rayan-Farhan/Recommendify.AI.git
cd Recommendify.AI
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Add Your API Key

Create a `.env` file in the root directory:

```env
GROQ_API_KEY = your_groq_api_key
```

Get your GROQ API KEY from [here](https://groq.com)

### 4. Run the Tool

Either run everything at once using:

```bash
runme.bat
```

Or manually:

```bash
# Start backend
uvicorn main:app --reload

# In a separate terminal
streamlit run app.py
```

### 5. Try It Out!

Open the Streamlit app in your browser.

Enter a specific product name like:

- Sony WH-1000XM5  
- iPhone 15 Pro Max  
- DJI Mini 4 Pro  
- Tesla Model 3 2024  
- HyperX Cloud 2

---

## Output

Once the process completes, you get:

**Final Verdict** – "Recommended" or "Not Recommended"  
**Reason** – Summarized insight from 5 videos  
**Transparent summaries** of all analyzed videos  

Perfect for quick research, buyers on the fence, or even for affiliate marketers who want fast product insights!

---

## Built With

- **LangGraph** – AI agent state machine framework  
- **Groq + LLaMA3** – For LLM agents  
- **Streamlit** – Interactive frontend  
- **FastAPI** – Lightweight backend server  
- **YouTube APIs** – To fetch review data

---

## **Contributing**

Contributions are welcome! Please open an issue or submit a pull request for any changes. 

---

## **Contact**

If you have any questions or suggestions, feel free to reach out!

