# 🎮 CloudPlayGames — Back-end + Front-end Integrados

## Como rodar

```bash
# 1. Instalar dependências
npm install

# 2. Iniciar servidor
npm start
# ou
node server.js

# 3. Abrir no navegador
http://localhost:3000
```

---

## Endpoints da API

| Método | Rota | Descrição |
|---|---|---|
| `GET` | `/api/games` | Lista todos os 16 jogos |
| `GET` | `/api/games/:id` | Busca jogo por ID |
| `GET` | `/api/games?genre=RPG` | Filtra por gênero |
| `GET` | `/api/games?badge=sale` | Filtra por badge (sale/new/hot) |
| `GET` | `/api/games?search=batman` | Busca por nome |
| `POST` | `/api/checkout` | Processa pedido do carrinho |

### Exemplo — POST /api/checkout

**Request body:**
```json
{
  "cart": [{ "id": 1, "title": "Cyberpunk 2077", "price": 199.90 }],
  "payMethod": "pix",
  "total": 199.90
}
```

**Response:**
```json
{
  "success": true,
  "message": "Compra processada com sucesso!",
  "orderNum": "NXP-482910",
  "items": [{ "id": 1, "title": "Cyberpunk 2077", "price": 199.90 }]
}
```

---

## Correções aplicadas

| Arquivo | Problema | Correção |
|---|---|---|
| `server.js` | `res.json(games)` → variável `games` era undefined | Corrigido para `GAMES` |
| `server.js` | Não servia o `index.html` | Adicionado `express.static(__dirname)` |
| `server.js` | Endpoint `/api/games` sem filtros | Adicionados query params `genre`, `badge`, `search` |
| `server.js` | Sem endpoint por ID | Adicionado `GET /api/games/:id` |
| `index.html` | `handlePay` não chamava a API | Integrado com `POST /api/checkout` |
| `index.html` | `ConfirmacaoPage` usava `GAMES[4], GAMES[0]` hardcoded | Agora recebe o `cart` real como prop |
| `index.html` | `HomePage` usava `GAMES.find/slice` global | Corrigido para usar a prop `games` da API |
| `package.json` | Sem script `start` | Adicionado `"start": "node server.js"` |
