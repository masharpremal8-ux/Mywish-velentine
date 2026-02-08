# Mywish-velentine
A Valentine’s Day wish page for Dolly
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Happy Valentine’s Day, Dolly</title>
  <style>
    :root{
      --bg1:#ffdde1;
      --bg2:#ee9ca7;
      --card:#ffffffcc;
      --text:#222;
      --accent:#ff2d6d;
      --accent2:#ff6f91;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      min-height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      color:var(--text);
      background: radial-gradient(circle at top, var(--bg1), var(--bg2));
      overflow:hidden;
      padding:24px;
    }

    /* Floating hearts background */
    .hearts{
      position:fixed;
      inset:0;
      pointer-events:none;
      opacity:.35;
    }
    .heart{
      position:absolute;
      width:18px; height:18px;
      background: var(--accent);
      transform: rotate(45deg);
      animation: floatUp linear infinite;
    }
    .heart::before,.heart::after{
      content:"";
      position:absolute;
      width:18px; height:18px;
      background: var(--accent);
      border-radius:50%;
    }
    .heart::before{left:-9px; top:0;}
    .heart::after{left:0; top:-9px;}
    @keyframes floatUp{
      from{ transform: translateY(45vh) rotate(45deg); }
      to{ transform: translateY(-130vh) rotate(45deg); }
    }

    .card{
      width:min(760px, 100%);
      background:var(--card);
      border:1px solid rgba(255,255,255,.6);
      border-radius:26px;
      padding:30px;
      box-shadow: 0 18px 55px rgba(0,0,0,.18);
      backdrop-filter: blur(10px);
      position:relative;
    }

    .badge{
      display:inline-flex;
      align-items:center;
      gap:10px;
      padding:8px 14px;
      border-radius:999px;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      color:white;
      font-weight:800;
      letter-spacing:.2px;
      box-shadow: 0 10px 22px rgba(255,45,109,.28);
    }

    h1{
      margin:16px 0 10px;
      font-size:clamp(28px, 4vw, 42px);
      line-height:1.1;
    }

    .subtitle{
      margin:0 0 18px;
      font-size: 16px;
      opacity:.9;
    }

    .message{
      background:rgba(255,255,255,.78);
      border:1px dashed rgba(255,45,109,.35);
      border-radius:18px;
      padding:18px 18px;
      font-size:18px;
      line-height:1.65;
    }
    .message strong{color:var(--accent)}

    .footer{
      display:flex;
      flex-wrap:wrap;
      gap:12px;
      align-items:center;
      justify-content:space-between;
      margin-top:18px;
    }

    .from{
      font-weight:800;
      color:#111;
    }

    .btn{
      border:0;
      padding:10px 14px;
      border-radius:14px;
      background:#111;
      color:#fff;
      font-weight:800;
      cursor:pointer;
      transition:.2s transform, .2s opacity;
    }
    .btn:hover{transform: translateY(-1px); opacity:.95}

    .tiny{
      font-size:12px;
      opacity:.75;
      margin-top:10px;
    }
  </style>
</head>
<body>

  <!-- Decorative hearts -->
  <div class="hearts" aria-hidden="true">
    <div class="heart" style="left:8%;  animation-duration:10s; animation-delay:-2s;"></div>
    <div class="heart" style="left:20%; animation-duration:12s; animation-delay:-6s; width:14px; height:14px;"></div>
    <div class="heart" style="left:33%; animation-duration:9s;  animation-delay:-4s; opacity:.6;"></div>
    <div class="heart" style="left:47%; animation-duration:13s; animation-delay:-8s; width:22px; height:22px;"></div>
    <div class="heart" style="left:62%; animation-duration:11s; animation-delay:-3s; opacity:.7;"></div>
    <div class="heart" style="left:76%; animation-duration:14s; animation-delay:-7s; width:16px; height:16px;"></div>
    <div class="heart" style="left:90%; animation-duration:10.5s; animation-delay:-5s; width:20px; height:20px;"></div>
  </div>

  <main class="card">
    <div class="badge">❤ Happy Valentine’s Day</div>

    <h1>Hey Dolly,</h1>
    <p class="subtitle">I made this just for you.</p>

    <section class="message" id="wish">
      <p>
        Dolly, I just wanted to say you’re genuinely special to me.
      </p>
      <p>
        I <strong>really like you</strong>—your vibe, your smile, and the way you make things feel lighter.
      </p>
      <p>
        No pressure at all… I simply wanted to be honest and let you know how I feel.
        If you’re okay with it, I’d love to spend more time with you and make more memories together.
      </p>
      <p>
        <strong>Happy Valentine’s Day, Dolly.</strong>
      </p>
    </section>

    <div class="footer">
      <div class="from">— <span id="from">Your Name</span></div>
      <button class="btn" onclick="copyWish()">Copy wish</button>
    </div>

    <div class="tiny">
      Tip: Replace <code>Your Name</code> with your name in the code. You can also edit the message text inside the <code>#wish</code> section.
    </div>
  </main>

  <script>
    function copyWish(){
      const text = document.getElementById("wish").innerText.trim()
        + "\n\n— " + document.getElementById("from").textContent;
      navigator.clipboard.writeText(text).then(() => {
        alert("Copied! Now you can paste it anywhere.");
      });
    }
  </script>
</body>
</html>
