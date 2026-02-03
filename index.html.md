<!DOCTYPE html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Your T-Shirt Brand - Redbubble</title>  
    <style>  
        /* CSS Variables for easy theme switching */  
        :root {  
            --bg-color: #ffffff; /* Light mode background */  
            --text-color: #333333;  
            --primary-color: #007bff; /* Blue accent */  
            --secondary-bg: #f8f9fa;  
            --card-bg: #ffffff;  
            --border-color: #e0e0e0;  
        }  
        [data-theme="dark"] {  
            --bg-color: #121212; /* Dark mode background */  
            --text-color: #ffffff;  
            --primary-color: #1e90ff;  
            --secondary-bg: #1e1e1e;  
            --card-bg: #2a2a2a;  
            --border-color: #444444;  
        }  
  
        /* Global Styles */  
        * { margin: 0; padding: 0; box-sizing: border-box; }  
        body { font-family: 'Arial', sans-serif; background-color: var(--bg-color); color: var(--text-color); line-height: 1.6; transition: background-color 0.3s, color 0.3s; }  
        a { text-decoration: none; color: var(--primary-color); }  
        button { cursor: pointer; transition: background-color 0.3s; }  
  
        /* Header */  
        header { background-color: var(--secondary-bg); padding: 1rem; display: flex; justify-content: space-between; align-items: center; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }  
        .logo { font-size: 1.5rem; font-weight: bold; }  
        nav { display: flex; gap: 1rem; }  
        nav a { padding: 0.5rem 1rem; border-radius: 5px; transition: background-color 0.3s; }  
        nav a:hover { background-color: var(--primary-color); color: white; }  
        #theme-toggle { background: none; border: none; font-size: 1.5rem; padding: 0.5rem; }  
  
        /* Sections */  
        section { padding: 2rem; max-width: 1200px; margin: 0 auto; }  
        #home { text-align: center; padding: 4rem 2rem; }  
        #home h1 { font-size: 2.5rem; margin-bottom: 1rem; }  
        #home p { font-size: 1.2rem; color: var(--text-color); opacity: 0.8; }  
  
        /* Shop Grid */  
        #shop .products { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1.5rem; }  
        .product-card { background-color: var(--card-bg); border: 1px solid var(--border-color); border-radius: 10px; overflow: hidden; box-shadow: 0 4px 8px rgba(0,0,0,0.1); transition: transform 0.3s; }  
        .product-card:hover { transform: translateY(-5px); }  
        .product-card img { width: 100%; height: 200px; object-fit: cover; }  
        .product-info { padding: 1rem; text-align: center; }  
        .product-info h3 { margin-bottom: 0.5rem; }  
        .price { font-weight: bold; color: var(--primary-color); margin-bottom: 1rem; }  
        .buy-btn { background-color: var(--primary-color); color: white; border: none; padding: 0.75rem 1.5rem; border-radius: 5px; width: 100%; }  
        .buy-btn:hover { background-color: #0056b3; }  
  
        /* About and Contact */  
        #about, #contact { background-color: var(--secondary-bg); }  
        #contact form { max-width: 400px; margin: 0 auto; }  
        #contact input, #contact textarea { width: 100%; padding: 0.75rem; margin-bottom: 1rem; border: 1px solid var(--border-color); border-radius: 5px; background-color: var(--card-bg); color: var(--text-color); }  
        #contact button { background-color: var(--primary-color); color: white; border: none; padding: 0.75rem; border-radius: 5px; width: 100%; }  
  
        /* Footer */  
        footer { text-align: center; padding: 1rem; background-color: var(--secondary-bg); border-top: 1px solid var(--border-color); }  
  
        /* Mobile Responsiveness */  
        @media (max-width: 768px) {   
            header { flex-direction: column; gap: 1rem; }  
            nav { flex-wrap: wrap; justify-content: center; }  
            #home h1 { font-size: 2rem; }  
        }  
    </style>  
</head>  
<body>  
    <!-- Header with Logo, Nav, and Theme Toggle -->  
    <header>  
        <div class="logo">  
            <img src="https://via.placeholder.com/150x50?text=Your+Logo" alt="Your Brand Logo" style="height: 50px;">  
        </div>  
        <nav>  
            <a href="#home">Home</a>  
            <a href="#shop">Shop</a>  
            <a href="#about">About</a>  
            <a href="#contact">Contact</a>  
        </nav>  
        <button id="theme-toggle">🌙</button> <!-- Moon icon for dark mode toggle -->  
    </header>  
  
    <!-- Home Section -->  
    <section id="home">  
        <h1>Welcome to Your T-Shirt Brand</h1>  
        <p>Unique designs, powered by Redbubble. Shop now and wear your style!</p>  
    </section>  
  
    <!-- Shop Section with Product Cards -->  
    <section id="shop">  
        <h2 style="text-align: center; margin-bottom: 2rem;">Shop Our T-Shirts</h2>  
        <div class="products" id="products-container">  
            <!-- Products will be dynamically added here via JavaScript -->  
        </div>  
    </section>  
  
    <!-- About Section -->  
    <section id="about">  
        <h2>About Us</h2>  
        <p>We create fun, original t-shirt designs inspired by pop culture, humor, and everyday life. All our products are printed on demand via Redbubble, ensuring high quality and fast shipping. Follow us for new drops!</p>  
    </section>  
  
    <!-- Contact Section -->  
    <section id="contact">  
        <h2>Contact Us</h2>  
        <form id="contact-form">  
            <input type="text" placeholder="Your Name" required>  
            <input type="email" placeholder="Your Email" required>  
            <textarea placeholder="Your Message" rows="5" required></textarea>  
            <button type="submit">Send Message</button>  
        </form>  
    </section>  
  
    <!-- Footer -->  
    <footer>  
        <p>&copy; 2023 Your T-Shirt Brand. All rights reserved. Powered by Redbubble.</p>  
    </footer>  
  
    <script>  
        // Dummy product data - Now 12 products! Easy to edit: Add/remove objects here.  
        const products = [  
            { image: 'https://source.unsplash.com/featured/?t-shirt,funny', title: 'Funny Cat T-Shirt', price: '$19.99', link: 'https://www.redbubble.com/i/t-shirt/Funny-Cat-Design/123456789' },  
            { image: 'https://source.unsplash.com/featured/?t-shirt,space', title: 'Space Explorer T-Shirt', price: '$21.99', link: 'https://www.redbubble.com/i/t-shirt/Space-Explorer/987654321' },  
            { image: 'https://source.unsplash.com/featured/?t-shirt,motivational', title: 'Motivational Quote T-Shirt', price: '$18.99', link: 'https://www.redbubble.com/i/t-shirt/Motivational-Quote/112233445' },  
            { image: 'https://source.unsplash.com/featured/?t-shirt,retro', title: 'Retro Gamer T-Shirt', price: '$22.99', link: 'https://www.redbubble.com/i/t-shirt/Retro-Gamer/556677889' },  
            { image: 'https://source.unsplash.com/featured/?t-shirt,animal', title: 'Wild Animal T-Shirt', price: '$20.99', link: 'https://www.redbubble.com/i/t-shirt/Wild-Animal/998877665' },  
            { image: 'https://source.unsplash.com/featured/?t-shirt,abstract', title: 'Abstract Art T-Shirt', price: '$23.99', link: 'https://www.redbubble.com/i/t-shirt/Abstract-Art/443322110' },  
            { image: 'https://source.unsplash.com/featured/?t-shirt,music', title: 'Rock Band T-Shirt', price: '$19.49', link: 'https://www.redbubble.com/i/t-shirt/Rock-Band/667788990' },  
            { image: 'https://source.unsplash.com/featured/?t-shirt,nature', title: 'Mountain Hiker T-Shirt', price: '$21.49', link: 'https://www.redbubble.com/i/t-shirt/Mountain-Hiker/334455667' },  
            { image: 'https://source.unsplash.com/featured/?t-shirt,humor', title: 'Dad Joke T-Shirt', price: '$17.99', link: 'https://www.redbubble.com/i/t-shirt/Dad-Joke/778899001' },  
            { image: 'https://source.unsplash.com/featured/?t-shirt,sports', title: 'Basketball Fan T-Shirt', price: '$20.49', link: 'https://www.redbubble.com/i/t-shirt/Basketball-Fan/112244668' },  
            { image: 'https://source.unsplash.com/featured/?t-shirt,vintage', title: 'Vintage Car T-Shirt', price: '$24.99', link: 'https://www.redbubble.com/i/t-shirt/Vintage-Car/889900112' },  
            { image: 'https://source.unsplash.com/featured/?t-shirt,tech', title: 'Code Ninja T-Shirt', price: '$22.49', link: 'https://www.redbubble.com/i/t-shirt/Code-Ninja/445566778' }  
        ];  
  
        // Function to render products  
        function renderProducts() {  
            const container = document.getElementById('products-container');  
            products.forEach(product => {  
                const card = document.createElement('div');  
                card.className = 'product-card';  
                card.innerHTML = `  
                    <img src="${product.image}" alt="${product.title}">  
                    <div class="product-info">  
                        <h3>${product.title}</h3>  
                        <p class="price">${product.price}</p>  
                        <button class="buy-btn" onclick="window.open('${product.link}', '_blank')">Buy Now</button>  
                    </div>  
                `;  
                container.appendChild(card);  
            });  
        }  
  
        // Theme toggle functionality  
        const themeToggle = document.getElementById('theme-toggle');  
        themeToggle.addEventListener('click', () => {  
            const currentTheme = document.documentElement.getAttribute('data-theme');  
            const newTheme = currentTheme === 'dark' ? 'light' : 'dark';  
            document.documentElement.setAttribute('data-theme', newTheme);  
            themeToggle.textContent = newTheme === 'dark' ? '☀️' : '🌙'; // Sun for light, moon for dark  
        });  
  
        // Contact form handler (demo - logs to console, no real send)  
        document.getElementById('contact-form').addEventListener('submit', (e) => {  
            e.preventDefault();  
            alert('Thanks for your message! (This is a demo – no email sent.)');  
            console.log('Form data:', new FormData(e.target));  
            e.target.reset();  
        });  
  
        // Initialize products on page load  
        renderProducts();  
    </script>  
</body>  
</html>  
