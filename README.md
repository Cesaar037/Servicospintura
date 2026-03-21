<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CJSM Pinturas</title>

<style>
body {margin:0;font-family:Arial;background:#f4f4f4;}
header {background:#1e3a8a;color:#fff;text-align:center;padding:20px;}
.container {max-width:900px;margin:auto;padding:20px;}
.card {background:#fff;padding:20px;border-radius:10px;margin-bottom:20px;box-shadow:0 0 10px #ccc;}
h2{text-align:center;}
input,select,textarea,button{width:100%;padding:12px;margin:8px 0;}
button{background:#16a34a;color:#fff;border:none;font-size:16px;}
.resultado{text-align:center;font-weight:bold;font-size:18px;}
.whatsapp{display:block;text-align:center;background:#25D366;color:#fff;padding:12px;text-decoration:none;border-radius:8px;margin-top:10px;}
.galeria img{width:100%;border-radius:10px;margin-top:10px;}
.avaliacao{background:#eee;padding:10px;border-radius:8px;margin-top:10px;}
</style>

</head>

<body>

<header>
<h1>CJSM PINTURAS</h1>
<p>Qualidade, confiança e acabamento profissional</p>
</header>

<div class="container">

<div class="card">
<h2>🎨 Faça seu orçamento</h2>

<select id="servico">
<option value="">Selecione o serviço</option>
<option value="18">Pintura interna simples</option>
<option value="25">Pintura padrão</option>
<option value="35">Pintura externa</option>
<option value="45">Pintura alto padrão</option>
<option value="50">Textura / grafiato</option>
<option value="40">Pintura de fachada</option>
<option value="60">Pintura industrial / epóxi</option>
</select>

<input type="number" id="area" placeholder="Área (m²)">

<button onclick="calcular()">Calcular Orçamento</button>

<div class="resultado" id="resultado"></div>

<a id="whatsapp" class="whatsapp" target="_blank">Falar no WhatsApp</a>

<p style="font-size:12px;text-align:center;">
*Valor estimado — pode variar após visita
</p>
</div>

<div class="card">
<h2>📸 Nossos serviços</h2>
<div class="galeria">
<img src="imagem1.jpg">
<img src="imagem2.jpg">
<img src="imagem3.jpg">
</div>
</div>

<div class="card">
<h2>⭐ Avaliações</h2>

<div id="listaAvaliacoes"></div>

<input type="text" id="nome" placeholder="Seu nome">
<textarea id="comentario" placeholder="Deixe sua avaliação"></textarea>

<button onclick="avaliar()">Enviar Avaliação</button>

</div>

</div>

<footer style="text-align:center;padding:15px;">
CJSM Pinturas - CNPJ: 60.956.057/0001-90
</footer>

<script>
function calcular(){
let preco=document.getElementById("servico").value;
let area=document.getElementById("area").value;

if(preco==""||area==""){alert("Preencha tudo");return;}

let total=preco*area;

document.getElementById("resultado").innerHTML="Valor: R$ "+total.toFixed(2);

let textoServico=document.getElementById("servico").options[document.getElementById("servico").selectedIndex].text;

let msg=`Olá, fiz um orçamento:
Serviço: ${textoServico}
Área: ${area}m²
Valor: R$ ${total.toFixed(2)}`;

let link="https://wa.me/5537999591572?text="+encodeURIComponent(msg);

document.getElementById("whatsapp").href=link;
}

function avaliar(){
let nome=document.getElementById("nome").value;
let comentario=document.getElementById("comentario").value;

if(nome==""||comentario==""){alert("Preencha tudo");return;}

let div=document.createElement("div");
div.className="avaliacao";
div.innerHTML="<b>"+nome+"</b><br>"+comentario;

document.getElementById("listaAvaliacoes").appendChild(div);

document.getElementById("nome").value="";
document.getElementById("comentario").value="";
}
</script>

</body>
</html>
