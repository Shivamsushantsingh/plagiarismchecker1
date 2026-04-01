# AI-Based Plagiarism Checker

##  Overview

This project is an **AI-powered Plagiarism Detection System** built using **Natural Language Processing (NLP)** techniques. It detects textual similarity between documents using **TF-IDF vectorization** and **Cosine Similarity**, enabling efficient identification of duplicate or plagiarized content.



## Key Features

* Detects plagiarism using similarity scoring
* Generates real-time similarity percentage
* NLP-based preprocessing (tokenization, stopword removal)
* Efficient vector-based text comparison using TF-IDF
* Supports large datasets for training and testing
* Model saving using Pickle for reuse



## Tech Stack

* **Language:** Python
* **Libraries:**

  * NLTK (Text preprocessing)
  * Scikit-learn (TF-IDF, similarity, evaluation)
  * NumPy (Numerical computations)
* **Modeling:** TF-IDF + Cosine Similarity
* **Dataset:** Custom dataset (`train_snli.txt`)



## Workflow

### Data Loading

* Reads dataset from `.txt` file
* Splits into:

  * Training set (80%)
  * Testing set (20%)



### Text Preprocessing

* Convert text to lowercase
* Remove punctuation and numbers
* Tokenization using NLTK
* Stopword removal
* Cleaned text reconstruction



### Feature Engineering

* Converts text into numerical form using:

  * **TF-IDF Vectorizer**



### Similarity Computation

* Uses:

  * **Cosine Similarity**
* Compares input text with all training documents



###  Plagiarism Detection

* Based on similarity threshold:

  * Default threshold = **0.8**
* Outputs:

  * Similarity score
  * Plagiarism status
  * Most similar document



## Model Evaluation

* Evaluated using test dataset
* Metric used:

  * **Accuracy Score**

Example Output:


Model Accuracy: 60.00%




## Demo Example


Input: "Machine learning powers modern technology"

Output:
Similarity Score: 0.82
Plagiarism Detected: True
Most Similar Document: <matched training text>




## Installation

```bash
git clone https://github.com/Shivamsushantsingh/plagiarismchecker1.git
cd plagiarismchecker1
pip install -r requirements.txt
```



##  Usage

```bash
python plagiarism_checker.py
```



##  Project Structure

```
📦 plagiarismchecker1
 ┣  dataset
 ┃ ┗ train_snli.txt
 ┣  plagiarism_checker.py
 ┣  README.md
 ┗  plagiarism_checker.pkl
```



##  Model Saving

* Model is saved using **Pickle** for reuse:

```python
with open('plagiarism_checker.pkl', 'wb') as f:
    pickle.dump(...)
```



##  Dataset Statistics

* Total Documents: ~10,000
* Training Data: 80%
* Testing Data: 20%
* Vocabulary Size: Generated dynamically



##  Use Cases

* Academic plagiarism detection
* Content originality checking
* Assignment evaluation systems
* Blog/article duplication analysis



##  Future Improvements

*  Deep Learning models (BERT, Transformers)
*  Support for PDF/DOCX files
*  Web deployment using Flask/FastAPI
*  Visualization dashboard



##  Contributing

Contributions are welcome! Feel free to fork the repo and submit pull requests.

---

