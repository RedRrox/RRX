<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RRX | YOUR AURA, YOUR RULES</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;800&family=Rajdhani:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-pure: #000000;
            --rrx-red: #ff0000;
            --rrx-glow: rgba(255, 0, 0, 0.6);
            --cyber-blue: #00f2ff;
            --glass: rgba(255, 255, 255, 0.03);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Rajdhani', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background-color: var(--bg-pure);
            color: #ffffff;
            overflow-x: hidden;
        }

        /* --- Custom Scrollbar --- */
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: #000; }
        ::-webkit-scrollbar-thumb { background: var(--rrx-red); border-radius: 10px; }

        /* --- Header --- */
        header {
            padding: 20px 5%;
            display: flex;
            justify-content: center;
            align-items: center;
            background: rgba(0, 0, 0, 0.9);
            border-bottom: 2px solid var(--rrx-red);
            box-shadow: 0 5px 25px var(--rrx-glow);
            position: sticky;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
        }

        .brand-name {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(28px, 5vw, 40px);
            font-weight: 800;
            color: var(--rrx-red);
            text-shadow: 0 0 20px var(--rrx-red);
            letter-spacing: 8px;
        }

        /* --- Hero Section --- */
        .hero {
            height: 70vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: radial-gradient(circle, rgba(255, 0, 0, 0.15) 0%, rgba(0,0,0,1) 80%);
            padding: 20px;
        }

        .hero h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(45px, 12vw, 90px);
            background: linear-gradient(to bottom, #fff 40%, var(--rrx-red));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 5px;
            filter: drop-shadow(0 0 10px rgba(255, 0, 0, 0.3));
        }

        .aura-text {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(14px, 4vw, 22px);
            color: #fff;
            letter-spacing: 5px;
            text-transform: uppercase;
            font-weight: 700;
            margin-top: 10px;
            animation: aura-glow 3s ease-in-out infinite;
        }

        @keyframes aura-glow {
            0%, 100% {
                text-shadow: 0 0 5px var(--rrx-red), 0 0 10px var(--rrx-red);
                opacity: 0.7;
                transform: scale(1);
            }
            50% {
                text-shadow: 0 0 25px var(--rrx-red), 0 0 50px var(--rrx-red);
                opacity: 1;
                transform: scale(1.05);
            }
        }

        /* --- Premium Void Burst Button --- */
        .rrx-btn {
            position: relative;
            margin-top: 35px;
            padding: 18px 50px;
            background: transparent;
            border: 2px solid var(--rrx-red);
            color: white;
            font-family: 'Orbitron', sans-serif;
            font-size: 16px;
            font-weight: bold;
            letter-spacing: 2px;
            cursor: pointer;
            overflow: hidden;
            transition: 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 0 15px var(--rrx-glow);
            border-radius: 4px;
        }

        .rrx-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 40px var(--rrx-red);
            background: var(--rrx-red);
        }

        .rrx-btn::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: var(--cyber-blue);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            opacity: 0;
            transition: width 0.6s ease-out, height 0.6s ease-out, opacity 0.6s ease-out;
        }

        .rrx-btn:active::after {
            width: 500px;
            height: 500px;
            opacity: 0.5;
        }

        /* --- Grid Layout --- */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            padding: 60px 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .product-card {
            background: var(--glass);
            border: 1px solid #1a1a1a;
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: 0.4s;
            backdrop-filter: blur(5px);
        }

        .product-card:hover {
            border-color: var(--rrx-red);
            box-shadow: 0 0 30px rgba(255, 0, 0, 0.15);
            transform: translateY(-10px);
        }

        .img-box {
            background: linear-gradient(45deg, #0a0a0a, #1a1a1a);
            height: 250px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 25px;
            color: #222;
            font-size: 50px;
            font-weight: 800;
            border: 1px solid #222;
        }

        .product-name {
            font-size: 26px;
            font-weight: 700;
            margin-bottom: 12px;
            letter-spacing: 1px;
        }

        .price {
            font-size: 30px;
            color: var(--rrx-red);
            font-weight: bold;
            margin-bottom: 25px;
        }

        /* --- Footer --- */
        footer {
            text-align: center;
            padding: 60px 20px;
            border-top: 1px solid #1a1a1a;
            color: #666;
            letter-spacing: 2px;
            font-size: 13px;
            background: #020202;
        }

        footer span {
            color: var(--rrx-red);
            font-weight: bold;
        }

        /* --- Mobile Responsiveness --- */
        @media (max-width: 768px) {
            .hero { height: 60vh; }
            .grid { padding: 40px 20px; }
            .rrx-btn { width: 100%; }
        }
    </style>
</head>
<body>

    <header>
        <div class="brand-name">RRX</div>
    </header>

    <main>
        <section class="hero">
            <h1>RRX CORE</h1>
            <p class="aura-text">YOUR AURA, YOUR RULES</p>
            <button class="rrx-btn">ACCESS INVENTORY</button>
        </section>

        <div class="grid">
            <div class="product-card">
                <div class="img-box">RRX-01</div>
                <div class="product-name">SHADOW MOUSE</div>
                <div class="price">৳ 2,500</div>
                <button class="rrx-btn" style="padding: 12px 30px; font-size: 14px; margin-top: 0;">GET NOW</button>
            </div>

            <div class="product-card">
                <div class="img-box">RRX-02</div>
                <div class="product-name">IGNITE KEYBOARD</div>
                <div class="price">৳ 4,800</div>
                <button class="rrx-btn" style="padding: 12px 30px; font-size: 14px; margin-top: 0;">GET NOW</button>
            </div>

            <div class="product-card">
                <div class="img-box">RRX-03</div>
                <div class="product-name">VOID HEADSET</div>
                <div class="price">৳ 3,500</div>
                <button class="rrx-btn" style="padding: 12px 30px; font-size: 14px; margin-top: 0;">GET NOW</button>
            </div>
        </div>
    </main>

    <footer>
        <p>&copy; 2026 <span>RRX</span> BRAND | POWERED BY <span>RRX STUDIOS</span></p>
    </footer>

</body>
</html>
