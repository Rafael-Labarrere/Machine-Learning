# Machine Learning

Repositório de estudos e projetos de **Aprendizado de Máquina**, desenvolvidos em Python durante minha formação em Ciência da Computação. Os notebooks exploram etapas do fluxo de trabalho de dados — exploração, pré-processamento, classificação, processamento de linguagem natural e regressão.

> **Organização:** os projetos estão organizados em diretórios na branch `main`. Cada pasta reúne o notebook e, quando aplicável, o README, as dependências e os dados necessários. Consulte a documentação de cada projeto para conhecer seus requisitos e caminhos de arquivos.

## Projetos

### 1. Previsão de salários em vagas de TI — Trabalho Final

**Autores:** Ígor Tavares Rocha e Rafael Afonso Labarrere

Projeto de regressão supervisionada para estimar salários de vagas de tecnologia a partir de atributos textuais e estruturados. Os notebooks exploram preparação de dados, transformação de atributos, representações textuais e avaliação de modelos. Consulte a documentação do projeto para identificar as diferenças entre as versões e os métodos utilizados em cada notebook.

- [Pasta do projeto, notebooks e arquivos](https://github.com/Rafael-Labarrere/Machine-Learning/tree/main/Trabalho%20Final)
- [README e instruções de execução](https://github.com/Rafael-Labarrere/Machine-Learning/blob/main/Trabalho%20Final/README.md)
- **Etapas:** preparação dos dados, transformação de atributos, modelagem e avaliação com métricas como MAE, MSE, RMSE e R².
- **Dataset:** consulte o README do projeto para obter o caminho esperado para `ai_job_dataset.csv` e as instruções de execução.

### 2. Processamento de Linguagem Natural (NLP)

Introdução a técnicas de processamento de texto em Python, incluindo expressões regulares, tokenização, normalização, análise de frequência de palavras e representações numéricas de documentos.

- [Pasta do projeto e notebook](https://github.com/Rafael-Labarrere/Machine-Learning/tree/main/NLP)
- [README e instruções de execução](https://github.com/Rafael-Labarrere/Machine-Learning/blob/main/NLP/README.md)
- **Notebook:** `Natural_language_Processing.ipynb`.
- **Tecnologias e conceitos:** NLTK, Gensim, pandas, Matplotlib, Bag of Words, dicionários de tokens e TF-IDF.

### 3. Pré-processamento de dados para análise de risco de crédito

Estudo de exploração e preparação de dados tabulares, com atenção a valores inconsistentes, dados ausentes e distribuição das variáveis.

- [Pasta do projeto e notebook](https://github.com/Rafael-Labarrere/Machine-Learning/tree/main/Risco-De-Cr%C3%A9dito)
- [README e instruções de execução](https://github.com/Rafael-Labarrere/Machine-Learning/blob/main/Risco-De-Cr%C3%A9dito/README.md)
- **Notebook:** `1_1_Inconsistentes_e_Faltantes.ipynb`.
- Os dados ficam na pasta `data/`; confira o README do projeto para os passos de execução.

### 4. Classificação de câncer de mama e métricas de avaliação

Exercício de classificação com o dataset de câncer de mama, voltado à compreensão e interpretação de métricas de desempenho de modelos.

- [Pasta do projeto e notebook](https://github.com/Rafael-Labarrere/Machine-Learning/tree/main/Breast%20Cancer)
- [README do projeto](https://github.com/Rafael-Labarrere/Machine-Learning/blob/main/Breast%20Cancer/README.md)
- **Notebook:** `Exemplo_metricas_cancer.ipynb`.
- **Tecnologias documentadas:** scikit-learn, NumPy, pandas, Matplotlib e Seaborn.

### 5. Classificação com o dataset Iris

Exercício introdutório de aprendizado de máquina com o conjunto de dados Iris, usado para explorar um problema clássico de classificação.

- [Pasta do projeto e notebook](https://github.com/Rafael-Labarrere/Machine-Learning/tree/main/ML%20Iris%20DataSet)
- [README e instruções de execução](https://github.com/Rafael-Labarrere/Machine-Learning/blob/main/ML%20Iris%20DataSet/README.md)
- **Notebook:** `machine_learning_with_iris_dataset.ipynb`.
- Consulte o README do projeto para confirmar o local do dataset e as instruções de instalação das dependências.

## Tecnologias e ferramentas

- **Linguagem:** Python
- **Ambiente:** Jupyter Notebook, VS Code e Google Colab
- **Manipulação e análise de dados:** pandas e NumPy
- **Aprendizado de máquina:** scikit-learn
- **NLP e modelos de linguagem:** NLTK, Gensim e Transformers/BERT
- **Modelos neurais:** PyTorch
- **Visualização:** Matplotlib e Seaborn

As tecnologias e dependências variam entre projetos. Consulte o README e o arquivo de dependências de cada projeto para obter instruções específicas.

## Como executar os notebooks

1. Abra a pasta do projeto desejado pelos links acima.
2. Leia o README específico do projeto antes de executar o notebook.
3. Instale uma versão de Python compatível com as dependências do projeto.
4. Crie e ative um ambiente virtual, quando recomendado.
5. Instale as dependências usando o arquivo `requirements.txt` existente na pasta do projeto.
6. Disponibilize os arquivos de dados nos caminhos esperados pelo notebook.
7. Abra o arquivo `.ipynb` no Jupyter Notebook, JupyterLab ou VS Code e execute as células em ordem.

Exemplo de criação de ambiente virtual no Windows (execute os comandos a partir da pasta do projeto):

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
```

**Dados e licenças:** os conjuntos de dados podem ter origens e licenças diferentes. Verifique a documentação de cada projeto antes de redistribuir os dados. Se um dataset não estiver incluído no repositório, siga as instruções do README correspondente para obtê-lo.

## Objetivo do repositório

Registrar a evolução prática em aprendizado de máquina, desde exercícios introdutórios de classificação e preparação de dados até projetos com dados textuais e tabulares. A organização em diretórios na branch `main` facilita a navegação e ajuda a encontrar os notebooks, as dependências e as instruções de reprodução de cada experimento.
