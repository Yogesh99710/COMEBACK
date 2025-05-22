<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Yogesh Comeback Fire Background</title>
<style>
  body, html {
    margin: 0; padding: 0; height: 100%; overflow: hidden;
    background: #000;
    font-family: 'Arial Black', Arial, sans-serif;
    color: white;
  }

  .fire-background {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    pointer-events: none;
    z-index: 0;
    background: radial-gradient(ellipse at center, #ff6600 10%, #330000 80%);
  }

  .text-container {
    position: relative;
    z-index: 1;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  /* Fiery animated gradient heading */
  .fiery-text {
    font-size: 5em;
    text-transform: uppercase;
    letter-spacing: 5px;
    margin: 0 0 20px;
    background: linear-gradient(45deg, #ff3e00, #ff6f00, #ffcb00, #ff3e00);
    background-size: 300% 300%;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: fieryGradient 3s ease infinite;
    text-shadow:
      0 0 10px #ff3e00,
      0 0 20px #ff6f00,
      0 0 30px #ffcb00,
      0 0 40px #ff3e00,
      0 0 60px #ff3e00;
  }

  @keyframes fieryGradient {
    0% {
      background-position: 0% 50%;
      text-shadow:
        0 0 8px #ff3e00,
        0 0 15px #ff6f00,
        0 0 20px #ffcb00;
    }
    50% {
      background-position: 100% 50%;
      text-shadow:
        0 0 15px #ffcb00,
        0 0 25px #ff6f00,
        0 0 35px #ff3e00;
    }
    100% {
      background-position: 0% 50%;
      text-shadow:
        0 0 8px #ff3e00,
        0 0 15px #ff6f00,
        0 0 20px #ffcb00;
    }
  }

  p {
    font-size: 2.8em;
    margin: 0 0 10px;
    color: #ffdd88;
    text-shadow:
      0 0 5px #ffdd88,
      0 0 10px #ffdd88,
      0 0 20px #ffbb33;
  }

  .percentage {
    font-size: 3.5em;
    color: #ffcc00;
    font-weight: 900;
    text-shadow:
      0 0 15px #ffcc00,
      0 0 30px #ffaa00,
      0 0 40px #ffaa00,
      0 0 50px #ffaa00;
    margin-top: 10px;
    animation: glow 1.5s ease-in-out infinite alternate;
  }

  @keyframes glow {
    0%, 100% {
      text-shadow:
      0 0 10px #ffcc00,
      0 0 20px #ffbb00,
      0 0 30px #ffaa00;
    }
    50% {
      text-shadow:
      0 0 20px #ffcc00,
      0 0 40px #ffbb00,
      0 0 60px #ffaa00;
    }
  }

  .fire-particle {
    position: absolute;
    bottom: 0;
    width: 12px;
    height: 25px;
    background: radial-gradient(circle at center, #ff5500, transparent 80%);
    border-radius: 40% 40% 40% 40% / 70% 70% 30% 30%;
    filter: drop-shadow(0 0 6px #ff6600);
    animation: rise 3s linear infinite;
    opacity: 0.8;
  }

  @keyframes rise {
    0% {
      transform: translateY(0) scale(1);
      opacity: 0.9;
    }
    50% {
      opacity: 1;
    }
    100% {
      transform: translateY(-350px) scale(0.3);
      opacity: 0;
    }
  }
</style>
</head>
<body>

<div class="fire-background"></div>

<div class="text-container">
  <h1 class="fiery-text">Yogesh Comeback Karega</h1>
  <p>Yogesh Top Karega 10th Class</p>
  <div class="percentage">95% +</div>
</div>

<script>
  const fireBg = document.querySelector('.fire-background');

  function createParticle() {
    const particle = document.createElement('div');
    particle.classList.add('fire-particle');
    particle.style.left = Math.random() * window.innerWidth + 'px';
    particle.style.animationDelay = (Math.random() * 3) + 's';
    const size = Math.random() * 15 + 8;
    particle.style.width = size + 'px';
    particle.style.height = size * 2 + 'px';

    fireBg.appendChild(particle);

    setTimeout(() => {
      particle.remove();
    }, 3000);
  }

  setInterval(createParticle, 70);
</script>

</body>
</html>
