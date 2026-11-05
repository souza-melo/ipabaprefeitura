# Template PortalFacil — Prefeitura Municipal de Ipaba/MG

Identidade visual **própria** (não é o template de Santana recolorido), construída no
método da skill `portalfacil-design-to-template` e **100% HTML + CSS (sem JavaScript)**.

## Como ver
- **Preview fiel:** abra `preview.html` (ou sirva a pasta e acesse `/preview.html`). É autocontido
  e mostra exatamente como a home vai ficar — com o menu, os boxes simulados e o responsivo.
- **Deploy no PortalFacil:** suba a pasta como `templateXX/`. O `index_1.html` (home) e o
  `index_2.html` (interna) usam as tags de box; o conteúdo dinâmico (menu, banners, notícias,
  busca) é preenchido pelo portal.

## Arquivos
```
template-ipaba/
├── index_1.html          # Home (documento PortalFacil completo, com boxes)
├── index_2.html          # Página interna (<InternalContent>)
├── head_elements_1.json  # <head> da home (fontes, ícones, CSS)
├── head_elements_2.json  # <head> da interna
├── css/
│   ├── style.css         # Design system (tokens :root PT-BR) + classes dos boxes
│   └── responsive.css    # 992 / 768 / 576 + menu mobile (checkbox-hack, sem JS)
├── js/script.js          # VAZIO por decisão de projeto (sem JS autoral)
├── images/logotipo.webp  # Brasão oficial de Ipaba (+ ipaba-marco.jpg, ipaba-orla.jpg no hero)
├── preview.html          # Preview visual autocontido (CSS puro)
└── preview-shots/        # Capturas do preview (desktop e mobile)
```

## Identidade (cores reais de Ipaba)
| Token | Hex | Uso |
|---|---|---|
| `--verde-600` | `#1e9e43` | **Primária** — header, botões, destaques |
| `--verde-700/800` | `#157a33` / `#11672c` | Rodapé, gradientes escuros |
| `--azul-600` | `#1e6a90` | **Secundária** — barra de menu |
| `--ambar-500` | `#f5b301` | **Acento** — e-SIC, busca, sublinhados |
| neutros | `#10211a` / `#2f4038` | Títulos / corpo |

Tipografia mantida igual à de Santana a seu pedido: **Montserrat** (títulos) + **DM Sans** (corpo).

## Boxes do PortalFacil usados (e o que preenchem)
| Seção | Box |
|---|---|
| Menu principal (barra azul) | `<MenuPortal local="main">` |
| Busca no header | `<BuscaAvancadaBox placeholder="O que você procura?">` |
| Hero / banners | `<BannerBox display-mode="slider" origin-data="latest" members="I" size="5">` |
| Notícias — destaque | `<MateriaBox display-mode="slider" members="I,T,H,D" size="5" date-format="dd/MM/yyyy">` |
| Notícias — lista | `<MateriaBox display-mode="list-static" members="I,T,D" size="2" use-btn-view-more>` |
| Página interna | `<InternalContent>` |

**Conteúdo fixo (HTML):** barra de acessibilidade, acesso rápido (Cidadão/Empresa/Turismo/Servidor/e-SIC),
grade de **Serviços & Secretarias**, faixa e-SIC, cards de Transparência e o rodapé.

## O que foi colocado "no lugar dos pontos de acesso" (seu pedido)
As secretarias (menu superior) e os serviços (box lateral) do portal atual de Ipaba viraram:
- **Acesso rápido** (4 cards flutuantes): Cidadão, Empresa, Turismo, Espaço do Servidor.
- **Serviços & Secretarias** na **mesma seção de abas** do portal de Santana do Paraíso (usada como
  parâmetro), porém **100% CSS (sem JS)** e com a identidade de Ipaba. São **19 cards verticais**
  (ícone em tile pastel + título + descrição + seta) filtráveis por **8 abas**:
  **Todos · Educação · Saúde · Fazenda · Administração · Transparência · Licitações · Atendimento**.
  - *Educação:* Sec. de Educação.
  - *Saúde:* Sec. de Saúde, Vigilância Sanitária.
  - *Fazenda:* Sec. de Fazenda.
  - *Administração:* Estrutura Adm., Bolsa Social, Processo Seletivo, Concurso Público, Legislação.
  - *Transparência:* Transparência, Contas Públicas, Respons. Fiscal, Diário Oficial.
  - *Licitações:* Licitações.
  - *Atendimento:* Protocolo Online, Perguntas Frequentes, Mapa do Site, Ouvidoria, e-SIC/LAI.
