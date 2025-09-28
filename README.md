<!-- calculator.html -->
<!DOCTYPE html>
<html lang="fa">
<head>
  <meta charset="UTF-8">
  <title>🧮 ماشین حساب</title>
  <style>
    body {
      font-family: sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f3f4f6;
    }
    .calculator {
      background: white;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
    }
    input {
      grid-column: span 4;
      padding: 10px;
      font-size: 20px;
      text-align: right;
      border-radius: 8px;
      border: 1px solid #ccc;
    }
    button {
      padding: 15px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      background: #e5e7eb;
      cursor: pointer;
      transition: 0.2s;
    }
    button:hover {
      background: #d1d5db;
    }
    .equal {
      background: #2563eb;
      color: white;
    }
    .equal:hover {
      background: #1d4ed8;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled>
    <button onclick="clearDisplay()">C</button>
    <button onclick="append('/')">÷</button>
    <button onclick="append('*')">×</button>
    <button onclick="append('-')">-</button>
    <button onclick="append('7')">7</button>
    <button onclick="append('8')">8</button>
    <button onclick="append('9')">9</button>
    <button onclick="append('+')">+</button>
    <button onclick="append('4')">4</button>
    <button onclick="append('5')">5</button>
    <button onclick="append('6')">6</button>
    <button onclick="append('.')">.</button>
    <button onclick="append('1')">1</button>
    <button onclick="append('2')">2</button>
    <button onclick="append('3')">3</button>
    <button class="equal" onclick="calculate()">=</button>
    <button onclick="append('0')" style="grid-column: span 2;">0</button>
  </div>

  <script>
    const display = document.getElementById("display");

    function append(value) {
      display.value += value;
    }

    function clearDisplay() {
      display.value = "";
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = "خطا!";
      }
    }
  </script>
</body>
</html>
