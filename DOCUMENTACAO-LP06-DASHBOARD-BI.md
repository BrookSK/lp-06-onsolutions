# Documentação — LP06 Dashboards e BI

## 1. Objetivo da landing page
Landing page de captação de leads para o serviço **Dashboards e BI** da ON Solutions Brasil. O objetivo central é levar o visitante a iniciar uma conversa no WhatsApp com uma mensagem pronta, destacando painéis em tempo real, unificação de dados de vários sistemas e relatórios automáticos. A conversão principal é o clique nos botões de WhatsApp.

## 2. Arquivo de referência e URL de destino
- **Arquivo de referência (fonte de verdade):** `06-lp-dashboard-bi.html`
- **URL de destino:** https://onsolutionsbrasil.com.br/lp/dashboard-bi/
- **Arquivo implementado:** `index.html` (na raiz do repositório).
- **Nota de deploy:** o domínio de publicação é `lp-06.onsolutionsbrasil.com.br`, cujo document root (via Plesk/Git) aponta para a raiz do repositório. Por isso o `index.html` foi colocado na **raiz** — assim a página é servida diretamente em `https://lp-06.onsolutionsbrasil.com.br/`. (A estrutura inicial em `lp/dashboard-bi/index.html` causava **403 Forbidden** na home do domínio por ausência de documento de índice na raiz.)

## 3. Estrutura de todas as seções
Ordem idêntica à referência:

1. **Cabeçalho fixo (`header.top`)** — logo + nome, telefone `(11) 97224-3329`, botão "Orçamento" (WhatsApp). Esconde ao rolar para baixo, reaparece ao rolar para cima e fica visível perto do topo.
2. **Hero (`section.hero`)** — badge "Orçamento direto no WhatsApp", título, subtítulo, 3 diferenciais (`.points`, visíveis a partir de 860px), selos de confiança (`.trust`) e o componente visual de conversa do WhatsApp (`.chat`) com cabeçalho, avatar, balão de mensagem (`.bubble`) e dica.
3. **Desafios (`section#dores`)** — título, subtítulo e 4 opções interativas (`.pain`) com `aria-pressed`, além da linha de orientação (`.pains-hint`).
4. **Benefícios (`section#beneficios`)** — 4 cards com ícones SVG, títulos e descrições específicos de Dashboards e BI.
5. **Clientes e indicadores (`section#clientes`)** — indicadores `100+`, `50+`, `Brasil e exterior` e carrossel de logotipos (`.marq`).
6. **Como funciona (`section#como-funciona`)** — 3 passos numerados.
7. **Oferta (`section#oferta`)** — bloco em degradê "O que você leva da conversa" com 3 itens.
8. **FAQ (`section#duvidas`)** — 3 perguntas em `<details>/<summary>` (abrir/fechar nativo).
9. **Chamada final (`section.final#conversa`)** — título, orientação e nota dos 30 minutos.
10. **Rodapé (`footer.foot`)** — identificação, descrição institucional, e-mail e links de LGPD/Privacidade.
11. **Botão fixo inferior (`.sticky`)** — "Pedir orçamento no WhatsApp", respeitando a área segura (`env(safe-area-inset-bottom)`).

## 4. Textos e conteúdos implementados
Todos extraídos **ipsis litteris** da referência. Destaques:

- **Título hero:** "Dashboards e BI com os números da sua empresa em tempo real" (com `Dashboards e BI` em `<mark>` verde-menta).
- **Subtítulo:** "Painéis claros no computador e no celular para você decidir com dados, e não com palpite."
- **Diferenciais:** "Indicadores atualizados na hora"; "Dados de vários sistemas em um só painel"; "Relatórios automáticos em PDF e Excel".
- **Desafios:** "Só sei meus números depois do fechamento."; "Cada área me traz um número diferente."; "Não consigo ver tudo em um só lugar."; "Quero saber logo quando algo sai do rumo."
- **Benefícios:** "Painéis em tempo real"; "Indicadores do seu jeito"; "Gráficos que você explora"; "Alertas de metas" (com as respectivas descrições).
- **Indicadores:** `100+` projetos entregues; `50+` clientes ativos; `Brasil e exterior` — clientes nacionais e internacionais.
- **Como funciona:** 1) Você chama no WhatsApp; 2) Entendemos o seu cenário; 3) Você recebe a proposta.
- **Oferta:** "O que você leva da conversa" + 3 itens de gargalos/prioridade/investimento.
- **FAQ:** "Quanto custa?"; "Meus dados estão em vários sistemas. Dá certo?"; "Minha equipe vai conseguir usar?" (respostas íntegras).
- **Final:** "Pronto para falar sobre dashboards e BI?"
- **Rodapé:** `contato@onsolutionsbrasil.com.br`, "LGPD e proteção de dados", "Política de privacidade".
- **Botão fixo:** "Pedir orçamento no WhatsApp".

## 5. Componentes utilizados
Página autossuficiente (single file), reproduzindo os componentes da referência: cabeçalho translúcido com desfoque, hero com degradê, card de conversa do WhatsApp, botões de desafio toggláveis, cards de benefícios, bloco de indicadores, carrossel de logotipos, passos numerados, bloco de oferta em degradê, acordeão de FAQ (`<details>`), chamada final e botão fixo inferior. Não há dependências externas além da fonte Poppins (Google Fonts).

