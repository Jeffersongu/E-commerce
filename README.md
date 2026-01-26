# E-commerce (Em execução)

<!-- https://github.com/gabriellbezerra/ed_de_ecommerce_dw_to_n8n_agent -->

## 1° Problema de Negócio
Uma empresa de e-commerce está aumentando sua operação digital e precisa usar dados para tomar decisões melhores. Você vai construir um sistema completo de dados que:
- Conecta dados de diferentes fontes;
- Estrutura um pipeline automático de engenharia de dados;
- Analisa vendas e clientes:
  - Quais são os TOP produtos que mais geram receita, e em qual canal (e-commerce vs loja física) eles performam melhor?
    Impacto: mostra onde está o dinheiro e onde dobrar a aposta.
    
  - Quem são os clientes mais valiosos (top clientes) e quanto eles representam da nossa receita total?
    Impacto: deixa claro o “efeito 80/20” e abre decisões de retenção.
    
  - Quais produtos estão mais caros que o mercado, e qual é o risco/oportunidade de ajuste de preço?

- Análises de Produtos:
  - Quais produtos temos no catálogo?
  - Quais são os produtos mais caros?
  - Quais são os 10 primeiros produtos mais caros?
  - Quais produtos custam mais de R$ 500?
  - Quais produtos nunca foram vendidos?
  - Classifique os produtos por faixa de preço?
  - Quais produtos têm preço acima da média geral?

- Análises de Vendas:
  - Qual é o total de vendas, receita total e ticket médio?
  - Qual é a maior e menor venda?
  - Quantos produtos diferentes foram vendidos?
  - Como ver o nome do produto junto com a venda?
  - Quantas vendas e qual a receita total por categoria?
  - Quais categorias geram mais de R$ 50.000 em receita?
  - Qual é a distribuição percentual de receita por canal?
  - Quais vendas foram feitas de produtos não cadastrados?

- Análises de Clientes:
  - Quem são nossos clientes?
  - Quais clientes compram mais?


- Análise Competitiva:
  - Quais produtos estão mais caros que a média dos concorrentes?
  - Quais produtos estão mais baratos no concorrente do que na nossa tabela?
  - Qual é a diferença percentual entre nossos preços e dos concorrentes?
  - Quais produtos top sellers estão mais caros que todos os concorrentes?

- Análises Avançadas:
  - Qual é a receita total por categoria?
  - Quais categorias geram mais de R$ 50.000 em receita?
  - Qual é o ticket médio por segmento de cliente?
  - Quais produtos têm preço acima da média geral?
  - Quais produtos estão mais caros que a média dos concorrentes?

- Estruturas de Dados:
  - Como criar uma visão para produtos com vendas?
  - Como criar uma tabela para armazenar resumo de vendas por categoria?
  - Como criar uma visão temporária para análise rápida?


- Utilizar inteligência artificial para apoiar decisões.



---
## 2° Contexto


---
## 3° Premissas da Análise

Para a condução desta análise, foram estabelecidas algumas premissas com o objetivo de garantir consistência, confiabilidade e alinhamento com o contexto do negócio.


---
## 4° Estratégia da Solução

Ferramentas Utilizadas:

- Supabase:
  - Supabase é essencialmente PostgreSQL com uma interface moderna e ferramentas extras;
  -  Compatível com AWS S3;
  -  Interface web;
  -  Editor SQL integrado, fácil de usar;
  -  Gratuito - Plano free generoso para aprender.

- Python:
  - Google Colab;
  - Ecossistema rico: Boto3, SQLAlchemy, Pandas;
  - Integração: Fácil integração com bancos de dados, APIs, sistemas.

- DBT:
  -  Código versionado (Git);
  -  Testes integrados de qualidade dos dados;
  -  Orquestração de dependências claras (resolvidas automaticamente);
  -  Padrões de modelagem (bronze, silver, gold);
  -  Documentação automática;
  -  Transformação dos dados usando SQL;
  -  Linha de execução com visualização como os modelos se relacionam;
  -  Modelo de transformação reutilizavável.

1° Realizar login no Supabase e criar um projeto/banco de dados (ecommerce);


2° Subir os arquivos CSV para o banco de dados Ecommerce (produtos, clientes e vendas):

<p align="center">
<img src="https://github.com/user-attachments/assets/19395688-a4b0-47c0-a8a7-ad3341efef68" width="400" alt="image">
</p>

3° Desenvolver um Data Lake S3 - Supabase Storage;

<p align="center">
<img src="https://github.com/user-attachments/assets/9a646442-db66-48be-bc8d-b3c0d8c60e62" width="600" alt="image">
</p>

Diferenças entre Data Lake e Banco de Dados: Data Lake é um local para armazenar dados em diversos formatos, ou seja, arquivos estruturados, semi estruturados e não estruturados, normalmente estão em cloud e o acesso ocorre por uma API/LIB. Banco de dados contém tabelas, ou seja, dados estruturados.

Data Lake S3 - Supabase Storage:

<p align="center">
<img src="https://github.com/user-attachments/assets/9ba4053a-f475-406f-84bf-0f668d7d96ba" width="600" alt="image">
</p>

4° Ingestão de dados com Python arquivo em formato parquet (preco_competidores) com IDE Google Coolab;

