# shopping-cart-page

//html 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Shopping Cart</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header class="navbar">
        <div class="logo">RED<span>STORE</span></div>
        <nav>
            <ul class="nav-links">
                <li><a href="#">Home</a></li>
                <li><a href="#">Shop</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
            <button class="menu-icon" onclick="toggleMenu()">☰</button>
        </nav>
    </header>

    <main class="cart-container">
        <h1>Shopping Cart</h1>
        <table class="cart-table">
            <thead>
                <tr>
                    <th>Product</th>
                    <th>Price</th>
                    <th>Quantity</th>
                    <th>Total</th>
                    <th>Remove</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>
                        <div class="product-info">
                            <img src="product1.jpg" alt="Product 1">
                            <p>Product 1</p>
                        </div>
                    </td>
                    <td>$50.00</td>
                    <td>
                        <input type="number" min="1" value="1">
                    </td>
                    <td>$50.00</td>
                    <td>
                        <button class="remove-btn">Remove</button>
                    </td>
                </tr>
                <tr>
                    <td>
                        <div class="product-info">
                            <img src="product2.jpg" alt="Product 2">
                            <p>Product 2</p>
                        </div>
                    </td>
                    <td>$30.00</td>
                    <td>
                        <input type="number" min="1" value="2">
                    </td>
                    <td>$60.00</td>
                    <td>
                        <button class="remove-btn">Remove</button>
                    </td>
                </tr>
            </tbody>
        </table>

        <div class="cart-summary">
            <h2>Cart Summary</h2>
            <p>Subtotal: $110.00</p>
            <p>Shipping: $10.00</p>
            <p><strong>Total: $120.00</strong></p>
            <button class="checkout-btn">Proceed to Checkout</button>
        </div>
    </main>

    <footer>
        <p>&copy; 2024 ShopCart. All rights reserved.</p>
    </footer>

    <script>
        // Toggle menu for mobile
        function toggleMenu() {
            const navLinks = document.querySelector('.nav-links');
            navLinks.classList.toggle('active');
        }
    </script>
</body>
</html>

//css
/* General Reset */
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    color: #333;
    line-height: 1.6;
}

/* Navbar */
.navbar {
    background-color: #333;
    color: white;
    padding: 10px 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.navbar .logo {
    font-size: 24px;
    font-weight: bold;
}

.navbar .logo span {
    color: #FFD700;
}

.navbar .nav-links {
    list-style: none;
    display: flex;
    gap: 20px;
    margin: 0;
    padding: 0;
}

.navbar .nav-links li a {
    text-decoration: none;
    color: white;
    font-weight: bold;
}

.menu-icon {
    display: none;
    background: none;
    border: none;
    color: white;
    font-size: 24px;
    cursor: pointer;
}

/* Cart Container */
.cart-container {
    max-width: 1200px;
    margin: 30px auto;
    padding: 20px;
    background: white;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

.cart-container h1 {
    text-align: center;
    margin-bottom: 20px;
    font-size: 28px;
    color: #444;
}

/* Cart Table */
.cart-table {
    width: 100%;
    border-collapse: collapse;
    margin-bottom: 20px;
}

.cart-table thead tr {
    background: #333;
    color: white;
}

.cart-table th, .cart-table td {
    padding: 10px;
    text-align: center;
}

.cart-table tbody tr:nth-child(even) {
    background-color: #f9f9f9;
}

.cart-table .product-info {
    display: flex;
    align-items: center;
    gap: 10px;
}

.cart-table .product-info img {
    width: 50px;
    border-radius: 4px;
}

.cart-table input[type="number"] {
    width: 60px;
    padding: 5px;
}

.remove-btn {
    background: #FF4C4C;
    color: white;
    border: none;
    padding: 8px 10px;
    cursor: pointer;
    border-radius: 4px;
    font-size: 14px;
}

.remove-btn:hover {
    background: #FF2C2C;
}

/* Cart Summary */
.cart-summary {
    text-align: right;
}

.cart-summary h2 {
    font-size: 22px;
    margin-bottom: 10px;
}

.cart-summary p {
    margin: 5px 0;
}

.cart-summary .checkout-btn {
    background: #28A745;
    color: white;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    border-radius: 4px;
    cursor: pointer;
}

.cart-summary .checkout-btn:hover {
    background: #218838;
}

/* Footer */
footer {
    text-align: center;
    padding: 20px 0;
    background: #333;
    color: white;
}

/* Responsive Design */
@media (max-width: 768px) {
    .nav-links {
        display: none;
        flex-direction: column;
        background: #333;
        position: absolute;
        top: 50px;
        right: 0;
        padding: 10px;
        width: 200px;
        border-radius: 4px;
    }

    .nav-links.active {
        display: flex;
    }

    .menu-icon {
        display: block;
    }

    .cart-table th, .cart-table td {
        font-size: 14px;
    }

    .cart-summary {
        text-align: center;
    }

    .cart-summary .checkout-btn {
        width: 100%;
    }
}
