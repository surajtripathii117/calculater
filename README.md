# calculater
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            background-color: #f9f9f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .calculator {
            width: 300px;
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        .calculator-screen {
            width: 100%;
            height: 50px;
            background: #f0f0f0;
            border: none;
            margin-bottom: 20px;
            text-align: right;
            font-size: 1.5em;
            padding: 10px;
            border-radius: 5px;
            box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .calculator-buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .button {
            height: 50px;
            background: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 1.2em;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .button:hover {
            background: #45a049;
        }

        .button.operator {
            background: #f0ad4e;
        }

        .button.operator:hover {
            background: #ec971f;
        }

        .button.clear {
            background: #d9534f;
        }

        .button.clear:hover {
            background: #c9302c;
        }

    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" class="calculator-screen" id="screen" disabled>
        <div class="calculator-buttons">
            <button class="button" onclick="appendValue('7')">7</button>
            <button class="button" onclick="appendValue('8')">8</button>
            <button class="button" onclick="appendValue('9')">9</button>
            <button class="button operator" onclick="appendValue('/')">&divide;</button>

            <button class="button" onclick="appendValue('4')">4</button>
            <button class="button" onclick="appendValue('5')">5</button>
            <button class="button" onclick="appendValue('6')">6</button>
            <button class="button operator" onclick="appendValue('*')">&times;</button>

            <button class="button" onclick="appendValue('1')">1</button>
            <button class="button" onclick="appendValue('2')">2</button>
            <button class="button" onclick="appendValue('3')">3</button>
            <button class="button operator" onclick="appendValue('-')">&minus;</button>

            <button class="button" onclick="appendValue('0')">0</button>
            <button class="button" onclick="appendValue('.')">.</button>
            <button class="button clear" onclick="clearScreen()">C</button>
            <button class="button operator" onclick="appendValue('+')">&plus;</button>

            <button class="button" style="grid-column: span 4;" onclick="calculateResult()">=</button>
        </div>
    </div>

    <script>
        const screen = document.getElementById('screen');

        function appendValue(value) {
            screen.value += value;
        }

        function clearScreen() {
            screen.value = '';
        }

        function calculateResult() {
            try {
                screen.value = eval(screen.value);
            } catch (error) {
                screen.value = 'Error';
            }
        }
    </script>
</body>
</html>
