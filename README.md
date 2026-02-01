<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Be My Valentine ❤️</title>
  <style>
    body {
      font-family: 'Comic Sans MS', cursive, sans-serif;
      text-align: center;
      background: linear-gradient(to right, #ff9a9e, #fecfef);
      margin: 0;
      height: 100vh;
      overflow: hidden;
    }
    h1 {
      color: #d10056;
      margin-top: 100px;
      font-size: 3em;
      text-shadow: 2px 2px #fff0f5;
    }
    .btn {
      padding: 15px 40px;
      font-size: 20px;
      margin: 20px;
      border: none;
      border-radius: 25px;
      cursor: pointer;
      transition: transform 0.2s;
    }
    .btn:hover {
      transform: scale(1.1);
    }
    .yes {
      background-color: #ff3366;
      color: white;
      box-shadow: 0 0 15px #ff6699;
    }
    .no {
      background-color: #fff;
      color: #333;
      position: absolute;
      border: 2px solid #ff3366;
      border-radius: 25px;
    }
    #meme {
      display: none;
      margin-top: 30px;
      animation: fadeIn 2s ease-in-out;
    }
    #meme img {
      max-width: 300px;
      border-radius: 15px;
      box-shadow: 0 0 20px #ff6699;
    }
    #meme h2 {
      color: #d10056;
      font-size: 2em;
    }
    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
    }
    /* Floating hearts */
    .heart {
      position: absolute;
      color: red;
      font-size: 24px;
      animation: floatUp 6s infinite;
    }
    @keyframes floatUp {
