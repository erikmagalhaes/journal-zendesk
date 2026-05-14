# Zendesk Journal · CX Intelligence

Journal mensal automático das novidades do Zendesk para a liderança de CX da Nuvemshop.

## Arquivos

| Arquivo | Descrição |
|---|---|
| `index.html` | Journal mensal — visível para o time |
| `dashboard.html` | Painel executivo — itens importantes, sugestões e insights de IA |
| `vercel.json` | Configuração do deploy no Vercel |

## Setup inicial (uma vez só)

### 1. Criar repositório no GitHub

1. Acesse [github.com/new](https://github.com/new)
2. Nome sugerido: `zendesk-journal`
3. Deixe **privado** (só você e quem você convidar acessa o código)
4. Clique em **Create repository**
5. Faça upload dos arquivos desta pasta direto pela interface do GitHub (botão "uploading an existing file")

### 2. Conectar ao Vercel

1. Acesse [vercel.com](https://vercel.com) e faça login
2. Clique em **Add New Project**
3. Escolha **Import Git Repository** e conecte sua conta GitHub
4. Selecione o repositório `zendesk-journal`
5. Clique em **Deploy** — sem configurar mais nada

A partir de agora, toda vez que você atualizar um arquivo no GitHub, o Vercel publica automaticamente em menos de 1 minuto.

### 3. URLs após o deploy

- **Journal do time:** `https://zendesk-journal.vercel.app`
- **Seu dashboard:** `https://zendesk-journal.vercel.app/dashboard.html`

Você pode customizar o domínio em Vercel → Settings → Domains.

---

## Atualização mensal (todo primeiro terça)

Na primeira terça de cada mês, substitua os arquivos `index.html` e `dashboard.html` pelos novos gerados pelo app. O Vercel publica automaticamente.

### Como atualizar pelo GitHub (sem terminal)

1. Acesse o repositório no GitHub
2. Clique no arquivo `index.html`
3. Clique no ícone de lápis (Edit)
4. Selecione todo o conteúdo e cole o novo arquivo
5. Clique em **Commit changes**
6. Repita para `dashboard.html`

O Vercel detecta o commit e publica em ~30 segundos.

---

## Idiomas

O site detecta automaticamente o idioma do navegador:
- Navegadores em **espanhol** → ES
- Todos os outros → PT

O usuário pode trocar manualmente pelo botão PT / ES no header.

---

## Estrutura de chaves de storage

| Chave | Tipo | Conteúdo |
|---|---|---|
| `zd_apr2026_v3` | Compartilhada | Sugestões do time (array JSON) |
| `zd_apr2026_imp` | Pessoal | IDs dos itens marcados como importantes |

A cada novo mês, atualize as chaves no código para evitar conflito com dados do mês anterior (ex: `zd_may2026_v3`).
