# Calculadora-en-html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora</title>
    <style>
        /* Añadimos estilos básicos para la calculadora */
        body {
            font-family: Arial, sans-serif;
        }

        .calculator {
            width: 220px;
            padding: 20px;
            margin: 100px auto;
            border: 1px solid #ccc;
            border-radius: 10px;
            background-color: #f9f9f9;
        }

        .display {
            width: 100%;
            height: 40px;
            background-color: #222;
            color: #fff;
            text-align: right;
            padding: 10px;
            margin-bottom: 10px;
            font-size: 24px;
            border-radius: 5px;
            box-sizing: border-box;
        }

        .btn {
            width: 50px;
            height: 50px;
            font-size: 20px;
            margin: 5px;
            cursor: pointer;
        }

        .row {
            display: flex;
            justify-content: space-between;
        }
    </style>
</head>
<body>

    <div class="calculator">
        <input type="text" class="display" id="display" disabled>
        <div class="row">
            <button class="btn" onclick="clearDisplay()">C</button>
            <button class="btn" onclick="appendToDisplay('(')">(</button>
            <button class="btn" onclick="appendToDisplay(')')">)</button>
            <button class="btn" onclick="appendToDisplay('/')">/</button>
        </div>
        <div class="row">
            <button class="btn" onclick="appendToDisplay('7')">7</button>
            <button class="btn" onclick="appendToDisplay('8')">8</button>
            <button class="btn" onclick="appendToDisplay('9')">9</button>
            <button class="btn" onclick="appendToDisplay('*')">*</button>
        </div>
        <div class="row">
            <button class="btn" onclick="appendToDisplay('4')">4</button>
            <button class="btn" onclick="appendToDisplay('5')">5</button>
            <button class="btn" onclick="appendToDisplay('6')">6</button>
            <button class="btn" onclick="appendToDisplay('-')">-</button>
        </div>
        <div class="row">
            <button class="btn" onclick="appendToDisplay('1')">1</button>
            <button class="btn" onclick="appendToDisplay('2')">2</button>
            <button class="btn" onclick="appendToDisplay('3')">3</button>
            <button class="btn" onclick="appendToDisplay('+')">+</button>
        </div>
        <div class="row">
            <button class="btn" onclick="appendToDisplay('0')">0</button>
            <button class="btn" onclick="appendToDisplay('.')">.</button>
            <button class="btn" onclick="calculate()">=</button>
        </div>
    </div>

    <script>
        // Función para añadir números o símbolos a la pantalla
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        // Función para limpiar la pantalla
        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        // Función para realizar el cálculo
        function calculate() {
            let expression = document.getElementById('display').value;
            try {
                let result = eval(expression);
                document.getElementById('display').value = result;
            } catch (error) {
                document.getElementById('display').value = 'Error';
            }
        }
    </script>
</body>
</html>
