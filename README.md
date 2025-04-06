<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Password Strength Checker</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f7f7f7;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            padding: 40px;
            width: 100%;
            max-width: 400px;
            text-align: center;
        }

        h1 {
            color: #333;
        }

        input {
            width: 100%;
            padding: 10px;
            margin: 20px 0;
            border: 2px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
        }

        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }

        button:hover {
            background-color: #45a049;
        }

        #strength {
            font-size: 18px;
            font-weight: bold;
            margin-top: 10px;
        }

        .weak {
            color: red;
        }

        .average {
            color: orange;
        }

        .strong {
            color: green;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Password Strength Checker</h1>
        <p>Şifrenizin güvenliğini kontrol edin:</p>
        <input type="password" id="password" placeholder="Şifrenizi girin" oninput="checkPasswordStrength()">
        <button onclick="checkPasswordStrength()">Şifreyi Kontrol Et</button>
        <p id="strength"></p>
    </div>

    <script>
        function checkPasswordStrength() {
            var password = document.getElementById('password').value;
            var strength = document.getElementById('strength');
            
            if (password.length < 6) {
                strength.innerText = "Zayıf";
                strength.className = "weak";
            } else if (password.length >= 6 && password.length < 12) {
                strength.innerText = "Ortalama";
                strength.className = "average";
            } else {
                strength.innerText = "Güçlü";
                strength.className = "strong";
            }
        }
    </script>
</body>
</html>
