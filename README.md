# StudyBot: NLP Study Analytics Chatbot

## Overview

StudyBot is a command-line chatbot built with Python that uses Natural Language Processing (NLP) and machine learning to analyze study-session records.

Instead of manually searching a spreadsheet, users can ask questions in natural language and receive answers calculated from their study data.

The project combines text classification with data analysis to demonstrate how NLP can be applied to a practical problem.

## Features

- **Natural Language Processing:** Tokenizes and processes questions using NLTK.
- **Intent Classification:** Uses TF-IDF and Logistic Regression to identify the user's intended question.
- **Subject Analysis:** Counts recorded sessions by subject.
- **Study Duration Analysis:** Calculates average, total, longest, and shortest elapsed session durations.
- **Productivity Analysis:** Summarizes self-reported study ratings.
- **Break Analysis:** Calculates average recorded breaks and sessions with no breaks.
- **Semester Analysis:** Summarizes study records and ratings by semester.
- **Command-Line Interface:** Allows users to interact with the chatbot directly in the terminal.
- **Data Preprocessing:** Handles missing values, inconsistent whitespace, and invalid time entries.

## Technology Stack

| Technology | Application |
|---|---|
| Python | Core programming language |
| Pandas | Dataset loading and analysis |
| NumPy | Numerical operations |
| NLTK | Text tokenization |
| Scikit-learn | TF-IDF and intent classification |
| Logistic Regression | Predicting question categories |

## Project Structure

```text
studybot-nlp-chatbot/
├── studybot.py
├── study_chart.tsv
├── requirements.txt
├── README.md
└── .gitignore
```

## Dataset

StudyBot uses a tab-separated study log containing the following fields:

- `Subject` — recorded study subject
- `Time started` — session start time
- `Time ending` — session end time
- `Breaks` — recorded break information
- `Rating` — self-reported study rating
- `Semester` — semester associated with the session

The dataset must be named `study_chart.tsv` and placed in the project directory.

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/studybot-nlp-chatbot.git
cd studybot-nlp-chatbot
```

Replace `YOUR-USERNAME` with your GitHub username.

### 2. Create a virtual environment

```bash
python3 -m venv .venv
```

Activate it on macOS or Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add the dataset

Place `study_chart.tsv` in the same directory as `studybot.py`.

### 5. Run the chatbot

```bash
python studybot.py
```

## Example Questions

Users can ask questions such as:

- Which subject did I study the most?
- How many sessions did I record for a particular subject?
- What was my average study duration?
- Which session lasted the longest?
- How many breaks did I take?
- What is my study rating distribution?
- How many study sessions were recorded in each semester?
- How did I perform in Semester 2?

Type `help` to display example questions or `exit` to close the application.

## How It Works

1. **Data loading:** Pandas reads the TSV dataset.
2. **Preprocessing:** The program cleans text fields and parses session times.
3. **Model training:** TF-IDF converts training questions into numerical features.
4. **Intent prediction:** Logistic Regression predicts the most likely question category.
5. **Question filtering:** The program identifies supported subject and semester references.
6. **Answer generation:** Pandas calculates the relevant statistics and returns a text response.

## Limitations

- The classifier uses a small set of manually written training examples.
- Unseen or ambiguous questions may be classified incorrectly.
- Study duration represents elapsed time between recorded start and end times; break durations are not subtracted.
- Subject labels are counted as recorded, so combined-subject entries may be treated separately.
- Ratings represent self-reported assessments and do not independently measure academic performance.
- Semester filters require semester labels to follow a consistent format.

## Future Improvements

- Add a Streamlit web interface.
- Expand the intent training dataset and evaluate classification performance on unseen questions.
- Improve subject and semester entity recognition.
- Add visualizations for study patterns and ratings.
- Introduce automated data validation and unit tests.
- Explore evidence-based descriptive recommendations from study patterns.

## Learning Outcomes

This project demonstrates practical skills in Python programming, NLP preprocessing, supervised text classification, data cleaning, statistical analysis, and command-line application development.

## License

This project is intended for educational and portfolio use. A formal open-source license can be added if the project is to be distributed or reused by others.