## Cabeçalho no modelo de Santana do Paraíso (a pedido — só as cores mudam)
A topbar, o header e o menu seguem o layout de Santana, recoloridos para a identidade verde de Ipaba:
- **Topbar (verde-escuro):** atalhos de acessibilidade à esquerda (*Ir ao conteúdo (1) · Ir ao menu (2) ·
  Ir à busca (3) · Ir ao rodapé (4)*) e, à direita, o botão **âmbar "Acessar Serviços"** (`.topbar-cta` → `#servicos`)
  — presente em `index_1`/`preview`, **ausente no `index_2`** (página interna).
- **Header (verde):** **brasão** (`logotipo.webp`) + escrita em HTML **"Prefeitura de Ipaba"** (branca) +
  **busca** + o **menu ao lado da busca** (inline, à direita) — sem barra de menu separada.
- **Menu (dentro do header):** grupos iguais aos de Santana — **A Cidade** (Localização, História, Turismo,
  Símbolos e Hino), **Prefeitura** (Organograma, Telefones Úteis), **Legislação** (Decretos, Portarias, Lei
  Orgânica, Leis Ordinárias, Instruções Normativas) + **Abra sua Empresa** e **Iluminação Pública**.
  No desktop é inline; no mobile vira **barra azul com hambúrguer** (checkbox-hack). No `index_1/2` o
  `MenuPortal` continua (itens no admin); no `preview.html` o menu é fixo.
- **Hero (painel):** mostra **somente 2 fotos reais de Ipaba** (`ipaba-marco.jpg` — marco "Terra boa é Ipaba";
  `ipaba-orla.jpg` — orla da lagoa) em **crossfade automático** (CSS puro, sem JS). O texto de boas-vindas
  foi removido.

## Identidade própria mantida (vs. clone de Santana)
- Paleta verde/azul-petróleo/âmbar (vs. navy/ciano).
- **Cards de acesso rápido flutuando** sobre o hero.
- **Serviços & Secretarias em abas** (mesmo padrão de Santana), 100% CSS.
- Rótulos de seção com **kicker + barra âmbar**; faixa e-SIC âmbar; rodapé verde institucional.
- Hero com legenda de boas-vindas sobre o banner.

## Sem JavaScript — como as interações foram resolvidas
- **Dropdowns do menu:** `:hover` / `:focus-within` (desktop).
- **Filtro de Serviços por abas:** radio-hack — 8 `<input type="radio" name="svc-filter">` ocultos + `<label>`
  (as abas). `#svcf-<cat>:checked ~ .svc-grid .svc-card:not(.cat-<cat>) { display:none }` esconde os cards
  fora da categoria; a aba ativa e o foco por teclado também saem de `:checked`/`:focus-visible`. Sem JS.
- **Menu mobile:** checkbox-hack (`#nav-toggle:checked ~ .navbar-nav`) — abre/fecha sem JS.
- **Voltar ao topo:** âncora `href="#header"` (sempre visível).
- **Ano do rodapé:** fixo no HTML (2026).
- Carrossel de banners/notícias: provido pelos próprios boxes no servidor (não exige JS autoral).

## Placeholders (trocar na implantação)
- `<!-- PLACEHOLDER -->` **Imagens do hero e das notícias:** no preview são gradientes; em produção
  vêm do BannerBox/MateriaBox. Datas/manchetes das notícias no preview são ilustrativas (conteúdo real: Orla da Lagoa Central, CMEI Dona Zica, Escola Laélio Bento Pereira).
- **Menu principal:** no `index_1/2` vem do `MenuPortal` (admin do PortalFacil); no preview os itens/links (A Cidade, Prefeitura, Legislação, Abra sua Empresa, Iluminação Pública) são ilustrativos (`href="#"`).
- **Hero (banner):** no preview usa as 2 fotos reais de Ipaba; no `index_1/2` o `BannerBox` traz os banners do admin.
- **Faixa "Ipaba em números"** (banda verde entre Serviços e Notícias): números ilustrativos
  (12 serviços / 24h / 100% transparência). **Habitantes = "+19 mil"** (IBGE ~19 mil; o modelo
  de Santana trazia "+45" — ajuste o valor conforme o dado oficial desejado).

## Verificações feitas (preview)
- ✅ Desktop 1440: header, menu (17 itens), hero, acesso rápido, serviços, notícias, e-SIC, transparência, rodapé.
- ✅ Mobile 390: sem scroll horizontal (`scrollWidth = 390`); grids em 1 coluna; **menu hambúrguer abre via CSS**.
- ✅ Dropdowns por hover/foco; foco visível (âmbar).
- ✅ Sem nenhum arquivo JS autoral.

## Próximos passos sugeridos
1. Trocar os `href="#"` pelos links reais do PortalFacil de Ipaba.
2. Cadastrar banners e notícias no admin (os boxes assumem).
3. Opcional: favicon dedicado (hoje aponta para `logotipo.webp`).
4. Rodar axe/Lighthouse e ajustar contrastes finos se necessário.
