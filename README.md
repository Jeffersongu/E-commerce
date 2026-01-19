# E-commerce

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
 
📁  [Acessar notebook de Ingestão de Dados](https://github.com/Jeffersongu/E-commerce/blob/main/Ingest%C3%A3o/Ingestao_de_Dados.ipynb)
 
 
 Colocar o código aqui - Ingestão Load!

<p align="center">
  <img src="https://github.com/user-attachments/assets/554e2aff-cdad-49de-88e3-2d4101072a75" width="800" alt="image">
</p>
 
 
5° Após a ingestão no banco de dados ecommerce realizar o Tratamento dos dados utilizando a arquitetura medalhão 

<p align="center">
  <img src="https://github.com/user-attachments/assets/783ac918-a4cb-4902-9fe2-1f42176a8685" width="800" alt="image">
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
