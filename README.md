pip install rasa spacy pandas numpy
rasa init
version: "2.0"

nlu:
- intent: greet
  examples: |
    - hey
    - hello
    - hi

- intent: ask_question
  examples: |
    - I have a question about my order
    - How can I change my password?

responses:
  utter_greet:
  - text: "Hello! How can I assist you today?"

  utter_ask_question:
  - text: "Sure, please provide more details about your issue."
version: "2.0"

stories:
- story: greet user
  steps:
  - intent: greet
  - action: utter_greet

- story: user asks a question
  steps:
  - intent: ask_question
  - action: utter_ask_question
import pandas as pd
import matplotlib.pyplot as plt

# Load and preprocess data
data = pd.read_csv('support_data.csv')
response_times = data['response_time']
satisfaction_scores = data['satisfaction_score']

# Plot response times
plt.figure(figsize=(10, 6))
plt.hist(response_times, bins=20, color='skyblue')
plt.title('Response Times Distribution')
plt.xlabel('Response Time (minutes)')
plt.ylabel('Frequency')
plt.show()

# Plot satisfaction scores
plt.figure(figsize=(10, 6))
plt.hist(satisfaction_scores, bins=10, color='salmon')
plt.title('Customer Satisfaction Scores')
plt.xlabel('Satisfaction Score')
plt.ylabel('Frequency')
plt.show()
# AI-Driven Customer Support System

## Overview
This project aims to develop an AI-Driven Customer Support System that handles inquiries, triages issues, and provides solutions autonomously. It also analyzes support data to improve response accuracy and efficiency.

## Features
- Natural Language Processing (NLP) for understanding and responding to inquiries.
- Automated responses using a chatbot integrated with a knowledge base.
- Data analysis and reporting to track response times, satisfaction, and issue resolution rates.
- Cloud integration for scalability and reliability.
- Customizable workflows for different customer requirements.

## Technologies Used
- Python, JavaScript (React)
- spaCy, Rasa
- Pandas, NumPy, SQL
- AWS, Google Cloud, Azure
- PostgreSQL, MongoDB
- Matplotlib, Seaborn

## Setup and Installation
1. Clone the repository: `git clone https://github.com/YourUsername/AI-Customer-Support-System`
2. Install dependencies: `pip install -r requirements.txt`
3. Train the Rasa model: `rasa train`
4. Run the chatbot: `rasa shell`

## Usage
Interact with the chatbot to get responses to your inquiries. Analyze the support data for insights.

## License
This project is licensed under the MIT License.