## 6. Identidade visual e estilos
- **Paleta (CSS vars):** `--ink #0B1220`, `--navy #0F172A`, `--bg #F5F8FB`, `--line #E2E8F0`, `--text #0F172A`, `--soft #52627A`, `--mint #5EEAD4`, `--teal #0D9488`, `--tealD #0F766E`, `--wa #25D366`, `--waD #1EBE5B`.
- **Tipografia:** Poppins (pesos 400–800), com fallback `"Segoe UI", system-ui, -apple-system, sans-serif`.
- Cabeçalho escuro translúcido com `backdrop-filter: blur`, hero em degradê radial+linear, botões WhatsApp em verde com cantos arredondados, cards com bordas suaves e sombras, seções claras/escuras alternadas. CSS transcrito integralmente da referência (inclui os dois `data:image/svg+xml` dos checkmarks).

## 7. Responsividade e breakpoints
CSS mobile-first com media queries nos mesmos pontos da referência:
- `max-width: 400px` — oculta o sufixo " Brasil" da marca.
- `max-width: 430px` — ajustes no CTA (esconde a seta, reduz padding/fonte).
- `max-width: 380px` — reduz fonte/gap dos CTAs; ajusta largura do container `.w`.
- `max-width: 340px` — compacta ainda mais os CTAs e reduz o ícone.
- `min-width: 860px` — layout em grid do hero/oferta/rodapé, exibe telefone e `.points`, colunas dos cards (benefícios 4 col, passos/stats 3 col) e espaçamentos ampliados.
- `prefers-reduced-motion: reduce` — desativa animações/transições e o auto-scroll do carrossel.

## 8. Funcionamento dos desafios interativos
- Cada `.pain` é um `<button>` com `aria-pressed` ("false"/"true"); o clique alterna o estado (marca/desmarca) e permite múltiplas seleções.
- Itens selecionados recebem destaque visual (borda e fundo verdes + check).
- A cada mudança, a função `sync()` recalcula a mensagem e atualiza **todos** os links com `data-wa-main` (telefone, orçamento do topo e barra fixa) e o balão de prévia (`[data-bubble]`) do hero.
- Orientações (`.pains-hint`): vazio sem seleção; texto de incentivo com 1 seleção; com 2+ informa a quantidade marcada.
- Comportamento da mensagem:
  - **Sem seleção:** mensagem padrão.
  - **Uma seleção:** "… Meu maior desafio hoje: <desafio>."
  - **Mais de uma:** "… Meus maiores desafios hoje: <d1>; <d2>; …" (separados por ponto e vírgula).
- Ao mudar o hash da URL, as seleções e orientações são resetadas.

## 9. Integração com WhatsApp
- **Número:** `5511972243329` (constante `WA_NUMBER`).
- **Link-base:** `https://wa.me/5511972243329`.
- Função `waLink(t)` monta o link com `?text=` + `encodeURIComponent(t)`.
- Todos os `[data-wa]` recebem `href`, `target="_blank"` e `rel="noopener"`.
- Pontos de clique (`data-pos`): `topo-telefone`, `topo`, `barra-fixa`.

## 10. Mensagem padrão e mensagem dinâmica
- **Padrão:** `Olá, vim do site e gostaria de saber mais sobre os serviços de Dashboards & BI.`
  (no HTML aparece como `Dashboards &amp; BI`; em runtime o texto enviado contém `&`.)
- **Dinâmica:** acrescenta os desafios selecionados conforme a seção 8, e ainda anexa a origem do anúncio (ver seção 11) quando aplicável.

## 11. Rastreamento e parâmetros de origem
- Config `ON_TRACKING = { gtmId:"", ga4Id:"", gadsId:"", gadsConversionLabel:"" }` — **todos vazios**, portanto nenhum script de rastreamento é carregado (GTM/GA4/Google Ads só carregam se preenchidos). Nenhum identificador fictício foi inserido.
- `ON_APPEND_ORIGIN = true`: captura `utm_term`/`kw`, `utm_campaign` e `gclid` da query string e, havendo algum, acrescenta uma linha "Origem: anúncio | Termo: … | Campanha: …" à mensagem do WhatsApp.
- Eventos: `whatsapp_click` (sempre, via `dataLayer`) e `generate_lead` (via `gtag`, quando houver tag configurada); conversão do Google Ads disparada apenas se `gadsId` e `gadsConversionLabel` estiverem preenchidos.

## 12. Imagens e logotipos utilizados — PENDÊNCIA
A referência embute as imagens em **Base64** (binário). Como a transcrição manual desses blocos corrompe os bytes (verificado: decodificação inválida), eles **não foram transcritos à mão** para não gerar imagens quebradas/inventadas. No lugar, cada imagem está marcada com um placeholder claro, preservando `alt`, `width`, `height` e classes originais para manter o layout idêntico:

