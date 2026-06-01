# Prompt Mensal — Zendesk Journal CX

Cole este prompt em uma **conversa nova** no Claude todo 1ª terça do mês.

---

## Prompt para copiar

```
Preciso atualizar o Zendesk Journal CX com as novidades de [MÊS ANTERIOR] de [ANO].

**Contexto do projeto:**
- Repositório GitHub: journal-zendesk (Vercel: journal-zendesk.vercel.app)
- Stack: HTML/CSS/JS puro, sem frameworks
- Backend: Google Apps Script → planilha Zendesk Journal V2
- Apps Script URL: https://script.google.com/macros/s/AKfycbxN6ATFNU-lD6sgWKpQWZruwON7xxAajsSQ05kwlYH6JHkRJBL_067s4qONOHUS0ZIUKw/exec

**Contexto da operação Nuvemshop CX:**
- Time de CX com atendimento Brasil e LATAM
- Canais ativos: e-mail, WhatsApp, voz, API, Slack
- Ferramentas ativas no Zendesk: Omnichannel, Criador de app, Fluxo de ação, Gatilhos, Automações, Intenções, Base de conhecimento, Copilot, Assistência automática
- Prioridades 2026: reduzir TTR, TMA e FRT — aumentar FCR e CSAT
- SEMPRE incluir atualizações de IA mesmo que não usemos hoje — a liderança precisa de visibilidade para decisões futuras

**Critério de inclusão — inclua TUDO que se enquadre em:**
- Impacta o dia a dia de quem atende tickets
- Impacta gestão, qualidade, relatórios e SLA
- Impacta configuração das ferramentas que já usamos
- Impacta decisões de médio/longo prazo (IA, novos canais, automação)

**Não incluir apenas:** mudanças de cobrança/planos, atualizações de infraestrutura de datacenter, features exclusivas de produtos que não são Zendesk Support/Talk/Messaging.

**O que preciso:**
1. Buscar as atualizações reais do Zendesk de [MÊS ANTERIOR]/[ANO] em:
   https://support.zendesk.com/hc/en-us/sections/4405298877338-What-s-new-in-Zendesk

2. Gerar um novo index.html completo com:
   - As novidades reais do mês (sem limite — inclua tudo relevante)
   - Imagens reais dos artigos do Zendesk (S3: zen-marketing-documentation.s3.amazonaws.com)
   - Resumo em PT-BR de 2-3 frases por card
   - Impacto CX destacado considerando as métricas TTR/TMA/FRT/FCR/CSAT
   - 2-3 sugestões de discovery práticas por card
   - Seções por categoria: IA & Automação / Relatórios & Dados / Canais / Agente
   - PT/ES toggle funcional
   - Formulário de sugestões integrado
   - Link para guia.html e a3.html no header
   - APPS_SCRIPT_URL já configurada: https://script.google.com/macros/s/AKfycbxN6ATFNU-lD6sgWKpQWZruwON7xxAajsSQ05kwlYH6JHkRJBL_067s4qONOHUS0ZIUKw/exec
   - Planilha ID: 1KX8zPfyUSFAs_zLxNZT93THm8OFgcUVH3o-eNEZkQg0
   - Aba marcacoes — gravada via GET com mode no-cors ao marcar um card:
     campos: Data, Mes, Titulo, Categoria, Resumo, Impacto, URL (capturados do DOM do card)
   - Aba sugestoes — gravada via GET com mode no-cors ao enviar o formulário:
     campos: Data, Nome, Area, Referencia, Sugestao
   - writeSheets() usa URLSearchParams + fetch mode no-cors
   - Marcações persistidas em window.storage (key: zj_[mes][ano]_imp)
   - Sugestões persistidas em localStorage (key: zj_[mes][ano]_sugs)

**Padrão visual — Design System Nuvemshop NS Closing Dashboard:**
Fonte: "Plus Jakarta Sans" (Google Fonts, display: swap), fallback system-ui, sans-serif
Tokens CSS:
  --bg: #001897              /* header e faixa de tabs */
  --panel-bg: #ffffff        /* fundo do conteúdo */
  --text: #111827            /* texto principal */
  --muted: #6b7280           /* labels, helpers, subtítulos */
  --primary: #2563eb         /* CTAs, ativos, destaques */
  --primary-soft: #dbeafe    /* hover sutil, badges */
  --primary-hover: #1d4ed8   /* hover de botões */
  --panel-border: #e5e7eb    /* bordas de cards e painéis */
  positivo: #059669 · negativo: #dc2626
Cards: border-radius 14px, box-shadow 0 1px 3px rgba(0,0,0,0.06), padding 0.85rem 1rem
Badges de categoria: fundo #dbeafe, cor #2563eb, border-radius 6px, 0.72rem/600
Princípios: #001897 apenas no chrome (header/tabs), conteúdo sempre sobre fundo branco,
sem zebra striping, hierarquia por densidade e cor muted.

Por favor, busca as atualizações reais e gera o index.html completo pronto para subir no GitHub.
```

