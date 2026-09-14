# Minhas Finanças — Landing Page

LP de aquisição para o **Minhas Finanças**, ferramenta AUVP de organização financeira pessoal.

## Abordagem

O produto é o protagonista da página: em vez de ilustrações ou banco de imagens, a LP é construída
com componentes de UI (dashboard, lista de transações, categorização, gráficos, metas, fluxo de
conexão Open Finance, cadastro manual e estados vazios) que reproduzem a interface real do app,
seguindo a referência visual do Copilot Money e do Monarch Money.

A narrativa segue a progressão do briefing:

1. **Espalhado** — contas e apps desconectados
2. **Centralizado** — tudo em um painel único
3. **Entendimento** — categorização automática
4. **Organização** — lista de transações organizada
5. **Acompanhamento** — metas com progresso

## Identidade visual

Tokens extraídos diretamente de [`ProdutosAUVP/central`](https://github.com/ProdutosAUVP/central)
(`src/index.css` / `docs/figma/design-tokens.json`), marca **Capital**:

- Cor primária `#023620` (verde AUVP), tipografia **Anek Latin** (display), **Sora** (UI/botões),
  **Roboto** (corpo de texto), radius `0.75rem`.
- Ver `css/tokens.css` para a lista completa de variáveis (cores semânticas, paleta de gráficos,
  sombras).

## Stack

Site estático (HTML/CSS/JS puro, sem build step) — fácil de publicar em qualquer host estático
(Vercel, GitHub Pages, Netlify) e de portar depois para Next.js/React se o time decidir evoluir
para um projeto com componentes reais do produto.

```
index.html
css/
  tokens.css    → design tokens (cores, tipografia, radius, sombras)
  base.css      → reset, tipografia, botões, cards, utilitários
  mockups.css   → componentes de "produto real" (dashboard, transações, metas, etc.)
  layout.css    → header, hero, storytelling, features, tour, prova social, footer
js/
  main.js       → scroll reveal, tabs do tour de produto, menu mobile
```

## Rodando localmente

```
python3 -m http.server 8000
# abrir http://localhost:8000
```

## Próximos passos sugeridos

- Substituir os mockups de UI por capturas reais do produto (com dados fictícios) assim que
  existirem telas de produção — a estrutura de componentes em `mockups.css` já reflete os
  contêineres esperados (frame de navegador, app shell, cards).
- Integrar formulário de cadastro/login com o backend real (CTAs `#comecar` / `#login`).
- Validar copy e números de prova social (depoimentos, estatísticas) com dados reais antes do
  lançamento — os atuais são placeholders ilustrativos.
