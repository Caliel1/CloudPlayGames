# 🎮 CloudPlayGames — Plataforma de Jogos Digitais

> A melhor plataforma de jogos digitais do Brasil. Mais de 12.000 títulos com download imediato.

---

## Visão Geral

CloudPlayGames é uma SPA (Single Page Application) de e-commerce de jogos digitais, construída com **React 18** puro (sem bundler), estilizada com CSS customizado e com suporte a **PWA** via Service Worker.

---

## Tecnologias

| Tecnologia | Uso |
|---|---|
| React 18 (CDN) | Interface e gerenciamento de estado |
| CSS Variables + Custom CSS | Estilização com tema dark neon |
| Google Fonts (Orbitron + Rajdhani) | Tipografia |
| Service Worker (PWA) | Cache offline e push notifications |
| Web App Manifest | Instalação como app nativo |

---

## Estrutura de Arquivos

```
files/
├── index.html       # App principal (HTML + CSS + React em um único arquivo)
├── manifest.json    # Configuração do PWA
├── sw.js            # Service Worker (cache offline + push notifications)
└── README.md        # Este arquivo
```

---

## Rotas do Site

A navegação é feita via estado interno do React com `window.history.pushState`. As rotas disponíveis são:

| Rota | Página | Descrição |
|---|---|---|
| `/` | **Home** | Hero, estatísticas, jogo em destaque, mais vendidos, categorias e lançamentos |
| `/login` | **Login / Cadastro** | Autenticação com e-mail/senha ou Google. Abas para entrar e criar conta |
| `/comprar` | **Loja** | Catálogo completo com busca e filtros por gênero (RPG, Ação, FPS, Puzzle...) |
| `/lista-de-desejo` | **Lista de Desejo** | Jogos salvos pelo usuário com opção de mover ao carrinho |
| `/pagamento` | **Checkout / Pagamento** | Resumo do carrinho, cupom de desconto e métodos: Cartão, PIX e Boleto |
| `/confirmacao` | **Confirmação do Pedido** | Tela de sucesso com número do pedido e próximos passos |

---

## Funcionalidades

- **Catálogo de jogos** com 8 títulos, badges (NOVO, OFERTA, HOT) e avaliações por estrelas
- **Carrinho de compras** com adição/remoção de itens e contador no navbar
- **Lista de desejo** com botão de coração em cada card
- **Sistema de autenticação** simulado (login, cadastro, logout, OAuth Google)
- **Checkout completo** com 3 métodos de pagamento (Cartão, PIX, Boleto)
- **Cupom de desconto** — use `CloudPlay10` para 10% off
- **Notificações toast** para feedback de ações do usuário
- **PWA** — instalável como app e funciona offline (cache-first)
- **Responsivo** — layout adaptado para mobile

---

## Como Usar

Basta abrir o `index.html` diretamente no navegador ou servir com qualquer servidor HTTP estático:

```bash
# Exemplo com Python
python -m http.server 8080

# Exemplo com Node.js (npx)
npx serve .
```

Acesse `http://localhost:8080` no navegador.

> **Nota:** O Service Worker requer HTTPS ou `localhost` para funcionar corretamente.

---

## Catálogo de Jogos

| Jogo | Gênero | Preço |
|---|---|---|
| Cyberpunk 2099 | RPG / Open World | R$ 199,90 (de R$ 299,90) |
| Shadow Realms | Action RPG | R$ 149,90 |
| Starforge | Estratégia / Ficção | R$ 89,90 |
| Neon Racer X | Corrida / Arcade | R$ 59,90 |
| Phantom Protocol | Stealth / Thriller | R$ 129,90 (de R$ 179,90) |
| Dragon Citadel | Fantasy / MMORPG | **GRÁTIS** |
| Hex Dimension | Puzzle / Sci-Fi | R$ 39,90 |
| Iron Vanguard | FPS / Tactical | R$ 179,90 |

---

## PWA — Progressive Web App

O projeto inclui suporte completo a PWA:

- **`manifest.json`** — define nome, ícones, cores e modo standalone
- **`sw.js`** — estratégia *Cache First* com fallback de rede; suporte a push notifications

---

© 2026 CloudPlayGames. Todos os direitos reservados.
