<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RRX | The Future of Gaming Gear</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;800&family=Rajdhani:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-pure: #000000;
            --rrx-red: #ff0000;
            --rrx-glow: rgba(255, 0, 0, 0.6);
            --cyber-blue: #00f2ff;
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

        /* --- Header & Branding --- */
        header {
            padding: 15px 5%;
            display: flex;
            justify-content: center; /* Centered for more premium feel */
            align-items: center;
            background: rgba(0, 0, 0, 0.9);
            border-bottom: 2px solid var(--rrx-red);
            box-shadow: 0 5px 20px var(--rrx-glow);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .brand-name {
            font-family: 'Orbitron', sans-serif;
            font-size: 35px;
            font-weight: 800;
            color: var(--rrx-red);
            text-shadow: 0 0 15px var(--rrx-red);
            letter-spacing: 5px;
        }

        /* --- Hero Section --- */
        .hero {
            height: 50vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: radial-gradient(circle, rgba(255, 0, 0, 0.15) 0%, rgba(0,0,0,1) 80%);
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        .hero h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(40px, 10vw, 80px);
            background: linear-gradient(to bottom, #fff 40%, var(--rrx-red));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 5px;
        }

        .hero p {
            font-size: 18px;
            color: #888;
            letter-spacing: 3px;
            text-transform: uppercase;
        }

        /* --- Premium Satisfying Button --- */
        .rrx-btn {
            position: relative;
            margin-top: 30px;
            padding: 15px 45px;
            background: transparent;
            border: 2px solid var(--rrx-red);
            color: white;
            font-family: 'Orbitron', sans-serif;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            overflow: hidden;
            transition: 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 0 10px var(--rrx-glow);
        }

        .rrx-btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 0 30px var(--rrx-red);
            background: var(--rrx-red);
        }

        /* Satisfying Burst on Click */
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
            width: 400px;
            height: 400px;
            opacity: 0.4;
        }

        /* --- Product Layout --- */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            padding: 50px 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .product-card {
            background: #0a0a0a;
            border: 1px solid #1a1a1a;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            transition: 0.4s;
        }

        .product-card:hover {
            border-color: var(--rrx-red);
            box-shadow: 0 0 20px rgba(255, 0, 0, 0.2);
            transform: scale(1.02);
        }

        .img-box {
            background: #111;
            height: 250px;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            color: #333;
            font-size: 40px;
            border: 1px dashed #333;
        }

        .product-name {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .price {
            font-size: 28px;
            color: var(--rrx-red);
            font-weight: bold;
            margin-bottom: 20px;
        }

        /* --- Mobile Optimization --- */
        @media (max-width: 768px) {
            .hero h1 { font-size: 50px; }
            .grid { padding: 30px 15px; }
            .brand-name { font-size: 28px; }
        }

        footer {
            text-align: center;
            padding: 40px;
            border-top: 1px solid #1a1a1a;
            color: #555;
            font-size: 14px;
            letter-spacing: 1px;
        }
    </style>
</head>
<body>

    <header>
        <div class="brand-name">RRX</div>
    </header>

    <section class="hero">
        <h1>RRX CORE</h1>
        <p>Premium Gaming Authority</p>
        <button class="rrx-btn">ACCESS INVENTORY</button>
    </section>

    <div class="grid">
        <div class="product-card">
            <div class="img-box">RRX-01</div>
            <div class="product-name">RRX SHADOW MOUSE</div>
            <div class="price">৳ 2,500</div>
            <button class="rrx-btn" style="padding: 10px 30px; font-size: 14px;">GET NOW</button>
        </div>

        <div class="product-card">
            <div class="img-box">RRX-02</div>
            <div class="product-name">RRX IGNITE KEYBOARD</div>
            <div class="price">৳ 4,800</div>
            <button class="rrx-btn" style="padding: 10px 30px; font-size: 14px;">GET NOW</button>
        </div>

        <div class="product-card">
            <div class="img-box">RRX-03</div>
            <div class="product-name">RRX VOID HEADSET</div>
            <div class="price">৳ 3,500</div>
            <button class="rrx-btn" style="padding: 10px 30px; font-size: 14px;">GET NOW</button>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 RRX BRAND | DESIGNED BY AGENT HUMU</p>
    </footer>

</body>
</html>
