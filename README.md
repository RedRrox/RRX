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

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
        body { background-color: var(--bg-pure); color: #ffffff; overflow: hidden; }

        /* --- Welcome Overlay --- */
        #welcome-overlay {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.92);
            backdrop-filter: blur(20px);
            z-index: 9999;
            display: flex; justify-content: center; align-items: center;
            transition: 1s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .welcome-card {
            max-width: 550px; width: 90%;
            background: #080808; border: 1px solid var(--rrx-red);
            border-radius: 20px; padding: 40px; text-align: center;
            box-shadow: 0 0 40px rgba(255, 0, 0, 0.2);
            animation: fadeIn 0.8s ease;
        }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

        .welcome-card h2 { font-family: 'Orbitron', sans-serif; color: var(--rrx-red); margin-bottom: 20px; letter-spacing: 5px; }
        .welcome-card p { font-size: 18px; line-height: 1.8; color: #bbb; margin-bottom: 25px; }
        .welcome-card .highlight { color: var(--rrx-red); font-weight: 700; font-size: 22px; display: block; margin: 15px 0; }

        .continue-btn {
            background: transparent; border: 2px solid var(--rrx-red); color: white;
            padding: 15px 45px; font-family: 'Orbitron', sans-serif; font-weight: bold;
            text-transform: uppercase; cursor: pointer; transition: 0.3s;
            box-shadow: 0 0 15px var(--rrx-glow);
        }
        .continue-btn:hover { background: var(--rrx-red); box-shadow: 0 0 30px var(--rrx-red); transform: scale(1.05); }

        /* --- Main Page --- */
        header {
            padding: 20px 5%; display: flex; justify-content: center; align-items: center;
            background: rgba(0, 0, 0, 0.9); border-bottom: 2px solid var(--rrx-red);
            box-shadow: 0 5px 25px var(--rrx-glow); position: sticky; top: 0; z-index: 1000;
        }

        .brand-name {
            font-family: 'Orbitron', sans-serif; font-size: clamp(28px, 5vw, 40px);
            font-weight: 800; color: var(--rrx-red); text-shadow: 0 0 20px var(--rrx-red); letter-spacing: 8px;
        }

        .hero {
            height: 60vh; display: flex; flex-direction: column; justify-content: center;
            align-items: center; text-align: center;
            background: radial-gradient(circle, rgba(255, 0, 0, 0.15) 0%, rgba(0,0,0,1) 80%);
            padding: 20px;
        }

        .hero h1 {
            font-family: 'Orbitron', sans-serif; font-size: clamp(45px, 12vw, 90px);
            background: linear-gradient(to bottom, #fff 40%, var(--rrx-red));
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }

        .aura-text {
            font-family: 'Orbitron', sans-serif; font-size: clamp(14px, 4vw, 22px);
            color: #fff; letter-spacing: 5px; text-transform: uppercase;
            font-weight: 700; margin-top: 10px; animation: aura-glow 3s ease-in-out infinite;
        }

        @keyframes aura-glow {
            0%, 100% { text-shadow: 0 0 5px var(--rrx-red), 0 0 10px var(--rrx-red); opacity: 0.7; transform: scale(1); }
            50% { text-shadow: 0 0 25px var(--rrx-red), 0 0 50px var(--rrx-red); opacity: 1; transform: scale(1.05); }
        }

        /* --- Product Grid --- */
        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 30px; padding: 60px 5%; max-width: 1400px; margin: 0 auto; }
        
        .product-card { 
            position: relative;
            background: var(--glass); border: 1px solid #1a1a1a; border-radius: 15px; 
            padding: 25px; text-align: center; transition: 0.4s; backdrop-filter: blur(5px);
            display: flex; flex-direction: column; justify-content: space-between;
        }

        .product-card:hover { border-color: var(--rrx-red); box-shadow: 0 0 30px rgba(255, 0, 0, 0.15); transform: translateY(-10px); }

        .badge {
            position: absolute; top: 15px; right: 15px;
            padding: 5px 12px; font-size: 11px; font-weight: bold; border-radius: 4px; font-family: 'Orbitron', sans-serif;
            z-index: 2;
        }
        .stock-out { background: #333; color: #888; border: 1px solid #444; }
        .offer-tag { background: var(--rrx-red); color: white; box-shadow: 0 0 15px var(--rrx-red); border: 1px solid white; }

        /* Updated Image Box to show real images */
        .img-box { 
            background: #0a0a0a; height: 200px; 
            border-radius: 10px; overflow: hidden;
            margin-bottom: 20px; border: 1px solid #222;
            display: flex; align-items: center; justify-content: center;
        }

        .img-box img {
            width: 100%; height: 100%; object-fit: cover;
            transition: 0.5s;
        }

        .product-card:hover .img-box img { transform: scale(1.1); }

        .product-name { font-size: 19px; font-weight: 700; margin-bottom: 12px; color: #fff; min-height: 55px; line-height: 1.4; }
        .price { font-size: 28px; color: var(--rrx-red); font-weight: bold; margin-bottom: 20px; }

        .rrx-btn {
            padding: 15px 30px; background: transparent;
            border: 2px solid var(--rrx-red); color: white; font-family: 'Orbitron', sans-serif;
            font-size: 14px; font-weight: bold; cursor: pointer; transition: 0.3s;
        }
        .rrx-btn:disabled { border-color: #333; color: #444; cursor: not-allowed; }

        footer { text-align: center; padding: 60px 20px; border-top: 1px solid #1a1a1a; color: #666; letter-spacing: 2px; font-size: 13px; }
        footer span { color: var(--rrx-red); font-weight: bold; }

        @media (max-width: 768px) { .hero { height: 60vh; } }
    </style>
</head>
<body>

    <div id="welcome-overlay">
        <div class="welcome-card">
            <h2>RRX STUDIOS</h2>
            <p>আপনার বিশ্বস্ত গেমিং মার্কেটপ্লেস, যেখানে পাবেন জনপ্রিয় গেম, ইন-গেম আইটেম এবং এক্সক্লুসিভ অফার। দ্রুত ডেলিভারি, সিকিউর লেনদেন এবং সহজ পেমেন্ট সুবিধা (বিকাশ ও নগদ)।</p>
            <span class="highlight">আপনার বিশ্বাস, আমাদের আমানত।</span>
            <p style="font-size: 14px; color: var(--rrx-red); letter-spacing: 3px;">YOUR AURA, YOUR RULES 🎮🔥</p>
            <button class="continue-btn" onclick="enterSite()">Enter RRX CORE</button>
        </div>
    </div>

    <header>
        <div class="brand-name">RRX</div>
    </header>

    <main>
        <section class="hero">
            <h1>RRX CORE</h1>
            <p class="aura-text">YOUR AURA, YOUR RULES</p>
        </section>

        <div class="grid">
            <div class="product-card">
                <div class="badge offer-tag">OFFER (STOCK OUT)</div>
                <div class="img-box">
                    <img src="mccombo.png" alt="Minecraft Combo">
                </div>
                <h3 class="product-name">Minecraft Java + Bedrock Edition (Combo) | Microsoft Account</h3>
                <div class="price">৳ 2,000</div>
                <button class="rrx-btn" disabled>GET NOW</button>
            </div>

            <div class="product-card">
                <div class="badge stock-out">OUT OF STOCK</div>
                <div class="img-box">
                    <img src="gtav.png" alt="GTA V">
                </div>
                <h3 class="product-name">Grand Theft Auto 5 | GTA V – Online Premium Edition | Rockstar Redeem Key</h3>
                <div class="price">৳ 2,100</div>
                <button class="rrx-btn" disabled>GET NOW</button>
            </div>

            <div class="product-card">
                <div class="badge offer-tag">OFFER (STOCK OUT)</div>
                <div class="img-box">
                    <img src="forza.png" alt="Forza Horizon 5">
                </div>
                <h3 class="product-name">Forza Horizon 5 – Premium Edition | Steam Account</h3>
                <div class="price">৳ 3,999</div>
                <button class="rrx-btn" disabled>GET NOW</button>
            </div>
        </div>
    </main>

    <footer>
        <p>&copy; 2026 <span>RRX</span> BRAND | POWERED BY <span>RRX STUDIOS</span></p>
    </footer>

    <script>
        function enterSite() {
            const overlay = document.getElementById('welcome-overlay');
            overlay.style.opacity = '0';
            setTimeout(() => {
                overlay.style.display = 'none';
                document.body.style.overflow = 'auto';
            }, 1000);
        }
    </script>
</body>
</html>
