# Fine-Tuning-BERT-Automated-Essay-Scoring
The project investigates the use of a pre-trained NLP model (BERT) for automating essay scoring using a regression technique. We compared two approaches: 1) Fine-tuning BERT on IELTS essay responses with the prompt given to the students, and 2) Doing the same as approach 1 but with added custom features extracted from the dataset.

# Overview-Goals
The goal is to compare AI-driven scoring with human scoring to assess the accuracy and efficiency of AI in educational assessments. We also aim to test the capabilities and strengths of the BERT model. For this reason, in model two, we added additional features to see if there would be any improvement.

# Problem statment/Why?
NLP algorithms are being used to score essays, but it’s unclear how well they compare to human scorers. In general, human scoring of essays is slow and can be inconsistent, for instance, the same test scorer might give the same piece of writing different score depanding in so many factors. In contrast, AI can score essays quickly and consistently but struggles with understanding nuanced language. This project compares AI-driven scoring using the BERT model with human scoring to see if AI can be just as accurate and efficient.

# Data Collection and Preprocessing
We used the IELTS writing scored essays dataset from Kaggle. The dataset includes two types of essays, task 1 and task 2. Since task 1 assesses the candidate's ability to analyze a graph or chart, we decided to focus only on task 2 and filtered out task 1 in the preprocessing stage.

For the second model, we extracted the following features in the same Google Colab document:
- The length of the essay.
- Number of linking words.
- Number of unique words.
- Number of spelling errors.
- Synonyms used.
- Grammar mistakes (using the LanguageTool tool).

# Methods
1. We fine-tuned the BERT model with the dataset we found on Kaggle, without extracting additional features, to test the capabilities of the BERT model in scoring IELTS essay tasks.
2. Similarly, we fine-tuned the BERT model, but this time we extracted additional features before the fine-tuning step. This was done to see if we could improve the accuracy compared to the first model.

- We split the dataset into a training set, cross-validation set, and testing set (more details in the Google Colab document).
- Normalization of the extracted features was performed.

Fine-Tuning Steps We Followed:

1. Call the pre-trained model (Source of model: https://huggingface.co/google-bert/bert-base-cased)
2. Call the tokenizer.
3. Convert the tokenized inputs and labels into TensorFlow datasets.
4. Train the model.

# How to use?
1- Clone the repository:

git clone https://github.com/AhmedAlabkri/Fine-Tuning-BERT-Automated-Essay-Scoring.git

cd Fine-Tuning-BERT-Automated-Essay-Scoring

2- Install the dependencies from the requirements.txt:

pip install -r requirements.txt

3- Then you can run the notebooks, run all the cells in each notebook to execute the code and reproduce the results.

# Key Findings
- Both models demonstrated the potential to score IELTS essays, with the first model showing slightly better performance on test data.
  
- The inclusion of custom features in the second model did not significantly improve accuracy, highlighting the robustness of the BERT model alone.

- While the models showed potential, the current scoring accuracy of the BERT model still needs improvement to match the precision of human evaluators.

- The Mean Absolute Error (MAE) was used as the evaluation metric, showing close performance between training and test datasets, indicating minimal overfitting.

# Significance
- This project underscores the viability of using AI for automated essay scoring, which can enhance the efficiency of educational assessments.

- The results suggest that while BERT-based models can provide consistent scoring, further refinement is necessary to achieve accuracy comparable to human evaluators, thereby reducing time and cost associated with manual grading.


# Authors
- Ahmed Alabkri
- Ernest Amoateng

# References
- The pre-trained model from Huggingface: https://huggingface.co/google-bert/bert-base-cased
- IELTS scores from Kaggle: https://www.kaggle.com/datasets/mazlumi/ielts-writing-scored-essays-dataset/data

