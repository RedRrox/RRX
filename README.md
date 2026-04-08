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
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.95); backdrop-filter: blur(20px);
            z-index: 10000; display: flex; justify-content: center; align-items: center;
            transition: 1s ease;
        }
        .welcome-card {
            max-width: 580px; width: 90%; background: #080808; border: 1px solid var(--rrx-red);
            border-radius: 20px; padding: 40px; text-align: center; box-shadow: 0 0 50px rgba(255, 0, 0, 0.3);
        }
        .continue-btn {
            background: transparent; border: 2px solid var(--rrx-red); color: white;
            padding: 16px 50px; font-family: 'Orbitron', sans-serif; font-weight: bold;
            text-transform: uppercase; cursor: pointer; transition: 0.3s;
            box-shadow: 0 0 15px var(--rrx-glow); margin-top: 10px;
        }
        .continue-btn:hover { background: var(--rrx-red); transform: scale(1.05); }

        /* --- Header --- */
        header {
            padding: 30px 5%; display: flex; justify-content: center; align-items: center;
            background: #000000; border-bottom: 2px solid var(--rrx-red);
            box-shadow: 0 5px 25px var(--rrx-glow); position: relative; z-index: 10;
        }
        .brand-name { font-family: 'Orbitron', sans-serif; font-size: clamp(32px, 6vw, 45px); font-weight: 800; color: var(--rrx-red); text-shadow: 0 0 20px var(--rrx-red); letter-spacing: 10px; }

        /* --- Hero --- */
        .hero { height: 40vh; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; background: radial-gradient(circle, rgba(255, 0, 0, 0.1) 0%, rgba(0,0,0,1) 80%); padding: 20px; }
        .hero h1 { font-family: 'Orbitron', sans-serif; font-size: clamp(40px, 10vw, 85px); background: linear-gradient(to bottom, #fff 40%, var(--rrx-red)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .aura-text { font-family: 'Orbitron', sans-serif; font-size: clamp(14px, 4vw, 22px); color: #fff; letter-spacing: 5px; text-transform: uppercase; font-weight: 700; margin-top: 15px; animation: aura-glow 3s infinite; }
        @keyframes aura-glow { 0%, 100% { opacity: 0.7; } 50% { opacity: 1; text-shadow: 0 0 20px var(--rrx-red); } }

        /* --- Grid --- */
        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 35px; padding: 40px 5% 100px 5%; max-width: 1400px; margin: 0 auto; }
        .product-card { position: relative; background: var(--glass); border: 1px solid #1a1a1a; border-radius: 15px; padding: 30px 25px; text-align: center; transition: 0.4s; display: flex; flex-direction: column; justify-content: space-between; }
        .product-card:hover { border-color: var(--rrx-red); box-shadow: 0 0 30px rgba(255, 0, 0, 0.15); transform: translateY(-10px); }
        .badge { position: absolute; top: 15px; right: 15px; padding: 5px 12px; font-size: 11px; font-weight: bold; border-radius: 4px; font-family: 'Orbitron'; }
        .offer-tag { background: var(--rrx-red); color: white; box-shadow: 0 0 15px var(--rrx-red); }
        .img-box { background: #050505; height: 260px; border-radius: 12px; overflow: hidden; margin-bottom: 25px; border: 1px solid #111; display: flex; align-items: center; justify-content: center; }
        .img-box img { width: 100%; height: 100%; object-fit: contain; padding: 10px; }
        .price { font-size: 32px; color: var(--rrx-red); font-weight: bold; margin-bottom: 25px; display: block; }
        
        /* --- Buy Button --- */
        .buy-now-btn {
            background: var(--rrx-red); color: white; border: none; padding: 15px;
            font-family: 'Orbitron'; font-weight: bold; cursor: pointer;
            box-shadow: 0 0 15px var(--rrx-glow); transition: 0.3s; text-decoration: none;
        }
        .buy-now-btn:hover { box-shadow: 0 0 30px var(--rrx-red); transform: scale(1.02); }

        /* --- Payment Page (Hidden by default) --- */
        #payment-page {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: #000; z-index: 10001; overflow-y: auto; padding: 40px 5%;
        }
        .payment-container { max-width: 500px; margin: 0 auto; background: #080808; border: 1px solid var(--rrx-red); border-radius: 20px; padding: 30px; }
        .method-box { display: flex; gap: 15px; margin: 20px 0; }
        .method { flex: 1; padding: 15px; border: 1px solid #222; border-radius: 10px; cursor: pointer; text-align: center; transition: 0.3s; }
        .method.active { border-color: var(--rrx-red); background: rgba(255, 0, 0, 0.1); }
        .method.soon { opacity: 0.5; cursor: not-allowed; }
        input { width: 100%; padding: 15px; margin-bottom: 15px; background: #111; border: 1px solid #222; color: #fff; border-radius: 8px; }
        input:focus { border-color: var(--rrx-red); outline: none; }
        .submit-btn { width: 100%; padding: 18px; background: var(--rrx-red); border: none; color: white; font-family: 'Orbitron'; font-weight: 800; cursor: pointer; border-radius: 8px; }

        footer { text-align: center; padding: 60px; border-top: 1px solid #1a1a1a; color: #555; font-size: 13px; }
        footer span { color: var(--rrx-red); }
    </style>
</head>
<body>

    <div id="welcome-overlay">
        <div class="welcome-card">
            <h2>RRX CORE</h2>
            <p>আপনার বিশ্বস্ত গেমিং মার্কেটপ্লেস। দ্রুত ডেলিভারি এবং সিকিউর লেনদেনের নিশ্চয়তা।</p>
            <span class="highlight">আপনার বিশ্বাস, আমাদের আমানত।</span>
            <button class="continue-btn" onclick="enterSite()">Enter RRX CORE</button>
        </div>
    </div>

    <div id="payment-page">
        <div class="payment-container">
            <button onclick="closePayment()" style="background: none; border: none; color: #666; cursor: pointer; font-family: 'Orbitron'; margin-bottom: 20px;">[ BACK TO STORE ]</button>
            <h2 style="font-family: 'Orbitron'; color: var(--rrx-red); margin-bottom: 10px;">CHECKOUT</h2>
            <p id="selected-product" style="color: #888; margin-bottom: 20px; font-weight: bold;"></p>
            
            <div class="method-box">
                <div class="method active">bKash<br><small>01XXXXXXXXX</small></div>
                <div class="method soon">Nagad<br><small>COMING SOON</small></div>
            </div>

            <form action="#">
                <input type="text" placeholder="Your Full Name" required>
                <input type="text" placeholder="Game Player ID / Account Email" required>
                <input type="text" placeholder="bKash Transaction ID (TrxID)" required>
                <p style="font-size: 12px; color: #666; margin-bottom: 15px;">* পেমেন্ট কমপ্লিট করার পর TrxID দিয়ে সাবমিট করুন।</p>
                <button type="submit" class="submit-btn">CONFIRM ORDER</button>
            </form>
        </div>
    </div>

    <header>
        <div class="brand-name">RRX</div>
    </header>

    <main id="main-content">
        <section class="hero">
            <h1>RRX CORE</h1>
            <p class="aura-text">YOUR AURA, YOUR RULES</p>
        </section>

        <div class="grid">
            <div class="product-card">
                <div class="badge offer-tag">AVAILABLE</div>
                <div class="img-box"><img src="mccombo.png" alt="Minecraft"></div>
                <h3 class="p-name">Minecraft Java + Bedrock Edition (Combo)</h3>
                <span class="price">৳ 2,000</span>
                <button class="buy-now-btn" onclick="openPayment('Minecraft Combo - ৳ 2,000')">BUY NOW</button>
            </div>

            <div class="product-card">
                <div class="badge offer-tag">AVAILABLE</div>
                <div class="img-box"><img src="gtav.png" alt="GTA V"></div>
                <h3 class="p-name">Grand Theft Auto 5 | GTA V – Premium Edition</h3>
                <span class="price">৳ 2,100</span>
                <button class="buy-now-btn" onclick="openPayment('GTA V Premium - ৳ 2,100')">BUY NOW</button>
            </div>

            <div class="product-card">
                <div class="badge offer-tag">AVAILABLE</div>
                <div class="img-box"><img src="forza.png" alt="Forza 5"></div>
                <h3 class="p-name">Forza Horizon 5 – Premium Edition | Steam</h3>
                <span class="price">৳ 3,999</span>
                <button class="buy-now-btn" onclick="openPayment('Forza Horizon 5 - ৳ 3,999')">BUY NOW</button>
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
            }, 800);
        }

        function openPayment(productName) {
            document.getElementById('payment-page').style.display = 'block';
            document.getElementById('selected-product').innerText = "Ordering: " + productName;
            document.body.style.overflow = 'hidden';
        }

        function closePayment() {
            document.getElementById('payment-page').style.display = 'none';
            document.body.style.overflow = 'auto';
        }
    </script>
</body>
</html>
