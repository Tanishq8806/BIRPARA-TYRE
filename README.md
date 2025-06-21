# BIRPARA-TYRE
DEALS IN ALL COMPANY TYRESshowroom-website/
│
├── index.html         
├── stock.html        
├── billing.html       
├── style.css         
└── script.js          


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Tyre Stock</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h2>Available Tyres</h2>
  <div class="tyre-list">
    <div class="tyre-card">
      <h3>Michelin Pilot Sport</h3>
      <p>Size: 205/55R16</p>
      <p>Price: ₹6,500</p>
      <p>In Stock: 15</p>
    </div>
    <div class="tyre-card">
      <h3>MRF ZLX</h3>
      <p>Size: 185/65R15</p>
      <p>Price: ₹4,200</p>
      <p>In Stock: 30</p>
    </div>
  </div>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Billing</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h2>Billing System</h2>
  <form onsubmit="generateBill(); return false;">
    <label for="tyre">Select Tyre:</label>
    <select id="tyre">
      <option value="Michelin Pilot Sport">Michelin Pilot Sport - ₹6,500</option>
      <option value="MRF ZLX">MRF ZLX - ₹4,200</option>
    </select>
    <br><br>
    <label for="qty">Quantity:</label>
    <input type="number" id="qty" value="1" min="1">
    <br><br>
    <button type="submit">Generate Bill</button>
  </form>

  <div id="bill-output"></div>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  margin: 20px;
}
nav a {
  margin: 10px;
  text-decoration: none;
  color: blue;
}
.tyre-card {
  border: 1px solid #ccc;
  padding: 15px;
  margin-bottom: 10px;
}
function generateBill() {
  const tyre = document.getElementById('tyre').value;
  const qty = parseInt(document.getElementById('qty').value);

  let price = tyre.includes('Michelin') ? 6500 : 4200;
  let total = price * qty;

  document.getElementById('bill-output').innerHTML = `
    <h3>Bill Summary</h3>
    <p>Tyre: ${tyre}</p>
    <p>Quantity: ${qty}</p>
    <p>Total Amount: ₹${total}</p>
  `;
}