- Acesse o código: [Ingestão](https://github.com/Jeffersongu/E-commerce/blob/main/Ingest%C3%A3o/Ingestao_de_Dados.ipynb)

- Imagem da tabela:

<p align="center">
<img src="https://github.com/user-attachments/assets/554e2aff-cdad-49de-88e3-2d4101072a75" width="600" alt="image">
</p>


5° Este projeto recria os principais KPIs utilizando o DBT para tratar os dados e arquitetura Medalhão. Os KPIs estão organizados em 3 Data Marts (áreas de negócio), seguindo o padrão usado pelas empresas:

- Data Wharehouse - Objetivo: Repositório centralizado de dados organizados para análise e relatórios: 
  - Repositório centralizado de dados organizados para análise e relatórios;
  - Performance para consultas;
  - Mantém histórico de dados para análise temporal;
  - Integração com múltiplas fontes de dados;
  - Estrutura otimizada para análises complexas;
  - Isolamento, não impacta sistemas operacionais.

- Camada Bronze (Raw Data) - Objetivo: Capturar dados exatamente como vêm da fonte (cópia) e criar o contrato mínimo do dado - Características:
  - Dados brutos, com transformações mínimas;
  - Padronização básica (seleciona colunas explícitas, padronização de nomes, tipos, remove lixo e adiciona);
  - Permite replay (reprocessar se necessário);
  - Histórico completo;
  - Schema estável (contrato fixo).

- Camada Silver (Cleaned Data) - Objetivo: Limpar, padronizar e enriquecer dados - Características:
  - Dados limpos e padronizados;
  - Validações aplicadas;
  - Tratamento de nulos e duplicatas;
  - Enriquecimentos básicos;
  - Schema otimizado para análise.

- Camada Gold (Business Metrics e Data Marts) - Objetivo: Criar métricas de negócio prontas para análise, organizadas em Data Marts - Características:
  - KPIs e métricas de negócio;
  - Organizados em Data Marts (áreas de negócio);
  - Agregações complexas;
  - Rankings e segmentações;
  - Dados prontos para dashboards;
  - Schema otimizado para consumo.

- Data Marts - Objetivo: Criar subconjuntos de dados organizados por área de negócio - Características:
  - Foco: Cada área tem seus KPIs específicos;
  - Performance: Consultas mais rápidas (dados organizados);
  - Manutenção: Mais fácil de manter e atualizar;
  - Colaboração: Times diferentes trabalham em áreas diferentes;
  - Segurança: Permissões por área de negócio.

6° Transformação dos dados com DBT - IDE na Cloud;

7° Criar a conta Try DBT com o Projeto AnalyticsEcommerce;

8° Selecionar a conexão com PostgreSQL no DBT e preencha com os dados de conexão do banco ecommerce na IDE Supabase (PostgreSQL):

<p align="center">
<img src="https://github.com/user-attachments/assets/e1c9adad-41d1-4c4f-9cf2-fbc7b0cf1413" width="800" alt="image">
</p>

9° Set o projeto no repositório do GitHub;

10° Iniciar o dbt project e realize o commit (Models: Delete folder example e crie Folder bronze, silver e gold);

11° Configure o arquivo dbt_project.yml é o coração do projeto dbt. Ele define como o dbt vai se comportar:
- Define o nome do projeto;
- Configura onde estão os modelos, macros, testes;
- Define materializações padrão por camada (bronze=view, silver=table, gold=table);
- Define schemas por camada (bronze, silver, gold);
- Define variáveis do projeto (thresholds, top N, etc.).

<p align="center">
<img src="https://github.com/user-attachments/assets/cb547e37-3143-4edc-8ff7-1204c69f1d52" width="800" alt="image">
</p>


12° Definir a fontes de Dados (_sources.yml) com o arquivo _sources.yml que documenta as tabelas raw (fonte original dos dados):
- Define de onde vêm os dados (tabelas raw);
- Documenta colunas e tipos;
- Permite usar {{ source('raw', 'produtos') }} nos modelos;
- Habilita testes nas fontes.

<p align="center">
<img src="https://github.com/user-attachments/assets/3a2a9670-5c4e-4f09-93e1-9d3638071074" width="800" alt="image">
</p>

13° Defina os scrypts sql para cada tabela das camadas (commit e merge em cada camada), para finalizar materialize as tabelas no banco ecommerce (Build models);

14° Para a camada Gold crie subcamadas (Sales, Pricing e Customer_success) e salve os scrypts;

<p align="center">
<img src="https://github.com/user-attachments/assets/da11bd76-df72-419f-af72-ac6d221c57d5" width="800" alt="image">
</p>


<p align="center">
<img src="https://github.com/user-attachments/assets/8cca8eb1-029b-4f1f-924a-6efd46f20d85" width="800" alt="image">
</p>



---
## 5° Insights da Análise
Não basta somente apresentar os dados ou visuais, é extremamente importante explicar com palavras o que o gráfico quer dizer, não acredite que os stakeholders entenderam os gráficos simplesmente observando, a parte técnica deve ser abstraída para que todos entendam. A análise dos dados permitiu identificar padrões relevantes como:


---
## 6° Resultados
Conclusão das análises, depois que descrevemos os visuais e encontramos pontos de melhoria, qual é a conclusão geral, qual será a recomendação para solucionar o problema. Link para o relatório completo:



---
## 7° Próximos Passos
O que faríamos com mais tempo para trabalhar neste projeto por exemplo:

- Cria um banco de dados local (PostgreSQL);
- Desenvolver um Dashboard;
- Web Scraping - Análise de concorrência;
- API Externas;
