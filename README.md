<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        body { font-family: Arial, sans-serif; }
        .calculator { width: 200px; margin: 100px auto; }
        .display { width: 100%; height: 40px; text-align: right; font-size: 24px; }
        .button { width: 46%; height: 40px; margin: 2%; font-size: 20px; }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" class="display" id="display" disabled />
        <div>
            <button class="button" onclick="clearDisplay()">C</button>
            <button class="button" onclick="appendToDisplay('7')">7</button>
            <button class="button" onclick="appendToDisplay('8')">8</button>
            <button class="button" onclick="appendToDisplay('9')">9</button>
            <button class="button" onclick="appendToDisplay('/')">/</button>
        </div>
        <div>
            <button class="button" onclick="appendToDisplay('4')">4</button>
            <button class="button" onclick="appendToDisplay('5')">5</button>
            <button class="button" onclick="appendToDisplay('6')">6</button>
            <button class="button" onclick="appendToDisplay('*')">*</button>
        </div>
        <div>
            <button class="button" onclick="appendToDisplay('1')">1</button>
            <button class="button" onclick="appendToDisplay('2')">2</button>
            <button class="button" onclick="appendToDisplay('3')">3</button>
            <button class="button" onclick="appendToDisplay('-')">-</button>
        </div>
        <div>
            <button class="button" onclick="appendToDisplay('0')">0</button>
            <button class="button" onclick="calculateResult()">=</button>
            <button class="button" onclick="appendToDisplay('+')">+</button>
        </div>
    </div>
    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }
        function clearDisplay() {
            document.getElementById('display').value = '';
        }
        function calculateResult() {
            const display = document.getElementById('display');
            try {
                display.value = eval(display.value);
            } catch (error) {
                display.value = 'Error';
            }
        }
    </script>
</body>
</html>
