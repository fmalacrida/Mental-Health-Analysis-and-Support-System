# Mental Health Analysis and Support System

## Project Overview
This project combines machine learning and natural language processing to create an intelligent mental health support system. Using the Reddit Mental Health Dataset, it analyzes mental health-related posts to identify potential suicide risk and provides supportive responses through an AI-powered chatbot.

## Dataset
This project uses the **Reddit Mental Health Dataset**, a comprehensive collection of mental health-related posts from various subreddits.

**Dataset Citation:**
```
Low, Daniel M., Laurie Rumker, Tanya Talkar, John Torous, Guillermo Cecchi, and Satrajit S. Ghosh. 
"Natural Language Processing Reveals Vulnerable Mental Health Support Groups and Heightened Health Anxiety on Reddit During COVID-19: Observational Study." 
Journal of Medical Internet Research 22, no. 10 (2020): e22635. 
https://doi.org/10.2196/22635
```

**Dataset Source:** [Zenodo - Reddit Mental Health Dataset](https://zenodo.org/records/3941387)

The dataset includes:
- Mental health-related posts from multiple subreddits
- Posts covering topics like depression, anxiety, suicide, and COVID-19
- Text features and various metrics for analysis
- Pre and post COVID-19 timeframes

## Features
- Advanced text analysis using TF-IDF features
- Ensemble machine learning model for risk assessment
- Real-time risk level detection
- GPT-3.5-powered supportive chatbot
- Comprehensive data preprocessing and feature selection
- Optimized for suicide risk detection

## Project Structure
```
project/
├── data/                            # Data directory
│   ├── COVID19_support_post_features_tfidf_256.csv
│   └── [other CSV files]
├── models/                          # Saved models
│   └── best_model.joblib
├── train_model.py                   # Model training pipeline
├── chatbot.py                       # Chatbot implementation
├── requirements.txt                 # Project dependencies
└── .env                            # Environment variables
```

## Installation

1. Clone the repository:
```bash
git clone [repository-url]
cd [project-directory]
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required packages:
```bash
pip install -r requirements.txt
```

4. Set up environment variables:
Create a `.env` file with:
```
OPENAI_API_KEY=your_openai_api_key_here
```

## Usage

### Training the Model
To train the machine learning model:
```bash
python train_model.py
```

This will:
- Load and process the data
- Train an ensemble of models
- Save the best model to the models directory
- Generate performance metrics and visualizations

### Running the Chatbot
To start the chatbot:
```bash
python chatbot.py
```

The chatbot will:
- Load the trained model
- Initialize the GPT-3.5 interface
- Provide an interactive chat experience
- Monitor risk levels in real-time

## Model Performance
The current model achieves:
- 88% precision for non-suicide posts
- 64% precision for suicide posts
- 90% recall for non-suicide posts
- 59% recall for suicide posts
- Overall accuracy of 83%

## Technical Details

### Machine Learning Pipeline
- Feature extraction using TF-IDF
- SMOTE for handling class imbalance
- Ensemble of RandomForest classifiers
- Feature selection for dimensionality reduction

### Risk Assessment
Risk levels are categorized as:
- Normal: Score < 0.4
- Medium: Score 0.4 - 0.7
- High: Score > 0.7 or presence of high-risk keywords

### Chatbot Architecture
- GPT-3.5-turbo model for response generation
- Real-time risk assessment integration
- Contextual response system
- Crisis resource provision

## Dependencies
- Python 3.8+
- scikit-learn
- pandas
- numpy
- imbalanced-learn
- openai
- python-dotenv
- joblib

## Note on Data Privacy
This system is designed with privacy in mind. All conversations are handled with strict confidentiality, and no personal data is stored beyond the current session.

## Disclaimer
This system is not a replacement for professional mental health care. It is designed to provide support and risk detection but should not be used as the sole source of mental health assistance.

## Contributing
Contributions are welcome! Please read our contributing guidelines before submitting pull requests.

## Acknowledgments
- Reddit Mental Health Dataset creators and contributors
- Mental health communities for providing valuable insights
- OpenAI for GPT-3.5
- Scientific community for mental health research and resources

## Citation
If you use this project or the dataset, please cite:
```
@article{low2020natural,
  title={Natural Language Processing Reveals Vulnerable Mental Health Support Groups and Heightened Health Anxiety on Reddit During COVID-19: Observational Study},
  author={Low, Daniel M and Rumker, Laurie and Talkar, Tanya and Torous, John and Cecchi, Guillermo and Ghosh, Satrajit S},
  journal={Journal of Medical Internet Research},
  volume={22},
  number={10},
  pages={e22635},
  year={2020},
  publisher={JMIR Publications Inc., Toronto, Canada}
}
