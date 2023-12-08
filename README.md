<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>E-commerce Platform</title>
  <style>
    /* Inline CSS */
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: #333;
      color: #fff;
      padding: 10px;
      text-align: center;
    }
    .product {
      border: 1px solid #ccc;
      padding: 20px;
      margin: 10px;
      width: 200px;
      float: left;
      text-align: center;
    }
    .cart {
      border: 1px solid #ccc;
      padding: 20px;
      margin: 10px;
      width: 200px;
      float: right;
    }
  </style>
</head>
<body>

  <header>
    <h1>E-commerce Platform</h1>
  </header>

  <div class="product" id="product1">
    <h2>Product 1</h2>
    <p>Price: $20</p>
    <button onclick="addToCart('Product 1', 20)">Add to Cart</button>
  </div>

  <div class="product" id="product2">
    <h2>Product 2</h2>
    <p>Price: $30</p>
    <button onclick="addToCart('Product 2', 30)">Add to Cart</button>
  </div>

  <div class="cart" id="cart">
    <h2>Cart</h2>
    <ul id="cart-items">
    </ul>
    <p>Total: $<span id="cart-total">0</span></p>
  </div>

  <script>
    // JavaScript
    let cartItems = [];
    let total = 0;

    function addToCart(productName, price) {
      cartItems.push({ name: productName, price: price });
      total += price;

      let cartItemsList = document.getElementById("cart-items");
      let cartTotal = document.getElementById("cart-total");

      cartItemsList.innerHTML = "";
      cartItems.forEach(item => {
        let li = document.createElement("li");
        li.textContent = `${item.name} - $${item.price}`;
        cartItemsList.appendChild(li);
      });

      cartTotal.textContent = total;
    }
  </script>

</body>
</html>
