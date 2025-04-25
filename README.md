<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Guess The Number - Dark Mode</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #121212;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            color: #FFFFFF;
        }

        h1 {
            color: #BB86FC;
            margin-bottom: 20px;
        }

        #guessnumber {
            padding: 10px;
            font-size: 16px;
            border: 2px solid #373737;
            border-radius: 8px;
            margin-right: 10px;
            background-color: #1E1E1E;
            color: #FFFFFF;
            outline: none;
        }

        #guessnumber:focus {
            border-color: #BB86FC;
        }

        button {
            padding: 10px 20px;
            margin: 15px;
            font-size: 16px;
            background-color: #BB86FC;
            color: #121212;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #985EFF;
        }

        #result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
            color: #FFFFFF;
        }
    </style>
</head>
<body>
    <h1>Guess The Number</h1>
    <input id="guessnumber" type="number" placeholder="Enter 1 - 10">
    <button onclick="check()">Check</button>
    <p id="result">Let's Start The Game!</p>
    <p id = "score">Score:10</p>

    <script>
        var guessnumber = document.getElementById("guessnumber");
        var result = document.getElementById("result");
        var randomnumber = Math.floor(Math.random() * 10) + 1;
        var score = document.getElementById("score")
        var totalscore = 10;

        function check() {
            var enterednumber = parseInt(guessnumber.value);
            if (enterednumber === randomnumber) {
                result.textContent = 'You are Right!';
                alert("YOU WON....");
            } else {
                totalscore = totalscore - 1
                score.textContent = "Score:" +totalscore
                result.textContent = 'You are Wrong!';
            }
        }
    </script>
</body>
</html>
