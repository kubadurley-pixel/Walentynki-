# Walentynki-
Strona walentynkowa 
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <title>Pytanie...</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #fff0f3;
            font-family: 'Arial', sans-serif;
            text-align: center;
        }
        h1 { color: #ff4d6d; font-size: 2.5rem; }
        .buttons { margin-top: 20px; position: relative; height: 50px; width: 300px; }
        button {
            padding: 15px 30px;
            font-size: 1.2rem;
            cursor: pointer;
            border: none;
            border-radius: 10px;
            transition: 0.3s;
        }
        #yesBtn { background-color: #ff4d6d; color: white; }
        #noBtn { background-color: #adb5bd; color: white; position: absolute; right: 0; }
        .heart {
            font-size: 100px;
            color: #ff4d6d;
            display: none;
            animation: beat 0.8s infinite;
        }
        @keyframes beat {
            0% { transform: scale(1); }
            50% { transform: scale(1.2); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body>

    <div id="content">
        <h1>Czy zostaniesz moją Walentynką? ❤️</h1>
        <div class="buttons">
            <button id="yesBtn" onclick="sayYes()">TAK</button>
            <button id="noBtn" onmouseover="moveNo()" onclick="eraseNo()">NIE</button>
        </div>
    </div>

    <div id="heartDisplay" class="heart">❤️</div>

    <script>
        function eraseNo() {
            document.getElementById('noBtn').style.display = 'none';
        }

        function moveNo() {
            // Dodatkowy efekt: "NIE" ucieka przed myszką, zanim zniknie
            const btn = document.getElementById('noBtn');
            btn.style.opacity = (parseFloat(btn.style.opacity) || 1) - 0.3;
            if(parseFloat(btn.style.opacity) <= 0.1) btn.style.display = 'none';
        }

        function sayYes() {
            document.getElementById('content').style.display = 'none';
            document.getElementById('heartDisplay').style.display = 'block';
        }
    </script>
</body>
</html>
