<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Jad & Neo</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #121212;
      color: #eee;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
      justify-content: center;
      text-align: center;
    }
    h1 {
      font-size: 3rem;
      margin-bottom: 0.2em;
      color: #ff3333;
    }
    p.subtitle {
      font-size: 1.2rem;
      margin-top: 0;
      margin-bottom: 2rem;
      color: #ccc;
    }
    .button {
      display: block;
      width: 250px;
      margin: 12px auto;
      padding: 15px 0;
      background-color: #ff3333;
      color: white;
      text-decoration: none;
      border-radius: 30px;
      font-weight: 600;
      font-size: 1.1rem;
      transition: background-color 0.3s ease;
    }
    .button:hover {
      background-color: #cc2929;
    }
    .button.disabled {
      background-color: #555;
      cursor: not-allowed;
      opacity: 0.6;
    }
    .countdown {
      margin-top: 20px;
      font-size: 1rem;
      color: #ff6666;
      font-weight: bold;
    }
    footer {
      margin-top: 40px;
      font-size: 0.8rem;
      color: #666;
    }
    @media (max-width: 400px) {
      .button {
        width: 90%;
      }
      h1 {
        font-size: 2.2rem;
      }
    }
  </style>
</head>
<body>
  <h1>Jad & Neo</h1>
  <p class="subtitle">Custom 3D Toys for Everyone.<br>🚀 Made by a young inventor.</p>

  <a href="https://wa.me/9613422883" class="button" target="_blank" rel="noopener noreferrer">🛍️ Order Your Custom Toy</a>

  <a href="https://www.facebook.com/yourfacebookpage" class="button" target="_blank" rel="noopener noreferrer">📘 Follow Me on Facebook</a>

  <a href="https://wa.me/9613422883" class="button" target="_blank" rel="noopener noreferrer">💬 Message Me on WhatsApp</a>

  <a href="#" class="button disabled" tabindex="-1" aria-disabled="true">❓ Who is Neo? (Coming Soon...)</a>

  <div class="countdown">
    🔒 Neo will be revealed after <strong>100 orders!</strong><br>
    🚀 Current orders: <strong>0 / 100</strong>
  </div>

  <footer>
    &copy; 2025 Jad & Neo | Made with 💡 by Jad
  </footer>
</body>
</html>

 https://jad-and-neo.github.io/jad-neo-website/
