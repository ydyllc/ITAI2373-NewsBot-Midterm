# NewsBot Intelligence System
### ITAI 2373 | Natural Language Processing Midterm Project

**Developer:** Raymond Newton  
**Course:** ITAI 2373 – Natural Language Processing  
**Institution:** Houston Community College  
**Repository:** https://github.com/ydyllc/ITAI2373-NewsBot-Midterm

## Project Overview

NewsBot Intelligence System is an NLP-powered application developed to analyze news articles, classify them into categories, identify important entities, evaluate sentiment, and generate insights from unstructured text.

The purpose of this project was to demonstrate how the different natural language processing techniques covered throughout the first eight modules of ITAI 2373 could be integrated into one functional system.

Rather than treating preprocessing, text classification, sentiment analysis, and named entity recognition as separate exercises, I wanted to explore how they could work together to produce information that could be useful in media monitoring, research, and business intelligence.

The project was developed using Python and Google Colab, with scikit-learn, spaCy, NLTK, pandas, and additional visualization libraries.

## Project Features

NewsBot integrates eight areas of NLP development:

1. **NLP Application and Business Context:** Identifying practical applications for automated news intelligence.
2. **Text Preprocessing:** Cleaning, tokenization, stop-word handling, and lemmatization.
3. **TF-IDF Analysis:** Transforming text into numerical features and identifying important terms.
4. **Part-of-Speech Tagging:** Examining grammatical patterns across news categories.
5. **Syntax and Semantic Analysis:** Dependency parsing and subject-verb-object relationship extraction.
6. **Sentiment Analysis:** Identifying positive, negative, and neutral emotional tone using VADER.
7. **Text Classification:** Training and comparing machine learning models to predict news categories.
8. **Named Entity Recognition:** Extracting people, organizations, locations, and other named entities using spaCy.

The completed system integrates these components into a pipeline that can process a new headline and article description and return classification, sentiment, entity, and linguistic analysis.

## Dataset

**Dataset:** HuffPost News Category Dataset  
**Author:** Rishabh Misra  
**Source:** https://www.kaggle.com/datasets/rmisra/news-category-dataset

The project uses a reproducible, balanced sample of **2,000 news records** from the original dataset, which contains 209,527 records.

The six classification categories are:

| Category | Articles |
|---|---:|
| Entertainment | 333 |
| Finance | 334 |
| Politics | 333 |
| Sports | 333 |
| Technology | 334 |
| Wellness | 333 |
| **Total** | **2,000** |

The Finance category combines the original Business and Money labels.

**Dataset limitation:** The records contain headlines and brief descriptions rather than full article bodies. NewsBot's findings should be interpreted within that limitation.

## Machine Learning Results

Six classification configurations were compared using stratified cross-validation, including Naive Bayes, Logistic Regression, and Support Vector Machines.

**The best-performing configuration was TF-IDF with Multinomial Naive Bayes.**

| Evaluation metric | Result |
|---|---:|
| Test articles | 400 |
| Correct predictions | 297 |
| Accuracy | 74.25% |
| Macro Precision | 74.38% |
| Macro Recall | 74.30% |
| Macro F1-score | 74.12% |

Sports and Politics achieved the strongest category F1-scores, while Finance was the most challenging category.

One important finding was the overlap between Finance and Technology. Articles discussing technology companies, acquisitions, financial performance, and product development could contain vocabulary associated with both categories.

The results also showed that adding more engineered features did not automatically improve classification performance. The simpler TF-IDF and Naive Bayes approach performed better than the enhanced configurations tested.

Seven end-to-end integration scenarios executed successfully. These tests confirmed that the complete application pipeline could process new inputs, although successful execution should not be confused with perfect classification accuracy.

## Extra-Credit Enhancements

The third notebook extends the original system with additional analysis and an interactive interface.

### Interactive Gradio Dashboard

A Gradio interface allows users to enter a news headline and description and view:

- Predicted news category and model probabilities
- Sentiment analysis
- Named entities
- Generated descriptive insights
- Optional experimental enhanced NER results

The Gradio interface was successfully launched during notebook execution.

### Historical News Analysis

Additional visualizations examine category distributions, sentiment patterns, and selected entity mentions over time.

These analyses are exploratory. The sampled dataset is not evenly distributed across years, so the historical results should not be interpreted as representative trends across the entire news industry.

