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
   - APPS_SCRIPT_URL já configurada (a mesma acima)
   - window.storage para marcações, localStorage para sugestões

**Padrão visual de referência:** mesmo design do arquivo index.html atual
(navy #0D1B2A, verde #00C853, Inter, cards com borda âmbar quando marcados)

Por favor, busca as atualizações reais e gera o index.html completo pronto para subir no GitHub.
```

---

## Checklist após receber o arquivo

- [ ] Baixar o `index.html` gerado
- [ ] Abrir o GitHub → `journal-zendesk` → `index.html`
- [ ] Clicar no lápis (editar) → selecionar tudo → colar o novo conteúdo
- [ ] Commit changes
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

**Nome:** `Zendesk Journal CX — Atualização Mensal`
**Cadência:** `First Tuesday of every month`

```
Você é responsável por atualizar o Zendesk Journal CX, curadoria mensal de novidades do Zendesk para o time de CX da Nuvemshop.

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

TAREFA:
1. Identifique o mês anterior a hoje e acesse:
   https://support.zendesk.com/hc/en-us/sections/4405298877338-What-s-new-in-Zendesk

2. Para cada atualização relevante extraia:
   - Título em português
   - Categoria: IA & Automação / Relatórios & Dados / Canais / Agente
   - Resumo em 2-3 frases em português
   - Impacto CX considerando TTR, TMA, FRT, FCR, CSAT quando aplicável
   - 2-3 sugestões de discovery práticas
   - URL e imagem do artigo (zen-marketing-documentation.s3.amazonaws.com)

3. Abra o index.html atual em:
   https://github.com/erikmagalhaes/journal-zendesk

4. Gere novo index.html mantendo todo CSS e estrutura visual intactos:
   - PT/ES toggle com traduções para espanhol
   - Formulário de sugestões integrado
   - Links para guia.html e a3.html no header
   - APPS_SCRIPT_URL: https://script.google.com/macros/s/AKfycbxN6ATFNU-lD6sgWKpQWZruwON7xxAajsSQ05kwlYH6JHkRJBL_067s4qONOHUS0ZIUKw/exec
   - window.storage para marcações, localStorage para sugestões

5. Faça commit no repositório github.com/erikmagalhaes/journal-zendesk
   Branch: main — Mensagem: "Journal [MÊS] [ANO] — atualização automática"

6. Confirme que journal-zendesk.vercel.app foi atualizado.

REGRAS: nunca inventar atualizações. Manter sintaxe JS válida. Preservar guia.html, a3.html e README.md.
```
