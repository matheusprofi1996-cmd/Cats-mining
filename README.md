# Cats-mining
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>CATS Mining 🐱</title>
  <style>
    body {
      background: #0f172a;
      color: white;
      font-family: Arial;
      text-align: center;
      padding: 30px;
    }

    .box {
      background: #1e293b;
      padding: 20px;
      border-radius: 15px;
      max-width: 400px;
      margin: auto;
      box-shadow: 0 0 20px rgba(0,0,0,0.5);
    }

    button {
      background: #22c55e;
      border: none;
      padding: 15px;
      color: white;
      border-radius: 10px;
      cursor: pointer;
      font-size: 16px;
      margin-top: 15px;
    }

    button.stop {
      background: #ef4444;
    }

    .stat {
      margin-top: 15px;
      font-size: 18px;
    }
  </style>
</head>
<body>

  <div class="box">
    <h1>🐱 CATS Mining</h1>
    <p>Ajude animais enquanto gera recompensas</p>

    <button id="toggleBtn">Ativar</button>

    <div class="stat">Saldo: <span id="balance">0.0000</span> CATS</div>
    <div class="stat">Doado: <span id="donated">0.0000</span> CATS</div>
    <div class="stat">Status: <span id="status">Desligado</span></div>
  </div>

<script>
let mining = false;
let balance = 0;
let donated = 0;

const balanceEl = document.getElementById("balance");
const donatedEl = document.getElementById("donated");
const statusEl = document.getElementById("status");
const btn = document.getElementById("toggleBtn");

btn.onclick = () => {
  mining = !mining;

  if (mining) {
    btn.innerText = "Parar";
    btn.classList.add("stop");
    statusEl.innerText = "Ativo 🟢";
  } else {
    btn.innerText = "Ativar";
    btn.classList.remove("stop");
    statusEl.innerText = "Desligado 🔴";
  }
};

// Simulação inteligente de geração
setInterval(() => {
  if (mining) {
    let ganho = Math.random() * 0.002;
    let doacao = ganho * 0.3;

    balance += ganho - doacao;
    donated += doacao;

    balanceEl.innerText = balance.toFixed(4);
    donatedEl.innerText = donated.toFixed(4);
  }
}, 1000);
</script>

</body>
</html>
