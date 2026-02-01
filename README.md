<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Valentine's Day</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: pink;
      margin-top: 100px;
    }
    h1 {
      color: red;
    }
    .btn {
      padding: 15px 30px;
      font-size: 18px;
      margin: 20px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    .yes {
      background-color: #ff4d4d;
      color: white;
    }
    .no {
      background-color: #ccc;
      color: black;
      position: absolute;
    }
    #meme {
      display: none;
      margin-top: 30px;
    }
    #meme img {
      max-width: 300px;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <h1>Will you be my Valentine? ❤️</h1>
  <button class="btn yes" onclick="showMeme()">Yes</button>
  <button class="btn no" id="noBtn">No</button>

  <div id="meme">
    <h2>Yay! 🥰</h2>
    <img src="https://i.imgur.com/0D0MZcC.png" alt="Cute Happy Meme">
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");

    noBtn.addEventListener("mouseover", () => {
      const x = Math.floor(Math.random() * (window.innerWidth - 100));
      const y = Math.floor(Math.random() * (window.innerHeight - 50));
      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    });

    function showMeme() {
      document.getElementById("meme").style.display = "block";
    }
  </script>
</body>
</html>
