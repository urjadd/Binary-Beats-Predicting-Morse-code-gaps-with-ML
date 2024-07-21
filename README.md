# Morse Code

### Word Separation Using Two Methods

#### Method 1: Counting Words Using Space Separation
Replaced '/n' (newline) with spaces and split sentences by spaces.

#### Method 2: Word Tokenization
Used the NLTK library for better word separation.

### Data Cleaning

#### Removing Escape Sequences
Used a regular expression pattern `r'\\[a-zA-Z]+|\[a-z]+'` to remove tags and sequence characters from the loaded file.

### Converting Text to Morse Code
Iterated through cleaned text character by character, replacing each with its corresponding Morse code representation based on a predefined dictionary. Stored the result in `morse_text`.

### Introducing Data Corruption for Testing

The `corrupt_data` function randomly replaced a specified percentage of characters in the Morse code text with '?', excluding spaces. It returned the corrupted text and a list of original replaced characters, and printed the count of corrupted characters.

### Predicting Question Mark Labels Using Context

The `predict_question_mark` function used a hash table to predict replacements for '?' in Morse code by comparing dot and dash counts within a context window. It returned a list of predicted characters.

### Evaluating Accuracy of Predictive Model Across Corrupted Data

Evaluated a predictive model's accuracy on corrupted Morse code data. Iterated over varying corruption levels (1%, 2%, 3%, 5%, 10%) and window sizes (2, 3, 4, 5). Organized results into a 2D list for performance analysis.

Accuracy Results: 64% (window_size = 3)

### Generating Morse Code Frequency Features and Creating DataFrame

Replaced a character with '?', calculated features (dot/dash counts and ratios), and compiled these into a DataFrame for analysis.

### Training and Evaluating Models for Morse Code Prediction

#### SVM Classifier
Trained a linear kernel SVM classifier on a 75% training and 25% testing split. Accuracy: 60.97%.

#### Logistic Regression
Trained a Logistic Regression model on a 75% training and 25% testing split. Accuracy: 60.85%.

#### Decision Tree
Trained a Logistic Regression model on a 75% training and 25% testing split. Accuracy: 69%

#### Recurrent Neural Network (RNN)
Developed and trained an RNN with TensorFlow's Keras API. Data was preprocessed, model constructed (embedding, LSTM, and dense layers), and trained over 10 epochs. Evaluated on an 80% training and 20% testing split. Test Accuracy: 62.75%.

##### The Decision Tree model had the highest accuracy at 69%

#### Future Work

1. **Emergency Communication Systems:** Improve Morse code-based emergency communications with error correction and predictive text for reliability.
   
2. **Assistive Communication Devices:** Enhance devices for individuals with impairments by integrating predictive text and error correction for Morse code input.

3. **Historical Document Digitization:** Aid in the accurate transcription and analysis of historical Morse code documents for archival and research purposes.
