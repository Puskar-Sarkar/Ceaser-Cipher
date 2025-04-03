# Ceaser-Cipher
This is a program in C to implement Ceaser Cipher
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Caesar Cipher</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
        }
        input, button {
            margin: 10px;
            padding: 10px;
        }
    </style>
    <script>
        function caesarCipher(text, shift) {
            let result = "";
            for (let i = 0; i < text.length; i++) {
                let char = text[i];
                if (char.match(/[a-z]/i)) {
                    let code = text.charCodeAt(i);
                    let shiftBase = (char === char.toUpperCase()) ? 65 : 97;
                    result += String.fromCharCode(((code - shiftBase + shift) % 26 + 26) % 26 + shiftBase);
                } else {
                    result += char;
                }
            }
            return result;
        }
        function encrypt() {
            let text = document.getElementById("inputText").value;
            let shift = parseInt(document.getElementById("shift").value);
            document.getElementById("result").innerText = "Encrypted: " + caesarCipher(text, shift);
        }
    </script>
</head>
<body>
    <h2>Caesar Cipher</h2>
    <p>The Caesar cipher is a simple encryption technique where each letter is shifted by a fixed number of places.</p>
    <label for="inputText">Enter text:</label>
    <input type="text" id="inputText" placeholder="Type here...">
    <br>
    <label for="shift">Shift:</label>
    <input type="number" id="shift" value="3">
    <br>
    <button onclick="encrypt()">Encrypt</button>
    <h3 id="result"></h3>
</body>
</html>