---

## Checklist após receber o arquivo

- [ ] Baixar o `index.html` gerado
- [ ] Abrir o GitHub → `journal-zendesk` → `index.html`
- [ ] Clicar no lápis (editar) → selecionar tudo → colar o novo conteúdo
- [ ] Commit changes com mensagem: `Journal [MÊS] [ANO] — atualização automática`
- [ ] Aguardar ~1 min → Vercel redeploya automaticamente
- [ ] Acessar journal-zendesk.vercel.app e conferir

---

## Informações de referência (não mudam)

| Item | Valor |
|------|-------|
| URL do site | https://journal-zendesk.vercel.app |
| Planilha | https://docs.google.com/spreadsheets/d/1KX8zPfyUSFAs_zLxNZT93THm8OFgcUVH3o-eNEZkQg0/edit |
| Apps Script | https://script.google.com/macros/s/AKfycbxN6ATFNU-lD6sgWKpQWZruwON7xxAajsSQ05kwlYH6JHkRJBL_067s4qONOHUS0ZIUKw/exec |
| Repositório | github.com/erikmagalhaes/journal-zendesk |
| Fonte Zendesk | https://support.zendesk.com/hc/en-us/sections/4405298877338 |

---

## Prompt para o Cowork Scheduled Tasks

**Nome:** `zendesk-journal-cx-monthly`
**Cadência:** `Toda terça-feira às 9h (0 9 * * 2) — guarda interna garante execução só na 1ª terça do mês`

