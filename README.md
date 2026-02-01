<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine? ❤️</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background: linear-gradient(135deg, #ffdde1 0%, #ee9ca7 100%);
            font-family: 'Comic Sans MS', cursive, sans-serif;
            overflow: hidden;
            text-align: center;
        }

        h1 {
            color: #d32f2f;
            font-size: 2.5rem;
            z-index: 100;
            pointer-events: none;
        }

        .main-buttons {
            display: flex;
            gap: 20px;
            z-index: 100;
        }

        button {
            padding: 15px 35px;
            font-size: 1.5rem;
            font-weight: bold;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            transition: transform 0.2s;
        }

        #yesBtn {
            background-color: #ff4081;
            color: white;
        }

        #yesBtn:hover {
            transform: scale(1.2);
        }

        .no-clone {
            background-color: #757575;
            color: white;
            position: fixed;
            z-index: 50;
            pointer-events: auto;
        }

        #success {
            display: none;
            z-index: 200;
            animation: popIn 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .meme-gif {
            width: 300px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        @keyframes popIn {
            0% { transform: scale(0); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body>

    <div id="quiz">
        <h1>Will you be my Valentine? ❤️</h1>
        <div class="main-buttons">
            <button id="yesBtn" onclick="celebrate()">YES</button>
            <button id="noBtn" onmouseover="multiplyNo()">NO</button>
        </div>
    </div>

    <div id="success">
        <h1>YAYYY! I LOVE YOU! 🥰✨</h1>
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpqcWp6emJqZzZqZzZqZzZqZzZqZzZqZzZqZzZqZzZqZzZqJmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1n/ICOgUNoMPvGDINDqCc/giphy.gif" class="meme-gif">
    </div>

    <script>
        function multiplyNo() {
            // Create multiple "No" buttons all over the screen
            for(let i = 0; i < 5; i++) {
                const clone = document.createElement('button');
                clone.innerText = "NO";
                clone.className = 'no-clone';
                
                // Random position
                const x = Math.random() * (window.innerWidth - 100);
                const y = Math.random() * (window.innerHeight - 50);
                
                clone.style.left = x + 'px';
                clone.style.top = y + 'px';
                
                // Make the clone also trigger more clones
                clone.onmouseover = multiplyNo;
                
                document.body.appendChild(clone);
            }

            // Move the original "No" button too
            const noBtn = document.getElementById('noBtn');
            noBtn.style.position = 'fixed';
            noBtn.style.left = Math.random() * (window.innerWidth - 100) + 'px';
            noBtn.style.top = Math.random() * (window.innerHeight - 50) + 'px';
        }

        function celebrate() {
            document.getElementById('quiz').style.display = 'none';
            // Remove all the fake No buttons
            const clones = document.querySelectorAll('.no-clone');
            clones.forEach(c => c.remove());
            
            document.getElementById('success').style.display = 'block';
            document.body.style.background = "#ffc1e3";
        }
    </script>
</body>
</html>
