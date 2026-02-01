<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For You ❤️</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background: linear-gradient(135deg, #ffebee 0%, #fce4ec 100%);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden;
            text-align: center;
        }

        h1 {
            color: #d32f2f;
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .container {
            position: relative;
            width: 100%;
            height: 300px;
        }

        button {
            padding: 15px 35px;
            font-size: 1.2rem;
            font-weight: bold;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            position: absolute;
            transition: all 0.3s ease;
        }

        #yesBtn {
            background-color: #ff4081;
            color: white;
            left: 50%;
            transform: translateX(-120%);
            z-index: 10;
        }

        #noBtn {
            background-color: #757575;
            color: white;
            left: 50%;
            transform: translateX(20%);
        }

        /* Success Screen Styles */
        #success {
            display: none;
            animation: fadeIn 0.8s ease-in;
        }

        .meme-img {
            max-width: 90%;
            height: auto;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            margin-top: 20px;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }
    </style>
</head>
<body>

    <div id="quiz">
        <h1>Will you be my Valentine? ❤️</h1>
        <div class="container">
            <button id="yesBtn" onclick="celebrate()">YES</button>
            <button id="noBtn" onmouseover="moveButton()">NO</button>
        </div>
    </div>

    <div id="success">
        <h1>YAYYY! I KNEW IT! 🥰❤️</h1>
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpqcWp6emJqZzZqZzZqZzZqZzZqZzZqZzZqZzZqZzZqZzZqJmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1n/ICOgUNoMPvGDINDqCc/giphy.gif" alt="Happy Cat" class="meme-img">
    </div>

    <script>
        function moveButton() {
            const btn = document.getElementById('noBtn');
            const x = Math.random() * (window.innerWidth - 150);
            const y = Math.random() * (window.innerHeight - 100);
            
            btn.style.position = 'fixed';
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
            
            // Make "Yes" button grow every time she misses "No"
            const yes = document.getElementById('yesBtn');
            const currentSize = parseFloat(window.getComputedStyle(yes).fontSize);
            yes.style.fontSize = (currentSize + 2) + 'px';
        }

        function celebrate() {
            document.getElementById('quiz').style.display = 'none';
            document.getElementById('success').style.display = 'block';
            document.body.style.backgroundColor = '#f8bbd0';
        }
    </script>
</body>
</html>