| Placeholder | Onde aparece | `alt` | Dimensões |
|---|---|---|---|
| `TODO_LOGO_BRAND` | cabeçalho e avatar do chat | (vazio, decorativo) | 32×32 e 38×38 |
| `TODO_LOGO_1` | carrossel | "Logo Braziliana" | — |
| `TODO_LOGO_2` | carrossel | "Logo Quatri Automação" | — |
| `TODO_LOGO_3` | carrossel | "Logo Brooks Construtora" | — |
| `TODO_LOGO_4` | carrossel | "Logo CrossHR" | — |
| `TODO_LOGO_5` | carrossel | "Logo MultiLife Care" | — |
| `TODO_LOGO_6` | carrossel | "Logo Mafedo Engenharia" | — |

Observações:
- O **favicon** (também Base64 na referência) está no `<link rel="icon">`; atualmente com placeholder a ser substituído pelo Base64 original.
- O 7º chip do carrossel é **texto** ("Central RZ"), exatamente como na referência — não é imagem.
- **Ação pendente:** substituir cada placeholder pelo Base64 exato da referência (serão enviados separadamente). Após isso, os logos ficam idênticos ao original. Nenhum logo foi substituído por imagem genérica.

## 13. Metadados e SEO
- **Title:** `Dashboards e BI | ON Solutions Brasil`
- **Description:** `Painéis claros no computador e no celular para você decidir com dados, e não com palpite.`
- **Canonical:** `https://onsolutionsbrasil.com.br/lp/dashboard-bi/`
- **Robots:** `noindex,follow`
- **Theme color:** `#0B1220`
- **viewport** com `viewport-fit=cover`; hierarquia de títulos (`h1` único no hero, `h2` nas seções, `h3` nos cards); `aria-pressed`, `aria-live`, `aria-label` e `aria-hidden` preservados; estados de foco visíveis (`:focus-visible`); `prefers-reduced-motion` respeitado; `decoding="async"` nas imagens do carrossel.

## 14. Arquivos criados e modificados
- **Criado:** `index.html` na raiz do repositório (estrutura, CSS, textos, interatividade, WhatsApp, rastreamento e SEO completos; logos como placeholder). Inicialmente em `lp/dashboard-bi/index.html` e depois movido para a raiz para casar com o document root do domínio `lp-06.onsolutionsbrasil.com.br` e resolver o 403 Forbidden.
- **Criado:** `DOCUMENTACAO-LP06-DASHBOARD-BI.md` (este arquivo).
- **Não modificado:** nenhum outro arquivo. O repositório não continha landing pages anteriores nem componentes compartilhados (apenas `README.md`), portanto não há risco de regressão em outras LPs.

## 15. Testes realizados e respectivos resultados
Executada uma suíte automatizada (Node.js) cobrindo estrutura, textos e lógica — **35/35 PASS**. Itens verificados:
- Metadados (title, description, canonical, robots, theme-color), doctype e `lang`.
- Presença e ordem das 8 seções, 4 desafios, 4 benefícios, 3 FAQ, indicadores, passos, oferta, final, rodapé e botão fixo.
- WhatsApp: número, `encodeURIComponent`, 3 `data-pos`.
- Rastreamento: `ON_TRACKING` vazio, eventos `whatsapp_click` e `generate_lead`, captura de `utm_term`/`kw`/`utm_campaign`/`gclid`.
- Placeholders: 2× `TODO_LOGO_BRAND` e 6× `TODO_LOGO_n`.
- **Lógica da mensagem dinâmica (simulada):** padrão sem seleção; "Meu maior desafio hoje:" com 1; "Meus maiores desafios hoje:" com separador `; ` para 2+ — todos corretos.

Testes **não** executados ainda (dependem de navegador/aprovação):
- Verificação visual pixel a pixel em navegador e em larguras reais (340/380/400/430/860px+).
- Clique real abrindo o WhatsApp.
- Animação do carrossel e comportamento de ocultar/mostrar o cabeçalho em rolagem real.

## 16. Problemas encontrados e soluções aplicadas
- **Imagens Base64 muito grandes / corrupção na transcrição:** a cópia manual dos blocos Base64 falhou na decodificação (comprimento inválido). Solução: não transcrever à mão; usar placeholders marcados preservando atributos e documentar a pendência para substituição pelos Base64 originais.
- **Escrita do arquivo em uma única operação falhava (limite de requisições):** solução — montar o `index.html` em blocos sequenciais (`head`+CSS, header, hero, seções, script).
- **Carrossel referencia `cases-track` (elemento de home inexistente):** comportamento preservado da referência; como a trilha já possui chips inline, o bloco de clonagem a partir de `cases-track` é ignorado e o loop/duplicação funciona normalmente na página standalone.

## 17. Pendências
1. **Substituir os placeholders de logo** (`TODO_LOGO_BRAND`, `TODO_LOGO_1`…`TODO_LOGO_6`) e o **favicon** pelos Base64 exatos da referência (serão enviados). Após isso, a fidelidade visual fica completa.
2. **Validação visual em navegador** e conferência de responsividade/comportamentos (carrossel, cabeçalho, WhatsApp) — a realizar mediante sua autorização.
