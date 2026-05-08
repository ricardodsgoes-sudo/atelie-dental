# Ateliê Dental

Site institucional do **Ateliê Dental — Laboratório de Próteses**. Site B2B voltado para dentistas e clínicas, com formulário de orçamento, vitrine de serviços, fluxo de trabalho, equipe e infraestrutura tecnológica.

## Estrutura

```
.
├── index.html              # Home
├── servicos.html           # Catálogo de serviços
├── como-funciona.html      # Fluxo de trabalho
├── sobre.html              # Empresa e equipe
├── tecnologia.html         # Estrutura CAD/CAM
├── contato.html            # Formulário + Google Maps
├── assets/
│   └── images/             # Imagens otimizadas (organizadas por contexto)
│       ├── brands/         # Logos de scanners/CAD/CAM
│       ├── cases/          # Casos antes/depois
│       ├── contato/        # Hero e secundárias da página de contato
│       ├── hero/           # Banners principais
│       ├── services/       # Imagens dos serviços
│       ├── team/           # Foto da equipe técnica
│       └── tecnologia/     # Banner e imagens de fluxo digital
└── docs/                   # Documentação interna (não deploy)
    ├── PRD.md              # Product Requirements
    └── references/         # Layouts e referências de design
```

## Stack

- **HTML5 + CSS3 + Vanilla JavaScript** — sem framework, sem build step
- **Google Fonts** — Cormorant Garamond + Manrope (carregamento via `<link>`)
- **Google Maps embed** — sem necessidade de API key na página de contato
- **IntersectionObserver** — animações de scroll com `prefers-reduced-motion` respeitado
- **Hamburger menu mobile** — drawer fullscreen com aria-expanded e ESC para fechar

## Como rodar localmente

Como o projeto é HTML estático puro, basta abrir qualquer arquivo `.html` no navegador. Para evitar problemas com `file://` (CORS no embed do mapa, por exemplo), use um servidor local simples:

```bash
# Python 3
python -m http.server 8000

# Node (se tiver npx instalado)
npx serve .
```

Acesse depois `http://localhost:8000`.

## Deploy (Hostinger)

Faça upload via FTP ou File Manager das seguintes pastas/arquivos para a raiz do `public_html`:

- Todos os arquivos `.html` da raiz
- Pasta `assets/`
- `README.md` (opcional)

**Não enviar** `docs/`, `.git/`, `.gitignore`, `.agent.md` — são arquivos de desenvolvimento.

## Design system

Tokens definidos em CSS variables em cada página (idênticos):

| Token | Valor | Uso |
|---|---|---|
| `--bg` | `#050505` | Fundo principal |
| `--ink` | `#f6f0e5` | Texto claro |
| `--gold` | `#d6a94f` | Dourado base |
| `--gold-2` | `#f0c76e` | Dourado claro / hover |
| `--muted` | `#bdb5a6` | Texto secundário |
| `--container` | `1320px` | Largura máxima |
| `--pad` | `28px` | Padding lateral |

**Tipografia**: Cormorant Garamond 600 (display) + Manrope 400/500/700/800 (UI/body).

**Breakpoints**: 1100px (tablet/desktop), 720px (mobile).
