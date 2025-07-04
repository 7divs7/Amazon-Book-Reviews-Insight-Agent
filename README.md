![LangGraph](https://img.shields.io/badge/LLM_Orchestration-LangGraph-blueviolet)
![Claude](https://img.shields.io/badge/LLM-Claude_3.7-9cf)
![Databricks](https://img.shields.io/badge/Platform-Databricks-orange)
![UnityCatalog](https://img.shields.io/badge/Data%20Access-Unity_Catalog-green)
![Genie](https://img.shields.io/badge/AI/BI-Genie_Spaces-ff69b4)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle-yellow)


# ⭐ Amazon Review Insight Agent

An LLM-powered, agentic system that enables natural language exploration of Amazon product reviews. Built with **LangGraph**, **Claude** and **Databricks AI/BI Genie**, it allows users to ask flexible questions and get structured, sentiment-rich insights from large-scale product review data.

📦 Dataset: [Amazon Product Reviews (Kaggle)](https://www.kaggle.com/datasets/datafiniti/consumer-reviews-of-amazon-products)

---

## 🔍 Example Queries

- "What do customers dislike about Samsung headphones?"
- "Summarise the sentiment around Kindle's battery life."
- "What are the top complaints in the electronics category?"
- "Compare positive reviews between Bose and JBL speakers."

---

## 🕸️ Graph
- Planner: Parses user intent, generates task prompts
- AI/ BI Genie: Filters reviews from a Delta Table in Unity Catalog
- Analyzer: Uses Claude to extract sentiment, keywords, and summaries

```mermaid
---
config:
  theme: redux
---

flowchart TD
    A(["User Query"])
    A --> B{"Planner (Claude LLM)"}
    B --> C["Genie Agent (Delta Table Filter)"]
    B --> D["Analyzer (Claude LLM)"]
    C --> E["Filtered Reviews"]
    E --> D
    D --> F["Final Insight"]
```

---

## 🚀 How to Run
Set up and run the Amazon Review Insight Agent locally in just a few steps:

1. Clone the Repository
  ```bash
  git clone https://github.com/7divs7/amazon-review-insight-agent.git
  cd amazon-review-insight-agent
  ```
2. Install Dependencies

  Make sure you have Python 3.9 or above installed.
  ```bash
  pip install -r requirements.txt
  ```

3. Set Environment Variables

  Create a .env file in the root folder and add the following:
  ```bash
  ANTHROPIC_API_KEY=your_claude_api_key
  DATABRICKS_HOST=https://<your-workspace>.cloud.databricks.com
  DATABRICKS_TOKEN=your_personal_access_token
  ```

5. Run the Agent

  Simply run the script to interact with the LangGraph-powered pipeline:
  ```bash
  python amazon_review_agent.py
  ```
  
  Or import and invoke it inside another script or notebook:
  ```bash
  from amazon_review_agent import run_review_agent
  
  query = "Summarize what customers are saying about Kindle battery life."
  response = run_review_agent(query)
  print(response)
  ```

---

### 📁 Project Structure

```vbnet
amazon-review-insight-agent/
├── amazon_review_agent.py
├── README.md
├── requirements.txt
├── .env.example
```

---

## 💬 Want to Turn This Into a Chat App?
This project can be easily extended into a chat-based web application using tools like Streamlit or Gradio. By wrapping the LangGraph chain in a backend function, users can ask natural language questions and receive real-time insights from Amazon product reviews. The agent can also be deployed as a model serving endpoint in Databricks, with a custom UI (e.g., Streamlit) as the frontend. This makes it well-suited for building interactive product feedback assistants or customer experience dashboards.

## 🙋‍♀️ Author
**Divyani Panda**  
_Data Scientist \| Agentic AI Developer_  

[![LinkedIn-profile](https://img.shields.io/badge/LinkedIn-Profile-teal.svg)](https://www.linkedin.com/in/divyani-panda-5a8345194/)
[![shields.io](https://img.shields.io/badge/Website-divyanipanda.com-orange)](https://www.divyanipanda.com/)