### Experimental NER Enhancement

An additional research experiment compared standard spaCy named entity recognition with a rule-assisted approach using a fixed entity lexicon.

| NER Method | Strict Entity F1 |
|---|---:|
| spaCy baseline | 74.51% |
| spaCy + fixed lexicon | 96.30% |

The evaluation used 20 manually constructed examples. Although the enhanced method improved performance on this small test set, the results do not establish its accuracy on unseen news articles.

This experiment demonstrates the potential value of domain-specific entity rules, but it is not a separately trained NER model or a production-ready entity resolution system.

## Repository Structure

```text
ITAI2373-NewsBot-Midterm/
├── README.md
├── Notebooks/
│   ├── 01_NewsBot_Validated.ipynb
│   ├── 02_NewsBot_Final.ipynb
│   └── 03_NewsBot_Extra_Credit.ipynb
├── Results/
│   ├── 02_NewsBot_Final_Dashboard/
│   └── 03_NewsBot_Extra_Credit/
└── Reports/
    ├── Technical Analysis Report
    └── Individual Reflection
```

The three notebooks document the development process:

- **01 – Validated:** The completed and evaluated baseline system.
- **02 – Final:** The baseline system with additional analytical summaries and dashboard outputs.
- **03 – Extra Credit:** The most complete version, including the interactive Gradio interface, historical analysis, and experimental NER enhancement.

The Results folders contain exported CSV files supporting the model evaluation and analytical findings. Visualizations and execution outputs are also preserved within the Jupyter notebooks.

## How to Run NewsBot

1. Open `Notebooks/03_NewsBot_Extra_Credit.ipynb` in Google Colab.
2. Use a Python 3 runtime with an internet connection.
3. Select **Runtime → Run all**.
4. Allow the notebook to install required Python packages and NLP resources.
5. The notebook will attempt to retrieve the HuffPost dataset automatically using `kagglehub`. If retrieval fails, follow the notebook's manual dataset-upload instructions.
6. Review the preprocessing, analysis, model evaluation, and integration-test outputs.
7. At the end of the extra-credit notebook, the Gradio interface launches with a temporary public sharing link for interactive testing.

The core project is designed for Google Colab's free CPU environment. No paid GPU or external API service is required.

**Important:** Gradio sharing links are temporary and accessible to anyone who has the link while the session is active. Do not enter confidential or sensitive information into the demonstration.

## Individual Contributions

Although the original assignment was structured as a group project, I completed my NewsBot submission individually.

My contributions included adapting the project requirements into an integrated NLP workflow, preparing the dataset, developing and testing the processing stages, comparing classification approaches, reviewing errors, and interpreting the results.

I also implemented additional analytical features, investigated limitations in named entity recognition, and developed an interactive demonstration interface.

AI-assisted coding tools were used as learning and debugging resources during development. The project documentation explains the methodology, results, limitations, and decisions made throughout the process.

## Business Applications and Future Improvements

NewsBot demonstrates how NLP could support:

- **Media monitoring:** Automatically organizing and examining news coverage.
- **Business intelligence:** Identifying recurring topics, organizations, and sentiment patterns.
- **Research:** Exploring language patterns and relationships across categories.
- **Information management:** Reducing manual effort when organizing large collections of text.

Potential future improvements include expanding the training dataset, introducing contextual embeddings such as BERT, improving entity disambiguation, exploring multi-label classification, and evaluating the system using longer, more recent articles.

The current system is a research and educational prototype. Its predictions and entity relationships should not be treated as verified facts without human review.

## Conclusion

This project helped me understand that developing an NLP system requires more than training a classification model. Data preparation, linguistic context, model evaluation, integration testing, and interpretation all contribute to the reliability of the final results.

NewsBot demonstrates how the techniques covered in ITAI 2373 can be combined into a working application while also identifying opportunities for future improvements.

## References

- Misra, R. *News Category Dataset*. Kaggle. https://www.kaggle.com/datasets/rmisra/news-category-dataset
- Houston Community College. *ITAI 2373 Natural Language Processing, Modules 1–8*. Course instructional materials.
- scikit-learn documentation: https://scikit-learn.org/
- spaCy documentation: https://spacy.io/
- NLTK documentation: https://www.nltk.org/
- Gradio documentation: https://www.gradio.app/
