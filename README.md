
# E-commerce Product Assistant

A Streamlit-based web application for scraping product reviews from Flipkart and storing them in AstraDB vector database for AI-powered product analysis.

## Features

- 🛒 **Product Scraping**: Scrape product reviews from Flipkart
- 📊 **Data Processing**: Transform and process scraped data
- 🧠 **Vector Storage**: Store data in AstraDB for AI analysis
- 📱 **Web Interface**: User-friendly Streamlit interface
- 🔍 **Search & Analysis**: AI-powered product search and recommendations

## Prerequisites

- Python 3.10+
- [uv](https://docs.astral.sh/uv/) package manager
- AstraDB account and credentials
- Google API key for embeddings

## Installation

### 1. Clone the Repository
```bash
git clone <repository-url>
cd ecomm-prod-assistant
```

### 2. Install Dependencies with uv
```bash
# Install all dependencies from requirements.txt
uv pip install -r requirements.txt

# Install additional required packages
uv pip install langchain-google-genai==2.1.8
uv pip install langchain-astradb
```

### 3. Environment Setup
Create a `.env` file in the project root with the following variables:
```env
GOOGLE_API_KEY=your_google_api_key_here
ASTRA_DB_API_ENDPOINT=your_astra_db_endpoint_here
ASTRA_DB_APPLICATION_TOKEN=your_astra_db_token_here
ASTRA_DB_KEYSPACE=your_keyspace_name_here
GROQ_API_KEY=your_groq_api_key_here
```

## Running the Application

### Method 1: Using Virtual Environment Python (Recommended)
```bash
.\venv\Scripts\python.exe -m streamlit run scrapper_ui.py --server.port 8508
```

### Method 2: Using uv run
```bash
uv run streamlit run scrapper_ui.py --server.port 8508
```

### Method 3: Traditional pip (if uv is not available)
```bash
# Activate virtual environment
.\venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
pip install langchain-google-genai==2.1.8

# Run the application
streamlit run scrapper_ui.py --server.port 8508
```

## Access the Application

Once running, open your browser and navigate to:
- **Local URL**: http://localhost:8508
- **Network URL**: http://192.168.178.22:8508

## Usage

1. **Enter Product Names**: Add one or more product names you want to scrape
2. **Configure Parameters**: Set the number of products and reviews per product
3. **Start Scraping**: Click "Start Scraping" to begin the process
4. **Download Data**: Download the scraped data as CSV
5. **Store in Vector DB**: Store the data in AstraDB for AI analysis

## Troubleshooting

### Common Issues

1. **ModuleNotFoundError**: Ensure all dependencies are installed using `uv pip install`
2. **Port Already in Use**: Change the port number in the run command
3. **Environment Variables**: Make sure all required environment variables are set in `.env` file

### Dependencies

Key packages used:
- `streamlit==1.49.1` - Web interface
- `langchain-google-genai==2.1.8` - Google AI integration
- `langchain-astradb==0.6.1` - AstraDB vector store
- `selenium==4.35.0` - Web scraping
- `beautifulsoup4==4.13.5` - HTML parsing

## Project Structure

```
ecomm-prod-assistant/
├── prod_assistant/
│   ├── etl/                 # Data extraction and transformation
│   ├── utils/               # Utility functions and model loaders
│   ├── workflow/            # AI workflows
│   └── config/              # Configuration files
├── data/                    # Scraped data storage
├── templates/               # HTML templates
├── static/                  # Static assets
└── scrapper_ui.py          # Main Streamlit application
```
