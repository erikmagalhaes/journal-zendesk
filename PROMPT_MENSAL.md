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

**O que preciso:**
1. Buscar as atualizações reais do Zendesk de [MÊS ANTERIOR]/[ANO] em:
   https://support.zendesk.com/hc/en-us/sections/4405298877338-What-s-new-in-Zendesk

2. Filtrar apenas o que é relevante para times de CX/suporte ao cliente
   (ignorar updates de vendas, e-commerce, admin puro)

3. Gerar um novo index.html completo com:
   - As novidades reais do mês (6 a 10 cards)
   - Imagens reais dos artigos do Zendesk (S3: zen-marketing-documentation.s3.amazonaws.com)
   - Resumo em PT-BR de 2-3 frases por card
   - Impacto CX destacado em cada card
   - 2-3 sugestões de discovery expansíveis por card (geradas por você)
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
