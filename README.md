<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Online Store</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background: #333;
            color: #fff;
            padding: 10px;
            text-align: center;
        }
        .container {
            width: 90%;
            margin: 20px auto;
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
        }
        .product {
            background: #fff;
            border: 1px solid #ddd;
            padding: 20px;
            text-align: center;
            width: 250px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        .product img {
            max-width: 100%;
            height: auto;
        }
        .product h3 {
            font-size: 18px;
            margin: 10px 0;
        }
        .product p {
            font-size: 16px;
            color: #666;
        }
        .product button {
            background: #28a745;
            color: #fff;
            padding: 10px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }
        .product button:hover {
            background: #218838;
        }
        #cart {
            margin: 20px auto;
            width: 90%;
            background: #fff;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        #cart h2 {
            margin-bottom: 10px;
        }
        #cart-items {
            list-style-type: none;
            padding: 0;
        }
        #cart-items li {
            padding: 10px;
            border-bottom: 1px solid #ddd;
        }
    </style>
</head>
<body>
    <header>
        <h1>My Simple Store</h1>
    </header>

    <div class="container">
        <div class="product">
            <img src="https://via.placeholder.com/200" alt="Product 1">
            <h3>Product 1</h3>
            <p>$10.00</p>
            <button onclick="addToCart('Product 1', 10.00)">Add to Cart</button>
        </div>
        
        <div class="product">
            <img src="https://via.placeholder.com/200" alt="Product 2">
            <h3>Product 2</h3>
            <p>$15.00</p>
            <button onclick="addToCart('Product 2', 15.00)">Add to Cart</button>
        </div>

        <div class="product">
            <img src="https://via.placeholder.com/200" alt="Product 3">
            <h3>Product 3</h3>
            <p>$20.00</p>
            <button onclick="addToCart('Product 3', 20.00)">Add to Cart</button>
        </div>
    </div>

    <div id="cart">
        <h2>Your Cart</h2>
        <ul id="cart-items"></ul>
        <p><strong>Total: $<span id="total">0.00</span></strong></p>
    </div>

    <script>
        let cart = [];

        function addToCart(productName, price) {
            cart.push({ productName, price });
            displayCart();
        }

        function displayCart() {
            const cartItems = document.getElementById('cart-items');
            const totalElement = document.getElementById('total');
            
            cartItems.innerHTML = '';
            let total = 0;

            cart.forEach(item => {
                const li = document.createElement('li');
                li.textContent = `${item.productName} - $${item.price.toFixed(2)}`;
                cartItems.appendChild(li);
                total += item.price;
            });

            totalElement.textContent = total.toFixed(2);
        }
    </script>
</body>
</html>
