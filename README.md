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
            --glass: rgba(255, 255, 255, 0.03);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
        body { background-color: var(--bg-pure); color: #ffffff; }

        /* --- Welcome Overlay --- */
        #welcome-overlay {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.95);
            backdrop-filter: blur(20px);
            z-index: 10000;
            display: flex; justify-content: center; align-items: center;
            transition: 1s ease;
        }

        .welcome-card {
            max-width: 580px; width: 90%;
            background: #080808; border: 1px solid var(--rrx-red);
            border-radius: 20px; padding: 40px; text-align: center;
            box-shadow: 0 0 50px rgba(255, 0, 0, 0.3);
            animation: fadeIn 0.8s ease;
        }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

        .welcome-card h2 { font-family: 'Orbitron', sans-serif; color: var(--rrx-red); margin-bottom: 25px; letter-spacing: 5px; font-size: 32px; }
        .welcome-card p { font-size: 19px; line-height: 1.8; color: #ccc; margin-bottom: 20px; }
        .welcome-card .highlight { color: var(--rrx-red); font-weight: 700; font-size: 24px; display: block; margin: 20px 0; letter-spacing: 1px; }

        .continue-btn {
            background: transparent; border: 2px solid var(--rrx-red); color: white;
            padding: 16px 50px; font-family: 'Orbitron', sans-serif; font-weight: bold;
            text-transform: uppercase; cursor: pointer; transition: 0.3s;
            box-shadow: 0 0 15px var(--rrx-glow); margin-top: 10px;
        }
        .continue-btn:hover { background: var(--rrx-red); box-shadow: 0 0 30px var(--rrx-red); transform: scale(1.05); }

        /* --- Header (Static - No Move) --- */
        header {
            padding: 30px 5%; 
            display: flex; 
            justify-content: center; 
            align-items: center;
            background: #000000; 
            border-bottom: 2px solid var(--rrx-red);
            box-shadow: 0 5px 25px var(--rrx-glow);
            position: relative; /* Fixed: It stays at the top and moves away when scrolling */
            z-index: 10;
        }

        .brand-name {
            font-family: 'Orbitron', sans-serif; font-size: clamp(32px, 6vw, 45px);
            font-weight: 800; color: var(--rrx-red); text-shadow: 0 0 20px var(--rrx-red); letter-spacing: 10px;
        }

        /* --- Hero Section --- */
        .hero {
            height: 40vh; display: flex; flex-direction: column; justify-content: center;
            align-items: center; text-align: center;
            background: radial-gradient(circle, rgba(255, 0, 0, 0.1) 0%, rgba(0,0,0,1) 80%);
            padding: 20px;
        }

        .hero h1 {
            font-family: 'Orbitron', sans-serif; font-size: clamp(40px, 10vw, 85px);
            background: linear-gradient(to bottom, #fff 40%, var(--rrx-red));
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }

        .aura-text {
            font-family: 'Orbitron', sans-serif; font-size: clamp(14px, 4vw, 22px);
            color: #fff; letter-spacing: 5px; text-transform: uppercase;
            font-weight: 700; margin-top: 15px; animation: aura-glow 3s infinite;
        }
        @keyframes aura-glow { 0%, 100% { opacity: 0.7; } 50% { opacity: 1; text-shadow: 0 0 20px var(--rrx-red); } }

        /* --- Product Grid --- */
        .grid { 
            display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); 
            gap: 35px; padding: 40px 5% 100px 5%; max-width: 1400px; margin: 0 auto;
        }
        
        .product-card { 
            position: relative; background: var(--glass); border: 1px solid #1a1a1a; 
            border-radius: 15px; padding: 30px 25px; text-align: center; transition: 0.4s;
            display: flex; flex-direction: column; justify-content: space-between;
        }
        .product-card:hover { border-color: var(--rrx-red); box-shadow: 0 0 30px rgba(255, 0, 0, 0.15); transform: translateY(-10px); }

        .badge {
            position: absolute; top: 15px; right: 15px;
            padding: 5px 12px; font-size: 11px; font-weight: bold; border-radius: 4px; font-family: 'Orbitron';
        }
        .stock-out { background: #222; color: #666; }
        .offer-tag { background: var(--rrx-red); color: white; box-shadow: 0 0 15px var(--rrx-red); }

        .img-box { 
            background: #050505; height: 260px; border-radius: 12px; 
            overflow: hidden; margin-bottom: 25px; border: 1px solid #111;
            display: flex; align-items: center; justify-content: center;
        }
        .img-box img { width: 100%; height: 100%; object-fit: contain; padding: 10px; transition: 0.6s; }
        .product-card:hover .img-box img { transform: scale(1.08); }

        .price { font-size: 32px; color: var(--rrx-red); font-weight: bold; margin-bottom: 25px; display: block; }
        .rrx-btn { padding: 15px; border: 1px solid #222; background: transparent; color: #444; font-family: 'Orbitron'; cursor: not-allowed; }

        footer { text-align: center; padding: 60px; border-top: 1px solid #1a1a1a; color: #555; font-size: 13px; }
        footer span { color: var(--rrx-red); }
    </style>
</head>
<body>

    <div id="welcome-overlay">
        <div class="welcome-card">
            <h2>RRX CORE</h2>
            <p>
                আপনার বিশ্বস্ত গেমিং মার্কেটপ্লেস, যেখানে পাবেন জনপ্রিয় গেম, ইন-গেম আইটেম এবং এক্সক্লুসিভ অফার। দ্রুত ডেলিভারি, সিকিউর লেনদেন এবং সহজ পেমেন্ট সুবিধা (বিকাশ ও নগদ) নিয়ে আমরা প্রস্তুত।
            </p>
            <span class="highlight">আপনার বিশ্বাস, আমাদের আমানত।</span>
            <p style="font-size: 15px; color: var(--rrx-red); letter-spacing: 3px; font-family: 'Orbitron';">YOUR AURA, YOUR RULES </p>
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
                <div class="img-box"><img src="mccombo.png" alt="Minecraft"></div>
                <h3 style="font-size: 20px; min-height: 55px; line-height:1.4;">Minecraft Java + Bedrock Edition (Combo) | Microsoft Account</h3>
                <span class="price">৳ 2,000</span>
                <button class="rrx-btn" disabled>OUT OF STOCK</button>
            </div>

            <div class="product-card">
                <div class="badge stock-out">OUT OF STOCK</div>
                <div class="img-box"><img src="gtav.png" alt="GTA V"></div>
                <h3 style="font-size: 20px; min-height: 55px; line-height:1.4;">Grand Theft Auto 5 | GTA V – Online Premium Edition | Rockstar Key</h3>
                <span class="price">৳ 2,100</span>
                <button class="rrx-btn" disabled>OUT OF STOCK</button>
            </div>

            <div class="product-card">
                <div class="badge offer-tag">OFFER (STOCK OUT)</div>
                <div class="img-box"><img src="forza.png" alt="Forza 5"></div>
                <h3 style="font-size: 20px; min-height: 55px; line-height:1.4;">Forza Horizon 5 – Premium Edition | Steam Account</h3>
                <span class="price">৳ 3,999</span>
                <button class="rrx-btn" disabled>OUT OF STOCK</button>
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
                document.body.style.overflow = 'auto'; // Re-enable scrolling after entry
            }, 800);
        }
    </script>
</body>
</html>
