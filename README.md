**Full-Stack-Agentic-Framework-for-Natural-Language-to-SQL-Translation**

**Overview**

This project develops a full-stack web application that translates natural language queries into SQL statements using a Large Language Model (LLM) pipeline, enabling non-technical users to interact with relational databases effortlessly. The system uses the Spider Dataset, fine-tuned LLaMA 3.1 8B model, and an agentic layer to handle ambiguity resolution, schema validation, and runtime query diagnostics. It features a Streamlit front-end, SQLite backend, and Ollama-based local LLM inference.

**Objectives**

•	Allow users to query databases in plain English.
•	Automatically generate accurate SQL queries from natural language.
•	Execute queries and display results in a clear, interactive UI.
•	Detect ambiguous queries and ask clarifying questions.
•	Provide schema-aware validation to ensure correctness.

**📂 Dataset**
The project uses the Spider Dataset (xlangai/spider), a large-scale cross-domain benchmark for Text-to-SQL tasks.
•	Domains: Education, aviation, music, and more.
•	Data format: SQLite databases with multiple tables, schema files, and query mappings.
•	Includes 200 database schemas, natural language questions, and ground-truth SQL queries.

**🛠 Tech Stack**
•	Frontend: Streamlit (interactive UI)
•	Backend: Python, SQLite, SQLAlchemy
•	LLM: LLaMA 3.1 8B Instruct (fine-tuned with LoRA)
•	Deployment: Ollama (local inference)
•	Visualization: Plotly (dynamic charts)
•	Version Control & Hosting: Hugging Face (model hosting)

**🔍 Key Features**
1.	Natural Language to SQL Conversion – Converts user queries into schema-aware SQL statements.
2.	Ambiguity Resolution – Detects unclear queries and requests clarification.
3.	Schema Viewer – Displays database tables, columns, and relationships.
4.	Query History – Stores previous queries, SQL outputs, and results.
5.	Error Handling – Suggests corrections for invalid SQL or schema mismatches.
6.	Interactive Visualizations – Auto-generates bar, pie, and scatter plots for results.
7.	Local LLM Execution – Uses Ollama for CPU-based inference to avoid cloud dependencies.
   
**🧠 Model Implementation**
1.Pretraining
•	Loaded meta-llama/Llama-3.1-8B-Instruct with 4-bit quantization for efficiency.
•	Used Hugging Face for model hosting and retrieval.
2.Fine-tuning with LoRA
•	Fine-tuned on Spider Dataset using LoRA to train only 0.67% of model parameters.
•	Training setup:
o	Learning rate: 2e-4
o	Scheduler: Cosine decay
o	Epochs: 3
o	Tracking: Weights & Biases
•	Achieved BLEU: 0.5158, Exact Match: 0.2400, SQL Accuracy: 0.2400.

**📊 Performance**
Metric	Pretrained	Fine-tuned
BLEU Score	0.3925	0.5158
Exact Match	0.0700	0.2400
SQL Accuracy	0.0700	0.2400

**🚀 Process**
1.	User Input: A natural language query is entered into the Streamlit UI.
2.	Ambiguity Check: The agent detects unclear queries and requests more details if necessary.
3.	Prompt Creation: Schema details + user query → prompt for LLaMA model.
4.	SQL Generation: Model returns one or more candidate queries.
5.	Validation & Execution: Query is checked for schema compliance, then executed on SQLite DB.
6.	Result Display: Interactive table + downloadable CSV + auto-generated visualizations.


