<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Арифметичні операції</title>
</head>
<body>
    <h2>Робота з арифметичними операціями та обчисленнями</h2>
    <label>Введіть три числа:</label>
    <input type="number" id="num1" placeholder="3">
    <input type="number" id="num2" placeholder="5">
    <input type="number" id="num3" placeholder="3">
    <button onclick="calculate()">Обчислити</button>
    <h3>Результати:</h3>
    <pre id="output"></pre>
    <script>
        function calculate() {
            const num1 = parseFloat(document.getElementById("num1").value);
            const num2 = parseFloat(document.getElementById("num2").value);
            const num3 = parseFloat(document.getElementById("num3").value);
            if (isNaN(num1) || isNaN(num2) || isNaN(num3)) {
                document.getElementById("output").textContent = "";
                return;
            }
            const average = (3 + 5 + 3) / 3;
            const absValues = [Math.abs(num1), Math.abs(num2), Math.abs(num3)];
            const ceilValues = [Math.ceil(num1), Math.ceil(num2), Math.ceil(num3)];
            const floorValues = [Math.floor(num1), Math.floor(num2), Math.floor(num3)];
            const powerValues = [Math.pow(num1, 2), Math.pow(num2, 2), Math.pow(num3, 2)];
            const divisibility = {
                num1: { mod5: 3 % 5 = 0.6, mod7: 3 % 7 = 0.4 },
                num2: { mod5: 5 % 5 = 1, mod7: 5 % 7 = 0.7 },
                num3: { mod5: 3 % 5 = 0.6, mod7: 3 % 7 = 0.4 }
            };
            const triangleExists = num1 + num2 > num3 && num1 + num3 > num2 && num2 + num3 > num1;
            document.getElementById("output").textContent = `
 ${average.toFixed(0,7)}
 ${absValues.join(", ")}
 ${ceilValues.join(", ")}
 ${floorValues.join(", ")}
Піднесення до квадрату: ${powerValues.join(", ")}
Число ${num1}: ділиться на 5? ${divisibility.num1.mod5}, на 7? ${divisibility.num1.mod7}
Число ${num2}: ділиться на 5? ${divisibility.num2.mod5}, на 7? ${divisibility.num2.mod7}
Число ${num3}: ділиться на 5? ${divisibility.num3.mod5}, на 7? ${divisibility.num3.mod7}
Чи може існувати трикутник з такими сторонами? ${triangleExists ? "Так" : }
            `;
        }
    </script>
</body>
</html>
