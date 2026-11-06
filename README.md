<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Diwali | Abhishek Verma</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --gold: #ffd36c;
  --orange: #ff9e24;
  --cream: #fff0c4;
}

body {
  background: #050d20;
  color: white;
  font-family: Georgia, serif;
  overflow-x: hidden;
  min-height: 100vh;
}

body::before {
  content: "";
  position: fixed;
  inset: 0;
  z-index: -5;
  background:
    radial-gradient(ellipse at 50% 10%, #25446d, #101d3d 48%, #030713);
}

/* STAR BACKGROUND */

#sky {
  position: fixed;
  inset: 0;
  overflow: hidden;
  pointer-events: none;
  z-index: -2;
}

.star {
  position: absolute;
  background: white;
  border-radius: 50%;
  box-shadow: 0 0 9px white;
  animation: twinkle 2s infinite alternate;
}

@keyframes twinkle {
  from { opacity: .2; transform: scale(.7); }
  to { opacity: 1; transform: scale(1.5); }
}

/* GOLDEN LIGHT RAYS */

.rays {
  position: fixed;
  top: -40%;
  left: 50%;
  width: 100vw;
  height: 100vh;
  transform: translateX(-50%);
  pointer-events: none;
  z-index: -1;
  background: repeating-conic-gradient(
    from 0deg at 50% 0%,
    transparent 0deg 9deg,
    #ffc45b12 10deg 11deg,
    transparent 12deg 20deg
  );
  animation: rayGlow 7s ease-in-out infinite alternate;
}

@keyframes rayGlow {
  from { opacity: .2; }
  to { opacity: .8; }
}

/* GOLDEN RAIN */

.rain {
  position: fixed;
  top: -15px;
  width: 3px;
  height: 12px;
  border-radius: 50%;
  background: #ffdc81;
  box-shadow: 0 0 10px 2px #ffae32;
  animation: rainFall linear infinite;
  pointer-events: none;
  z-index: 0;
}

@keyframes rainFall {
  to {
    transform: translateY(110vh) translateX(40px);
    opacity: .1;
  }
}

/* SHOOTING STARS */

