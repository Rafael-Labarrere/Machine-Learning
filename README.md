# Natural Language Processing (NLP)

This branch contains a Jupyter Notebook with introductory exercises in **Natural Language Processing (NLP)** using Python. It explores text processing techniques, from regular expressions and tokenization to lexical normalization and basic text-vectorization methods.

## Topics covered

- **Regular expressions (`re`)** — find patterns, split text, and extract words, numbers, hashtags, and mentions.
- **Tokenization with NLTK** — split text into sentences and tokens, including social-media text.
- **Text normalization** — work with stop words and lemmatization.
- **Gensim** — build a token dictionary, convert documents into a bag-of-words representation, and calculate TF-IDF weights.
- **Basic visualization** — visualize sentence or line-length distributions with Matplotlib.

## Tools and libraries

- Python 3.10 or newer
- Jupyter Notebook
- [NLTK](https://www.nltk.org/) for tokenization, stop words, and WordNet tools
- [Gensim](https://radimrehurek.com/gensim/) for dictionary/corpus construction and TF-IDF
- pandas for tabular data handling
- Matplotlib for plots

Python's built-in `re` module is used for regular expressions and does not need to be installed separately.

## Set up the environment

### 1. Clone the repository and switch to this branch

~~~bash
git clone https://github.com/Rafael-Labarrere/Machine-Learning.git
cd Machine-Learning
git switch Natural-Language-Processing
~~~

If you already have the repository locally, open its folder and run `git switch Natural-Language-Processing`.

### 2. Create and activate a virtual environment

**Windows (PowerShell):**

~~~powershell
py -m venv .venv
.venv\\Scripts\\Activate.ps1
~~~

If PowerShell blocks activation, you can use Command Prompt instead:

~~~bat
.venv\\Scripts\\activate.bat
~~~

**macOS / Linux:**

~~~bash
python3 -m venv .venv
source .venv/bin/activate
~~~

### 3. Install dependencies

With the virtual environment activated, run:

~~~bash
python -m pip install --upgrade pip
python -m pip install jupyter nltk pandas matplotlib gensim
~~~

### 4. Download the NLTK resources

Run this once in the activated environment:

~~~bash
python -c "import nltk; nltk.download('punkt'); nltk.download('punkt_tab'); nltk.download('wordnet'); nltk.download('omw-1.4'); nltk.download('stopwords')"
~~~

Some NLTK versions do not require every resource listed above, but downloading them helps avoid common tokenizer and corpus lookup errors.

### 5. Launch the notebook

From the repository root:

~~~bash
jupyter notebook
~~~

Open **Natural_Language_Processing.ipynb** in the browser and run the cells from top to bottom. You can also open the notebook in VS Code with the Jupyter extension and select the .venv Python interpreter as the kernel.

## Running in Google Colab

The notebook includes an **Open in Colab** badge. Open the notebook in Colab and run the cells in order. Install any missing packages in a notebook cell with:

~~~python
%pip install nltk pandas matplotlib gensim
~~~

The notebook downloads NLTK resources in its setup cell. Colab sessions are temporary, so package installations and downloaded files may need to be repeated in a new session.

## Input text files

The notebook uses three plain-text files stored in the `data/` folder at the repository root:

```text
Machine-Learning/
├── data/
│   ├── holy_grail.txt
│   ├── debugging.txt
│   └── articles.txt
├── Natural_Language_Processing.ipynb
└── README.md
```

Create the `data/` folder and add all three files before running the cells that read them. The filenames are case-sensitive on some systems, so keep them exactly as shown. The notebook expects the paths `data/holy_grail.txt`, `data/debugging.txt`, and `data/articles.txt`.

- **`holy_grail.txt`** — text for the line-length histogram exercise. The repository's suggested sample text is fine; you can replace it with other text you have permission to use.
- **`debugging.txt`** — an English article about software debugging, used to count the most frequent tokens with a Bag of Words approach.
- **`articles.txt`** — a small collection of documents for the Gensim dictionary exercise. Put **one document per line**. The example below includes the word `transport`, which the notebook looks up in the dictionary.

Example content for `articles.txt`:

```text
Public transport connects neighborhoods and helps people travel across a city.
Software debugging helps developers find bugs and fix errors in computer programs.
Electric buses can reduce pollution and improve urban transport systems.
Machine learning uses data to identify patterns and make predictions.
Reliable transport networks support commuters, businesses, and local communities.
```

The text in these files is sample input, not a required dataset. You can replace it with other suitable text; the results will change accordingly.
## Learning objectives

By completing the notebook, you should gain practical experience with common NLP preprocessing steps and understand how a collection of text documents can be transformed into numerical representations. The Gensim examples introduce a dictionary and bag-of-words corpus, followed by **TF-IDF** (Term Frequency–Inverse Document Frequency), which gives higher weight to terms that are more informative within a document collection.

## References

- [NLTK documentation](https://www.nltk.org/)
- [Gensim documentation](https://radimrehurek.com/gensim/)
- [Jupyter documentation](https://docs.jupyter.org/)
