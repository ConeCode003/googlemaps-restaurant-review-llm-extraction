# googlemaps-restaurant-review-llm-extraction

LLM-powered information extraction from Google Maps restaurant reviews. Using Llama 3.1 (Groq API) to extract structured sentiment and aspect-based insights for ML-based rating prediction.

## Overview

This project demonstrates automatic extraction of structured information from unstructured restaurant review text using Large Language Models (LLMs). The extracted data is used for:
- Aspect-based sentiment analysis (food, service, atmosphere, price, cleanliness, location)
- Predictive modeling to predict human ratings based on extracted text features
- **Self-consistency validation**: Measuring how well LLM-extracted evidence predicts the LLM's own final sentiment
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

- **Data Cleaning**: Filtering short reviews and text length distribution analysis
- **LLM Extraction**: Structured extraction of sentiment and aspect-based insights
- **Predictive Analysis**: Random Forest models for both human ratings and LLM self-consistency check
- **Self-Consistency Analysis**: Validating if LLM conclusions are logically founded on extracted evidence
- **Visualizations**: KDE plots, Feature Importance, and Confusion Matrices for both models

## Dataset

The dataset contains Google Maps-style restaurant reviews with:
- Business name
- Author name
- Photo
- Review text
- Rating (1-5 stars)
- Rating category

Source: [Kaggle - Google Maps Restaurant Reviews](https://www.kaggle.com/datasets/denizbilginn/google-maps-restaurant-reviews)

## Key Insights

- Reviews are filtered to remove very short texts (< 10th percentile) to ensure quality extraction.
- LLM successfully extracts 6 aspect categories with high granularity.
- **Human Rating Prediction (Accuracy ~58.3%)**: Proves that extracted text features are strong predictors of actual guest satisfaction.
- **LLM Self-Consistency (Accuracy ~55%)**: Reveals that LLM sentiment is more nuanced than simple feature counting, often weighing specific critical issues (e.g., hygiene) more heavily than general praise.

## License

This project is for educational purposes.
