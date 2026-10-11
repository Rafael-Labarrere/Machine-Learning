# Natural Language Processing (NLP)

This project contains a Jupyter Notebook with introductory exercises in **Natural Language Processing (NLP)** using Python. It covers regular expressions, tokenization, text normalization, word-frequency analysis, and text vectorization with Gensim.

## Topics covered

- **Regular expressions (`re`)** — find patterns and extract text.
- **NLTK** — tokenize text, use stop words, and explore lemmatization.
- **Bag of Words** — count token frequencies in an article.
- **Gensim** — build a dictionary from documents and explore Bag of Words and TF-IDF representations.
- **Matplotlib** — visualize text-related data.

## Requirements

- Python 3.10 or newer
- Jupyter Notebook
- Packages listed in [`requirements.txt`](requirements.txt)

The built-in Python module `re` does not need to be installed separately.

## Set up locally

### 1. Clone the repository and switch to the correct branch

```bash
git clone https://github.com/Rafael-Labarrere/Machine-Learning.git
cd Machine-Learning
git switch Natural-Language-Processing
```

If you already have a local copy, open the repository directory and switch to the branch above.

### 2. Create and activate a virtual environment

**Windows PowerShell:**

```powershell
py -m venv .venv
.venv\Scripts\Activate.ps1
```

If PowerShell prevents activation, you can use Command Prompt:

```bat
.venv\Scripts\activate.bat
```

**macOS / Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install the dependencies

With the virtual environment activated, run these commands from the repository root:

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### 4. Launch the notebook

```bash
jupyter notebook
```

Open `Natural_Language_Processing.ipynb` and run the cells in order. In VS Code, you can open the notebook with the Jupyter extension and select the `.venv` environment as its kernel.

The notebook downloads the NLTK resources it uses (including `punkt`, `wordnet`, `omw-1.4`, and `stopwords`). An internet connection may be required the first time those resources are downloaded.

## Input text files

The notebook reads three text files from the repository's **`tests/`** directory. Make sure the filenames and folder name match this structure:

```text
Machine-Learning/
├── tests/
│   ├── holy_grail.txt
│   ├── debugging.txt
│   └── articles.txt
├── Natural_Language_Processing.ipynb
├── README.md
└── requirements.txt
```

Create the `tests/` folder if it does not exist, and place all three files inside it before running the cells that load them. The notebook's paths should point to `tests/holy_grail.txt`, `tests/debugging.txt`, and `tests/articles.txt`.

- **`holy_grail.txt`** — sample text used in the line-length visualization exercise. The suggested sample text is sufficient, and you may replace it with text you have permission to use.
- **`debugging.txt`** — an English article about software debugging, used for tokenization and word-frequency counting.
- **`articles.txt`** — a small collection of documents used in the Gensim dictionary exercise. Put **one document per line**. The example below includes the word `transport`, which the notebook looks up in the dictionary.

Example content for `articles.txt`:

```text
Public transport connects neighborhoods and helps people travel across a city.
Software debugging helps developers find bugs and fix errors in computer programs.
Electric buses can reduce pollution and improve urban transport systems.
Machine learning uses data to identify patterns and make predictions.
Reliable transport networks support commuters, businesses, and local communities.
```

These are sample inputs, not a fixed dataset. You can replace them with other appropriate text, but the notebook's results will change accordingly.

## Running in Google Colab

Use the **Open in Colab** badge at the top of the notebook. If a package is missing in Colab, run `%pip install -r requirements.txt` after making the repository files available to the session, or install the listed packages directly. The `tests/` text files must also be accessible at the expected paths in the Colab session.

## Learning objectives

After completing the notebook, you should have practical experience with common NLP preprocessing steps and understand how text documents can be converted into numerical representations. The Gensim exercises introduce dictionaries, Bag of Words, and **TF-IDF** (Term Frequency–Inverse Document Frequency).

## References

- [NLTK documentation](https://www.nltk.org/)
- [Gensim documentation](https://radimrehurek.com/gensim/)
- [Jupyter documentation](https://docs.jupyter.org/)
