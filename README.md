# JurisData Analytics

> 🚧 Em construção / Work in Progress

**PT** | [EN](#en)

---

## PT

Pipeline de jurimetria trabalhista aplicado às decisões do TRT-21 (Rio Grande do Norte), combinando engenharia de dados, NLP e LLM para identificar padrões de litígios e estimar risco de condenação por categoria de reclamação.

### Stack

Python 3.13 · PostgreSQL · Power BI · spaCy · BERTimbau · Gemini API

### Fases

- [x] Fase 1 — Ingestão de dados (API CNJ DataJud → PostgreSQL)
- [ ] Fase 2 — Modelagem relacional (dimensões, views, feature store)
- [ ] Fase 3 — NLP e clustering de decisões
- [ ] Fase 4 — Pareceres automáticos com LLM
- [ ] Fase 5 — Dashboard executivo no Power BI

### Dados

40.232 processos · Classe 985 (Ação Trabalhista - Rito Ordinário) · Período 2018–2024 · TRT-21/RN

### Autor

Fabricio Guimarães — Analista de Dados · Mestrando em Inteligência Computacional (PPgTI/UFRN)

---

## EN

<a name="en"></a>

Labor litigation analytics pipeline applied to decisions from TRT-21 (Rio Grande do Norte, Brazil), combining data engineering, NLP and LLM to identify litigation patterns and estimate conviction risk by claim category.

### Stack

Python 3.13 · PostgreSQL · Power BI · spaCy · BERTimbau · Gemini API

### Phases

- [x] Phase 1 — Data ingestion (CNJ DataJud API → PostgreSQL)
- [ ] Phase 2 — Relational modeling (dimensions, views, feature store)
- [ ] Phase 3 — NLP and decision clustering
- [ ] Phase 4 — Automated legal briefs with LLM
- [ ] Phase 5 — Executive dashboard in Power BI

### Data

40,232 cases · Class 985 (Labor Lawsuit - Ordinary Rite) · Period 2018–2024 · TRT-21/RN

### Author

Fabricio Guimarães — Data Analyst · MSc Student in Computational Intelligence (PPgTI/UFRN)
