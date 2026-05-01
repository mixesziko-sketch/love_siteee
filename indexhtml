<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>رسالة حب</title>
    <style>
        * { box-sizing: border-box; }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #1f1c2c 0%, #928dab 100%);
            color: #fff;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }
        .container {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            padding: 30px;
            width: 90%;
            max-width: 450px;
            text-align: center;
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
            border: 1px solid rgba(255, 255, 255, 0.18);
        }
        
        /* شاشة كلمة المرور */
        #password-screen {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 70vh;
        }
        input[type="password"] {
            padding: 12px;
            border-radius: 25px;
            border: none;
            text-align: center;
            font-size: 1.1rem;
            margin: 15px 0;
            width: 80%;
            outline: none;
            background: rgba(255, 255, 255, 0.8);
        }
        button {
            background: #ff3366;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 25px;
            font-size: 1.1rem;
            cursor: pointer;
            font-weight: bold;
            transition: 0.3s;
        }
        button:hover { background: #ff1a55; }
        
        /* شاشة المحتوى الرئيسي */
        #main-content { display: none; }
        .timer-box {
            background: rgba(255, 255, 255, 0.15);
            padding: 15px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .timer-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            margin-top: 10px;
        }
        .timer-item {
            background: rgba(0, 0, 0, 0.2);
            padding: 8px;
            border-radius: 8px;
            font-size: 0.9rem;
        }
        .timer-item span { display: block; font-weight: bold; font-size: 1.2rem; color: #ff6699; }
        
        .card-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-top: 20px;
        }
        .card {
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            cursor: pointer;
            transition: 0.3s;
            min-height: 80px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        .card:hover {
            background: rgba(255, 255, 255, 0.2);
        }
        .hidden-text {
            display: none;
            font-size: 0.9rem;
            color: #ff99bb;
            margin-top: 10px;
            font-weight: bold;
        }
        .message-box {
            margin-top: 20px;
            background: rgba(255, 51, 102, 0.3);
            padding: 15px;
            border-radius: 10px;
            line-height: 1.6;
        }
    </style>
</head>
<body>

    <div class="container" id="password-screen">
        <h2>🔐 أدخل كلمة المرور</h2>
        <p>الباسورد هو: <code>love</code></p>
        <input type="password" id="pass-input" placeholder="اكتب كلمة المرور هنا...">
        <button onclick="checkPassword()">دخول</button>
    </div>

    <div class="container" id="main-content">
        <h1>إلى سارة ❤️</h1>
        <p>أجمل صدفة في حياتي، كل ثانية تمر وأنا معك هي عمر كامل.</p>
        
        <div class="timer-box">
            <p>الوقت الذي قضيناه معاً:</p>
            <div class="timer-grid">
                <div class="timer-item"><span id="years">0</span> سنة</div>
                <div class="timer-item"><span id="months">0</span> شهر</div>
                <div class="timer-item"><span id="days">0</span> يوم</div>
                <div class="timer-item"><span id="hours">0</span> ساعة</div>
                <div class="timer-item"><span id="minutes">0</span> دقيقة</div>
                <div class="timer-item"><span id="seconds">0</span> ثانية</div>
            </div>
        </div>

        <p>اضغطي على الكروت 🌸</p>
        <div class="card-grid">
            <div class="card" onclick="revealText(0, 'text-0')">
                <span>الكارت الأول</span>
                <div class="hidden-text" id="text-0">بحبك جداً</div>
            </div>
            <div class="card" onclick="revealText(1, 'text-1')">
                <span>الكارت الثاني</span>
                <div class="hidden-text" id="text-1">أنتِ الأمان</div>
            </div>
            <div class="card" onclick="revealText(2, 'text-2')">
                <span>الكارت الثالث</span>
                <div class="hidden-text" id="text-2">ضحكتك تسوى الدنيا</div>
            </div>
            <div class="card" onclick="revealText(3, 'text-3')">
                <span>الكارت الرابع</span>
                <div class="hidden-text" id="text-3">عمري كله لكِ</div>
            </div>
        </div>

        <div class="message-box">
            <p><strong>رسالة من القلب:</strong></p>
            <p>ربنا يخليكي ليا ومايحرمنيش منك أبداً يا روح قلبي، ويارب العمر كله مع بعض ❤️</p>
        </div>
        
    </div>

    <script>
        // التحقق من الباسورد
        function checkPassword() {
            const input = document.getElementById('pass-input').value;
            if (input.toLowerCase() === 'love') {
                document.getElementById('password-screen').style.display = 'none';
                document.getElementById('main-content').style.display = 'block';
                startTimer();
            } else {
                alert('كلمة المرور غير صحيحة، جربي مرة أخرى!');
            }
        }

        // إظهار وإخفاء النصوص داخل الكروت
        function revealText(id) {
            const textElem = document.getElementById('text-' + id);
            if (textElem.style.display === 'block') {
                textElem.style.display = 'none';
            } else {
                textElem.style.display = 'block';
            }
        }

        // عداد الوقت
        function startTimer() {
            // يمكنك تغيير التاريخ بالأسفل ليطابق تاريخ بداية معرفتكم (سنة - شهر - يوم)
            const startDate = new Date('2021-04-04T00:00:00'); 
            setInterval(() => {
                const now = new Date();
                const diff = now - startDate;
                
                const seconds = Math.floor(diff / 1000) % 60;
                const minutes = Math.floor(diff / 1000 / 60) % 60;
                const hours = Math.floor(diff / 1000 / 60 / 60) % 24;
                const days = Math.floor(diff / 1000 / 60 / 60 / 24) % 30;
                const months = Math.floor(diff / 1000 / 60 / 60 / 24 / 30) % 12;
                const years = Math.floor(diff / 1000 / 60 / 60 / 24 / 365);
                
                document.getElementById('years').innerText = years;
                document.getElementById('months').innerText = months;
                document.getElementById('days').innerText = days;
                document.getElementById('hours').innerText = hours;
                document.getElementById('minutes').innerText = minutes;
                document.getElementById('seconds').innerText = seconds;
            }, 1000);
        }
    </script>
</body>
</html>
