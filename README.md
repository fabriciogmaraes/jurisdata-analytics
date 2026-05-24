# JurisData Analytics

**PT** | [EN](#en)

---

## PT

Pipeline de jurimetria trabalhista aplicado às decisões do TRT-21 (Rio Grande do Norte), combinando engenharia de dados, NLP e LLM para identificar padrões de litígios e estimar risco de condenação por categoria de reclamação.

### Stack

Python 3.13 · PostgreSQL · Power BI · scikit-learn · Llama 3.3 70b · Groq API

### Fases

- [x] Fase 1 — Ingestão de dados (API CNJ DataJud → PostgreSQL)
- [x] Fase 2 — Modelagem relacional (star schema, views analíticas, feature store)
- [x] Fase 3 — NLP e clustering de decisões
- [x] Fase 4 — Pareceres automáticos com LLM
- [x] Fase 5 — Dashboard executivo no Power BI

### Dados

40.232 processos · Classe 985 (Ação Trabalhista - Rito Ordinário) · Período 2018–2024 · TRT-21/RN<br>
Star schema: 3 dimensões · 1 tabela fato · 3 views analíticas · Feature store (40.154 registros)<br>
K-Means k=3 · Silhouette=0.339 · Davies-Bouldin=0.836<br>
Clusters: Litígios Antigos (18.934) · Litígios Recentes (21.181) · Casos Atípicos (39)<br>
10 pareceres gerados · Llama 3.3 70b (Groq) · RAG via PostgreSQL · 8.312 tokens consumidos<br>
Power BI: 3 telas · Panorama geral · Análise de clusters · Calculadora de risco trabalhista

### Estrutura do projeto

```text
jurisdata/
├── notebooks/
│   ├── 01_ingestion.ipynb        # Ingestão API DataJud → PostgreSQL
│   ├── 02_modeling.ipynb         # Star schema, views, feature store
│   ├── 03_nlp_clustering.ipynb   # Pré-processamento, PCA, K-Means
│   └── 04_llm_pareceres.ipynb    # RAG + Llama 3.3 70b (Groq)
├── outputs/
│   └── figures/
│       └── clusters_pca_2d.png   # Visualização 2D dos clusters
├── dashboard/
│   └── JurisData.pbix            # Dashboard Power BI (3 telas)
├── .env.example                  # Variáveis de ambiente necessárias
└── README.md
```

### Pré-requisitos

- Python 3.13+
- PostgreSQL 14+
- Power BI Desktop
- Conta no [CNJ DataJud](https://datajud-wiki.cnj.jus.br/api-publica/acesso/) (API Key gratuita)
- Conta no [Groq](https://console.groq.com) (gratuito)

### Como executar

**1. Clone o repositório**

    git clone https://github.com/fabriciogmaraes/jurisdata-analytics.git
    cd jurisdata-analytics

**2. Configure as variáveis de ambiente**

    cp .env.example .env

**3. Crie o banco de dados**

    CREATE DATABASE jurisdata;

**4. Execute os notebooks em ordem**

    01_ingestion.ipynb → 02_modeling.ipynb → 03_nlp_clustering.ipynb → 04_llm_pareceres.ipynb

**5. Abra o dashboard**

    Abra JurisData.pbix no Power BI Desktop e conecte ao seu PostgreSQL local

### Autor

Fabricio Guimarães — Analista de Dados · Mestrando em Inteligência Computacional (PPgTI/UFRN)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/fabriciogmaraes)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:fabriciogmaraes@hotmail.com)

---

## EN

<a name="en"></a>

Labor litigation analytics pipeline applied to decisions from TRT-21 (Rio Grande do Norte, Brazil), combining data engineering, NLP and LLM to identify litigation patterns and estimate conviction risk by claim category.

### Stack

Python 3.13 · PostgreSQL · Power BI · scikit-learn · Llama 3.3 70b · Groq API

### Phases

- [x] Phase 1 — Data ingestion (CNJ DataJud API → PostgreSQL)
- [x] Phase 2 — Relational modeling (star schema, analytical views, feature store)
- [x] Phase 3 — NLP and decision clustering
- [x] Phase 4 — Automated legal briefs with LLM
- [x] Phase 5 — Executive dashboard in Power BI

### Data

40,232 cases · Class 985 (Labor Lawsuit - Ordinary Rite) · Period 2018–2024 · TRT-21/RN<br>
Star schema: 3 dimensions · 1 fact table · 3 analytical views · Feature store (40,154 records)<br>
K-Means k=3 · Silhouette=0.339 · Davies-Bouldin=0.836<br>
Clusters: Ancient Litigation (18,934) · Recent Litigation (21,181) · Atypical Cases (39)<br>
10 legal briefs generated · Llama 3.3 70b (Groq) · RAG via PostgreSQL · 8,312 tokens consumed<br>
Power BI: 3 pages · General overview · Cluster analysis · Labor risk calculator

### Project structure

```text
jurisdata/
├── notebooks/
│   ├── 01_ingestion.ipynb        # DataJud API ingestion → PostgreSQL
│   ├── 02_modeling.ipynb         # Star schema, views, feature store
│   ├── 03_nlp_clustering.ipynb   # Preprocessing, PCA, K-Means
│   └── 04_llm_pareceres.ipynb    # RAG + Llama 3.3 70b (Groq)
├── outputs/
│   └── figures/
│       └── clusters_pca_2d.png   # 2D cluster visualization
├── dashboard/
│   └── JurisData.pbix            # Power BI dashboard (3 pages)
├── .env.example                  # Required environment variables
└── README.md
```

### Prerequisites

- Python 3.13+
- PostgreSQL 14+
- Power BI Desktop
- [CNJ DataJud](https://datajud-wiki.cnj.jus.br/api-publica/acesso/) account (free API Key)
- [Groq](https://console.groq.com) account (free)

### How to run

**1. Clone the repository**

    git clone https://github.com/fabriciogmaraes/jurisdata-analytics.git
    cd jurisdata-analytics

**2. Set up environment variables**

    cp .env.example .env

**3. Create the database**

    CREATE DATABASE jurisdata;

**4. Run the notebooks in order**

    01_ingestion.ipynb → 02_modeling.ipynb → 03_nlp_clustering.ipynb → 04_llm_pareceres.ipynb

**5. Open the dashboard**

    Open JurisData.pbix in Power BI Desktop and connect to your local PostgreSQL

### Author

Fabricio Guimarães — Data Analyst · MSc Student in Computational Intelligence (PPgTI/UFRN)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/fabriciogmaraes)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:fabriciogmaraes@hotmail.com)
