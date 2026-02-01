## Visão Geral da Ingestão de Dados

Nesta etapa do projeto, foi desenvolvido o processo de ingestão de dados para um banco de dados em nuvem, utilizando Supabase. Supabase Storage (Data Lake) simula o Storage S3 da AWS e o Python, com o objetivo de preparar os dados para as próximas etapas de transformação com dbt.

<p align="center">
<img src="https://github.com/user-attachments/assets/172ab40b-479b-401e-8a07-b8b438315678"
" width="300" alt="image">
</p>

</br>

---

## Tecnologias Utilizadas na Ingestão

Supabase (PostgreSQL):

- Banco de dados relacional baseado em PostgreSQL;
- Compatível com AWS S3;
- Interface web intuitiva;
- Editor SQL integrado;
- Plano gratuito adequado para estudos e projetos educacionais;
- Utilizado como banco de dados transacional (OLTP) do projeto.

</br>

Supabase Storage (Data Lake – S3):

- Armazenamento de arquivos em nuvem;
- Suporte a diferentes formatos de dados;
- Acesso via API;
- Utilizado como Data Lake, simulando um ambiente S3.

</br>

Python:

- Execução via Google Colab;
- Bibliotecas utilizadas: Pandas, SQLAlchemy e Boto3 (ou equivalente para Storage);
- Integração: Fácil integração com bancos de dados, APIs, sistemas.


---

## Criação do Projeto no Supabase - Banco de Dados E-commerce

### Criação do Projeto no Supabase:
- Login na plataforma Supabase;
- Criação de um novo projeto e banco de dados chamado Ecommerce;
- Configuração inicial do ambiente para receber dados estruturados.

</br>

1° Realizar login no Supabase e criar um projeto/banco de dados (ecommerce);


### Carga Inicial de Dados via CSV:

Foram carregados manualmente arquivos CSV no banco de dados Ecommerce, contendo as seguintes tabelas:

- Produtos;
- Clientes;
- Vendas;
- Esses dados representam a base transacional inicial do projeto.


2° Subir os arquivos CSV para o banco de dados Ecommerce (produtos, clientes e vendas):

<p align="center">
<img src="https://github.com/user-attachments/assets/c129ee01-0892-415c-8b54-6cf485b440c9"
" width="400" alt="image">
</p>


### Implementação do Data Lake (Supabase Storage):

Foi criado um Data Lake utilizando o Supabase Storage, com o objetivo de armazenar dados em formatos variados, separados do banco relacional.

3° Desenvolver um Data Lake S3 - Supabase Storage;

<p align="center">
<img src="https://github.com/user-attachments/assets/0f1da56a-d098-41fb-93b4-bff752d9673b" width="400" alt="image">
</p>

Diferenças entre Data Lake e Banco de Dados: Data Lake é um local para armazenar dados em diversos formatos, ou seja, arquivos estruturados, semi estruturados e não estruturados, normalmente estão em cloud e o acesso ocorre por uma API/LIB. Banco de dados contém tabelas, ou seja, dados estruturados.

Data Lake S3 - Supabase Storage:

<p align="center">
<img src="https://github.com/user-attachments/assets/9ba4053a-f475-406f-84bf-0f668d7d96ba" width="600" alt="image">
</p>


### Ingestão de Dados em Parquet com Python:

Nesta etapa, foi desenvolvido um processo de ingestão de dados externos utilizando Python, com armazenamento em formato Parquet, simulando um cenário real de ingestão de dados analíticos.

- Preço de Competidores (preco_competidores);
- Formato: Parquet;
- Armazenado no Data Lake (Supabase Storage).

4° Ingestão de dados com Python arquivo em formato parquet (preco_competidores) com IDE Google Coolab;

- Acesse o código: [Ingestão](https://github.com/Jeffersongu/E-commerce/blob/main/Ingest%C3%A3o/Ingestao_de_Dados.ipynb)

- Imagem da tabela:

<p align="center">
<img src="https://github.com/user-attachments/assets/554e2aff-cdad-49de-88e3-2d4101072a75" width="600" alt="image">
</p>
