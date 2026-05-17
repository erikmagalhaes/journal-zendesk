# Como subir o Zendesk Journal CX no Vercel

## Arquivos do projeto

```
zendesk-journal/
├── index.html        ← página principal
├── a3.html           ← A3 de melhoria contínua
├── vercel.json       ← configuração do Vercel
└── api/
    └── claude.js     ← função de backend (guarda a chave em segurança)
```

---

## Passo 1 — Criar o repositório no GitHub

1. Acesse https://github.com e faça login
2. Clique no **+** (canto superior direito) → **New repository**
3. Nome: `zendesk-journal-cx`
4. Visibilidade: **Public**
5. Clique em **Create repository**
6. Na página do repositório, clique em **uploading an existing file**
7. Arraste os 4 arquivos acima para a área de upload
8. Clique em **Commit changes**

---

## Passo 2 — Criar conta no Vercel

1. Acesse https://vercel.com
2. Clique em **Sign Up** → **Continue with GitHub**
3. Autorize o acesso

---

## Passo 3 — Fazer o deploy

1. No painel do Vercel, clique em **Add New → Project**
2. Localize o repositório `zendesk-journal-cx` e clique em **Import**
3. Não mude nada nas configurações — clique direto em **Deploy**
4. Aguarde ~1 minuto. O Vercel vai gerar uma URL tipo:
   `https://zendesk-journal-cx.vercel.app`

---

## Passo 4 — Adicionar a chave da API do Claude ⚠️ OBRIGATÓRIO

Sem esse passo a IA não funciona.

1. No painel do projeto no Vercel, vá em **Settings → Environment Variables**
2. Clique em **Add**
3. Preencha:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** sua chave da API (começa com `sk-ant-...`)
   - **Environment:** marque os três — Production, Preview, Development
4. Clique em **Save**
5. Vá em **Deployments** → clique nos três pontos do deploy mais recente → **Redeploy**

> Onde pegar a chave: https://console.anthropic.com → API Keys → Create Key

---

## Passo 5 — Acessar o site

Após o redeploy (≈1 min), acesse a URL gerada pelo Vercel.
O site estará no ar e funcionando com a IA.

---

## Atualizações futuras

Para atualizar o site (ex: novo mês no seletor):
1. Edite o arquivo no GitHub diretamente (botão de lápis no arquivo)
2. Faça commit — o Vercel redeploya automaticamente em ~1 minuto

---

## Dúvidas comuns

**"Function timeout"** → A busca de IA pode demorar até 60s.
No painel do Vercel, vá em Settings → Functions → Max Duration → coloque **60**.

**"A planilha não está recebendo dados"** → O MCP do Google Sheets precisa
que o Google Sheets MCP esteja autorizado. Entre em contato para configurar
um Google Apps Script como alternativa mais simples.
