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
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
        body { background-color: var(--bg-pure); color: #ffffff; overflow: hidden; } /* Initially hidden scroll */

        /* --- Welcome Overlay --- */
        #welcome-overlay {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(15px);
            z-index: 9999;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: 0.8s ease;
        }

        .welcome-card {
            max-width: 500px;
            width: 90%;
            background: rgba(20, 20, 20, 0.9);
            border: 2px solid var(--rrx-red);
            border-radius: 20px;
            padding: 40px 30px;
            text-align: center;
            box-shadow: 0 0 50px var(--rrx-glow);
            animation: card-entry 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        @keyframes card-entry {
            from { transform: scale(0.7); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        .welcome-card h2 { font-family: 'Orbitron', sans-serif; color: var(--rrx-red); margin-bottom: 20px; letter-spacing: 3px; }
        .welcome-card p { font-size: 18px; line-height: 1.6; color: #ddd; margin-bottom: 25px; }
        .welcome-card .highlight { color: var(--rrx-red); font-weight: bold; font-size: 20px; display: block; margin-top: 15px; }

        /* --- Continue Button --- */
        .continue-btn {
            background: var(--rrx-red);
            color: white;
            border: none;
            padding: 15px 40px;
            font-family: 'Orbitron', sans-serif;
            font-weight: bold;
            text-transform: uppercase;
            cursor: pointer;
            border-radius: 5px;
            box-shadow: 0 0 20px var(--rrx-glow);
            transition: 0.3s;
        }

        .continue-btn:hover { transform: scale(1.1); box-shadow: 0 0 30px var(--rrx-red); }

        /* --- Main Page Styles --- */
        header {
            padding: 20px; text-align: center; background: #000; border-bottom: 2px solid var(--rrx-red);
        }
        .brand-name { font-family: 'Orbitron', sans-serif; font-size: 35px; color: var(--rrx-red); letter-spacing: 8px; }
        
        .hero { height: 60vh; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; }
        .hero h1 { font-family: 'Orbitron', sans-serif; font-size: 60px; color: #fff; text-shadow: 0 0 20px var(--rrx-red); }
        .aura-text { font-family: 'Orbitron', sans-serif; letter-spacing: 5px; color: var(--rrx-red); margin-top: 10px; animation: glow 2s infinite; }
        
        @keyframes glow { 0%, 100% { opacity: 0.6; } 50% { opacity: 1; text-shadow: 0 0 10px var(--rrx-red); } }

        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; padding: 50px 5%; }
        .card { background: #0a0a0a; border: 1px solid #222; padding: 25px; text-align: center; border-radius: 10px; transition: 0.3s; }
        .card:hover { border-color: var(--rrx-red); transform: translateY(-5px); }
        .price { color: var(--rrx-red); font-size: 24px; font-weight: bold; margin: 15px 0; }

        footer { text-align: center; padding: 40px; border-top: 1px solid #222; color: #444; font-size: 12px; }
    </style>
</head>
<body>

    <div id="welcome-overlay">
        <div class="welcome-card">
            <h2>RRX STUDIOS</h2>
            <p>
                আপনার বিশ্বস্ত গেমিং মার্কেটপ্লেস, যেখানে পাবেন জনপ্রিয় গেম, ইন-গেম আইটেম এবং এক্সক্লুসিভ অফার। দ্রুত ডেলিভারি, সিকিউর লেনদেন এবং সহজ পেমেন্ট সুবিধা (বিকাশ ও নগদ) নিয়ে আমরা প্রস্তুত।
            </p>
            <span class="highlight">আপনার বিশ্বাস, আমাদের আমানত।</span>
            <p style="font-size: 14px; margin-top: 10px; color: var(--rrx-red);">YOUR AURA, YOUR RULES 🎮🔥</p>
            
            <button class="continue-btn" onclick="enterSite()">Continue to Store</button>
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
            <div class="card">
                <div style="height:150px; background:#111; display:flex; align-items:center; justify-content:center; color:#333; font-size:40px; border-radius:10px;">RRX-01</div>
                <h3>SHADOW MOUSE</h3>
                <div class="price">৳ 2,500</div>
                <button class="continue-btn" style="padding:10px 20px; font-size:12px;">Order Now</button>
            </div>
            <div class="card">
                <div style="height:150px; background:#111; display:flex; align-items:center; justify-content:center; color:#333; font-size:40px; border-radius:10px;">RRX-02</div>
                <h3>IGNITE KEYBOARD</h3>
                <div class="price">৳ 4,800</div>
                <button class="continue-btn" style="padding:10px 20px; font-size:12px;">Order Now</button>
            </div>
            <div class="card">
                <div style="height:150px; background:#111; display:flex; align-items:center; justify-content:center; color:#333; font-size:40px; border-radius:10px;">RRX-03</div>
                <h3>VOID HEADSET</h3>
                <div class="price">৳ 3,500</div>
                <button class="continue-btn" style="padding:10px 20px; font-size:12px;">Order Now</button>
            </div>
        </div>
    </main>

    <footer>
        <p>&copy; 2026 RRX BRAND | POWERED BY RRX STUDIOS</p>
    </footer>

    <script>
        function enterSite() {
            const overlay = document.getElementById('welcome-overlay');
            overlay.style.opacity = '0';
            overlay.style.visibility = 'hidden';
            document.body.style.overflow = 'auto'; // Re-enable scrolling
        }
    </script>

</body>
</html>
