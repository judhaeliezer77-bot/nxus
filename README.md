<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NEXUS-Δ PRIME — Presentación</title>
<style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body, html {
        height: 100%;
        width: 100%;
        background: #000;
        color: #fff;
        font-family: "Garamond", serif;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 10px;
    }

    .container {
        text-align: center;
        max-width: 90%;
        padding: 30px;
        border: 1px solid #222;
        box-shadow: 0 0 30px rgba(255,255,255,0.05) inset;
        opacity: 1;
        transition: opacity 1s ease;
    }

    .symbol {
        font-size: 80px;
        font-weight: bold;
        margin-bottom: 20px;
        animation: pulse 2s infinite;
    }

    .riddle {
        font-size: 18px;
        line-height: 1.6;
        margin-bottom: 25px;
        opacity: 0;
        animation: fadeIn 2s forwards 0.5s;
    }

    input[type="text"] {
        padding: 12px 15px;
        font-size: 18px;
        border: 1px solid #444;
        background: #111;
        color: #fff;
        margin-right: 5px;
        width: 60%;
        max-width: 200px;
    }

    button {
        padding: 12px 20px;
        font-size: 18px;
        border: 1px solid #444;
        background: #222;
        color: #fff;
        cursor: pointer;
        transition: all 0.3s;
    }

    button:hover {
        background: #333;
        border-color: #0ff;
        color: #0ff;
        transform: scale(1.05);
    }

    .error-message {
        color: #f55;
        margin-top: 12px;
        display: none;
        font-style: italic;
        font-size: 16px;
    }

    @keyframes pulse {
        0%, 100% { transform: scale(1); }
        50% { transform: scale(1.05); }
    }

    @keyframes fadeIn {
        from { opacity: 0;}
        to { opacity: 1;}
    }

    @media (max-width: 480px) {
        .symbol { font-size: 60px; }
        .riddle { font-size: 16px; }
        input[type="text"] { width: 100%; margin-bottom: 10px; }
        button { width: 100%; font-size: 16px; }
    }
</style>
</head>
<body>

<div class="container" id="container">
    <div class="symbol">ΩΔ</div>

    <div class="riddle">
        Entre el día y la noche me escondo,<br>
        sombra que susurra al mundo hondo.<br>
        Cuando el sol se despide y la luna me abraza,<br>
        solo mi nombre abrirá la plaza.<br><br>
        ¿Cuál es mi nombre secreto?
    </div>

    <div class="input-area">
        <input type="text" id="answer" placeholder="Escribe la respuesta">
        <button onclick="checkAnswer()">INGRESAR</button>
        <div class="error-message" id="error">Respuesta incorrecta</div>
    </div>
</div>

<script>
function checkAnswer() {
    const answer = document.getElementById('answer').value.trim().toLowerCase();
    const error = document.getElementById('error');
    const container = document.getElementById('container');

    if(answer === 'umbrae') {
        container.style.opacity = 0;
        setTimeout(() => {
            window.location.href = "fase2.3.html"; // Cambia al archivo real
        }, 1000);
    } else {
        error.style.display = 'block';
    }
}
</script>

</body>
</html>
