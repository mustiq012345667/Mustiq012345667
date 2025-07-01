<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Mustiq Hacker Portalı</title>
  <style>
    body {
      margin: 0;
      background: #000;
      color: #0f0;
      font-family: monospace;
      overflow: hidden;
    }
    #matrix {
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      z-index: 0;
    }
    .content {
      position: relative;
      z-index: 1;
      text-align: center;
      padding-top: 20vh;
    }
    a {
      color: #0f0;
      text-decoration: none;
      border-bottom: 1px dashed #0f0;
    }
    a:hover {
      opacity: 0.7;
    }
  </style>
</head>
<body>

<canvas id="matrix"></canvas>

<div class="content">
  <h1>🖥️ Selamın Aleyküm Canlar</h1>
  <p>Ben <strong>Mustafa K.</strong></p>
  <p>Bu site <strong>Termux</strong> ve <strong>Hacker temasında</strong> hazırlandı.</p>
  <p>Instagram: <a href="https://instagram.com/mustiq012345667" target="_blank">@mustiq012345667</a></p>
</div>

<script>
  const canvas = document.getElementById('matrix');
  const ctx = canvas.getContext('2d');
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;

  const letters = 'アァカサタナハマヤャラワガザダバパイィキシチニヒミリヰギジヂビピウゥクスツヌフムユュルグズヅブプエェケセテネヘメレヱゲゼデベペオォコソトノホモヨョロヲゴゾドボポヴッン0123456789';
  const fontSize = 16;
  const columns = canvas.width / fontSize;
  const drops = Array(Math.floor(columns)).fill(1);

  function draw() {
    ctx.fillStyle = 'rgba(0, 0, 0, 0.05)';
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = '#0F0';
    ctx.font = fontSize + 'px monospace';
    for (let i = 0; i < drops.length; i++) {
      const text = letters[Math.floor(Math.random() * letters.length)];
      const x = i * fontSize;
      const y = drops[i] * fontSize;
      ctx.fillText(text, x, y);
      if (y > canvas.height && Math.random() > 0.975) {
        drops[i] = 0;
      }
      drops[i]++;
    }
  }
  setInterval(draw, 33);
</script>

</body>
</html>
