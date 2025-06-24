## Hi i am zaxxydeven 👋

<p align="center">
  <img src="https://media.tenor.com/2uyENRmiUt0AAAAC/coding.gif" width="600"/>
</p>

## 🌐 Socials:
[![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?logo=YouTube&logoColor=white)](https://youtube.com/@ZaxxyDev) [![email](https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white)](mailto:xdvenom260@gmail.com) 

# 💻 Tech Stack:
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E) ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white) ![GraphQL](https://img.shields.io/badge/-GraphQL-E10098?style=for-the-badge&logo=graphql&logoColor=white) ![Windows Terminal](https://img.shields.io/badge/Windows%20Terminal-%234D4D4D.svg?style=for-the-badge&logo=windows-terminal&logoColor=white)
# 📊 GitHub Stats:
![](https://github-readme-stats.vercel.app/api?username=ZAXXYDEVEN&theme=gotham&hide_border=false&include_all_commits=false&count_private=false)<br/>
![](https://nirzak-streak-stats.vercel.app/?user=ZAXXYDEVEN&theme=gotham&hide_border=false)<br/>
![](https://github-readme-stats.vercel.app/api/top-langs/?username=ZAXXYDEVEN&theme=gotham&hide_border=false&include_all_commits=false&count_private=false&layout=compact)

### ✍️ Random Dev Quote
![](https://quotes-github-readme.vercel.app/api?type=horizontal&theme=merko)

### 🔝 Top Contributed Repo
![](https://github-contributor-stats.vercel.app/api?username=ZAXXYDEVEN&limit=5&theme=merko&combine_all_yearly_contributions=true)

---
[![](https://visitcount.itsvg.in/api?id=ZAXXYDEVEN&icon=0&color=0)](https://visitcount.itsvg.in)

<!-- Proudly created with GPRM ( https://gprm.itsvg.in ) -->

<p align="center">
  <img src="https://cdn.dribbble.com/users/1162077/screenshots/3848914/programmer.gif" width="400"/>
</p>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Snake Game</title>
  <style>
    canvas {
      background: #000;
      display: block;
      margin: auto;
      margin-top: 50px;
    }
  </style>
</head>
<body>
<canvas id="game" width="400" height="400"></canvas>
<script>
const canvas = document.getElementById("game");
const ctx = canvas.getContext("2d");

const box = 20;
let snake = [{ x: 9 * box, y: 10 * box }];
let direction = null;

let food = {
  x: Math.floor(Math.random() * 19 + 1) * box,
  y: Math.floor(Math.random() * 19 + 1) * box
};

function draw() {
  ctx.fillStyle = "black";
  ctx.fillRect(0, 0, 400, 400);

  for (let i = 0; i < snake.length; i++) {
    ctx.fillStyle = i === 0 ? "lime" : "green";
    ctx.fillRect(snake[i].x, snake[i].y, box, box);
  }

  ctx.fillStyle = "red";
  ctx.fillRect(food.x, food.y, box, box);

  let headX = snake[0].x;
  let headY = snake[0].y;

  if (direction === "LEFT") headX -= box;
  if (direction === "RIGHT") headX += box;
  if (direction === "UP") headY -= box;
  if (direction === "DOWN") headY += box;

  if (headX === food.x && headY === food.y) {
    food = {
      x: Math.floor(Math.random() * 19 + 1) * box,
      y: Math.floor(Math.random() * 19 + 1) * box
    };
  } else {
    snake.pop();
  }

  const newHead = { x: headX, y: headY };

  // Game Over
  if (
    headX < 0 || headY < 0 ||
    headX >= 400 || headY >= 400 ||
    snake.some(segment => segment.x === headX && segment.y === headY)
  ) {
    clearInterval(game);
    alert("Game Over!");
  }

  snake.unshift(newHead);
}

document.addEventListener("keydown", e => {
  if (e.key === "ArrowLeft" && direction !== "RIGHT") direction = "LEFT";
  if (e.key === "ArrowUp" && direction !== "DOWN") direction = "UP";
  if (e.key === "ArrowRight" && direction !== "LEFT") direction = "RIGHT";
  if (e.key === "ArrowDown" && direction !== "UP") direction = "DOWN";
});

const game = setInterval(draw, 100);
</script>
</body>
</html>
