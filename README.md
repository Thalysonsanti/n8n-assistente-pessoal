# 🤖 Assistente Pessoal com n8n

Este projeto implementa um **Assistente Pessoal de Produtividade e Controle Financeiro** utilizando automações no **n8n**, integrado com **Telegram, OpenAI, Google Calendar e Google Sheets**.

O assistente permite registrar **gastos, receitas e compromissos** através de mensagens ou áudios enviados pelo Telegram.

---

# 🚀 Funcionalidades

## 📅 Gestão de Agenda
O assistente identifica compromissos nas mensagens do usuário e cria eventos automaticamente no **Google Calendar**.

Exemplos:

Marcar reunião amanhã às 14h  
Consulta médica dia 20 às 9h  
Lembrete de pagar conta sexta

Dados registrados:

- Título do evento
- Data
- Horário
- Duração (se informado)
- Observações

Se alguma informação essencial estiver faltando, o assistente solicita ao usuário.

---

## 💰 Controle Financeiro

O assistente identifica **gastos ou receitas** e registra automaticamente em uma **planilha do Google Sheets**.

Campos registrados:

- Data
- Descrição
- Categoria
- Tipo (Gasto ou Receita)
- Valor

Categorias sugeridas:

- Alimentação
- Transporte
- Moradia
- Lazer
- Assinaturas
- Investimentos
- Outros

### Exemplos de comandos

Gastei 45 reais com almoço  
Paguei 120 da internet  
Recebi 800 de um cliente

Registro esperado:

Data: hoje  
Descrição: Almoço  
Categoria: Alimentação  
Tipo: Gasto  
Valor: 45

---

## 📊 Consultas Inteligentes

O usuário também pode consultar informações:

Quanto gastei hoje?  
Quais compromissos tenho amanhã?  
Quanto gastei com alimentação esse mês?

O assistente consulta as ferramentas conectadas antes de responder.

---

# 🧠 Tecnologias Utilizadas

- n8n (Automação de workflows)
- OpenAI (Agente de IA)
- Telegram Bot API
- Google Calendar API
- Google Sheets API

---

# ⚙️ Estrutura do Projeto


---

# 🔄 Fluxo da Automação

Fluxo principal do assistente:

1️⃣ Usuário envia mensagem ou áudio no Telegram  
2️⃣ O n8n recebe a mensagem via **Telegram Trigger**  
3️⃣ Caso seja áudio:
- o arquivo é baixado
- enviado para transcrição com OpenAI  

4️⃣ A mensagem é enviada ao **Agente de IA**

5️⃣ O agente decide qual ferramenta utilizar:

- Calendário
- Financeiro
- Memória
- Consulta de dados

6️⃣ O resultado é retornado ao usuário no Telegram.

---

# 📥 Como usar

## 1️⃣ Importar os workflows

No n8n:

Workflows → Import → Import from file

Importe os arquivos:

- assistente-pessoal.json
- agente-calendário.json
- agente-financeiro.json

---

## 2️⃣ Configurar credenciais

Você precisará configurar:

- Telegram Bot Token
- OpenAI API Key
- Google Calendar
- Google Sheets

---

## 3️⃣ Criar planilha financeira

Crie uma planilha com as colunas:

Data  
Descrição  
Categoria  
Tipo  
Valor  

---

## 4️⃣ Ativar o workflow

Após configurar:

Activate Workflow

Agora o assistente já poderá responder no Telegram.

---

# 📌 Exemplo de Uso

Usuário envia:

"Gastei 45 no almoço"

Resposta do assistente:

Registro feito:  
Gasto de R$45,00 em Alimentação (Almoço) no dia 16/03.

---

Usuário envia:

"Marcar reunião com cliente amanhã às 14h"

Resposta:

Evento criado:  
Reunião com cliente — 18/03 às 14h.

---

# 🔒 Regras do Assistente

- Nunca inventar dados
- Sempre confirmar valores monetários
- Utilizar números para valores financeiros
- Perguntar ao usuário em caso de ambiguidade

---

# 🧩 Melhorias Futuras

- Dashboard financeiro automático
- Relatórios mensais
- Integração com Notion
- Integração com banco de dados
- Notificações automáticas de contas

---

# 👨‍💻 Autor

Thalyson Santiago

Projeto desenvolvido para estudo de **automação, IA e produtividade pessoal com n8n**.

