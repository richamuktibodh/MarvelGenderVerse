## Project Description
Predicted the sentiment, gender, emotion, and personality of each character using their dialogues across Marvel Universe movies. Got a trend across the movies and characters, and analyzed the results.

## Data
Made the dataset on our own by scraping the Marvel movie scripts, and mapping dialogues to characters. The dataset consists of 15 movies.

## Methodology
1. Sentiment Analysis: Used VADER sentiment analysis tool to predict the sentiment of each dialogue. The dialogues were classified into positive, negative, and neutral sentiments based on the compound score of the VADER.

2. Gender Prediction: We fine-tuned a RoBERTa transformer model by adding a single classification layer on top of the pre-trained model. This was done using the [twitter gender dataset](https://www.kaggle.com/datasets/crowdflower/twitter-user-gender-classification). After this, the transformer weights were frozen and we trained only the linear classification layer on the Marvel dataset. 

3. Emotion Prediction: We used the [GoEmotions dataset](https://huggingface.co/datasets/google-research-datasets/go_emotions) which has 27 unique emotions. We utilised the pre-trained BERT model for zero shot emotion classification on the Marvel Dataset.

4. Personality Prediction: Fine-tuned a RoBERTa transformer model by adding a single classification layer on top of the pre-trained model. This was done using the [MBTI dataset](https://www.kaggle.com/datasnaek/mbti-type) which has 16 unique personality types.

## Results
For a detailed analysis of the results, please refer to the [report](NLP_Project_Report.pdf)

## How to run the code
1. Clone the repository
2. Run the following command to install the required libraries:
```bash
pip install -r requirements.txt
```
3. Since there are 4 different models, the code is divided into 4 different notebooks. Run the following notebooks in the given order:
    - Sentiment Analysis: [here](Sentiment_analysis\sentiment.ipynb) 
    - Gender Prediction: [baseline](gender_analysis\Baseline_for_gender_Classification.ipynb), [RoBERTa](gender_analysis\gender-classification.ipynb)
    - Emotion Prediction: [here](Go_Emotions_analysis\goEmotionInference.ipynb)
    - Personality Prediction: [BERT](personality_analysis\MBTI_bert.ipynb), [RoBERTa](personality_analysis\MBTI_roberta.ipynb)

<!-- ## Contributors -->
