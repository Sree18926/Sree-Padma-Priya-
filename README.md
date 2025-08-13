<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f7f7f7;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .calculator {
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.12);
            padding: 24px;
            max-width: 320px;
        }
        #display {
            width: 100%;
            height: 40px;
            font-size: 1.5em;
            margin-bottom: 16px;
            text-align: right;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 12px;
        }
        button {
            padding: 16px;
            font-size: 1.1em;
            border: none;
            border-radius: 4px;
            background: #eee;
            cursor: pointer;
            transition: background 0.2s;
        }
        button:hover {
            background: #d4d4d4;
        }
        .operator {
            background: #f9c846;
        }
        .operator:hover {
            background: #f7b600;
        }
        .equal {
            background: #4CAF50;
            color: #fff;
        }
        .equal:hover {
            background: #43a047;
        }
        .clear {
            background: #e57373;
            color: #fff;
        }
        .clear:hover {
            background: #d32f2f;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" readonly>
        <div class="buttons">
            <button onclick="append('7')">7</button>
            <button onclick="append('8')">8</button>
            <button onclick="append('9')">9</button>
            <button class="operator" onclick="append('/')">÷</button>
            <button onclick="append('4')">4</button>
            <button onclick="append('5')">5</button>
            <button onclick="append('6')">6</button>
            <button class="operator" onclick="append('*')">×</button>
            <button onclick="append('1')">1</button>
            <button onclick="append('2')">2</button>
            <button onclick="append('3')">3</button>
            <button class="operator" onclick="append('-')">−</button>
            <button onclick="append('0')">0</button>
            <button onclick="append('.')">.</button>
            <button class="clear" onclick="clearDisplay()">C</button>
            <button class="operator" onclick="append('+')">+</button>
            <button class="equal" style="grid-column: span 4;" onclick="calculate()">=</button>
        </div>
    </div>
    <script>
        const display = document.getElementById('display');
        function append(value) {
            display.value += value;
        }
        function clearDisplay() {
            display.value = '';
        }
        function calculate() {
            try {
                display.value = eval(display.value.replace(/÷/g, '/').replace(/×/g, '*'));
            } catch (e) {
                display.value = 'Error';
            }
        }
    </script>
</body>
</html>
