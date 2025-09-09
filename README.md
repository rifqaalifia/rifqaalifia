<!-- Profile Banner -->
<p align="center">
  <img src="rifqa.img.jpg" alt="Rifqa Alifia Nurmadina" width="200" style="border-radius:50%;"/>
</p>

<h1 align="center">Hi 👋, I'm Rifqa Alifia Nurmadina</h1>
<h3 align="center">✨ A passionate learner who loves exploring IT, design, and making new friends ✨</h3>

---

## 🌸 About Me  
- 🌐 Interests: Web Design, App Design, Conflict Mediation, UI/UX, E-Learning, Travelling, Art  
- 🎯 Always curious to learn new things about **IT & Creative Design**  
- 🤝 Open to collaboration & meeting new people  
- 📷 Instagram: [@qa._lifiaan](https://instagram.com/qa._lifiaan)  

---

## ⚡ GitHub Stats  
<p align="center">
  <img src="https://komarev.com/ghpvc/?username=rifqaalifia&label=Profile%20views&color=0e75b6&style=flat" alt="visitor badge"/>
</p>

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=rifqaalifia&show_icons=true&theme=tokyonight" alt="stats"/>
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=rifqaalifia&theme=tokyonight" alt="streak"/>
</p>

<p align="center">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=rifqaalifia&theme=tokyonight"/>
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=rifqaalifia&theme=tokyonight"/>
</p>

<p align="center">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=rifqaalifia&theme=tokyonight"/>
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=rifqaalifia&theme=tokyonight&utcOffset=7"/>
</p>

---

## 🏆 Achievements  
<p align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=rifqaalifia&theme=onestar&no-frame=true&column=6" alt="trophy"/>
</p>

---

## 🚀 Tech Stack  
<p align="center">
  <img src="https://skillicons.dev/icons?i=html,css,js,react,figma,github,vscode,python,java" />
</p>

---

## 📊 Activity Graph  
<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=rifqaalifia&theme=tokyo-night" alt="activity graph"/>
</p>

---

## 🐱 Fun Corner: Cat Game 🎮  
<p align="center">
  <iframe src="https://koda.nu/simple/cat/" width="400" height="500"></iframe>
</p>  

*(If GitHub doesn’t render iframe, click here 👉 [Play Cat Game](https://koda.nu/simple/cat/))*  

---

## ✨ Quote of the Day  
> “Design with empathy, learn with curiosity, and connect with kindness.”  

---

<p align="center">💙 Thank you for visiting my profile 💙</p>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>🐱 Cat Jump Game</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(to top, #1e3c72, #2a5298);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
    }
    .game {
      width: 800px;
      height: 300px;
      background: #f0f8ff;
      border: 5px solid #2a5298;
      border-radius: 15px;
      overflow: hidden;
      position: relative;
    }
    #cat {
      width: 60px;
      height: 60px;
      background: url("https://i.ibb.co/3kZPp74/cat.png") no-repeat center/cover;
      position: absolute;
      bottom: 0;
      left: 50px;
    }
    #obstacle {
      width: 50px;
      height: 50px;
      background: url("https://i.ibb.co/Tmfv58H/mouse.png") no-repeat center/cover;
      position: absolute;
      bottom: 0;
      right: -60px;
      animation: move 2s linear infinite;
    }
    @keyframes move {
      0% { right: -60px; }
      100% { right: 100%; }
    }
    .jump {
      animation: jump 0.6s ease;
    }
    @keyframes jump {
      0% { bottom: 0; }
      50% { bottom: 120px; }
      100% { bottom: 0; }
    }
    .scoreboard {
      position: absolute;
      top: 10px;
      left: 10px;
      font-size: 20px;
      color: #2a5298;
      font-weight: bold;
    }
    .game-over {
      display: none;
      position: absolute;
      top: 40%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-size: 30px;
      color: red;
      font-weight: bold;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      font-size: 16px;
      background: #2a5298;
      color: #fff;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    button:hover {
      background: #1e3c72;
    }
  </style>
</head>
<body>
  <div class="game" id="game">
    <div class="scoreboard">Score: <span id="score">0</span></div>
    <div id="cat"></div>
    <div id="obstacle"></div>
    <div class="game-over" id="game-over">💀 Game Over 💀<br/><button onclick="restart()">Restart</button></div>
  </div>

  <script>
    const cat = document.getElementById("cat");
    const obstacle = document.getElementById("obstacle");
    const scoreElement = document.getElementById("score");
    const gameOverElement = document.getElementById("game-over");
    let score = 0;
    let playing = true;

    document.addEventListener("keydown", function(event) {
      if (event.code === "Space" && !cat.classList.contains("jump") && playing) {
        jump();
      }
    });

    function jump() {
      cat.classList.add("jump");
      setTimeout(() => {
        cat.classList.remove("jump");
      }, 600);
    }

    let checkCollision = setInterval(() => {
      if (!playing) return;

      let catTop = parseInt(window.getComputedStyle(cat).getPropertyValue("bottom"));
      let obstacleLeft = parseInt(window.getComputedStyle(obstacle).getPropertyValue("left"));

      if (obstacleLeft > 30 && obstacleLeft < 100 && catTop <= 40) {
        gameOver();
      } else if (obstacleLeft < 0) {
        score++;
        scoreElement.textContent = score;
      }
    }, 50);

    function gameOver() {
      playing = false;
      obstacle.style.animationPlayState = "paused";
      gameOverElement.style.display = "block";
    }

    function restart() {
      score = 0;
      scoreElement.textContent = score;
      gameOverElement.style.display = "none";
      obstacle.style.animationPlayState = "running";
      playing = true;
    }
  </script>
</body>
</html>
