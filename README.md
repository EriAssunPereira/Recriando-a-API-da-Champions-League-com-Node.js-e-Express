# Recriando a API da Champions League com Node.js e Express

Neste artigo, você aprenderá a construir uma API robusta e eficiente para acessar e manipular dados da **Champions League**. Utilizaremos **Node.js** e o framework **Express** para criar uma API que integra informações detalhadas sobre equipes, jogadores, partidas e classificações.

## Pré-requisitos
Certifique-se de ter o **Node.js** e o **npm** (Node Package Manager) instalados em seu ambiente de desenvolvimento.

## Passo 1: Configuração Inicial
1. Crie um novo diretório para o projeto e navegue até ele no terminal.
2. Inicialize um novo projeto Node.js com:
   ```bash
   npm init -y
   ```
3. Instale o Express com o comando:
   ```bash
   npm install express
   ```

## Passo 2: Estruturação do Projeto
Organize seu projeto em módulos para manter o código limpo e manutenível. Sugerimos a seguinte estrutura:

- `index.js`: Arquivo principal que inicia o servidor.
- `routes/`: Diretório para armazenar as rotas da API.
- `controllers/`: Diretório para os controladores que lidam com a lógica de negócios.
- `models/`: Diretório para os modelos de dados.

## Passo 3: Definição das Rotas
Vamos definir algumas rotas básicas para nossa API:

### Rotas de Equipes
No arquivo `routes/teams.js`, defina rotas para operações CRUD relacionadas às equipes:
```javascript
// routes/teams.js
const express = require('express');
const router = express.Router();

// Rota para listar todas as equipes
router.get('/', (req, res) => {
  // Lógica para listar equipes
  res.json({ teams: [] });
});

// Rota para obter uma equipe específica pelo ID
router.get('/:id', (req, res) => {
  // Lógica para obter uma equipe
  res.json({ team: {} });
});

module.exports = router;
```

### Rotas de Jogadores
No arquivo `routes/players.js`, defina rotas para operações CRUD relacionadas aos jogadores:
```javascript
// routes/players.js
const express = require('express');
const router = express.Router();

// Rota para listar todos os jogadores
router.get('/', (req, res) => {
  // Lógica para listar jogadores
  res.json({ players: [] });
});

// Rota para obter um jogador específico pelo ID
router.get('/:id', (req, res) => {
  // Lógica para obter um jogador
  res.json({ player: {} });
});

module.exports = router;
```

## Passo 4: Inicialização do Servidor
No arquivo `index.js`, configure o servidor Express e as rotas:
```javascript
// index.js
const express = require('express');
const app = express();
const teamsRoute = require('./routes/teams');
const playersRoute = require('./routes/players');

app.use('/teams', teamsRoute);
app.use('/players', playersRoute);

const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
  console.log(`Servidor rodando na porta ${PORT}`);
});
```

## Executando a API
Para iniciar a API, execute o comando:
```bash
node index.js
```
Agora você pode acessar as rotas `/teams` e `/players` para interagir com os dados da Champions League.

## Conclusão
Parabéns! Você criou uma API da Champions League com **Node.js** e **Express**. Continue desenvolvendo e expandindo sua API para incluir mais funcionalidades e dados.

Espero que este guia tenha sido útil para qualquer um que queira iniciar seu projeto de API.
