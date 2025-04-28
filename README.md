<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Conversor de Tempo (Em Construção)</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    
            <div class="loading-spinner"></div>
        </div>
    </div>

    <div class="container">
        <h1>Conversor de Unidades de Tempo</h1>

        <div class="input-group">
            <label for="valor">Valor:</label>
            <input type="number" id="valor" placeholder="Digite o valor">
        </div>

        <div class="input-group">
            <label for="unidadeInicial">De:</label>
            <select id="unidadeInicial">
                <option value="segundos">Segundos</option>
                <option value="minutos">Minutos</option>
                <option value="horas">Horas</option>
            </select>
        </div>

        <div class="input-group">
            <label for="unidadeFinal">Para:</label>
            <select id="unidadeFinal">
                <option value="segundos">Segundos</option>
                <option value="minutos">Minutos</option>
                <option value="horas">Horas</option>
            </select>
        </div>

        <button onclick="converterTempo()">Converter</button>

        <div id="resultado" class="resultado"></div>
    </div>

    <script>
        function converterTempo() {
            const valor = parseFloat(document.getElementById('valor').value);
            const unidadeInicial = document.getElementById('unidadeInicial').value;
            const unidadeFinal = document.getElementById('unidadeFinal').value;
            const resultadoElemento = document.getElementById('resultado');

            if (isNaN(valor)) {
                resultadoElemento.textContent = "Digite um número.";
                return;
            }

            const taxas = {
                segundos: 1,
                minutos: 60,
                horas: 3600
            };

            const valorEmSegundos = valor * taxas[unidadeInicial];
            const resultado = valorEmSegundos / taxas[unidadeFinal];

            resultadoElemento.textContent = `${valor} ${unidadeInicial} = ${resultado.toFixed(2)} ${unidadeFinal}`;
        }
    </script>
</body>
</html>
