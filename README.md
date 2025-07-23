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
      justify-content: flex-start;
      text-align: center;
    }
    h1 {
      font-size: 3rem;
      margin: 1rem 0 0.2em;
      color: #ff3333;
    }
    p.subtitle {
      font-size: 1.2rem;
      margin: 0 0 2rem;
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
      margin: 20px;
      font-size: 1rem;
      color: #ff6666;
      font-weight: bold;
    }
    footer {
      margin: 40px 0 20px;
      font-size: 0.8rem;
      color: #666;
    }
    .products, .google-products {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      padding: 20px;
    }
    .product {
      background-color: #1e1e1e;
      border-radius: 15px;
      padding: 15px;
      width: 280px;
      text-align: left;
      color: white;
      box-shadow: 0 0 10px #000;
    }
    .product img {
      width: 100%;
      border-radius: 10px;
    }
    .product h3 {
      margin: 0.5em 0 0.2em;
      color: #ff4444;
    }
    .product p {
      margin: 0.2em 0;
      font-size: 0.95rem;
    }
    .soldout {
      color: #ff8888;
      font-weight: bold;
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

  <a href="https://wa.me/9613422883" class="button" target="_blank">🛍️ Order Your Custom Toy</a>
  <a href="https://www.facebook.com/yourfacebookpage" class="button" target="_blank">📘 Follow Me on Facebook</a>
  <a href="https://wa.me/9613422883" class="button" target="_blank">💬 Message Me on WhatsApp</a>
  <a href="#" class="button disabled">❓ Who is Neo? (Coming Soon...)</a>

  <div class="countdown">
    🔒 Neo will be revealed after <strong>100 orders!</strong><br>
    🚀 Current orders: <strong>0 / 100</strong>
  </div>

  <h2>📦 Featured Products (Static)</h2>
  <div class="products">
    <div class="product">
      <img src="https://via.placeholder.com/280x180?text=Robot+Neo" alt="Neo Robot Toy" />
      <h3>Neo Mini Robot</h3>
      <p>3D printed robot with moving legs.</p>
      <p>Price: $45</p>
      <p>Status: <span class="soldout">Sold Out</span></p>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/280x180?text=Custom+Toy" alt="Custom Toy" />
      <h3>Custom Toy</h3>
      <p>Your design turned into a real toy!</p>
      <p>Price: $30</p>
      <p>Status: Available</p>
    </div>
  </div>

  <h2>📊 Live Product List (Google Sheet)</h2>
  <div class="google-products" id="google-products">
    <p>Loading products from sheet...</p>
  </div>

  <h2>🔐 Admin Upload System</h2>
  <p class="subtitle">(Coming soon: upload products easily with images and prices)</p>

  <footer>
    &copy; 2025 Jad & Neo | Made with 💡 by Jad
  </footer>

  <!-- Google Sheets integration -->
  <script>
    const sheetID = 'YOUR_SHEET_ID';
    const sheetName = 'Products';
    const url = `https://docs.google.com/spreadsheets/d/${sheetID}/gviz/tq?tqx=out:json&sheet=${sheetName}`;

    fetch(url)
      .then(res => res.text())
      .then(data => {
        const json = JSON.parse(data.substr(47).slice(0, -2));
        const rows = json.table.rows;
        const container = document.getElementById('google-products');
        container.innerHTML = '';
        rows.forEach(row => {
          const name = row.c[0]?.v;
          const description = row.c[1]?.v || '';
          const price = row.c[2]?.v || '';
          const image = row.c[3]?.v || 'https://via.placeholder.com/280x180?text=Toy';
          const sold = row.c[4]?.v === 'yes';

          const div = document.createElement('div');
          div.className = 'product';
          div.innerHTML = `
            <img src="${image}" alt="${name}" />
            <h3>${name}</h3>
            <p>${description}</p>
            <p>Price: $${price}</p>
            <p>Status: ${sold ? '<span class="soldout">Sold Out</span>' : 'Available'}</p>
          `;
          container.appendChild(div);
        });
      });
  </script>
</body>
</html> <!DOCTYPE html>
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
      justify-content: flex-start;
      text-align: center;
    }
    h1 {
      font-size: 3rem;
      margin: 1rem 0 0.2em;
      color: #ff3333;
    }
    p.subtitle {
      font-size: 1.2rem;
      margin: 0 0 2rem;
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
      margin: 20px;
      font-size: 1rem;
      color: #ff6666;
      font-weight: bold;
    }
    footer {
      margin: 40px 0 20px;
      font-size: 0.8rem;
      color: #666;
    }
    .products, .google-products {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      padding: 20px;
    }
    .product {
      background-color: #1e1e1e;
      border-radius: 15px;
      padding: 15px;
      width: 280px;
      text-align: left;
      color: white;
      box-shadow: 0 0 10px #000;
    }
    .product img {
      width: 100%;
      border-radius: 10px;
    }
    .product h3 {
      margin: 0.5em 0 0.2em;
      color: #ff4444;
    }
    .product p {
      margin: 0.2em 0;
      font-size: 0.95rem;
    }
    .soldout {
      color: #ff8888;
      font-weight: bold;
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

  <a href="https://wa.me/9613422883" class="button" target="_blank">🛍️ Order Your Custom Toy</a>
  <a href="https://www.facebook.com/yourfacebookpage" class="button" target="_blank">📘 Follow Me on Facebook</a>
  <a href="https://wa.me/9613422883" class="button" target="_blank">💬 Message Me on WhatsApp</a>
  <a href="#" class="button disabled">❓ Who is Neo? (Coming Soon...)</a>

  <div class="countdown">
    🔒 Neo will be revealed after <strong>100 orders!</strong><br>
    🚀 Current orders: <strong>0 / 100</strong>
  </div>

  <h2>📦 Featured Products (Static)</h2>
  <div class="products">
    <div class="product">
      <img src="https://via.placeholder.com/280x180?text=Robot+Neo" alt="Neo Robot Toy" />
      <h3>Neo Mini Robot</h3>
      <p>3D printed robot with moving legs.</p>
      <p>Price: $45</p>
      <p>Status: <span class="soldout">Sold Out</span></p>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/280x180?text=Custom+Toy" alt="Custom Toy" />
      <h3>Custom Toy</h3>
      <p>Your design turned into a real toy!</p>
      <p>Price: $30</p>
      <p>Status: Available</p>
    </div>
  </div>

  <h2>📊 Live Product List (Google Sheet)</h2>
  <div class="google-products" id="google-products">
    <p>Loading products from sheet...</p>
  </div>

  <h2>🔐 Admin Upload System</h2>
  <p class="subtitle">(Coming soon: upload products easily with images and prices)</p>

  <footer>
    &copy; 2025 Jad & Neo | Made with 💡 by Jad
  </footer>

  <!-- Google Sheets integration -->
  <script>
    const sheetID = 'YOUR_SHEET_ID';
    const sheetName = 'Products';
    const url = `https://docs.google.com/spreadsheets/d/${sheetID}/gviz/tq?tqx=out:json&sheet=${sheetName}`;

    fetch(url)
      .then(res => res.text())
      .then(data => {
        const json = JSON.parse(data.substr(47).slice(0, -2));
        const rows = json.table.rows;
        const container = document.getElementById('google-products');
        container.innerHTML = '';
        rows.forEach(row => {
          const name = row.c[0]?.v;
          const description = row.c[1]?.v || '';
          const price = row.c[2]?.v || '';
          const image = row.c[3]?.v || 'https://via.placeholder.com/280x180?text=Toy';
          const sold = row.c[4]?.v === 'yes';

          const div = document.createElement('div');
          div.className = 'product';
          div.innerHTML = `
            <img src="${image}" alt="${name}" />
            <h3>${name}</h3>
            <p>${description}</p>
            <p>Price: $${price}</p>
            <p>Status: ${sold ? '<span class="soldout">Sold Out</span>' : 'Available'}</p>
          `;
          container.appendChild(div);
        });
      });
  </script>
</body>
</html>

 https://jad-and-neo.3d.printed-gifts
