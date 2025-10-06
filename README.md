<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RopeX - Cordes Premium</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 100%);
            color: #fff;
            overflow-x: hidden;
        }

        .hero {
            height: 100vh;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .animated-bg {
            position: absolute;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 50% 50%, rgba(255, 107, 53, 0.15), transparent 50%);
            animation: pulse 4s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.2); opacity: 0.8; }
        }

        .particle {
            position: absolute;
            width: 3px;
            height: 3px;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            animation: float 6s infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) translateX(0); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) translateX(50px); opacity: 0; }
        }

        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            background: rgba(10, 10, 10, 0.8);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            color: transparent;
        }

        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        .nav-links a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, #ff6b35, #f7931e);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .hero-content {
            text-align: center;
            z-index: 10;
            animation: fadeInUp 1s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h1 {
            font-size: 72px;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #fff, #ff6b35);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            color: transparent;
            animation: glow 2s ease-in-out infinite;
        }

        @keyframes glow {
            0%, 100% { filter: drop-shadow(0 0 20px rgba(255, 107, 53, 0.5)); }
            50% { filter: drop-shadow(0 0 40px rgba(255, 107, 53, 0.8)); }
        }

        .subtitle {
            font-size: 24px;
            margin-bottom: 40px;
            color: #ccc;
        }

        .cta-button {
            padding: 18px 45px;
            font-size: 18px;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            border: none;
            border-radius: 50px;
            color: #fff;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(255, 107, 53, 0.4);
            position: relative;
            overflow: hidden;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .cta-button:hover::before {
            width: 300px;
            height: 300px;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(255, 107, 53, 0.6);
        }

        .products {
            padding: 100px 50px;
            background: rgba(26, 26, 46, 0.5);
        }

        .special-section {
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.1) 0%, rgba(26, 26, 46, 0.8) 100%);
            border-top: 2px solid rgba(255, 107, 53, 0.3);
            border-bottom: 2px solid rgba(255, 107, 53, 0.3);
        }

        .special-card {
            border: 2px solid rgba(255, 107, 53, 0.3);
            background: rgba(255, 107, 53, 0.05);
        }

        .special-card:hover {
            border-color: rgba(255, 107, 53, 0.8);
            box-shadow: 0 20px 60px rgba(255, 107, 53, 0.5);
        }

        .cart-link {
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            padding: 10px 20px;
            border-radius: 25px;
            transition: all 0.3s;
        }

        .cart-link:hover {
            transform: scale(1.1);
            box-shadow: 0 5px 20px rgba(255, 107, 53, 0.5);
        }

        .cart-link::after {
            display: none;
        }

        #cart-count {
            background: rgba(255, 255, 255, 0.3);
            padding: 2px 8px;
            border-radius: 10px;
            font-weight: bold;
        }

        .cart-section {
            padding: 100px 50px;
            background: rgba(10, 10, 10, 0.8);
            min-height: 60vh;
        }

        .cart-section h2 {
            text-align: center;
            font-size: 48px;
            margin-bottom: 60px;
            background: linear-gradient(45deg, #fff, #ff6b35);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            color: transparent;
        }

        .cart-container {
            max-width: 1000px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 40px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .cart-empty {
            text-align: center;
            color: #aaa;
            font-size: 20px;
            padding: 60px;
        }

        .cart-item {
            display: grid;
            grid-template-columns: 80px 1fr auto auto auto;
            gap: 20px;
            align-items: center;
            padding: 20px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 15px;
            margin-bottom: 15px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.3s;
        }

        .cart-item:hover {
            background: rgba(255, 107, 53, 0.05);
            border-color: rgba(255, 107, 53, 0.3);
        }

        .cart-item-icon {
            font-size: 50px;
            text-align: center;
        }

        .cart-item-info h4 {
            font-size: 20px;
            margin-bottom: 5px;
        }

        .cart-item-info p {
            color: #aaa;
            font-size: 14px;
        }

        .cart-item-price {
            font-size: 22px;
            color: #ff6b35;
            font-weight: bold;
        }

        .quantity-controls {
            display: flex;
            align-items: center;
            gap: 10px;
            background: rgba(255, 255, 255, 0.05);
            padding: 5px 10px;
            border-radius: 25px;
        }

        .quantity-btn {
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            border: none;
            color: white;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 18px;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .quantity-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 5px 15px rgba(255, 107, 53, 0.5);
        }

        .quantity-display {
            min-width: 40px;
            text-align: center;
            font-weight: bold;
            font-size: 18px;
        }

        .remove-btn {
            background: rgba(255, 50, 50, 0.2);
            border: 1px solid rgba(255, 50, 50, 0.5);
            color: #ff5050;
            padding: 8px 15px;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: bold;
        }

        .remove-btn:hover {
            background: rgba(255, 50, 50, 0.4);
            transform: scale(1.05);
        }

        .cart-summary {
            margin-top: 40px;
            padding: 30px;
            background: rgba(255, 107, 53, 0.1);
            border-radius: 15px;
            border: 2px solid rgba(255, 107, 53, 0.3);
        }

        .cart-summary-row {
            display: flex;
            justify-content: space-between;
            padding: 15px 0;
            font-size: 18px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .cart-summary-row:last-child {
            border-bottom: none;
        }

        .cart-total {
            font-size: 32px;
            font-weight: bold;
            color: #ff6b35;
        }

        .checkout-btn {
            width: 100%;
            padding: 20px;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            border: none;
            border-radius: 15px;
            color: white;
            font-size: 20px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 20px;
            transition: all 0.3s;
        }

        .checkout-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(255, 107, 53, 0.6);
        }

        .checkout-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .continue-shopping {
            text-align: center;
            margin-top: 20px;
        }

        .continue-shopping a {
            color: #ff6b35;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s;
        }

        .continue-shopping a:hover {
            color: #f7931e;
        }

        .products h2 {
            text-align: center;
            font-size: 48px;
            margin-bottom: 60px;
            background: linear-gradient(45deg, #fff, #ff6b35);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            color: transparent;
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .product-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 30px;
            transition: all 0.4s;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }

        .product-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 107, 53, 0.1), transparent);
            transform: rotate(45deg);
            transition: all 0.6s;
        }

        .product-card:hover::before {
            left: 100%;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(255, 107, 53, 0.3);
            border-color: rgba(255, 107, 53, 0.5);
        }

        .product-image {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, #2a2a3e 0%, #3a3a4e 100%);
            border-radius: 15px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            position: relative;
            overflow: hidden;
        }

        .product-image::after {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: linear-gradient(180deg, transparent, rgba(255, 107, 53, 0.2));
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0%, 100% { transform: translateY(100%); }
            50% { transform: translateY(-100%); }
        }

        .product-title {
            font-size: 24px;
            margin-bottom: 10px;
            color: #fff;
        }

        .product-desc {
            color: #aaa;
            margin-bottom: 20px;
            line-height: 1.6;
        }

        .product-price {
            font-size: 28px;
            color: #ff6b35;
            font-weight: bold;
            margin-bottom: 20px;
        }

        .buy-button {
            width: 100%;
            padding: 15px;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            border: none;
            border-radius: 10px;
            color: #fff;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 16px;
        }

        .buy-button:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px rgba(255, 107, 53, 0.5);
        }

        .features {
            padding: 100px 50px;
            text-align: center;
        }

        .features h2 {
            font-size: 48px;
            margin-bottom: 60px;
            background: linear-gradient(45deg, #fff, #ff6b35);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            color: transparent;
        }

        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .feature-item {
            padding: 40px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s;
        }

        .feature-item:hover {
            background: rgba(255, 107, 53, 0.1);
            border-color: rgba(255, 107, 53, 0.5);
            transform: translateY(-5px);
        }

        .feature-icon {
            font-size: 60px;
            margin-bottom: 20px;
        }

        .feature-title {
            font-size: 24px;
            margin-bottom: 15px;
        }

        footer {
            text-align: center;
            padding: 40px;
            background: rgba(10, 10, 10, 0.8);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
    </style>
</head>
<body>
    <nav>
        <div class="logo">RopeX</div>
        <ul class="nav-links">
            <li><a href="#accueil">Accueil</a></li>
            <li><a href="#produits">Produits</a></li>
            <li><a href="#zachary">Spécial Zachary</a></li>
            <li><a href="#features">Avantages</a></li>
            <li><a href="#contact">Contact</a></li>
            <li><a href="#panier" class="cart-link">🛒 Panier (<span id="cart-count">0</span>)</a></li>
        </ul>
    </nav>

    <section class="hero" id="accueil">
        <div class="animated-bg"></div>
        <div class="hero-content">
            <h1>Cordes Premium</h1>
            <p class="subtitle">L'excellence dans chaque fibre</p>
            <button class="cta-button">Découvrir la collection</button>
        </div>
    </section>

    <section class="products" id="produits">
        <h2>Nos Produits Exclusifs</h2>
        <div class="product-grid">
            <div class="product-card">
                <div class="product-image">🧵</div>
                <h3 class="product-title">Corde Pro Series</h3>
                <p class="product-desc">Résistance maximale pour usage professionnel. Fibres haute performance.</p>
                <div class="product-price">89.99 €</div>
                <button class="buy-button" onclick="addToCart('Corde Pro Series', 89.99, '🧵')">Ajouter au panier</button>
            </div>
            <div class="product-card">
                <div class="product-image">⚡</div>
                <h3 class="product-title">Corde Extreme</h3>
                <p class="product-desc">Pour les conditions extrêmes. Résiste aux UV et à l'humidité.</p>
                <div class="product-price">129.99 €</div>
                <button class="buy-button" onclick="addToCart('Corde Extreme', 129.99, '⚡')">Ajouter au panier</button>
            </div>
            <div class="product-card">
                <div class="product-image">🎯</div>
                <h3 class="product-title">Corde Precision</h3>
                <p class="product-desc">Légère et maniable. Idéale pour les travaux de précision.</p>
                <div class="product-price">69.99 €</div>
                <button class="buy-button" onclick="addToCart('Corde Precision', 69.99, '🎯')">Ajouter au panier</button>
            </div>
        </div>
    </section>

    <section class="products special-section" id="zachary">
        <h2>Collection Spéciale Zachary</h2>
        <p style="text-align: center; color: #aaa; margin-bottom: 60px; font-size: 18px;">Des cordes conçues pour des besoins spécifiques et performances optimales</p>
        <div class="product-grid">
            <div class="product-card special-card">
                <div class="product-image">💪</div>
                <h3 class="product-title">Corde Soutien Gros</h3>
                <p class="product-desc">Diamètre renforcé 25mm. Capacité de charge exceptionnelle jusqu'à 2000kg. Idéale pour levage lourd et structures massives.</p>
                <div class="product-price">199.99 €</div>
                <button class="buy-button" onclick="addToCart('Corde Soutien Gros', 199.99, '💪')">Ajouter au panier</button>
            </div>
            <div class="product-card special-card">
                <div class="product-image">🔥</div>
                <h3 class="product-title">Corde Masse Musculaire</h3>
                <p class="product-desc">Conception ergonomique pour entraînement intensif. Grip antidérapant et résistance progressive. Parfaite pour CrossFit.</p>
                <div class="product-price">149.99 €</div>
                <button class="buy-button" onclick="addToCart('Corde Masse Musculaire', 149.99, '🔥')">Ajouter au panier</button>
            </div>
            <div class="product-card special-card">
                <div class="product-image">🎯</div>
                <h3 class="product-title">Corde Fin de Partie</h3>
                <p class="product-desc">Ultra-légère et ultra-résistante. Technologie carbon fiber. Pour les finitions précises et travaux délicats.</p>
                <div class="product-price">179.99 €</div>
                <button class="buy-button" onclick="addToCart('Corde Fin de Partie', 179.99, '🎯')">Ajouter au panier</button>
            </div>
        </div>
    </section>

    <section class="cart-section" id="panier">
        <h2>Mon Panier</h2>
        <div class="cart-container">
            <div id="cart-items">
                <div class="cart-empty">
                    <p>🛒 Votre panier est vide</p>
                    <p style="font-size: 16px; margin-top: 10px;">Ajoutez des produits pour commencer vos achats !</p>
                </div>
            </div>
            <div id="cart-summary" style="display: none;">
                <div class="cart-summary">
                    <div class="cart-summary-row">
                        <span>Sous-total:</span>
                        <span id="subtotal">0.00 €</span>
                    </div>
                    <div class="cart-summary-row">
                        <span>Livraison:</span>
                        <span id="shipping">Gratuite</span>
                    </div>
                    <div class="cart-summary-row">
                        <span>Total:</span>
                        <span class="cart-total" id="total">0.00 €</span>
                    </div>
                    <button class="checkout-btn" id="checkout-btn">Procéder au paiement</button>
                </div>
                <div class="continue-shopping">
                    <a href="#produits">← Continuer mes achats</a>
                </div>
            </div>
        </div>
    </section>

    <section class="features" id="features">
        <h2>Pourquoi Choisir RopeX ?</h2>
        <div class="feature-grid">
            <div class="feature-item">
                <div class="feature-icon">🏆</div>
                <h3 class="feature-title">Qualité Premium</h3>
                <p>Matériaux certifiés et testés en conditions réelles</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">🚚</div>
                <h3 class="feature-title">Livraison Rapide</h3>
                <p>Expédition sous 24h partout au Canada</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">💎</div>
                <h3 class="feature-title">Garantie 10 Ans</h3>
                <p>Nous garantissons la durabilité de nos produits</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">🌱</div>
                <h3 class="feature-title">Éco-responsable</h3>
                <p>Fabrication respectueuse de l'environnement</p>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2025 RopeX - Tous droits réservés</p>
    </footer>

    <script>
        // Panier en mémoire
        let cart = [];

        // Fonction pour ajouter au panier
        function addToCart(name, price, icon) {
            const existingItem = cart.find(item => item.name === name);
            
            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({
                    name: name,
                    price: price,
                    icon: icon,
                    quantity: 1
                });
            }
            
            updateCart();
            
            // Animation de confirmation
            const btn = event.target;
            const originalText = btn.textContent;
            btn.textContent = '✓ Ajouté !';
            btn.style.background = 'linear-gradient(45deg, #4CAF50, #45a049)';
            setTimeout(() => {
                btn.textContent = originalText;
                btn.style.background = 'linear-gradient(45deg, #ff6b35, #f7931e)';
            }, 1000);
        }

        // Fonction pour mettre à jour le panier
        function updateCart() {
            const cartCount = document.getElementById('cart-count');
            const cartItems = document.getElementById('cart-items');
            const cartSummary = document.getElementById('cart-summary');
            
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = totalItems;
            
            if (cart.length === 0) {
                cartItems.innerHTML = `
                    <div class="cart-empty">
                        <p>🛒 Votre panier est vide</p>
                        <p style="font-size: 16px; margin-top: 10px;">Ajoutez des produits pour commencer vos achats !</p>
                    </div>
                `;
                cartSummary.style.display = 'none';
            } else {
                let itemsHTML = '';
                let subtotal = 0;
                
                cart.forEach((item, index) => {
                    const itemTotal = item.price * item.quantity;
                    subtotal += itemTotal;
                    
                    itemsHTML += `
                        <div class="cart-item">
                            <div class="cart-item-icon">${item.icon}</div>
                            <div class="cart-item-info">
                                <h4>${item.name}</h4>
                                <p>${item.price.toFixed(2)} € / unité</p>
                            </div>
                            <div class="cart-item-price">${itemTotal.toFixed(2)} €</div>
                            <div class="quantity-controls">
                                <button class="quantity-btn" onclick="decreaseQuantity(${index})">-</button>
                                <span class="quantity-display">${item.quantity}</span>
                                <button class="quantity-btn" onclick="increaseQuantity(${index})">+</button>
                            </div>
                            <button class="remove-btn" onclick="removeFromCart(${index})">✕</button>
                        </div>
                    `;
                });
                
                cartItems.innerHTML = itemsHTML;
                cartSummary.style.display = 'block';
                
                document.getElementById('subtotal').textContent = subtotal.toFixed(2) + ' €';
                document.getElementById('total').textContent = subtotal.toFixed(2) + ' €';
            }
        }

        // Fonction pour augmenter la quantité
        function increaseQuantity(index) {
            cart[index].quantity++;
            updateCart();
        }

        // Fonction pour diminuer la quantité
        function decreaseQuantity(index) {
            if (cart[index].quantity > 1) {
                cart[index].quantity--;
                updateCart();
            }
        }

        // Fonction pour retirer du panier
        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCart();
        }

        // Fonction de paiement
        document.addEventListener('DOMContentLoaded', function() {
            const checkoutBtn = document.getElementById('checkout-btn');
            if (checkoutBtn) {
                checkoutBtn.addEventListener('click', function() {
                    if (cart.length > 0) {
                        alert('🎉 Merci pour votre commande ! Redirection vers le paiement...');
                        // Ici vous pouvez ajouter la logique de paiement réelle
                    }
                });
            }
        });

        // Créer des particules animées
        const hero = document.querySelector('.hero');
        for (let i = 0; i < 50; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 6 + 's';
            particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
            hero.appendChild(particle);
        }

        // Animation smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        // Animation au scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.product-card, .feature-item').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.6s ease-out';
            observer.observe(el);
        });

        // Effet de parallaxe au scroll
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallax = document.querySelector('.animated-bg');
            if (parallax) {
                parallax.style.transform = `translateY(${scrolled * 0.5}px)`;
            }
        });
    </script>
</body>
</html>
