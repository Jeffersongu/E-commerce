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
