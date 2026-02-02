## 🤖 Agente de IA com N8N

Agentes de IA são sistemas que combinam modelos de linguagem (como GPT) com ferramentas externas (Tools) para realizar tarefas complexas de forma autônoma.

Agentes de IA permitem:

- Conversar naturalmente - Usuários fazem perguntas em linguagem natural
- Acessar dados reais - Consultar bancos de dados, APIs, planilhas
- Memorizar contexto - Lembrar informações de conversas anteriores
- Aplicar guardrails - Limitar o comportamento do agente
- Executar ações - Fazer queries, cálculos, análises automaticamente


---
## 🎯 Objetivos

O objetivo é criar um Agente de IA usando n8n, permitindo que usuários conversem com seu banco de dados de forma natural através do Telegram. O agente de IA funcionará no Telegram que consulta o banco Supabase usando linguagem natural.

<br/>

<p align="center">
<img src="https://github.com/user-attachments/assets/b58ae5c9-9d41-4586-866e-cb3b82312550" width="600" alt="image">
</p>


---
## 🔄 Fluxo de Dados com Agente de IA

O diagrama abaixo mostra como o Agente de IA funciona:

<br/>

<p align="center">
<img src="https://github.com/user-attachments/assets/4632450d-c8a9-410c-9e27-4c3fbf087567" width="9000" alt="image">
</p>


---
## 🛠️ Ferramentas Utilizadas

- N8N;
- OpenAI;
- Supabase;
- Telegram.


---
## 📝 Estratégia 

### Etapa 1: Agente de E-commerce

Objetivo: Criar um agente especializado em e-commerce
- System Message: Instruções que definem o comportamento do agente
- Guardrails: Limites que previnem respostas indesejadas
- Prompt Engineering: Como escrever instruções eficazes

1° Realizar login da versão trial;

2° Selecionar o node que iniciará o gatilho Chat Trigger;

3° Selecionar o node AI Agent;

4° Conecte um modelo de LLM OpenAI Chat Model.


<p align="center">
<img src="https://github.com/user-attachments/assets/f921705e-fce0-4054-bf5d-684f48061bc1" width="800" alt="image">
</p>


---
### Etapa 2: Memória em Agentes de IA

Objetivo: Mostrar como o agente memoriza informações da conversa.

- Como configurar memória no n8n:
  - 1° Habilitar a memória do agente de IA, selecione o node Simple Memory;
  - 2° Abra o AI Agent e selecione em Add Option System Message;
  - 3° Crie um prompt com os requisitos do Agente de IA e insira Guardrails:

  - Você é um Analista de E-commerce especializado, fornecendo insights práticos e recomendações baseadas em dados, sempre observando guardrails de segurança — sem sugerir práticas antiéticas, evitar dados sensíveis, alertar sobre riscos críticos e esclarecer limitações profissionais. Não responda nada fora do tema e de sua especialização, diga que  não pode ajudar!


<p align="center">
<img src="https://github.com/user-attachments/assets/23c4a6e1-c015-40b4-bf34-d4b671ecf7f9" width="800" alt="image">
</p>


---
### Etapa 3: Consultando Tabela com Tool (Supabase)

Objetivo: Fazer o agente consultar o Supabase usando Tools.
- 1° Selecione Tools e escolha o node Supabase Tool;
- 2° Selecione a credencial;
- 3° Abra o banco ecommerce no Supabase e selecione Project Settings, em Data API copie a URL e insira em Host;
- 4 Selecione API Keys, Legacy anon copie secret e insira Service Role Secret;
- 5° Parameters selecione em Operations Get Many


---
### Etapa 4: Bot no Telegram

Objetivo: Criar um Bot para responder perguntas de negócio.

- 1° Criar Bot com BotFather: Procure por @BotFather e Envie /newbot no Telegram;
  
- 2° Escolha um nome: especialistaecommerceanalyses_bot;
  
- 3° Escolha um username: JeffDados_bot;

<p align="center">
<img src="https://github.com/user-attachments/assets/92b3dc84-baae-4097-8c4a-6b6a9f2c9f83" width="400" alt="image">
</p>

  
- 4° Copie (Use this token to access the HTTP API) o tolken que o BotFather fornecer e procure pelo bot criado;

- 5° Procure pelo node Telegram, em Triggers selecione On Message;

- 6° Crie uma conta nova e cole o Token de acesso:

<p align="center">
<img src="https://github.com/user-attachments/assets/3db4c5ce-f501-43a3-862e-1ba1c2cb84b8" width="800" alt="image">
</p>
  

- 7° Execute step e envie uma mensagem para o bot;

- 8° Apague gatilho Chat Trigger e conecte o Telegram Trigger;

- 9° Clique no IA Agent e altere Source for Prompt (User Message) para Define below, repita para o node Simple Memory;

- 10° Em Prompt (User Message) arraste T Text e execute o passo 

<p align="center">
<img src="https://github.com/user-attachments/assets/394aa755-fb71-4d24-b4a0-397d27d017d3" width="400" alt="image">
</p>
  

- 11° Procure o node de saída Telegram Send a Text Message;

- 12° Conecte a credencial, Resource Message, Operation Send Message;

- 13° Chat ID - Telegram Trigger arraste From ID em Text arraste o parâmetro AI Agente Output, execute o step;

<p align="center">
<img src="https://github.com/user-attachments/assets/adbeeb88-d406-478d-8fff-8e61902081c3" width="800" alt="image">
</p>


---
## 🚀 Próximos Passos

- Alterar o meio de interação com o Agente de IA para Whatsapp;
- Memória com conexão ao Banco de Dados PostgreSQL;
- Consulta direta ao Data Marts.

