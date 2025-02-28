# BallerGues
Gues Footballar
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BallerGues - Futbolcu Tahmin Oyunu</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f4;
        }
        #game-container {
            margin: 50px auto;
            padding: 20px;
            width: 80%;
            max-width: 500px;
            background: white;
            box-shadow: 0px 0px 10px rgba(0,0,0,0.1);
            border-radius: 10px;
        }
        img {
            width: 200px;
            height: 200px;
            object-fit: cover;
            border-radius: 50%;
        }
        input {
            width: 80%;
            padding: 10px;
            margin: 10px 0;
        }
        button {
            padding: 10px 20px;
            background: blue;
            color: white;
            border: none;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <h1>BallerGues - Futbolcu Tahmin Oyunu</h1>
    <div id="game-container">
        <img id="player-image" src="" alt="Futbolcu">
        <p>Bu futbolcu kim?</p>
        <input type="text" id="guess" placeholder="Futbolcunun adını gir">
        <button onclick="checkGuess()">Tahmin Et</button>
        <p id="result"></p>
    </div>

    <script>
        // Rastgele futbolcuların verisi (Transfermarkt API olmadığı için manuel ekledik)
        const players = [
            { name: "Cristiano Ronaldo", image: "https://upload.wikimedia.org/wikipedia/commons/8/8c/Cristiano_Ronaldo_2018.jpg" },
            { name: "Lionel Messi", image: "https://upload.wikimedia.org/wikipedia/commons/b/b8/Lionel_Messi_20180626.jpg" },
            { name: "Neymar", image: "https://upload.wikimedia.org/wikipedia/commons/4/4b/Neymar_2018.jpg" }
        ];

        let currentPlayer = players[Math.floor(Math.random() * players.length)];
        document.getElementById("player-image").src = currentPlayer.image;

        function checkGuess() {
            let guess = document.getElementById("guess").value.trim();
            let resultText = document.getElementById("result");

            if (guess.toLowerCase() === currentPlayer.name.toLowerCase()) {
                resultText.innerHTML = "? Doğru Tahmin! Bu " + currentPlayer.name;
            } else {
                resultText.innerHTML = "? Yanlış! Tekrar dene.";
            }
        }
    </script>

</body>
</html>
