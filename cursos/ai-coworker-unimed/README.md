# LP · AI Coworker Unimed — AIMANA

Landing page da jornada **AI Coworker Unimed** (turma 15/06/2026). Preview estático, pronto para revisão de UX e subida no GitHub.

## Como abrir localmente
Basta abrir `index.html` no navegador. É HTML + CSS puro, single file, sem build step e sem dependências externas de JS (só Google Fonts via CDN).

## Estrutura

```
lp-ai-coworker/
├── index.html                 # página completa, single-file (CSS embedded)
└── assets/
    ├── logo-aimana-branco.svg
    ├── luiz-otero.jpg
    ├── edson-cascais.jpg
    ├── barbara vallim.jpeg
    ├── andre luiz.jpeg
    ├── gibram.jpeg
    ├── sergio.jpeg
    ├── rafael_cunha.jpeg
    └── nano-banana/
        ├── coworker-hero.jpg
        ├── coworker-opening.jpg
        └── coworker-bancada.jpg
```

## Identidade visual

Paleta AIMANA aplicada via CSS variables no `<style>` do topo do HTML:

- Navy `#2b296b` · Ink `#0f0f2d` · Blue `#2c479e`
- Teal `#2bbcb6` · Cream `#f7f4ec`
- Accent Unimed Green `#00995d`
- Accent Pink `#e91e90`

Tipografia: **Titillium Web** (300, 400, 600, 700, 900) via Google Fonts.

## Notas para UX

- Fotos dos experts (`.host-ph.filled`) usam `onerror` para fallback a iniciais caso a imagem falhe.
- Dois nomes de arquivo contêm espaço (`andre luiz.jpeg`, `barbara vallim.jpeg`) — no HTML são referenciados como `andre%20luiz.jpeg` / `barbara%20vallim.jpeg`. Se preferir, renomeie para `kebab-case` e atualize os `src=`.
- Links para a LP irmã (Curso) apontam para `../lp-curso-unimed/index.html`; ajuste conforme estrutura final do site.
- Nenhum JS na página — modo edição foi removido para produção.
- **Carrossel "Enterprises que confiam na AIMANA"** (2ª dobra): 12 logos carregados diretamente do site institucional (`https://www.aimana.ai/Logos%20Clientes%20sem%20fundo/N.png`). Animação CSS infinita (48s). Para produção final, baixar e hospedar os logos no próprio CDN do site.

## Notas para dev

- Sem dependências externas além de Google Fonts.
- Imagens hero/opening são JPEGs grandes (≈7 MB cada). Sugerido gerar versões WebP responsivas (`srcset`) antes de produção.
- O form `#inscricao` está sem `action=` — conectar à API/ferramenta de captura (HubSpot, RD, Webflow Forms etc.).
- Página inteira é acessível single-file: mover CSS/JS inline para arquivos separados se preferir padrão do repositório.
- Testar em Chrome, Safari e Firefox — usa CSS Grid com áreas nomeadas e `clamp()` em algumas tipografias.