### Hi there 👋

I am Dharm Patel


![coding](https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExdGVtNmFiczJmc2ExOGlkMGp6OGhhZzB4bG5wM2c5cDE0NXlob3VxeSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/u2pmTWUi0MXjyrMaVj/giphy.gif)


# 💫 About Me:
.🌱 I’m currently learning Cyber security<br>.👯 I’m looking to collaborate on Frontend project<br>.💬 Ask me about : Space & Tech.<br>.⚡ get in touch with me : dharmpatel24123@gmail.com


## 🌐 Socials:
[![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white)](https://linkedin.com/in/Dharm patel) 

# 💻 Tech Stack:
![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white) ![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white) ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white) ![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white) ![Canva](https://img.shields.io/badge/Canva-%2300C4CC.svg?style=for-the-badge&logo=Canva&logoColor=white) ![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white)
# 📊 GitHub Stats:
![](https://github-readme-stats.vercel.app/api?username=Dharm2412&theme=dark&hide_border=true&include_all_commits=false&count_private=false)<br/>
![](https://github-readme-streak-stats.herokuapp.com/?user=Dharm2412&theme=dark&hide_border=true)<br/>
![](https://github-readme-stats.vercel.app/api/top-langs/?username=Dharm2412&theme=dark&hide_border=true&include_all_commits=false&count_private=false&layout=compact)

---
[![](https://visitcount.itsvg.in/api?id=Dharm2412&icon=0&color=0)](https://visitcount.itsvg.in)

<!-- Proudly created with GPRM ( https://gprm.itsvg.in ) -->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>GitHub Snake Game</title>
    <style>
        body, html {
          margin: 0;
          padding: 0;
          display: flex;
          justify-content: center;
          align-items: center;
          height: 100vh;
          background-color: #f0f0f0;
        }
        #gameArea {
          display: grid;
          grid-template-columns: repeat(20, 20px);
          grid-gap: 2px;
        }
        .cell {
          width: 20px;
          height: 20px;
          background-color: #e0e0e0;
        }
        .snake {
          background-color: #64C964;
        }
        .food {
          background-color: #ff4500;
        }
    </style>
</head>
<body>
    <div id="gameArea"></div>
    <script>
        const gameArea = document.getElementById('gameArea');
        const rows = 20, cols = 20;
        let snake = [{ x: 10, y: 10 }];
        let food = { x: Math.floor(Math.random() * cols) + 1, y: Math.floor(Math.random() * rows) + 1 };
        let direction = { x: 0, y: 0 };

        function initGame() {
          document.addEventListener('keydown', changeDirection);
          window.setInterval(moveSnake, 200);
        }

        function draw() {
          gameArea.innerHTML = '';
          snake.forEach(segment => gameArea.appendChild(createCell(segment.x, segment.y, 'snake')));
          gameArea.appendChild(createCell(food.x, food.y, 'food'));
        }

        function createCell(x, y, className) {
          const cell = document.createElement('div');
          cell.style.gridColumnStart = x;
          cell.style.gridRowStart = y;
          cell.classList.add('cell', className);
          return cell;
        }

        function moveSnake() {
          const head = { x: snake[0].x + direction.x, y: snake[0].y + direction.y };
          snake.unshift(head);
          if (head.x === food.x && head.y === food.y) {
            food = { x: Math.floor(Math.random() * cols) + 1, y: Math.floor(Math.random() * rows) + 1 };
          } else {
            snake.pop();
          }
          if (head.x < 1 || head.x > cols || head.y < 1 || head.y > rows || snake.slice(1).some(segment => segment.x === head.x && segment.y === head.y)) {
            snake = [{ x: 10, y: 10 }];
            direction = { x: 0, y: 0 };
          }
          draw();
        }

        function changeDirection(event) {
          if (event.keyCode === 37 && direction.x === 0) direction = { x: -1, y: 0 };
          if (event.keyCode === 38 && direction.y === 0) direction = { x: 0, y: -1 };
          if (event.keyCode === 39 && direction.x === 0) direction = { x: 1, y: 0 };
          if (event.keyCode === 40 && direction.y === 0) direction = { x: 0, y: 1 };
        }

        initGame();
    </script>
</body>
</html>