.shooting-star {
  position: fixed;
  top: 10%;
  left: -100px;
  width: 100px;
  height: 2px;
  background: linear-gradient(90deg, transparent, #fff, #ffd36c);
  box-shadow: 0 0 12px #ffd36c;
  transform: rotate(-25deg);
  animation: shooting 4s linear infinite;
  pointer-events: none;
  z-index: 0;
}

.shooting-star.two {
  top: 38%;
  animation-delay: 2.5s;
  animation-duration: 5s;
}

@keyframes shooting {
  0% { left: -120px; opacity: 0; }
  10% { opacity: 1; }
  50% { left: 110%; opacity: 0; }
  100% { left: 110%; opacity: 0; }
}

/* GOLDEN CLOUD */

.cloud {
  position: fixed;
  z-index: 2;
  top: -160px;
  left: 50%;
  transform: translateX(-50%);
  width: 145px;
  height: 72px;
  border-radius: 60px;
  background: linear-gradient(135deg, #fff1bd, #ffbd50, #e58b22);
  box-shadow:
    0 0 25px #ffca64,
    0 0 65px #ff9e24,
    0 0 110px #ff9e2477;
  animation:
    cloudDrop 5s 1s forwards,
    cloudFloat 3s 6s ease-in-out infinite;
}

.cloud::before,
.cloud::after {
  content: "";
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(135deg, #fff2c5, #ffc04f);
}

.cloud::before {
  width: 85px;
  height: 85px;
  top: -38px;
  left: 15px;
}

.cloud::after {
  width: 75px;
  height: 75px;
  top: -28px;
  right: 8px;
}

.cloud-face {
  position: absolute;
  z-index: 2;
  width: 100%;
  top: 23px;
  text-align: center;
  color: #754214;
  font: bold 17px Arial;
}

@keyframes cloudDrop {
  to { top: 16%; }
}

@keyframes cloudFloat {
  0%, 100% { margin-top: 0; }
  50% { margin-top: -15px; }
}

/* MAIN CONTENT */

.container {
  position: relative;
  z-index: 3;
  width: min(760px, 94%);
  margin: auto;
  padding: 35px 0 60px;
  text-align: center;
}

.hero {
  min-height: 90vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.small-title {
  color: var(--gold);
  letter-spacing: 5px;
  font: 12px Arial;
  text-transform: uppercase;
}

h1 {
  font-size: clamp(38px, 9vw, 70px);
  color: var(--cream);
  text-shadow: 0 0 30px #ffae35;
  margin: 20px 0;
}

.name {
  font: 25px Arial;
  letter-spacing: 3px;
  color: #fff;
}

p {
  font: 15px/1.9 Arial, sans-serif;
  color: #e3e9f5;
  margin: 15px auto;
  max-width: 550px;
}

button {
  padding: 15px 27px;
  margin: 18px 5px;
  border: 1px solid #ffe3a0;
  border-radius: 35px;
  background: linear-gradient(120deg, #fff1bd, #ffae37);
  color: #38200b;
  font-weight: bold;
  cursor: pointer;
  font-size: 14px;
  box-shadow: 0 0 25px #ffae3580;
  transition: .3s;
}

button:hover {
  transform: translateY(-4px);
  box-shadow: 0 0 40px #ffc15b;
}

.scene {
  display: none;
  min-height: 550px;
  margin: 30px 0;
  padding: 40px 15px;
  border: 1px solid #ffd36c66;
  border-radius: 25px;
  background: linear-gradient(145deg, #10264bdf, #071329ed);
  box-shadow: 0 0 45px #ffb43b22;
}

.scene.active {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  animation: sceneIn 1s ease;
}

@keyframes sceneIn {
  from {
    opacity: 0;
    transform: translateY(35px) scale(.97);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

h2 {
  color: var(--gold);
  font-size: clamp(25px, 6vw, 38px);
  margin: 15px 0;
}

/* SCENE 1 - DIYA */

.diya {
  position: relative;
  width: 220px;
  height: 220px;
  margin: 25px auto;
  display: flex;
  justify-content: center;
}

.diya-glow {
  position: absolute;
  top: 40px;
  width: 180px;
  height: 150px;
  background: #ff9e24;
  border-radius: 50%;
  filter: blur(55px);
  animation: glow 2s infinite alternate;
}

.flame {
  position: absolute;
  top: 10px;
  width: 45px;
  height: 85px;
  border-radius: 70% 20% 70% 50%;
  transform: rotate(5deg);
  background: radial-gradient(
    ellipse at 50% 70%,
    white,
    #fff4a1 25%,
    #ffb329 55%,
    #ff641c 80%,
    transparent
  );
  filter: drop-shadow(0 0 18px orange);
  animation: flicker .8s infinite alternate;
  z-index: 2;
}

.bowl {
  position: absolute;
  bottom: 28px;
  width: 210px;
  height: 85px;
  border-radius: 15px 15px 100px 100px;
  background: linear-gradient(
    #ffe29a,
    #d77a26 55%,
    #73300f
  );
  border-bottom: 5px solid #ffd36c;
  box-shadow: 0 0 35px #ff9e24;
}

@keyframes flicker {
  to { transform: rotate(-5deg) scale(1.1); }
}

@keyframes glow {
  to { opacity: .8; transform: scale(1.2); }
}

/* SCENE 2 - DOORWAY */

.door {
  position: relative;
  width: 270px;
  height: 350px;
  margin: 30px auto;
  border: 12px solid #c58b42;
  border-bottom: none;
  border-radius: 150px 150px 0 0;
  background: linear-gradient(135deg, #63371e, #1e100c);
  box-shadow: 0 0 45px #ffb64b77;
}

.door-inner {
  position: absolute;
  inset: 17px;
  border: 2px solid #e9bd6c;
  border-bottom: none;
  border-radius: 130px 130px 0 0;
  background: radial-gradient(ellipse at 50% 80%, #ffb43b55, transparent);
}

.door-star {
  position: absolute;
  top: 35%;
  width: 100%;
  font-size: 55px;
  color: gold;
  text-shadow: 0 0 25px orange;
}

.garland {
  position: absolute;
  top: -12px;
  left: 5px;
  width: 100%;
  font-size: 30px;
  color: #ffdc75;
  text-shadow: 0 0 15px orange;
  animation: glow 2s infinite alternate;
}

/* SCENE 3 - SWEETS */

.plate {
  width: 240px;
  height: 115px;
  border-radius: 50%;
  border: 9px solid #ffe1a0;
  background: linear-gradient(120deg, #98491e, #d98b39);
  margin: 30px auto;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
  box-shadow: 0 0 35px #ffb43b66;
}

.sweet {
  width: 53px;
  height: 53px;
  border-radius: 50%;
  background: radial-gradient(circle at 30% 20%, #fff0b8, #edaf45 60%, #a85417);
  box-shadow: inset 0 -5px 10px #874014;
}

.code {
  max-width: 480px;
  padding: 18px;
  margin: 25px auto;
  border-radius: 12px;
  border: 1px solid #72e6b4;
  background: #061c20;
  color: #a6f5d2;
  text-align: left;
  font: 13px/1.8 monospace;
}

/* FIREWORKS */

.spark {
  position: fixed;
  z-index: 10;
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background: #ffe7a1;
  box-shadow: 0 0 12px 4px orange;
  pointer-events: none;
  animation: explode 1.5s forwards;
}

@keyframes explode {
  to {
    opacity: 0;
    transform: translate(var(--x), var(--y)) scale(.1);
  }
}

footer {
  color: #a8bad3;
  font: 11px Arial;
  letter-spacing: 2px;
  padding: 30px 5px;
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: .01ms !important;
    transition-duration: .01ms !important;
  }
}
</style>
</head>

<body>

<div id="sky"></div>
<div class="rays"></div>
<div class="shooting-star"></div>
<div class="shooting-star two"></div>

<!-- GOLDEN CLOUD -->
<div class="cloud">
  <div class="cloud-face">♥</div>
</div>

<div class="container">

<!-- INTRO -->
<section class="hero">

  <div class="small-title">
    A Magical Festival Surprise
  </div>

  <h1>Happy Diwali!</h1>

  <div class="name">Abhishek Verma</div>

  <p>
    Tonight, the sky has a little magic
    waiting just for you.
    Follow the lights and discover your surprise!
  </p>

  <button onclick="showScene('diyaScene')">
    Open Your Magical Surprise
  </button>

</section>

<!-- SCENE 1 -->

<section id="diyaScene" class="scene">

  <h2>A Little Light, A Lot of Happiness</h2>

  <p>
    May this beautiful flame bring light,
    peace, happiness and success into your life.
  </p>

  <div class="diya">

    <div class="diya-glow"></div>
    <div class="flame"></div>
    <div class="bowl"></div>

  </div>

  <button onclick="showScene('doorScene')">
    Discover the Next Surprise
  </button>

</section>

<!-- SCENE 2 -->

<section id="doorScene" class="scene">

  <h2>Welcome to a Beautiful Diwali Night</h2>

  <p>
    A special doorway decorated with
    the warmth and beauty of the festival.
  </p>

  <div class="door">

    <div class="door-inner"></div>
    <div class="door-star">✦</div>
    <div class="garland">✦ ✧ ✦ ✧ ✦</div>

  </div>

  <p>
    May your home always be filled
    with love, laughter and beautiful memories.
  </p>

  <button onclick="showScene('sweetScene')">
    Open Your Sweet Surprise
  </button>

</section>

<!-- SCENE 3 -->

<section id="sweetScene" class="scene">

  <h2>A Sweet Surprise Just for You!</h2>

  <p>
    Every celebration deserves
    a little sweetness.
  </p>

  <div class="plate">
    <div class="sweet"></div>
    <div class="sweet"></div>
    <div class="sweet"></div>
  </div>

  <h1>Happy Diwali!</h1>

  <div class="name">Abhishek Verma</div>

  <p>
    May your life compile without errors,
    your dreams run without limits,
    and every project bring you success.
  </p>

  <div class="code">
    // A special wish for Abhishek

    while (life) {
      happiness++;
      success++;
      keepShining();
    }

    // Happy Diwali!
  </div>

  <h2>Keep Coding. Keep Growing. Keep Shining!</h2>

  <p>
    Wishing you and your family
    a wonderful Diwali filled with
    happiness, peace and prosperity.
  </p>

  <button onclick="showScene('diyaScene')">
    Watch the Magic Again
  </button>

</section>

<footer>
  CREATED WITH LOVE & CODE
  <br><br>
  ESPECIALLY FOR ABHISHEK VERMA
</footer>

</div>

<script>

/* CREATE STARS */

const sky = document.getElementById("sky");

for (let i = 0; i < 100; i++) {
  const star = document.createElement("span");

  star.className = "star";
  star.style.left = Math.random() * 100 + "%";
  star.style.top = Math.random() * 100 + "%";
  star.style.width = (Math.random() * 3 + 1) + "px";
  star.style.height = star.style.width;
  star.style.animationDelay = Math.random() * 3 + "s";

  sky.appendChild(star);
}

/* GOLDEN RAIN */

for (let i = 0; i < 65; i++) {
  const light = document.createElement("div");

  light.className = "rain";
  light.style.left = Math.random() * 100 + "vw";
  light.style.animationDuration = (3 + Math.random() * 6) + "s";
  light.style.animationDelay = (-Math.random() * 8) + "s";
  light.style.opacity = .3 + Math.random() * .7;

  document.body.appendChild(light);
}

/* SCENE TRANSITIONS */

function showScene(id) {

  document.querySelectorAll(".scene").forEach(scene => {
    scene.classList.remove("active");
  });

  const next = document.getElementById(id);

  next.classList.add("active");

  window.scrollTo({
    top: next.offsetTop - 20,
    behavior: "smooth"
  });

  fireworks();
}

/* FIREWORKS */

function fireworks() {

  for (let i = 0; i < 55; i++) {

    const spark = document.createElement("div");

    spark.className = "spark";

    spark.style.left = Math.random() * 100 + "vw";
    spark.style.top = Math.random() * 70 + "vh";

    spark.style.setProperty(
      "--x",
      (Math.random() * 220 - 110) + "px"
    );

    spark.style.setProperty(
      "--y",
      (Math.random() * 220 - 110) + "px"
    );

    document.body.appendChild(spark);

    setTimeout(() => spark.remove(), 1600);
  }
}

</script>

</body>
</html>
