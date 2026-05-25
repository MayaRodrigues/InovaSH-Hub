# InovaSH Hub

> Site institucional do projeto de extensão **InovaSH Hub** — UTFPR Câmpus Santa Helena.
> Engajamento colaborativo da Quádrupla Hélice (Universidade, Governo, Setor Produtivo e Sociedade Civil) para a construção do hub de inovação da microrregião de Santa Helena, conectado ao Iguassu Valley.

---

## Sobre o projeto

O **InovaSH Hub** é um projeto de extensão universitária da UTFPR Câmpus Santa Helena que articula os quatro setores da Quádrupla Hélice (Etzkowitz, 2013) para criar colaborativamente um hub de inovação na região oeste do Paraná, alinhado às áreas prioritárias da Política Estadual de CT&I e conectado ao NAPI GDCT&I do Paraná.

- **Duração:** novembro de 2025 → novembro de 2028 (3 anos)
- **Instituição:** UTFPR — Câmpus Santa Helena
- **Parceria:** NAPI GDCT&I do Paraná · Iguassu Valley
- **Carga horária:** 4.800h
- **Alcance esperado:** 100+ pessoas diretamente atendidas, 1.000+ indiretamente impactadas

### Objetivos

1. **Levantar visão, necessidades e interesses** dos atores da Quádrupla Hélice por meio de formulários estruturados.
2. **Realizar eventos de consulta pública** para validar coletivamente os achados e desenhar o hub.
3. **Conectar os resultados ao NAPI GDCT&I PR**, garantindo continuidade e impacto sistêmico.

### Metodologia

Estruturação via **Matriz do Quadro Lógico (MQL)** — Pfeiffer (2000) e ASDI (2003) — aplicada de forma participativa com os atores do ecossistema.

### Etapas

| Etapa | Período | Status |
|------|---------|--------|
| 01 · Diagnóstico do ecossistema | 2025–26 | Em curso |
| 02 · Análise SWOT do Espaço Maker | 2026 | Em curso |
| 03 · Consulta pública | 2026–27 | A iniciar |
| 04 · Desenho do hub | 2027 | Planejada |
| 05 · Articulação NAPI GDCT&I | 2028 | Planejada |

### ODS alinhados

- **ODS 9** — Indústria, Inovação e Infraestrutura
- **ODS 11** — Cidades e Comunidades Sustentáveis
- **ODS 17** — Parcerias e Meios de Implementação

---

## Sobre o site

Website estático em HTML/CSS/JS puro, projetado com layout 100% fluido — sem larguras fixas, com tipografia escalonada via `clamp()` + `vw` e breakpoints estruturais para celular, tablet, notebook e desktop.

### Estrutura de arquivos

```
InovaSH Hub/
├── index.html          # Página principal (hero, sobre, objetivos, metodologia,
│                       # etapas, hélice, status, equipe, impacto, notícias, contato)
├── formularios.html    # Página dos dois formulários online (especialistas / público geral)
├── swot.html           # Página de destino do card SWOT (em construção)
├── style.css           # Estilos do projeto (tokens fluidos + breakpoints responsivos)
├── img/
│   ├── formulario1.jpg # QR Code do Formulário 1
│   └── formulario2.jpg # QR Code do Formulário 2
└── README.md
```

### Páginas

- **`index.html`** — landing principal com todas as seções do projeto (sobre, objetivos, metodologia, etapas, hélice, status, equipe, impacto, ODS, notícias, contato).
- **`formularios.html`** — apresenta os dois questionários da pesquisa:
  - *Formulário 1* — Avaliação de Governança, Gestão e Sustentabilidade em Habitats de Inovação (para especialistas).
  - *Formulário 2* — Hub de Inovação: a visão da comunidade (público geral).
- **`swot.html`** — placeholder "em breve" para a publicação dos resultados da análise SWOT do Espaço Maker.

---

## Stack & design

- **HTML5 + CSS3 + JavaScript vanilla** — zero dependências, zero build step.
- **Tipografia:** [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk), [Plus Jakarta Sans](https://fonts.google.com/specimen/Plus+Jakarta+Sans) e [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) via Google Fonts.
- **Layout fluido:** tokens com `clamp(min, fluid, max)` para espaçamentos, tipografia e raios.
- **Acessibilidade:** marcação semântica (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`), `aria-label` em controles, navegação por teclado.
- **Interatividade:**
  - Menu hamburguer responsivo.
  - Reveal-on-scroll com `IntersectionObserver`.
  - Anéis de progresso animados nos status cards.
  - Formulário de contato com confirmação inline.

### Breakpoints responsivos

| Faixa | Alvo |
|-------|------|
| `≤ 380px` | Mobile pequeno (iPhone SE etc.) |
| `≤ 640px` | Celular |
| `≤ 900px` | Tablet / colapso do nav para hamburguer |
| `≤ 1024px` | Tablet landscape / notebook pequeno |
| `≤ 1200px` | Notebook |
| `> 1200px` | Desktop |

---

## Como rodar

Como é um site 100% estático, basta abrir o `index.html` no navegador.

### Opção 1 — abrir direto

Clique duas vezes em `index.html` ou arraste-o para uma janela do navegador.

### Opção 2 — servidor local (recomendado para testes)

Qualquer servidor estático funciona:

```bash
# Python 3
python -m http.server 8000

# Node (com npx)
npx serve .

# VS Code: extensão "Live Server" → botão "Go Live"
```

Acesse: `http://localhost:8000`

---

## Personalização

### Cores e tokens

Todas as variáveis estão no topo do [`style.css`](style.css), dentro de `:root`:

```css
--ink:      #0A2540;   /* azul-escuro principal */
--blue:     #1E5AA8;   /* azul de apoio */
--tech:     #00C896;   /* verde "tech" / destaque */
--paper:    #F4F7FB;   /* fundo claro */
--muted:    #5C6E83;   /* texto secundário */
```

### Conteúdo

O conteúdo (textos, números, datas, integrantes da equipe, links dos formulários) está direto no HTML das três páginas — sem CMS, sem build. Editar é só abrir o arquivo e alterar.

### Links dos formulários

Os links dos dois formulários ficam em [`formularios.html`](formularios.html), dentro dos `<a class="btn ...">` de cada cartão. Substitua o `href` pelo link real do Google Forms (ou outra plataforma) e troque a imagem do QR Code em `img/formulario1.jpg` / `img/formulario2.jpg`.

---

## Equipe

- **Profa. Paula Regina Zarelli** — Coordenadora
- **Profa. Arlete T. Beuren** — Vice-coordenadora
- **Mayara R. Pereira** — Equipe técnica
<!-- - Vagas abertas para estudantes e voluntários-->
---
## Licença & créditos

© 2025 UTFPR Câmpus Santa Helena. Todos os direitos reservados.

Projeto de extensão universitária — versão `v0.1` (NOV 2025 — NOV 2028).


## 👨‍💻 Autores
Desenvolvido por Mayara Rodrigues Pereira @MayaRodrigues 
