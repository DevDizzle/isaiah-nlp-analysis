# Isaiah NLP Analysis

This repository provides an open-source Natural Language Processing (NLP) pipeline to analyze the biblical Book of Isaiah. It includes:

- **Data ingestion** from [api.scripture.api.bible](https://docs.api.bible).
- **Text cleaning** (HTML removal, lemmatization, stopword removal).
- **Word embeddings** using BERT.
- **Clustering** using K-Means and visualization with UMAP.
- **Topic Modeling** with LDA.
- **Summarization** of topics using Google Gemini (optional).

## Project Structure

\`\`\`
isaiah-nlp-analysis/
├── .gitignore
├── .env.example
├── LICENSE
├── README.md
├── requirements.txt
├── notebooks/
│   └── Scripture-Viz.ipynb
├── data/
├── artifacts/
└── scripts/
    ├── __init__.py
    ├── main.py
    ├── ingest.py
    ├── cleaning.py
    ├── embeddings.py
    ├── clustering.py
    ├── topic_modeling.py
    └── summarization.py
\`\`\`

- **\`scripts/\`**: Contains modular Python files for different steps of the pipeline.
- **\`main.py\`**: Orchestrates the entire workflow.
- **\`notebooks/\`**: Jupyter notebooks for demonstrations or quick explorations.
- **\`data/\`**: (Optional) place for local data.
- **\`artifacts/\`**: Output files such as plots (\`.png\`), CSVs, or models.

## Getting Started

1. **Clone the Repository**

   \`\`\`bash
   git clone https://github.com/yourusername/isaiah-nlp-analysis.git
   cd isaiah-nlp-analysis
   \`\`\`

2. **Create and Activate a Virtual Environment** (Optional but recommended)

   \`\`\`bash
   python3 -m venv venv
   source venv/bin/activate    # On macOS/Linux
   venv\\Scripts\\activate     # On Windows
   \`\`\`

3. **Install Requirements**

   \`\`\`bash
   pip install --upgrade pip
   pip install -r requirements.txt
   \`\`\`

4. **Setup Environment Variables**

   - Copy \`.env.example\` to \`.env\`:
     \`\`\`bash
     cp .env.example .env
     \`\`\`
   - Add your **API_KEY** (from [api.scripture.api.bible](https://docs.api.bible)) and **GEMINI_API_KEY** if you plan to run Gemini summarization.

5. **Run the Pipeline**

   \`\`\`bash
   python scripts/main.py
   \`\`\`

   This will:
   - Fetch Isaiah verses via the Bible API.
   - Clean and preprocess the text.
   - Generate embeddings, run clustering, and save visualizations to \`artifacts/\`.
   - Perform LDA topic modeling and save outputs in \`artifacts/\`.
   - Summarize the text (if **GEMINI_API_KEY** is provided).

## Notebooks

- \`Scripture-Viz.ipynb\`: An older or exploratory notebook that originally contained all the code, now split into separate scripts for maintainability. You can still use it for interactive experimentation.

## Contributing

1. Fork the repository.
2. Create a new branch: \`git checkout -b feature/my-feature\`.
3. Make your changes.
4. Submit a Pull Request.

## License

This project is licensed under the [MIT License](LICENSE). Feel free to modify to meet your needs.
