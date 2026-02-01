# Análise de E-commerce com Agente de IA (Em execução)

<!-- https://github.com/gabriellbezerra/ed_de_ecommerce_dw_to_n8n_agent -->

## 📊 Visão Geral do Projeto

Uma empresa de e-commerce está aumentando sua operação digital e precisa usar dados para tomar decisões melhores. Você vai construir um sistema completo de dados que:

- Conecta dados de diferentes fontes;
- Estrutura um pipeline automático de engenharia de dados;
- Analisa dos Dados;
- Utilizar inteligência artificial para apoiar decisões.

---
## 🎯 Objetivos

- Criar um banco de dados PostgreSQL com ambiente de desenvolvimento no Supabase;
- Desenvolver um Data Lake S3 com ambiente de desenvolvimento no Storage Supabase;
- Extração do arquivo parquet do Data Lake para o banco de dados utilizando Google Colab;
- Desenvolver um Data Warehouse com Arquitetura Medalhão (Raw, Bronze, Silver e Gold);
- Tratamento e Versionamento dos dados com DBT;

---
## 🗂️ Dataset

- Tabela dimensão clientes formato csv;
- Tabela dimensão produtos formato csv;
- Tabela fato vendas formato csv;
- Tabela dimensão preco_competidores formato parquet.


---
## 🛠️ Tecnologias Utilizadas

- Supabase (PostgreSQL);
- Supabase (Storage S3);
- Google Colab (Pandas, SQLAlchemy e Boto3);
- DBT;
- N8N.


---
## 🧱 Modelagem de Dados

A modelagem foi construída visando performance e clareza analítica, utilizando:

- Modelo estrela;
- Tabelas fato e dimensões;
- Relacionamentos otimizados para análise no Power BI


  
---
## 🔄 Pipeline de Dados (ELT)

O pipeline do projeto segue as seguintes etapas:

- Extração dos dados a partir de arquivos ou bases de dados;
- Carga dos dados no Data Warehouse;
- Transformação (limpeza, padronização, tipagem e enriquecimento) utilizando DBT.

</br>

<p align="center">
<img src="https://github.com/user-attachments/assets/8cca8eb1-029b-4f1f-924a-6efd46f20d85" width="800" alt="image">
</p>


---
## 🧭 Estratégia da Solução

A solução foi estruturada em etapas sequenciais para garantir organização, rastreabilidade e qualidade dos dados, desde a ingestão até a geração de análises e consumo por agente de IA. O fluxo segue uma arquitetura de dados em camadas, com automação do pipeline, tratamento padronizado e disponibilização final para exploração analítica e apoio à decisão.

### Etapa 1: Ingestão
Coleta e carregamento dos dados de múltiplas fontes (CSV e Parquet) para o Data Lake e banco PostgreSQL no Supabase, garantindo centralização e disponibilidade para processamento.

Etapa completa: [Ingestão](https://github.com/Jeffersongu/E-commerce/tree/main/Ingest%C3%A3o)

### Etapa 2: Tratamento
Limpeza, padronização e transformação dos dados utilizando DBT e arquitetura medalhão (Raw, Bronze, Silver e Gold), com versionamento e controle das regras de negócio.

Etapa completa: [Transformação](https://github.com/Jeffersongu/E-commerce/tree/main/Transforma%C3%A7%C3%A3o)

### Etapa 3: Agente de IA
Integração dos dados tratados a um agente de IA via N8N, permitindo consultas automatizadas, geração de respostas e apoio analítico baseado nos Data Marts.

Etapa completa: [Agente IA](https://github.com/Jeffersongu/E-commerce/tree/main/Agente%20IA)

### Etapa 4: Análise e Insights
Construção de visões analíticas e indicadores para exploração dos dados, geração de insights e suporte à tomada de decisão no contexto do e-commerce.

Etapa completa: [Análise](https://github.com/Jeffersongu/E-commerce/tree/main/An%C3%A1lises)


---
## ✅ Resultados

- Redução estimada de 60–80% no esforço manual de preparação de dados com pipeline automatizado;
- Aumento da confiabilidade das análises com dados tratados e versionados em camadas;
- Melhoria na rastreabilidade e governança, com transformações controladas via DBT;
- Tempo de disponibilização de dados analíticos reduzido de horas para minutos;
- Estrutura preparada para escala de novos dados e novas fontes;
- Maior agilidade em consultas e respostas analíticas com apoio de agente de IA;
- Base analítica consistente para suportar decisões de vendas, clientes e produtos.



---
## 🚀 Próximos Passos

- Cria um banco de dados local (PostgreSQL);
- Desenvolver um Dashboard;
- Web Scraping - Análise de concorrência;
- API Externas;
