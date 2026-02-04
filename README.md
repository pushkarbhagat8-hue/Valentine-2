<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Will You Be My Valentine 💖</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  height: 100vh;
  overflow: hidden;
  background: linear-gradient(135deg, #ff4d6d, #ff85a2);
  font-family: 'Poppins', sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.container {
  position: relative;
  z-index: 5;
  background: rgba(255,255,255,0.2);
  backdrop-filter: blur(12px);
  padding: 25px;
  border-radius: 25px;
  box-shadow: 0 25px 50px rgba(0,0,0,0.3);
  animation: pop 1.2s ease;
}

@keyframes pop {
  from {transform: scale(0.6); opacity: 0;}
  to {transform: scale(1); opacity: 1;}
}

h1 {
  color: white;
  margin-bottom: 10px;
}

.names {
  color: #fff;
  font-size: 1.1rem;
  margin-bottom: 12px;
}

.photo {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  object-fit: cover;
  border: 4px solid white;
  margin-bottom: 15px;
}

.buttons {
  position: relative;
  height: 80px;
}

button {
  padding: 12px 25px;
  font-size: 1.1rem;
  border-radius: 30px;
  border: none;
  cursor: pointer;
  position: absolute;
  transition: 0.3s;
}

#yes {
  background: #ff003c;
  color: white;
  left: 20%;
}

#no {
  background: white;
  color: #ff003c;
  right: 20%;
}

.fall {
  position: absolute;
  top: -30px;
  font-size: 22px;
  animation: fall linear infinite;
}

@keyframes fall {
  to {
    transform: translateY(110vh) rotate(360deg);
  }
}
</style>
</head>

<body>

<audio autoplay loop>
  <source src="love.mp3" type="audio/mpeg">
</audio>

<div class="container">
  <h1>Will you be my Valentine? 💖</h1>

  <div class="names">
    Pushkar ❤️ Your Princess
  </div>

  <img src="gf.jpg" class="photo">

  <div class="buttons">
    <button id="yes" onclick="yesClick()">Yes 💘</button>
    <button id="no" onmouseover="moveNo()">No 😶</button>
  </div>
</div>

<script>
let yesSize = 1.1;

function moveNo() {
  const noBtn = document.getElementById("no");
  noBtn.style.top = Math.random() * 60 + "px";
  noBtn.style.left = Math.random() * 200 + "px";

  yesSize += 0.2;
  document.getElementById("yes").style.transform = `scale(${yesSize})`;
}

function yesClick() {
  document.body.innerHTML = `
    <h1 style="color:white;font-size:3rem;">
      💖 Forever starts today 💖<br>
      Happy Valentine’s Day 🌹😍
    </h1>
  `;
}

/* Falling hearts & roses */
setInterval(() => {
  const el = document.createElement("div");
  el.className = "fall";
  el.innerHTML = Math.random() > 0.5 ? "💖" : "🌹";
  el.style.left = Math.random() * 100 + "vw";
  el.style.animationDuration = (3 + Math.random() * 3) + "s";
  document.body.appendChild(el);

  setTimeout(() => el.remove(), 6000);
}, 300);
</script>

</body>
</html>
