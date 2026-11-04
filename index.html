<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
    <title>Spin Masters ShiBa V4</title>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        * { box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body {
            margin: 0;
            background: linear-gradient(150deg, #0a0e27, #2a105a, #0a0e27);
            color: white;
            text-align: center;
            padding: 15px;
            min-height: 100vh;
        }
        header {
            font-size: 24px;
            font-weight: 900;
            color: #ffcf35;
            margin: 10px 0 20px;
            text-shadow: 0 2px 4px rgba(0,0,0,0.5);
            letter-spacing: 1px;
        }
        .card {
            background: rgba(23, 28, 66, 0.9);
            border: 1px solid #7653cb;
            border-radius: 20px;
            padding: 20px;
            margin: 15px auto;
            max-width: 440px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.4);
        }
        .stats { display: flex; justify-content: space-around; gap: 10px; }
        .stat {
            background: #292653;
            padding: 15px 10px;
            border-radius: 15px;
            flex: 1;
            box-shadow: inset 0 2px 5px rgba(0,0,0,0.3);
        }
        .stat b { display: block; font-size: 18px; margin-top: 5px; color: #ffcf35; }
        
        /* تنسيق عجلة الحظ */
        .wheel-container { position: relative; width: 260px; height: 260px; margin: 20px auto; }
        .pointer {
            position: absolute; top: -15px; left: 50%; transform: translateX(-50%);
            width: 0; height: 0;
            border-left: 15px solid transparent; border-right: 15px solid transparent;
            border-top: 30px solid #ff4b85;
            z-index: 10;
            filter: drop-shadow(0 4px 2px rgba(0,0,0,0.5));
        }
        .wheel {
            width: 100%; height: 100%;
            border-radius: 50%;
            border: 9px solid #ffd34e;
            background: conic-gradient(
                #ffcf36 0 45deg, #a52cff 45deg 90deg,
                #23c9a2 90deg 135deg, #ff4b85 135deg 180deg,
                #ffcf36 180deg 225deg, #a52cff 225deg 270deg,
                #23c9a2 270deg 315deg, #ff4b85 315deg 360deg
            );
            box-shadow: 0 0 30px #a64bff, inset 0 0 20px rgba(0,0,0,0.5);
            display: flex; align-items: center; justify-content: center;
            font-size: 55px;
            transition: transform 4s cubic-bezier(0.15, 0.7, 0.1, 1);
        }
        
        button {
            border: 0; border-radius: 14px; padding: 16px;
            margin: 6px 0; background: linear-gradient(90deg, #ffbd22, #ff7a00);
            color: #241039; font-size: 18px; font-weight: 900;
            width: 100%; cursor: pointer;
            box-shadow: 0 5px 0 #b35c00, 0 8px 15px rgba(0,0,0,0.3);
            transition: transform 0.1s;
        }
        button:active { transform: translateY(3px); box-shadow: 0 2px 0 #b35c00; }
        button:disabled { opacity: 0.6; transform: translateY(3px); box-shadow: 0 2px 0 #b35c00; }
        
        .small { background: linear-gradient(90deg, #5a4b8c, #3b2e66); color: white; box-shadow: 0 5px 0 #1e1442; }
        .small:active { box-shadow: 0 2px 0 #1e1442; }
        
        #message { color: #ffdc5b; font-size: 18px; min-height: 25px; font-weight: bold; margin: 10px 0; }
    </style>
</head>
<body>
    <header>👑 SPIN MASTERS SHIBA V4</header>

    <div class="card">
        <div style="font-size: 60px; margin-bottom: 10px;">🐕</div>
        <h2>مرحباً بك في عالم Shiba</h2>
        <div class="stats">
            <div class="stat">🪙 العملات<br><b id="coins">1000</b></div>
            <div class="stat">💎 الجواهر<br><b id="gems">50</b></div>
            <div class="stat">⭐ المستوى<br><b id="level">1</b></div>
        </div>
    </div>

    <div class="card">
        <h2>🎡 عجلة الحظ</h2>
        <div class="wheel-container">
            <div class="pointer"></div>
            <div class="wheel" id="wheel">🐾</div>
        </div>
        <div id="message">هل أنت مستعد للفوز؟</div>
        <button id="spin" onclick="spin()">🎯 ابدأ الدوران (10 عملات)</button>
    </div>

    <div class="card">
        <h2>🎁 صندوق الكنوز</h2>
        <div style="font-size:55px">💎🎁💰</div>
        <button class="small" onclick="openBox()">افتح صندوقاً (100 عملة)</button>
    </div>

    <div class="card">
        <h2>🏆 حساب اللاعب</h2>
        <p>النقاط: <b id="points">0</b></p>
        <button class="small" onclick="showProfile()">ملفي الشخصي</button>
        <button class="small" onclick="resetGame()">إعادة ضبط التجربة</button>
    </div>

    <script>
        const tg = window.Telegram?.WebApp;
        if (tg) { tg.ready(); tg.expand(); }

        let coins = Number(localStorage.coins ?? 1000);
        let gems = Number(localStorage.gems ?? 50);
        let points = Number(localStorage.points ?? 0);
        let busy = false;

        const rewards = [
            {name:"100 عملة", coins:100},
            {name:"50 عملة", coins:50},
            {name:"10 جواهر", gems:10},
            {name:"200 عملة", coins:200},
            {name:"5 جواهر", gems:5},
            {name:"75 عملة", coins:75},
            {name:"300 عملة", coins:300},
            {name:"20 جواهر", gems:20}
        ];

        function save() {
            localStorage.coins = coins;
            localStorage.gems = gems;
            localStorage.points = points;
            render();
        }

        function render() {
            document.getElementById("coins").textContent = coins;
            document.getElementById("gems").textContent = gems;
            document.getElementById("points").textContent = points;
            document.getElementById("level").textContent = 1 + Math.floor(points / 500);
        }

        function spin() {
            if (busy) return;
            if (coins < 10) { message("ليس لديك عملات كافية!"); return; }
            
            busy = true;
            coins -= 10;
            const i = Math.floor(Math.random() * rewards.length);
            const r = rewards[i];
            const wheel = document.getElementById("wheel");
            
            // دوران العجلة
            const totalRotation = 1800 + (i * 45); // 5 لفات + الزاوية المطلوبة
            wheel.style.transform = `rotate(${totalRotation}deg)`;
            
            document.getElementById("spin").disabled = true;
            save();
            
            setTimeout(() => {
                coins += r.coins || 0;
                gems += r.gems || 0;
                points += 25;
                message("🎉 ربحت " + r.name);
                save();
                busy = false;
                document.getElementById("spin").disabled = false;
            }, 4100);
        }

        function openBox() {
            if (coins < 100) { message("تحتاج إلى 100 عملة!"); return; }
            coins -= 100;
            const prize = 50 + Math.floor(Math.random() * 251);
            coins += prize;
            points += 20;
            message("🎁 حصلت على " + prize + " عملة!");
            save();
        }

        function message(t) { document.getElementById("message").textContent = t; }
        
        function showProfile() {
            message("⭐ مستواك: " + (1 + Math.floor(points / 500)) + " | نقاطك: " + points);
        }
        
        function resetGame() {
            coins = 1000; gems = 50; points = 0; save();
            message("تمت إعادة التجربة");
        }

        render();
    </script>
</body>
</html>
