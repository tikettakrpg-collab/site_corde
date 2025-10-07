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

        .agriculture-section {
            background: linear-gradient(135deg, rgba(139, 195, 74, 0.15) 0%, rgba(104, 159, 56, 0.1) 100%);
            border-top: 2px solid rgba(139, 195, 74, 0.4);
            border-bottom: 2px solid rgba(139, 195, 74, 0.4);
            position: relative;
            overflow: hidden;
        }

        .agriculture-section::before {
            content: '🌾';
            position: absolute;
            font-size: 200px;
            opacity: 0.03;
            top: 50%;
            left: 10%;
            transform: translateY(-50%) rotate(-15deg);
        }

        .agriculture-section::after {
            content: '🌾';
            position: absolute;
            font-size: 200px;
            opacity: 0.03;
            top: 50%;
            right: 10%;
            transform: translateY(-50%) rotate(15deg);
        }

        .agriculture-card {
            border: 2px solid rgba(139, 195, 74, 0.3);
            background: rgba(139, 195, 74, 0.05);
        }

        .agriculture-card:hover {
            border-color: rgba(139, 195, 74, 0.8);
            box-shadow: 0 20px 60px rgba(139, 195, 74, 0.4);
        }

        .agriculture-section h2 {
            text-align: center;
            font-size: 48px;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #fff, #8BC34A);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            color: transparent;
        }

        .vip-section {
            padding: 100px 50px;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a0a2e 100%);
            position: relative;
            overflow: hidden;
        }

        .vip-section::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 30% 50%, rgba(255, 215, 0, 0.1), transparent 40%),
                        radial-gradient(circle at 70% 50%, rgba(192, 192, 192, 0.1), transparent 40%);
            animation: vipPulse 8s ease-in-out infinite;
        }

        @keyframes vipPulse {
            0%, 100% { opacity: 0.5; transform: scale(1); }
            50% { opacity: 0.8; transform: scale(1.1); }
        }

        .vip-particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(255, 215, 0, 0.8);
            border-radius: 50%;
            box-shadow: 0 0 10px rgba(255, 215, 0, 0.5);
            animation: vipFloat 8s infinite;
        }

        @keyframes vipFloat {
            0%, 100% { transform: translateY(0) translateX(0) scale(1); opacity: 0; }
            10% { opacity: 1; }
            50% { transform: translateY(-50vh) translateX(100px) scale(1.5); opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) translateX(200px) scale(0.5); opacity: 0; }
        }

        .vip-section h2 {
            text-align: center;
            font-size: 56px;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #FFD700, #FFA500, #FFD700);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            color: transparent;
            text-shadow: 0 0 30px rgba(255, 215, 0, 0.5);
            animation: shimmerGold 3s ease-in-out infinite;
            position: relative;
            z-index: 10;
        }

        @keyframes shimmerGold {
            0%, 100% { filter: drop-shadow(0 0 20px rgba(255, 215, 0, 0.5)); }
            50% { filter: drop-shadow(0 0 40px rgba(255, 215, 0, 1)); }
        }

        .vip-subtitle {
            text-align: center;
            color: #aaa;
            margin-bottom: 60px;
            font-size: 20px;
            position: relative;
            z-index: 10;
        }

        .vip-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            max-width: 1400px;
            margin: 0 auto;
            position: relative;
            z-index: 10;
        }

        .vip-card {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 25px;
            padding: 40px;
            position: relative;
            overflow: hidden;
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            border: 2px solid;
        }

        .vip-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transform: rotate(45deg);
            transition: all 0.8s;
        }

        .vip-card:hover::before {
            left: 100%;
        }

        .vip-card:hover {
            transform: translateY(-15px) scale(1.02);
        }

        .vip-wood {
            border-color: rgba(139, 90, 43, 0.5);
            background: linear-gradient(135deg, rgba(139, 90, 43, 0.1), rgba(101, 67, 33, 0.05));
        }

        .vip-wood:hover {
            border-color: rgba(139, 90, 43, 1);
            box-shadow: 0 25px 70px rgba(139, 90, 43, 0.4);
        }

        .vip-bronze {
            border-color: rgba(205, 127, 50, 0.5);
            background: linear-gradient(135deg, rgba(205, 127, 50, 0.1), rgba(184, 115, 51, 0.05));
        }

        .vip-bronze:hover {
            border-color: rgba(205, 127, 50, 1);
            box-shadow: 0 25px 70px rgba(205, 127, 50, 0.4);
        }

        .vip-silver {
            border-color: rgba(192, 192, 192, 0.5);
            background: linear-gradient(135deg, rgba(192, 192, 192, 0.1), rgba(169, 169, 169, 0.05));
        }

        .vip-silver:hover {
            border-color: rgba(192, 192, 192, 1);
            box-shadow: 0 25px 70px rgba(192, 192, 192, 0.5);
        }

        .vip-gold {
            border-color: rgba(255, 215, 0, 0.5);
            background: linear-gradient(135deg, rgba(255, 215, 0, 0.15), rgba(218, 165, 32, 0.05));
        }

        .vip-gold:hover {
            border-color: rgba(255, 215, 0, 1);
            box-shadow: 0 25px 70px rgba(255, 215, 0, 0.6);
        }

        .vip-platinum {
            border-color: rgba(229, 228, 226, 0.5);
            background: linear-gradient(135deg, rgba(229, 228, 226, 0.15), rgba(181, 179, 176, 0.05));
        }

        .vip-platinum:hover {
            border-color: rgba(229, 228, 226, 1);
            box-shadow: 0 25px 70px rgba(229, 228, 226, 0.6);
        }

        .vip-diamond {
            border-color: rgba(185, 242, 255, 0.5);
            background: linear-gradient(135deg, rgba(185, 242, 255, 0.2), rgba(0, 191, 255, 0.1));
            position: relative;
        }

        .vip-diamond::after {
            content: '💎';
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 30px;
            opacity: 0.3;
            animation: rotateDiamond 4s linear infinite;
        }

        @keyframes rotateDiamond {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .vip-diamond:hover {
            border-color: rgba(185, 242, 255, 1);
            box-shadow: 0 25px 70px rgba(185, 242, 255, 0.8);
        }

        .vip-contributor {
            border-color: rgba(138, 43, 226, 0.6);
            background: linear-gradient(135deg, rgba(138, 43, 226, 0.25), rgba(75, 0, 130, 0.15));
            position: relative;
            overflow: hidden;
        }

        .vip-contributor::after {
            content: '👑';
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 35px;
            opacity: 0.4;
            animation: crownPulse 2s ease-in-out infinite;
        }

        @keyframes crownPulse {
            0%, 100% { transform: scale(1) rotate(0deg); }
            50% { transform: scale(1.2) rotate(10deg); }
        }

        .vip-contributor::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(138, 43, 226, 0.4), transparent);
            animation: contributorSweep 3s infinite;
        }

        @keyframes contributorSweep {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        .vip-contributor:hover {
            border-color: rgba(138, 43, 226, 1);
            box-shadow: 0 30px 80px rgba(138, 43, 226, 0.9), 
                        0 0 50px rgba(138, 43, 226, 0.6) inset;
            transform: translateY(-20px) scale(1.05);
        }

        .vip-pillar {
            border-color: rgba(255, 0, 127, 0.7);
            background: linear-gradient(135deg, rgba(255, 0, 127, 0.3), rgba(139, 0, 139, 0.2));
            position: relative;
            overflow: hidden;
            animation: pillarGlow 4s ease-in-out infinite;
        }

        @keyframes pillarGlow {
            0%, 100% { box-shadow: 0 0 30px rgba(255, 0, 127, 0.5); }
            50% { box-shadow: 0 0 60px rgba(255, 0, 127, 1), 0 0 100px rgba(255, 0, 127, 0.5); }
        }

        .vip-pillar::after {
            content: '⚡';
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 40px;
            opacity: 0.5;
            animation: lightningStrike 1.5s ease-in-out infinite;
        }

        @keyframes lightningStrike {
            0%, 100% { transform: scale(1) translateY(0); opacity: 0.5; }
            10% { transform: scale(1.3) translateY(-5px); opacity: 1; }
            20% { transform: scale(0.9) translateY(2px); opacity: 0.3; }
            30% { transform: scale(1.2) translateY(-3px); opacity: 1; }
        }

        .vip-pillar::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(255, 0, 127, 0.6), transparent 30%);
            animation: pillarRotate 4s linear infinite;
        }

        @keyframes pillarRotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .vip-pillar:hover {
            border-color: rgba(255, 0, 127, 1);
            box-shadow: 0 35px 100px rgba(255, 0, 127, 1), 
                        0 0 80px rgba(255, 0, 127, 0.8) inset,
                        0 0 150px rgba(139, 0, 139, 0.6);
            transform: translateY(-25px) scale(1.08);
        }

        .vip-contributor .vip-title,
        .vip-pillar .vip-title {
            position: relative;
            z-index: 10;
        }

        .vip-contributor .vip-price { 
            color: #BA55D3; 
            text-shadow: 0 0 20px rgba(138, 43, 226, 0.8);
            position: relative;
            z-index: 10;
        }
        
        .vip-pillar .vip-price { 
            color: #FF1493; 
            text-shadow: 0 0 30px rgba(255, 0, 127, 1);
            animation: priceGlow 2s ease-in-out infinite;
            position: relative;
            z-index: 10;
        }

        @keyframes priceGlow {
            0%, 100% { text-shadow: 0 0 30px rgba(255, 0, 127, 1); }
            50% { text-shadow: 0 0 50px rgba(255, 0, 127, 1), 0 0 70px rgba(139, 0, 139, 0.8); }
        }

        .vip-contributor .vip-button {
            background: linear-gradient(45deg, #8B00FF, #BA55D3);
            color: white;
            position: relative;
            z-index: 10;
            box-shadow: 0 10px 30px rgba(138, 43, 226, 0.5);
        }

        .vip-contributor .vip-button:hover {
            box-shadow: 0 15px 50px rgba(138, 43, 226, 0.8);
        }

        .vip-pillar .vip-button {
            background: linear-gradient(45deg, #FF1493, #8B008B);
            color: white;
            position: relative;
            z-index: 10;
            box-shadow: 0 10px 40px rgba(255, 0, 127, 0.6);
            animation: buttonPulse 2s ease-in-out infinite;
        }

        @keyframes buttonPulse {
            0%, 100% { box-shadow: 0 10px 40px rgba(255, 0, 127, 0.6); }
            50% { box-shadow: 0 15px 60px rgba(255, 0, 127, 1); }
        }

        .vip-pillar .vip-button:hover {
            box-shadow: 0 20px 70px rgba(255, 0, 127, 1);
        }

        .legendary-badge {
            position: absolute;
            top: -15px;
            left: 50%;
            transform: translateX(-50%);
            background: linear-gradient(45deg, #FFD700, #FFA500);
            padding: 8px 20px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: bold;
            letter-spacing: 2px;
            z-index: 20;
            box-shadow: 0 5px 20px rgba(255, 215, 0, 0.6);
            animation: badgeFloat 3s ease-in-out infinite;
        }

        @keyframes badgeFloat {
            0%, 100% { transform: translateX(-50%) translateY(0); }
            50% { transform: translateX(-50%) translateY(-5px); }
        }

        .vip-icon {
            font-size: 60px;
            text-align: center;
            margin-bottom: 20px;
            display: block;
        }

        .vip-title {
            font-size: 28px;
            text-align: center;
            margin-bottom: 15px;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .vip-price {
            text-align: center;
            font-size: 36px;
            font-weight: bold;
            margin-bottom: 25px;
        }

        .vip-wood .vip-price { color: #8B5A2B; }
        .vip-bronze .vip-price { color: #CD7F32; }
        .vip-silver .vip-price { color: #C0C0C0; }
        .vip-gold .vip-price { color: #FFD700; }
        .vip-platinum .vip-price { color: #E5E4E2; }
        .vip-diamond .vip-price { color: #B9F2FF; }

        .vip-benefits {
            list-style: none;
            margin-bottom: 30px;
        }

        .vip-benefits li {
            padding: 12px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            display: flex;
            align-items: center;
            gap: 10px;
            color: #ddd;
        }

        .vip-benefits li::before {
            content: '✓';
            color: #4CAF50;
            font-weight: bold;
            font-size: 18px;
        }

        .vip-button {
            width: 100%;
            padding: 15px;
            border: none;
            border-radius: 15px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .vip-wood .vip-button {
            background: linear-gradient(45deg, #8B5A2B, #654321);
            color: white;
        }

        .vip-bronze .vip-button {
            background: linear-gradient(45deg, #CD7F32, #B87333);
            color: white;
        }

        .vip-silver .vip-button {
            background: linear-gradient(45deg, #C0C0C0, #A9A9A9);
            color: #333;
        }

        .vip-gold .vip-button {
            background: linear-gradient(45deg, #FFD700, #DAA520);
            color: #333;
        }

        .vip-platinum .vip-button {
            background: linear-gradient(45deg, #E5E4E2, #B5B3B0);
            color: #333;
        }

        .vip-diamond .vip-button {
            background: linear-gradient(45deg, #B9F2FF, #00BFFF);
            color: #333;
        }

        .vip-button:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px rgba(255, 255, 255, 0.3);
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
            <li><a href="#agriculture">Agriculture</a></li>
            <li><a href="#vip">VIP Club</a></li>
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

    <section class="products agriculture-section" id="agriculture">
        <h2>Collection Agriculture</h2>
        <p style="text-align: center; color: #aaa; margin-bottom: 60px; font-size: 18px;">🌾 Cordes spécialement conçues pour les travaux agricoles et les champs</p>
        <div class="product-grid">
            <div class="product-card agriculture-card">
                <div class="product-image">🌾</div>
                <h3 class="product-title">Corde Champs de Coton</h3>
                <p class="product-desc">Fibre naturelle biodégradable. Résistante à l'humidité et aux variations climatiques. Idéale pour le balisage et l'attache des plants de coton.</p>
                <div class="product-price">79.99 €</div>
                <button class="buy-button" onclick="addToCart('Corde Champs de Coton', 79.99, '🌾')">Ajouter au panier</button>
            </div>
            <div class="product-card agriculture-card">
                <div class="product-image">🌾</div>
                <h3 class="product-title">Corde Champs de Blé</h3>
                <p class="product-desc">Traitement anti-UV renforcé. Parfaite pour les grandes cultures céréalières. Résiste aux frottements répétés des machines agricoles.</p>
                <div class="product-price">84.99 €</div>
                <button class="buy-button" onclick="addToCart('Corde Champs de Blé', 84.99, '🌾')">Ajouter au panier</button>
            </div>
            <div class="product-card agriculture-card">
                <div class="product-image">🚜</div>
                <h3 class="product-title">Corde Multi-Cultures</h3>
                <p class="product-desc">Polyvalente pour tous types de cultures. Extra-résistante aux intempéries. Traçabilité et marquage inclus pour gestion optimale.</p>
                <div class="product-price">94.99 €</div>
                <button class="buy-button" onclick="addToCart('Corde Multi-Cultures', 94.99, '🚜')">Ajouter au panier</button>
            </div>
        </div>
    </section>

    <section class="vip-section" id="vip">
        <h2>🌟 Club VIP RopeX 🌟</h2>
        <p class="vip-subtitle">Rejoignez notre programme exclusif et profitez d'avantages exceptionnels</p>
        
        <div class="vip-grid">
            <div class="vip-card vip-wood">
                <span class="vip-icon">🪵</span>
                <h3 class="vip-title">Wood</h3>
                <div class="vip-price">Gratuit</div>
                <ul class="vip-benefits">
                    <li>Accès au catalogue complet</li>
                    <li>Newsletter mensuelle</li>
                    <li>Support client standard</li>
                    <li>Garantie 1 an</li>
                </ul>
                <button class="vip-button">S'inscrire</button>
            </div>

            <div class="vip-card vip-bronze">
                <span class="vip-icon">🥉</span>
                <h3 class="vip-title">Bronze</h3>
                <div class="vip-price">29€/an</div>
                <ul class="vip-benefits">
                    <li>5% de réduction</li>
                    <li>Livraison gratuite dès 50€</li>
                    <li>Support prioritaire</li>
                    <li>Garantie 2 ans</li>
                    <li>Accès ventes privées</li>
                </ul>
                <button class="vip-button">Devenir Bronze</button>
            </div>

            <div class="vip-card vip-silver">
                <span class="vip-icon">🥈</span>
                <h3 class="vip-title">Silver</h3>
                <div class="vip-price">59€/an</div>
                <ul class="vip-benefits">
                    <li>10% de réduction</li>
                    <li>Livraison gratuite illimitée</li>
                    <li>Support prioritaire 24/7</li>
                    <li>Garantie 3 ans</li>
                    <li>Produits exclusifs</li>
                    <li>Programme de parrainage</li>
                </ul>
                <button class="vip-button">Devenir Silver</button>
            </div>

            <div class="vip-card vip-gold">
                <span class="vip-icon">🥇</span>
                <h3 class="vip-title">Gold</h3>
                <div class="vip-price">99€/an</div>
                <ul class="vip-benefits">
                    <li>15% de réduction</li>
                    <li>Livraison express gratuite</li>
                    <li>Support VIP dédié</li>
                    <li>Garantie 5 ans</li>
                    <li>Collections en avant-première</li>
                    <li>Personnalisation gratuite</li>
                    <li>Cadeau d'anniversaire</li>
                </ul>
                <button class="vip-button">Devenir Gold</button>
            </div>

            <div class="vip-card vip-platinum">
                <span class="vip-icon">⭐</span>
                <h3 class="vip-title">Platinum</h3>
                <div class="vip-price">199€/an</div>
                <ul class="vip-benefits">
                    <li>20% de réduction</li>
                    <li>Livraison premium internationale</li>
                    <li>Conseiller personnel dédié</li>
                    <li>Garantie à vie</li>
                    <li>Invitations événements exclusifs</li>
                    <li>Personnalisation illimitée</li>
                    <li>Retours gratuits à vie</li>
                    <li>Points de fidélité x3</li>
                </ul>
                <button class="vip-button">Devenir Platinum</button>
            </div>

            <div class="vip-card vip-diamond">
                <span class="vip-icon">💎</span>
                <h3 class="vip-title">Diamond</h3>
                <div class="vip-price">499€/an</div>
                <ul class="vip-benefits">
                    <li>30% de réduction sur tout</li>
                    <li>Livraison ultra-premium mondiale</li>
                    <li>Concierge personnel 24/7</li>
                    <li>Garantie absolue à vie</li>
                    <li>Accès usine & fabrication</li>
                    <li>Conception sur mesure</li>
                    <li>Cadeaux mensuels exclusifs</li>
                    <li>Points de fidélité x5</li>
                    <li>Statut VIP permanent</li>
                </ul>
                <button class="vip-button">Devenir Diamond</button>
            </div>

            <div class="vip-card vip-contributor">
                <div class="legendary-badge">🌟 LÉGENDAIRE 🌟</div>
                <span class="vip-icon">👑</span>
                <h3 class="vip-title">Contributeur</h3>
                <div class="vip-price">999€/an</div>
                <ul class="vip-benefits">
                    <li>40% de réduction permanente</li>
                    <li>Livraison express mondiale gratuite</li>
                    <li>Équipe dédiée personnelle</li>
                    <li>Garantie premium à vie</li>
                    <li>Participation au développement produits</li>
                    <li>Accès laboratoire R&D</li>
                    <li>Prototypes en exclusivité</li>
                    <li>Collections capsule personnalisées</li>
                    <li>Événements VIP internationaux</li>
                    <li>Points de fidélité x10</li>
                    <li>Badge contributeur officiel</li>
                </ul>
                <button class="vip-button">Devenir Contributeur</button>
            </div>

            <div class="vip-card vip-pillar">
                <div class="legendary-badge" style="background: linear-gradient(45deg, #FF1493, #8B008B);">⚡ MYTHIQUE ⚡</div>
                <span class="vip-icon">⚡👑⚡</span>
                <h3 class="vip-title">Pilier</h3>
                <div class="vip-price">2499€/an</div>
                <ul class="vip-benefits">
                    <li>50% de réduction sur TOUT</li>
                    <li>Jet privé pour livraisons</li>
                    <li>PDG disponible directement</li>
                    <li>Garantie infinie absolue</li>
                    <li>Co-création de gammes exclusives</li>
                    <li>Bureau dans nos locaux</li>
                    <li>Actions de l'entreprise offertes</li>
                    <li>Revenus passifs sur ventes</li>
                    <li>Influence stratégique directe</li>
                    <li>Éditions limitées à votre nom</li>
                    <li>Points de fidélité x20</li>
                    <li>Statut immortel dans l'histoire</li>
                    <li>Carte noire illimitée RopeX</li>
                </ul>
                <button class="vip-button">Devenir Pilier</button>
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

        // Créer des particules VIP
        const vipSection = document.querySelector('.vip-section');
        if (vipSection) {
            for (let i = 0; i < 30; i++) {
                const particle = document.createElement('div');
                particle.className = 'vip-particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 8 + 's';
                particle.style.animationDuration = (Math.random() * 4 + 6) + 's';
                
                // Varier les couleurs des particules
                const colors = ['rgba(255, 215, 0, 0.8)', 'rgba(192, 192, 192, 0.8)', 'rgba(185, 242, 255, 0.8)', 'rgba(229, 228, 226, 0.8)'];
                particle.style.background = colors[Math.floor(Math.random() * colors.length)];
                
                vipSection.appendChild(particle);
            }

            // Particules spéciales pour Contributeur et Pilier
            for (let i = 0; i < 20; i++) {
                const legendaryParticle = document.createElement('div');
                legendaryParticle.className = 'vip-particle';
                legendaryParticle.style.left = Math.random() * 100 + '%';
                legendaryParticle.style.animationDelay = Math.random() * 6 + 's';
                legendaryParticle.style.animationDuration = (Math.random() * 3 + 5) + 's';
                legendaryParticle.style.width = '6px';
                legendaryParticle.style.height = '6px';
                
                const legendaryColors = ['rgba(138, 43, 226, 1)', 'rgba(255, 0, 127, 1)', 'rgba(186, 85, 211, 1)'];
                legendaryParticle.style.background = legendaryColors[Math.floor(Math.random() * legendaryColors.length)];
                legendaryParticle.style.boxShadow = `0 0 20px ${legendaryColors[Math.floor(Math.random() * legendaryColors.length)]}`;
                
                vipSection.appendChild(legendaryParticle);
            }
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

        document.querySelectorAll('.product-card, .feature-item, .vip-card').forEach(el => {
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
