# Trabalho Final — Inteligência Artificial
## Previsão de salários em vagas de TI

**Autores:** Ígor Tavares Rocha e Rafael Afonso Labarrere  
**Problema:** regressão supervisionada para estimar salário em USD a partir de texto e atributos estruturados.

## Objetivo

O projeto combina representações textuais extraídas pelo BERT com variáveis estruturadas de vagas de emprego, alimentando uma rede densa em PyTorch. O notebook atual é uma versão integrada para execução local e substitui as referências antigas a quatro notebooks que ainda não existem no repositório.

## Dataset

O notebook espera o arquivo `data/ai_job_dataset.csv` na raiz do projeto. As colunas principais usadas são `salary_usd` (alvo), `job_title` e `required_skills`; quando presentes, também utiliza atributos como experiência, modalidade remota, localização, setor e porte da empresa.

O notebook falha com uma mensagem explícita se o arquivo ou as colunas essenciais estiverem ausentes. Confirme que o CSV corresponde a esse esquema: ele não é o mesmo esquema descrito em versões anteriores deste README (`title`, `description`, `salary`).

## Estrutura do repositório

```text
Machine-Learning/
├── data/
│   └── ai_job_dataset.csv
├── artifacts/                         # cache local dos embeddings BERT (gerado)
├── models/                            # modelo e métricas (gerados)
├── trabalho_final_igor_rafael_v02.ipynb
├── trabalho_final_igor_rafael_v01.ipynb # versão anterior
├── requirements.txt
├── .gitignore
└── README.md
```

As pastas `artifacts/` e `models/` são criadas pelo notebook e seus conteúdos não são versionados por padrão.

## Requisitos

- Python 3.10 ou 3.11 recomendado.
- Jupyter Notebook ou extensão Jupyter no VS Code.
- Internet na primeira execução para baixar o modelo `bert-base-uncased`.
- CPU funciona, mas a extração de embeddings pode ser demorada. GPU NVIDIA com CUDA, se disponível e configurada no PyTorch, pode acelerar essa etapa.

## Como executar localmente

No terminal, na raiz do repositório:

```powershell
py -3.10 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Coloque/confirme o dataset em `data/ai_job_dataset.csv`. Depois, abra `trabalho_final_igor_rafael_v02.ipynb` no VS Code/Jupyter e execute as células em ordem. Não é necessário montar Google Drive nem executar comandos `pip install` dentro do notebook.

### Execução de demonstração vs. experimento completo

Por padrão, `MAX_ROWS = 1000` para permitir verificar o fluxo com custo menor. Para processar todos os registros, altere para `MAX_ROWS = None`; isso pode exigir bastante tempo e memória, especialmente em CPU. O notebook salva os embeddings em cache para reutilizá-los quando o texto e a configuração permanecerem iguais.

## Pipeline

1. Carregamento e validação do CSV.
2. Limpeza da variável-alvo e criação do texto a partir do título e das habilidades.
3. Separação treino/validação antes do ajuste dos transformadores.
4. Imputação e transformação de atributos estruturados.
5. Extração congelada de embeddings BERT em lotes, com cache.
6. Treinamento de uma rede densa em PyTorch.
7. Avaliação com MAE, MSE, RMSE e R², além de gráficos.
8. Salvamento do modelo, pré-processador e métricas em `models/`.

## Métricas

- **MAE:** média dos erros absolutos, na unidade do alvo (USD).
- **MSE:** média dos erros quadráticos, em USD².
- **RMSE:** raiz do MSE, na unidade do alvo (USD).
- **R²:** comparação do modelo com um baseline que prevê a média; pode ser negativo.

## Limitações importantes

- Os resultados só devem ser considerados finais após executar o notebook completo e registrar as métricas obtidas.
- O modo de demonstração usa uma amostra e não deve ser comparado diretamente com resultados do dataset inteiro.
- O notebook atual faz regressão salarial, mas não analisa sozinho a evolução temporal dos salários. Para sustentar essa parte do tema, é necessário estudar a variável temporal do dataset e realizar uma avaliação temporal.
- Compare o modelo híbrido com baselines mais simples para medir se a complexidade do BERT traz benefício real.
