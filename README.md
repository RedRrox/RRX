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
            --discord: #5865F2;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
        body { background-color: var(--bg-pure); color: #ffffff; overflow-x: hidden; }

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

        /* --- Header --- */
        header { padding: 30px 5%; display: flex; justify-content: center; align-items: center; background: #000000; border-bottom: 2px solid var(--rrx-red); box-shadow: 0 5px 25px var(--rrx-glow); position: relative; z-index: 10; }
        .brand-name { font-family: 'Orbitron', sans-serif; font-size: clamp(32px, 6vw, 45px); font-weight: 800; color: var(--rrx-red); text-shadow: 0 0 20px var(--rrx-red); letter-spacing: 10px; }

        /* --- Hero --- */
        .hero { height: 50vh; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; background: radial-gradient(circle, rgba(255, 0, 0, 0.1) 0%, rgba(0,0,0,1) 80%); padding: 20px; }
        .hero h1 { font-family: 'Orbitron', sans-serif; font-size: clamp(40px, 10vw, 85px); background: linear-gradient(to bottom, #fff 40%, var(--rrx-red)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .aura-text { font-family: 'Orbitron', sans-serif; font-size: clamp(14px, 4vw, 22px); color: #fff; letter-spacing: 5px; text-transform: uppercase; font-weight: 700; margin-top: 15px; animation: aura-glow 3s infinite; }
        @keyframes aura-glow { 0%, 100% { opacity: 0.7; } 50% { opacity: 1; text-shadow: 0 0 20px var(--rrx-red); } }

        /* --- Discord Button (Hero) --- */
        .discord-btn {
            margin-top: 30px; padding: 12px 35px; border-radius: 50px; text-decoration: none; font-weight: 700; font-size: 0.9rem; font-family: 'Orbitron';
            text-transform: uppercase; letter-spacing: 2px; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            background: rgba(88, 101, 242, 0.1); color: var(--discord); border: 2px solid var(--discord);
        }
        .discord-btn:hover { background: var(--discord); color: white; box-shadow: 0 0 25px rgba(88, 101, 242, 0.5); transform: translateY(-5px); }

        /* --- Grid --- */
        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 35px; padding: 40px 5% 100px 5%; max-width: 1400px; margin: 0 auto; }
        .product-card { position: relative; background: var(--glass); border: 1px solid #1a1a1a; border-radius: 15px; padding: 30px 25px; text-align: center; transition: 0.4s; display: flex; flex-direction: column; justify-content: space-between; }
        .product-card:hover { border-color: var(--rrx-red); box-shadow: 0 0 30px rgba(255, 0, 0, 0.15); transform: translateY(-10px); }
        .img-box { background: #050505; height: 260px; border-radius: 12px; overflow: hidden; margin-bottom: 25px; border: 1px solid #111; display: flex; align-items: center; justify-content: center; }
        .img-box img { width: 100%; height: 100%; object-fit: contain; padding: 10px; }
        .price { font-size: 32px; color: var(--rrx-red); font-weight: bold; margin-bottom: 25px; display: block; }
        .buy-now-btn { background: var(--rrx-red); color: white; border: none; padding: 15px; font-family: 'Orbitron'; font-weight: bold; cursor: pointer; box-shadow: 0 0 15px var(--rrx-glow); transition: 0.3s; }
        .buy-now-btn:hover { box-shadow: 0 0 30px var(--rrx-red); transform: scale(1.02); }

        /* --- Payment & Success Overlays --- */
        #payment-overlay, #success-overlay {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.98); z-index: 10001; padding: 40px 5%; overflow-y: auto;
        }
        .payment-container { max-width: 500px; margin: 20px auto; background: #080808; border: 1px solid var(--rrx-red); border-radius: 20px; padding: 30px; text-align: left; box-shadow: 0 0 40px rgba(255, 0, 0, 0.2); }
        .method-box { display: flex; gap: 15px; margin: 20px 0; }
        .method { flex: 1; padding: 15px; border: 1px solid #222; border-radius: 10px; text-align: center; }
        .method.active { border-color: var(--rrx-red); background: rgba(255, 0, 0, 0.1); }
        input { width: 100%; padding: 15px; margin-bottom: 15px; background: #111; border: 1px solid #222; color: #fff; border-radius: 8px; font-size: 16px; }
        .submit-btn { width: 100%; padding: 18px; background: var(--rrx-red); border: none; color: white; font-family: 'Orbitron'; font-weight: 800; cursor: pointer; border-radius: 8px; box-shadow: 0 0 15px var(--rrx-glow); }

        /* --- Original Success Animation --- */
        .success-card { text-align: center; max-width: 500px; margin: 100px auto; animation: popIn 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        @keyframes popIn { from { transform: scale(0.5); opacity: 0; } to { transform: scale(1); opacity: 1; } }
        .check-icon { font-size: 80px; color: #00ff00; text-shadow: 0 0 20px #00ff00; margin-bottom: 20px; }

        footer { text-align: center; padding: 60px; border-top: 1px solid #1a1a1a; color: #555; font-size: 13px; }
        footer span { color: var(--rrx-red); }
    </style>
</head>
<body style="overflow: hidden;">

    <div id="welcome-overlay">
        <div class="welcome-card">
            <h2>RRX CORE</h2>
            <p>আপনার বিশ্বস্ত গেমিং মার্কেটপ্লেস, যেখানে পাবেন জনপ্রিয় গেম, ইন-গেম আইটেম এবং এক্সক্লুসিভ অফার। দ্রুত ডেলিভারি, সিকিউর লেনদেন এবং সহজ পেমেন্ট সুবিধা (বিকাশ ও নগদ) নিয়ে আমরা প্রস্তুত।</p>
            <span class="highlight">আপনার বিশ্বাস, আমাদের আমানত।</span>
            <p style="font-size: 15px; color: var(--rrx-red); letter-spacing: 3px; font-family: 'Orbitron';">YOUR AURA, YOUR RULES </p>
            <button class="continue-btn" onclick="enterSite()">Enter RRX CORE</button>
        </div>
    </div>

    <div id="payment-overlay">
        <div class="payment-container">
            <button onclick="closePayment()" style="background:none; border:none; color:#666; cursor:pointer; font-family:'Orbitron'; margin-bottom:20px;">[ BACK TO STORE ]</button>
            <h2 style="font-family:'Orbitron'; color:var(--rrx-red);">CHECKOUT</h2>
            <p id="order-info" style="color:#eee; margin: 15px 0; font-weight:bold;"></p>
            <div class="method-box">
                <div class="method active">bKash<br><small>Personal: 01779772201</small></div>
                <div class="method" style="opacity:0.4;">Nagad<br><small>COMING SOON</small></div>
            </div>
            <form onsubmit="processPayment(event)">
                <input type="text" placeholder="Your Name" required>
                <input type="text" placeholder="Player ID / Email" required>
                <input type="text" placeholder="bKash TrxID" required>
                <button type="submit" class="submit-btn">CONFIRM ORDER</button>
            </form>
            <p style="text-align:center; margin-top:15px; font-size:12px; color:#555;">যেকোনো সমস্যায় ডিসকর্ডে যোগাযোগ করুন।</p>
        </div>
    </div>

    <div id="success-overlay">
        <div class="success-card">
            <div class="check-icon">✓</div>
            <h1 style="font-family:'Orbitron'; color:#00ff00; letter-spacing:3px;">ORDER SUCCESSFUL!</h1>
            <p style="font-size:20px; color:#ccc; margin: 20px 0; line-height:1.6;">
                ধন্যবাদ! আপনার পেমেন্ট রিসিভ করা হয়েছে।<br>
                <span style="color:var(--rrx-red); font-weight:bold; font-size:24px;">২৪ ঘণ্টার মধ্যে</span><br>
                ডেলিভারি কমপ্লিট হয়ে যাবে।
            </p>
            <p style="color:#888; margin-bottom:20px;">যেকোনো প্রকার সমস্যায় আমাদের ডিসকর্ড সার্ভারে যোগাযোগ করুন।</p>
            <a href="https://discord.gg/vGKpaZdFtt" target="_blank" style="text-decoration:none; color:var(--discord); font-weight:bold; font-family:'Orbitron';">[ DISCORD SUPPORT ]</a><br>
            <button class="continue-btn" onclick="location.reload()" style="margin-top:30px;">BACK TO HOME</button>
        </div>
    </div>

    <header>
        <div class="brand-name">RRX</div>
    </header>

    <main>
        <section class="hero">
            <h1>RRX CORE</h1>
            <p class="aura-text">YOUR AURA, YOUR RULES</p>
            <a href="https://discord.gg/vGKpaZdFtt" target="_blank" class="discord-btn">Join Discord Server</a>
        </section>

        <div class="grid">
            <div class="product-card">
                <div class="img-box"><img src="mccombo.png" alt="Minecraft"></div>
                <h3 style="font-size:20px; min-height:55px;">Minecraft Java + Bedrock Combo</h3>
                <span class="price">৳ 2,000</span>
                <button class="buy-now-btn" onclick="openPayment('Minecraft Combo', '৳ 2,000')">BUY NOW</button>
            </div>
            <div class="product-card">
                <div class="img-box"><img src="gtav.png" alt="GTA V"></div>
                <h3 style="font-size:20px; min-height:55px;">GTA V Premium Edition</h3>
                <span class="price">৳ 2,100</span>
                <button class="buy-now-btn" onclick="openPayment('GTA V Premium', '৳ 2,100')">BUY NOW</button>
            </div>
            <div class="product-card">
                <div class="img-box"><img src="forza.png" alt="Forza 5"></div>
                <h3 style="font-size:20px; min-height:55px;">Forza Horizon 5 Premium</h3>
                <span class="price">৳ 3,999</span>
                <button class="buy-now-btn" onclick="openPayment('Forza Horizon 5', '৳ 3,999')">BUY NOW</button>
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
            setTimeout(() => { overlay.style.display = 'none'; document.body.style.overflow = 'auto'; }, 800);
        }
        function openPayment(name, price) {
            document.getElementById('payment-overlay').style.display = 'block';
            document.getElementById('order-info').innerText = name + " | " + price;
            document.body.style.overflow = 'hidden';
        }
        function closePayment() {
            document.getElementById('payment-overlay').style.display = 'none';
            document.body.style.overflow = 'auto';
        }
        function processPayment(e) {
            e.preventDefault();
            document.getElementById('payment-overlay').style.display = 'none';
            document.getElementById('success-overlay').style.display = 'block';
        }
    </script>
</body>
</html>
