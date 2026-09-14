# Estatística com Python: Probabilidade, Amostragem e Estimação

Projeto educacional composto por notebooks Jupyter para estudar conceitos fundamentais de Estatística usando Python. O material combina explicações, fórmulas, exemplos resolvidos, simulações e exercícios aplicados a uma base de dados da Pesquisa Nacional por Amostra de Domicílios (PNAD) de 2015.

## Objetivos

- Explorar uma base tabular com informações demográficas e de renda.
- Aplicar distribuições de probabilidade binomial, de Poisson e normal.
- Compreender o uso de população, amostra e amostragem aleatória simples.
- Simular o Teorema Central do Limite.
- Calcular probabilidades, margens de erro, intervalos e níveis de confiança.
- Determinar tamanhos de amostra considerando precisão, confiança e orçamento.
- Oferecer exercícios reproduzíveis para prática local.

## Conteúdos trabalhados

O notebook principal percorre cinco blocos:

1. **Conhecendo os dados** — carrega e apresenta a base PNAD utilizada no projeto.
2. **Distribuições de probabilidade** — exemplos de distribuição binomial, Poisson e normal, incluindo combinações e cálculos com `scipy.stats`.
3. **Amostragem** — diferencia população e amostra e demonstra amostragem aleatória simples, estratificada e por conglomerados.
4. **Estimação** — aborda Teorema Central do Limite, erro inferencial e intervalos de confiança.
5. **Cálculo do tamanho da amostra** — estima o número de observações necessário a partir do erro máximo, desvio padrão e nível de confiança.

O notebook de estimativas complementa o material com problemas práticos sobre composição de grupos, renda média, custos de entrevista, margem de erro e restrições orçamentárias.

## Estrutura

```text
.
├── dados/
│   └── dados.csv
├── Estimativas.ipynb
├── Projeto_Estatística_com_Python_probabilidade_e_amostragem.ipynb
├── Versão_bibliotecas.ipynb
├── README.md
└── requirements.txt
```

| Item | Finalidade |
| --- | --- |
| `Projeto_Estatística_com_Python_probabilidade_e_amostragem.ipynb` | Notebook principal, com teoria, exemplos e simulações. |
| `Estimativas.ipynb` | Exercícios e aplicações de probabilidades, amostragem e estimação. |
| `Versão_bibliotecas.ipynb` | Consulta as versões das bibliotecas usadas no ambiente. |
| `dados/dados.csv` | Base de dados consumida pelos notebooks. |

## Dados

O arquivo `dados/dados.csv` possui 76.840 registros e as colunas abaixo:

| Coluna | Descrição |
| --- | --- |
| `UF` | Código da unidade federativa. |
| `Sexo` | Código do sexo do respondente. |
| `Idade` | Idade em anos. |
| `Cor` | Código de cor ou raça. |
| `Anos de Estudo` | Anos/categoria de escolaridade. |
| `Renda` | Rendimento mensal do trabalho principal. |
| `Altura` | Altura em metros; variável elaborada para o material. |

Segundo a documentação dos notebooks, a fonte de referência é a [PNAD 2015 do IBGE](https://ww2.ibge.gov.br/home/estatistica/populacao/trabalhoerendimento/pnad2015/microdados.shtm). Os dados distribuídos no projeto já passaram por tratamento: rendas inválidas ou ausentes foram removidas e foram mantidos registros de pessoas de referência do domicílio.

## Tecnologias

- **Python** — linguagem dos cálculos e simulações.
- **JupyterLab/Jupyter Notebook** — ambiente interativo para abrir e executar os arquivos `.ipynb`.
- **Pandas** — leitura e manipulação dos dados CSV.
- **NumPy** — operações numéricas.
- **SciPy** — distribuições estatísticas, combinações, probabilidades e intervalos de confiança.
- **Matplotlib** — gráficos, como histogramas das médias amostrais.
- **ipykernel** — disponibiliza o kernel Python no Jupyter.

## Como executar localmente

### Pré-requisitos

- Python 3.10 ou superior;
- `pip`, o gerenciador de pacotes do Python;
- Git é opcional, caso o projeto seja clonado por repositório.

### 1. Obtenha o projeto

Clone o repositório, se ele estiver hospedado em uma plataforma Git, ou baixe/descompacte os arquivos mantendo a pasta `dados` no mesmo nível dos notebooks.

```bash
git clone <URL_DO_REPOSITORIO>
cd estatistica-com-python-probabilidade-amostragem
```

### 2. Crie e ative um ambiente virtual

No Windows (PowerShell):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

No macOS ou Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Instale as dependências

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### 4. Inicie o JupyterLab

```bash
jupyter lab
```

No navegador, abra `Projeto_Estatística_com_Python_probabilidade_e_amostragem.ipynb`. Para os exercícios, abra depois `Estimativas.ipynb`.

## Ordem recomendada de estudo

1. Execute `Versão_bibliotecas.ipynb` para conferir o ambiente.
2. Execute o notebook principal de cima para baixo.
3. Abra `Estimativas.ipynb` e resolva ou revise as atividades.

Algumas células dependem de variáveis criadas anteriormente; por isso, para reproduzir os resultados, execute cada notebook na ordem em que as células aparecem. As amostras que usam `random_state=101` tendem a produzir os mesmos resultados em execuções equivalentes.

## Informações importantes para compartilhamento

- O caminho do arquivo de dados é relativo: `dados/dados.csv`. Não mova o CSV sem atualizar os notebooks.
- O projeto foi criado como material didático e não como uma aplicação web ou pacote Python instalável.
- Os notebooks registram versões históricas de `pandas`, `numpy`, `scipy` e `matplotlib`; o `requirements.txt` propõe versões atuais compatíveis com Python moderno e com as APIs empregadas no material.
- Para uma nova análise, prefira trabalhar em uma cópia dos notebooks ou criar um notebook adicional, preservando a base original.
- Ao redistribuir ou publicar análises derivadas, mantenha a atribuição à fonte dos dados, o IBGE/PNAD 2015, e verifique as condições de uso aplicáveis.

## Arquitetura resumida

```text
dados/dados.csv
       │
       ▼
Notebooks Jupyter ──► Pandas/NumPy ──► SciPy (cálculos estatísticos)
       │                                      │
       └──────────────────────────────► Matplotlib (visualizações)
```

O projeto centraliza conteúdo, código e resultados nos notebooks. O CSV funciona como fonte local única; as bibliotecas Python realizam a preparação leve dos dados, os cálculos estatísticos e as visualizações.
