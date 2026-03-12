<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Melli's Birthday Vault</title>
    <style>
        :root {
            --gold: #d4af37;
            --pink: #ff69b4;
            --dark-blue: #0b1a2d;
        }
        body {
            margin: 0;
            background-color: #050a12;
            color: white;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            display: flex;
            justify-content: center;
            padding: 20px;
        }
        .container {
            width: 100%;
            max-width: 500px;
            background: linear-gradient(rgba(11, 26, 45, 0.9), rgba(11, 26, 45, 0.9)), url('https://clapperapp.com/BigBootyMelli') center/cover;
            border: 2px solid var(--gold);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 0 25px rgba(212, 175, 55, 0.3);
        }
        .header {
            padding: 20px;
            text-align: center;
            background: rgba(212, 175, 55, 0.1);
            border-bottom: 1px solid var(--gold);
        }
        .header h1 { color: var(--gold); margin: 0; font-size: 1.5rem; text-transform: uppercase; letter-spacing: 2px; }
        .header p { color: var(--pink); margin: 5px 0 0; font-weight: bold; font-style: italic; }

        .menu-items { padding: 20px; }
        .item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }
        .item-label { font-size: 1.1rem; }
        .item-price { font-size: 0.8rem; color: var(--gold); display: block; }
        
        .qty-controls { display: flex; align-items: center; gap: 12px; }
        .btn-qty {
            background: var(--gold);
            border: none;
            width: 30px;
            height: 30px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            font-size: 1.2rem;
        }
        .qty-num { width: 20px; text-align: center; font-weight: bold; }

        .summary {
            background: rgba(0,0,0,0.4);
            padding: 20px;
            text-align: center;
        }
        .total-box { font-size: 1.8rem; color: var(--gold); margin-bottom: 15px; font-weight: bold; }
        
        .action-btn {
            display: block;
            background: linear-gradient(45deg, var(--gold), #f9e29c);
            color: #000;
            text-decoration: none;
            padding: 15px;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.1rem;
            margin-bottom: 10px;
            transition: 0.3s;
        }
        .wish-btn {
            display: block;
            color: var(--pink);
            text-decoration: none;
            font-size: 0.9rem;
            margin-top: 10px;
        }
        .action-btn:hover { transform: scale(1.03); box-shadow: 0 0 15px var(--gold); }
    </style>
</head>
<body>

<div class="container">
    <div class="header">
        <h1>Melli's Vault 🎂</h1>
        <p>Night Off Birthday Specials</p>
    </div>

    <div class="menu-items">
        <div class="item">
            <div>
                <span class="item-label">Tits & Ass Pix 🍑</span>
                <span class="item-price">$3 each | 2 for $5</span>
            </div>
            <div class="qty-controls">
                <button class="btn-qty" onclick="changeQty(0, -1)">-</button>
                <span id="q0" class="qty-num">0</span>
                <button class="btn-qty" onclick="changeQty(0, 1)">+</button>
            </div>
        </div>

        <div class="item">
            <div>
                <span class="item-label">Pretty Kitty Pix 🐱</span>
                <span class="item-price">$4 each | 2 for $7</span>
            </div>
            <div class="qty-controls">
                <button class="btn-qty" onclick="changeQty(1, -1)">-</button>
                <span id="q1" class="qty-num">0</span>
                <button class="btn-qty" onclick="changeQty(1, 1)">+</button>
            </div>
        </div>

        <div class="item">
            <div>
                <span class="item-label">Short Clips 🎬</span>
                <span class="item-price">$8 each | 2 for $15</span>
            </div>
            <div class="qty-controls">
                <button class="btn-qty" onclick="changeQty(2, -1)">-</button>
                <span id="q2" class="qty-num">0</span>
                <button class="btn-qty" onclick="changeQty(2, 1)">+</button>
            </div>
        </div>

        <div class="item">
            <div>
                <span class="item-label">Long Videos 🎞️</span>
                <span class="item-price">$10 each</span>
            </div>
            <div class="qty-controls">
                <button class="btn-qty" onclick="changeQty(3, -1)">-</button>
                <span id="q3" class="qty-num">0</span>
                <button class="btn-qty" onclick="changeQty(3, 1)">+</button>
            </div>
        </div>
    </div>

    <div class="summary">
        <div class="total-box">Subtotal: $<span id="total">0.00</span></div>
        <a href="https://clapperapp.com/BigBootyMelli?is_invite=1&r=DJq9RRQkJa&c=in&m=co" target="_blank" class="action-btn">DM ME TO ORDER 💋</a>
        <a href="https://www.amazon.com/hz/wishlist/ls/163RAYPV2I5KY?ref_=wl_share" target="_blank" class="wish-btn">🎁 Spoil me on Amazon</a>
    </div>
</div>

<script>
    let qtys = [0, 0, 0, 0];

    function changeQty(idx, delta) {
        qtys[idx] = Math.max(0, qtys[idx] + delta);
        document.getElementById('q' + idx).innerText = qtys[idx];
        updateTotal();
    }

    function updateTotal() {
        let t = 0;
        t += Math.floor(qtys[0] / 2) * 5 + (qtys[0] % 2) * 3;
        t += Math.floor(qtys[1] / 2) * 7 + (qtys[1] % 2) * 4;
        t += Math.floor(qtys[2] / 2) * 15 + (qtys[2] % 2) * 8;
        t += qtys[3] * 10;
        document.getElementById('total').innerText = t.toFixed(2);
    }
</script>

</body>
</html>
