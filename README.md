// Backend simples usando Node.js + Express const express = require('express'); const cors = require('cors');

const app = express(); const PORT = process.env.PORT || 3001;

app.use(cors()); app.use(express.json());

// Banco de dados simulado const accounts = { "1234": ["Corvo Caído", "Ex-Prefeito", "Super Assassina"], "5678": ["Flash", "Mestre Marcial", "Retrógrado"], "9999": ["Cavaleiro da Morte", "Raposa Faísca"] };

// Rota para buscar os heróis da conta app.get('/api/heroes/:accountId', (req, res) => { const { accountId } = req.params; const heroes = accounts[accountId];

if (heroes) { res.json({ accountId, heroes }); } else { res.status(404).json({ error: 'Conta não encontrada' }); } });

app.listen(PORT, () => { console.log(Servidor rodando em http://localhost:${PORT}); });

npm install express cors  
node index.jscd hero-simulator npm install
