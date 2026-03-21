<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CJSM Pinturas</title>

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #f4f4f4;
}

header {
    background: #1e3a8a;
    color: white;
    padding: 20px;
    text-align: center;
}

section {
    padding: 20px;
    max-width: 900px;
    margin: auto;
}

.card {
    background: white;
    padding: 20px;
    margin-top: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px #ccc;
}

h2 {
    text-align: center;
}

input, button {
    width: 100%;
    padding: 10px;
    margin: 5px 0;
}

button {
    background: #16a34a;
    color: white;
    border: none;
    font-size: 16px;
    cursor: pointer;
}

.resultado {
    margin-top: 10px;
    font-size: 18px;
    text-align: center;
    font-weight: bold;
}

.whatsapp {
    display: block;
    text-align: center;
    margin-top: 15px;
    background: #25D366;
    color: white;
    padding: 12px;
    text-decoration: none;
    border-radius: 8px;
    font-weight: bold;
}

footer {
    text-align: center;
    padding: 15px;
    font-size: 14px;
    color: #555;
}
</style>

</head>

<body>

<header>
    <h1>CJSM PINTURAS</h1>
    <p>Profissionalismo e qualidade em pintura residencial e comercial</p>
</header>

<section>

<div class="card">
    <h2>🎨 Faça seu orçamento online</h2>

    <input type="number" id="area" placeholder="Área (m²)">
    <input type="number" id="preco" placeholder="Preço por m² (R$)">
    <input type="number" id="preparacao" placeholder="Preparação (R$)">
    <input type="number" id="extras" placeholder="Extras (R$)">

    <button onclick="calcular()">Calcular Orçamento</button>

    <div class="resultado" id="resultado"></div>

    <a id="whatsapp" class="whatsapp" target="_blank">
        Falar no WhatsApp
    </a>

    <p style="text-align:center; font-size:12px; margin-top:10px;">
        *Valor estimado — pode variar após avaliação no local.
    </p>
</div>

<div class="card">
    <h2>📌 Sobre nós</h2>
    <p>
        A CJSM Pinturas oferece serviços profissionais com qualidade, rapidez e excelente acabamento.
        Atendemos residências, comércios e galpões em toda a região.
    </p>
</div>

</section>

<footer>
    CJSM Pinturas - CNPJ: 60.956.057/0001-90
</footer>

<script>
function calcular() {
    let area = parseFloat(document.getElementById("area").value) || 0;
    let preco = parseFloat(document.getElementById("preco").value) || 0;
    let preparacao = parseFloat(document.getElementById("preparacao").value) || 0;
    let extras = parseFloat(document.getElementById("extras").value) || 0;

    let total = (area * preco) + preparacao + extras;

    document.getElementById("resultado").innerHTML =
        "Valor estimado: R$ " + total.toFixed(2);

    let mensagem = `Olá, fiz um orçamento no site CJSM Pinturas:
Área: ${area}m²
Valor estimado: R$ ${total.toFixed(2)}`;

    let numero = "5537999591572";

    let link = "https://wa.me/" + numero + "?text=" + encodeURIComponent(mensagem);

    document.getElementById("whatsapp").href = link;
}
</script>

</body>
</html>
