# LP · Curso IA no Sistema Unimed — AIMANA

Landing page do **Curso gratuito "IA no Sistema Unimed"** (12/05/2026). Preview estático, pronto para revisão de UX e subida no GitHub.

## Como abrir localmente
Basta abrir `index.html` no navegador. É HTML + CSS puro, single file, sem build step e sem dependências externas de JS (só Google Fonts via CDN).

## Estrutura

```
lp-curso-unimed/
├── index.html                 # página completa, single-file (CSS embedded)
└── assets/
    ├── logo-aimana-branco.svg
    ├── luiz-otero.jpg
    ├── edson-cascais.jpg
    └── nano-banana/
        ├── curso-hero.jpg
        └── curso-opening.jpg
```

## Identidade visual

Paleta AIMANA aplicada via CSS variables no `<style>` do topo do HTML:

- Navy `#2b296b` · Ink `#0f0f2d` · Blue `#2c479e`
- Teal `#2bbcb6` · Cream `#f7f4ec`
- Accent Unimed Green `#00995d`
- Accent Pink `#e91e90`

Tipografia: **Titillium Web** (300, 400, 600, 700, 900) via Google Fonts.

## Notas para UX

- Fotos dos hosts (Luiz Otero, Edson Cascais) usam `onerror` para fallback a iniciais caso a imagem falhe.
- Links para a LP irmã (AI Coworker) podem ser adicionados via `../lp-ai-coworker/index.html` se necessário.
- Nenhum JS na página — modo edição foi removido para produção.
- **Carrossel "Enterprises que confiam na AIMANA"** (2ª dobra): 12 logos carregados diretamente do site institucional (`https://www.aimana.ai/Logos%20Clientes%20sem%20fundo/N.png`). Animação CSS infinita (48s). Para produção final, baixar e hospedar os logos no próprio CDN do site.

## Notas para dev

- Sem dependências externas além de Google Fonts.
- Imagens hero/opening são JPEGs grandes (hero ≈7 MB). Sugerido gerar versões WebP responsivas (`srcset`) antes de produção.
- O form `#inscricao` está sem `action=` — conectar à API/ferramenta de captura (HubSpot, RD, Webflow Forms etc.).
- Página inteira é acessível single-file: mover CSS/JS inline para arquivos separados se preferir padrão do repositório.
- Testar em Chrome, Safari e Firefox 