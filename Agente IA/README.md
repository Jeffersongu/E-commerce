## Agente de IA com N8N

O objetivo é criar um Agente de IA usando n8n, permitindo que usuários conversem com seu banco de dados de forma natural através do Telegram. O agente de IA funcionará no Telegram que consulta o banco Supabase usando linguagem natural.

<p align="center">
<img src="https://github.com/user-attachments/assets/701585f2-6c6b-4906-96c4-ead99338c432" width="600" alt="image">
</p>

---

Agentes de IA são sistemas que combinam modelos de linguagem (como GPT) com ferramentas externas (Tools) para realizar tarefas complexas de forma autônoma.

Agentes de IA permitem:

- Conversar naturalmente - Usuários fazem perguntas em linguagem natural
- Acessar dados reais - Consultar bancos de dados, APIs, planilhas
- Memorizar contexto - Lembrar informações de conversas anteriores
- Aplicar guardrails - Limitar o comportamento do agente
- Executar ações - Fazer queries, cálculos, análises automaticamente


## Fluxo de Dados com Agente de IA

O diagrama abaixo mostra como o Agente de IA funciona:

<img width="721" height="847" alt="image" src="https://github.com/user-attachments/assets/00eeae47-7a42-40d8-ba13-300cb4e489d5" />

---



## Etapa 1: Agente de E-commerce

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

## Etapa 2: Memória em Agentes de IA

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


## Etapa 3: Consultando Tabela com Tool (Supabase)

Objetivo: Fazer o agente consultar o Supabase usando Tools.
- 1° Selecione Tools e escolha o node Supabase Tool;
- 2° Selecione a credencial;
- 3° Abra o banco ecommerce no Supabase e selecione Project Settings, em Data API copie a URL e insira em Host;
- 4 Selecione API Keys, Legacy anon copie secret e insira Service Role Secret;
- 5° Parameters selecione em Operations Get Many



