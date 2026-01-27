# Tratamento e Transformação de Dados (dbt)

Nesta etapa do projeto, foi construída a camada de transformação de dados no Data Warehouse PostgreSQL (Supabase) utilizando o DBT Cloud, aplicando a Arquitetura Medalhão. Os dados percorrem um fluxo estruturado entre as camadas Bronze (dados brutos), Silver (dados tratados e padronizados) e Gold (métricas de negócio), garantindo qualidade, rastreabilidade e performance. A partir da camada Gold, os dados são organizados em Data Marts orientados ao negócio (Sales, Pricing e Customer Success), disponibilizando KPIs prontos para análise e tomada de decisão, seguindo práticas amplamente adotadas em ambientes corporativos.

![Data Wharehouse - Transformação DBT](https://github.com/user-attachments/assets/0b418298-dc8b-4085-8e2d-5b10f99cd36e)


---
# Tecnologias Utilizadas
- DBT:
  -  Código versionado (Git);
  -  Testes integrados de qualidade dos dados;
  -  Orquestração de dependências claras (resolvidas automaticamente);
  -  Padrões de modelagem (bronze, silver, gold);
  -  Documentação automática;
  -  Transformação dos dados usando SQL;
  -  Linha de execução com visualização como os modelos se relacionam;
  -  Modelo de transformação reutilizavável.

# Arquitetura de Dados (Medalhão)

Este projeto recria os principais KPIs utilizando o DBT para tratar os dados e arquitetura Medalhão. Os KPIs estão organizados em 3 Data Marts (áreas de negócio), seguindo o padrão usado pelas empresas:

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

# Configuração do dbt Cloud

1° Transformação dos dados com DBT - IDE na Cloud;

2° Criar a conta Try DBT com o Projeto AnalyticsEcommerce;

3° Selecionar a conexão com PostgreSQL no DBT e preencha com os dados de conexão do banco ecommerce na IDE Supabase (PostgreSQL):

<p align="center">
<img src="https://github.com/user-attachments/assets/e1c9adad-41d1-4c4f-9cf2-fbc7b0cf1413" width="800" alt="image">
</p>

4° Set o projeto no repositório do GitHub;

# Configuração do dbt_project.yml

5° Iniciar o dbt project e realize o commit (Models: Delete folder example e crie Folder bronze, silver e gold);

6° Configure o arquivo dbt_project.yml é o coração do projeto dbt. Ele define como o dbt vai se comportar:
- Define o nome do projeto;
- Configura onde estão os modelos, macros, testes;
- Define materializações padrão por camada (bronze=view, silver=table, gold=table);
- Define schemas por camada (bronze, silver, gold);
- Define variáveis do projeto (thresholds, top N, etc.).

<p align="center">
<img src="https://github.com/user-attachments/assets/cb547e37-3143-4edc-8ff7-1204c69f1d52" width="800" alt="image">
</p>

# Configuração das Fontes de Dados (_sources.yml)

7° Definir a fontes de Dados (_sources.yml) com o arquivo _sources.yml que documenta as tabelas raw (fonte original dos dados):
- Define de onde vêm os dados (tabelas raw);
- Documenta colunas e tipos;
- Permite usar {{ source('raw', 'produtos') }} nos modelos;
- Habilita testes nas fontes.

<p align="center">
<img src="https://github.com/user-attachments/assets/3a2a9670-5c4e-4f09-93e1-9d3638071074" width="800" alt="image">
</p>

# Desenvolvimento dos Modelos SQL

8° Defina os scrypts sql para cada tabela das camadas (commit e merge em cada camada), para finalizar materialize as tabelas no banco ecommerce (Build models);

9° Para a camada Gold crie subcamadas (Sales, Pricing e Customer_success) e salve os scrypts;

<p align="center">
<img src="https://github.com/user-attachments/assets/da11bd76-df72-419f-af72-ac6d221c57d5" width="800" alt="image">
</p>

- Acesse o código: [Transformação](https://github.com/Jeffersongu/E-commerce/tree/main/Transforma%C3%A7%C3%A3o)
