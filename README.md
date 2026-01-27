# googlemaps-restaurant-review-llm-extraction

LLM-powered information extraction from Google Maps restaurant reviews. Using Llama 3.1 (Groq API) to extract structured sentiment and aspect-based insights for ML-based rating prediction.

## Overview

This project demonstrates automatic extraction of structured information from unstructured restaurant review text using Large Language Models (LLMs). The extracted data is used for:
- Aspect-based sentiment analysis (food, service, atmosphere, price, cleanliness, location)
- Predictive modeling (Random Forest) to predict ratings
- Exploratory data analysis and visualization

## Tech Stack

- **LLM**: Llama-3.1-8b-instant via Groq API
- **Framework**: LangChain with Pydantic schemas
- **ML**: scikit-learn (Random Forest)
- **Data**: pandas, numpy
- **Visualization**: matplotlib, seaborn

## Setup

1. Clone the repository:
```bash
git clone https://github.com/ConeCode003/googlemaps-restaurant-review-llm-extraction.git
cd googlemaps-restaurant-review-llm-extraction
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up environment variables:
Create a `.env` file with your Groq API key:
```
GROQ_API_KEY=your_api_key_here
```

4. Run the notebook:
```bash
jupyter notebook main.ipynb
```

## Project Structure

- `main.ipynb` - Main analysis notebook with data cleaning, LLM extraction, and ML modeling
- `prompts.py` - LLM system prompts and extraction schema
- `requirements.txt` - Python dependencies
- `data/reviews.csv` - Restaurant reviews dataset

## Features

- **Data Cleaning**: Filtering short reviews, text length analysis
- **LLM Extraction**: Structured extraction of sentiment and aspect-based comments
- **Predictive Analysis**: Random Forest model for rating prediction
- **Visualizations**: KDE plots, feature importance, confusion matrices

## Dataset

The dataset contains Google Maps-style restaurant reviews with:
- Business name
- Review text
- Rating (1-5 stars)

Source: [Kaggle - Google Maps Restaurant Reviews](https://www.kaggle.com/datasets/denizbilginn/google-maps-restaurant-reviews)

## Key Insights

- Reviews are filtered to remove very short texts (< 10th percentile)
- LLM extracts 6 aspect categories with positive/negative comments
- Random Forest model predicts ratings based on extracted features

## License

This project is for educational purposes.
