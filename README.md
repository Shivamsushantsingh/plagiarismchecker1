# AI-Based Plagiarism Detection System

##  Overview

This project is an **AI-powered plagiarism detection system** built using **Natural Language Processing (NLP)** techniques. It analyzes textual similarity between documents using **TF-IDF vectorization** and **Cosine Similarity** to identify potentially plagiarized content.

The system is designed to efficiently compare large volumes of text and provide **similarity scores, plagiarism detection results, and nearest matching documents**.



##  Key Features

*  Detects plagiarism using similarity scoring
*  Generates real-time similarity percentage
*  NLP preprocessing (tokenization, stopword removal, cleaning)
*  Efficient large-scale document comparison using TF-IDF
*  Handles datasets with thousands of documents
*  Model persistence using Pickle



##  Tech Stack

* **Language:** Python
* **Libraries:**

  * NLTK (Text preprocessing)
  * Scikit-learn (TF-IDF, similarity, evaluation)
  * NumPy (Numerical computations)
* **Techniques:** TF-IDF, Cosine Similarity
* **Dataset:** SNLI-based text dataset (`train_snli.txt`)



## System Workflow

###  Data Processing

* Loads dataset from `.txt` file
* Splits into training (80%) and testing (20%)



###  Text Preprocessing

* Lowercasing
* Removal of punctuation and numbers
* Tokenization using NLTK
* Stopword removal
* Clean text reconstruction



###  Feature Engineering

* Converts text into numerical vectors using:

  * **TF-IDF Vectorizer**



###  Similarity Computation

* Computes similarity using:

  * **Cosine Similarity**
* Compares input text with all training documents



###  Plagiarism Detection Logic

* Uses threshold-based classification:

  * Default threshold: **0.5 (tuned for better performance)**
* Outputs:

  * Similarity score
  * Plagiarism detection result
  * Most similar document



##  Model Performance

| Metric          | Value           |
| --------------- | --------------- |
| Accuracy        | ~54% (baseline) |
| Dataset Size    | ~367K documents |
| Vocabulary Size | ~27K            |

###  Note:

* Lower accuracy is due to:

  * Use of **TF-IDF (lexical similarity only)**
  



##  Sample Output

```id="xj7q3w"
Input: "Machine learning powers modern technology"

Similarity Score: 0.41  
Plagiarism Detected: False  
Most Similar Document: "A teacher and students learning through technology"
```



## Installation

```bash id="n2c6x1"
git clone https://github.com/Shivamsushantsingh/plagiarismchecker1.git
cd plagiarismchecker1
pip install -r requirements.txt
```



## Usage

```bash id="7n7r5t"
python plagiarism_checker.py
```


##  Project Structure

```id="qz0fuv"
 plagiarismchecker1
 ┣  dataset
 ┃ ┗ train_snli.txt
 ┣  plagiarism_checker.py
 ┣  README.md
 ┗  plagiarism_checker.pkl
```



##  Model Saving

```python id="l0k3ds"
with open('plagiarism_checker.pkl', 'wb') as f:
    pickle.dump({
        'vectorizer': vectorizer,
        'tfidf_matrix': tfidf_train,
        'threshold': threshold
    }, f)
```



##  Limitations

* TF-IDF captures only **word-level similarity**, not semantic meaning
* Dataset (SNLI) is not optimized for plagiarism detection
* Performance depends heavily on threshold tuning

---

##  Future Improvements

*  Implement **BERT / Sentence Transformers** for semantic similarity
*  Add support for PDF/DOCX file inputs
*  Build web interface using Flask/FastAPI
*  Improve accuracy using domain-specific plagiarism datasets
*  Optimize threshold using validation techniques



##  Use Cases

* Academic plagiarism detection
* Content originality verification
* Assignment evaluation systems
* Blog/article duplication analysis



##  Contributing

Contributions are welcome! Feel free to fork the repository and submit pull requests.