```
Você é responsável por atualizar o Zendesk Journal CX, curadoria mensal de novidades do Zendesk para o time de CX da Nuvemshop.

FIRST TUESDAY GUARD: Verifique o dia do mês de hoje. Se não estiver entre 1 e 7 (inclusive), esta não é a primeira terça do mês — pare imediatamente e não faça nada.

---

CONTEXTO DA OPERAÇÃO:
- Time de CX com atendimento Brasil e LATAM
- Canais ativos: e-mail, WhatsApp, voz, API, Slack
- Ferramentas ativas: Omnichannel, Criador de app, Fluxo de ação, Gatilhos, Automações, Intenções, Base de conhecimento, Copilot, Assistência automática
- Prioridades 2026: reduzir TTR, TMA e FRT — aumentar FCR e CSAT
- SEMPRE incluir atualizações de IA mesmo que não usemos hoje

CRITÉRIO DE INCLUSÃO — inclua tudo que:
- Impacta o dia a dia de quem atende tickets
- Impacta gestão, qualidade, relatórios e SLA
- Impacta configuração das ferramentas ativas
- Impacta decisões de médio/longo prazo
Não incluir: mudanças de cobrança/planos, infraestrutura de datacenter.

---

TAREFA:

1. Identifique o mês anterior a hoje e acesse via mcp__workspace__web_fetch:
   https://support.zendesk.com/hc/en-us/sections/4405298877338-What-s-new-in-Zendesk
   Leia cada artigo relevante do mês anterior individualmente.

2. Para cada atualização relevante extraia:
   - Título em português
   - Categoria: IA & Automação / Relatórios & Dados / Canais / Agente
   - Resumo em 2-3 frases em português
   - Impacto CX considerando TTR, TMA, FRT, FCR, CSAT quando aplicável
   - 2-3 sugestões de discovery práticas
   - URL e imagem do artigo (domínio zen-marketing-documentation.s3.amazonaws.com, encontrada na og:image do artigo)

3. Abra o index.html atual via Claude in Chrome:
   - mcp__Claude_in_Chrome__navigate → https://raw.githubusercontent.com/erikmagalhaes/journal-zendesk/main/index.html
   - mcp__Claude_in_Chrome__get_page_text → copie o HTML completo

4. Gere o novo index.html aplicando o Design System Nuvemshop:

   TIPOGRAFIA:
   - Fonte: "Plus Jakarta Sans" (Google Fonts, display: swap), fallback system-ui, sans-serif
   - Labels de card: 0.65rem/600/UPPERCASE/letter-spacing 0.08em
   - Valores principais: 1.5rem/700
   - Texto corpo: 0.85–0.9rem · muted: 0.72–0.78rem

   TOKENS CSS (:root):
     --bg:           #001897;   /* header e faixa de tabs */
     --panel-bg:     #ffffff;   /* fundo do conteúdo */
     --text:         #111827;
     --muted:        #6b7280;
     --primary:      #2563eb;
     --primary-soft: #dbeafe;
     --primary-hover:#1d4ed8;
     --panel-border: #e5e7eb;
     positivo: #059669 · negativo: #dc2626

   LAYOUT E CARDS:
   - Header/tabs: fundo #001897, texto branco
   - Cards: background #fff, border-radius 14px, box-shadow 0 1px 3px rgba(0,0,0,0.06), padding 0.85rem 1rem
   - Badges de categoria: fundo #dbeafe, cor #2563eb, border-radius 6px, 0.72rem/600
   - Sem zebra striping — separadores apenas com border-bottom 1px solid #e5e7eb
   - Cor #001897 limitada ao chrome do app — conteúdo sempre sobre fundo branco

   CONFIGURAÇÃO DA PLANILHA:
   - APPS_SCRIPT_URL: https://script.google.com/macros/s/AKfycbxN6ATFNU-lD6sgWKpQWZruwON7xxAajsSQ05kwlYH6JHkRJBL_067s4qONOHUS0ZIUKw/exec
   - Planilha ID: 1KX8zPfyUSFAs_zLxNZT93THm8OFgcUVH3o-eNEZkQg0
   - Aba marcacoes — gravada via GET com mode no-cors ao marcar um card:
     campos: Data, Mes, Titulo, Categoria, Resumo, Impacto, URL (capturados do DOM)
   - Aba sugestoes — gravada via GET com mode no-cors ao enviar o formulário:
     campos: Data, Nome, Area, Referencia, Sugestao
   - writeSheets() usa URLSearchParams + fetch mode: 'no-cors'
   - Marcações: window.storage (key: zj_[mes][ano]_imp)
   - Sugestões: localStorage (key: zj_[mes][ano]_sugs), renderizadas na seção de sugestões

   OUTROS ELEMENTOS OBRIGATÓRIOS:
   - PT/ES toggle com todas as traduções para espanhol
   - Formulário de sugestões integrado
   - Links para guia.html e a3.html no header
   - Seção de discovery expansível por card
   - Imagens reais dos artigos do Zendesk

   Salve o arquivo final em: /sessions/sweet-exciting-wozniak/mnt/outputs/index.html
   Ao concluir, notifique o usuário que o index.html está pronto na pasta Outputs
   e pode ser commitado manualmente com a mensagem: "Journal [MÊS] [ANO] — atualização automática"

---

REGRAS:
- Nunca inventar atualizações — usar apenas artigos oficiais do Zendesk
- Manter sintaxe JS válida (sem chaves extras ou erros de sintaxe)
- Preservar guia.html, a3.html e README.md intocados
- Se não encontrar atualizações do mês anterior, parar e reportar — não publicar edição vazia
```
