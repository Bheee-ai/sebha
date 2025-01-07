# sebha
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>صدقة جارية للمرحوم الحبيب محمد احمد حامد زياده</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            background-image: url('background.jpg'); /* استبدل بـ اسم صورتك */
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: #fff;
            text-align: center;
        }

        .content {
            padding: 20px;
        }

        h1 {
            margin-top: 50px;
            font-size: 36px;
        }

        .tasbeeh-counter {
            background: rgba(0, 0, 0, 0.7);
            padding: 20px;
            border-radius: 10px;
            margin: 20px auto;
            width: 80%;
            max-width: 600px;
        }

        .tasbeeh-counter button {
            margin: 5px;
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .footer {
            margin-top: 50px;
            font-size: 14px;
            color: #ccc;
        }
    </style>
</head>
<body>
    <!-- تشغيل الصوت -->
    <audio id="background-audio" autoplay loop muted>
        <source src="dua.mp3" type="audio/mp3">
        متصفحك لا يدعم الصوت.
    </audio>

    <script>
        // إزالة الكتم وتشغيل الصوت بعد أول تفاعل مع الصفحة
        window.addEventListener('click', function () {
            const audio = document.getElementById('background-audio');
            audio.muted = false; // إلغاء الكتم
            audio.play(); // تشغيل الصوت
        });
    </script>

    <!-- محتوى الموقع -->
    <div class="content">
        <h1>صدقة جارية على روح المرحوم الحبيب محمد احمد حامد زياده</h1>

        <div class="tasbeeh-counter">
            <h2>عداد التسبيح</h2>
            
            <!-- تسبيحة سبحان الله -->
            <p>سبحان الله</p>
            <button onclick="incrementCounter('سبحان الله')">زيادة</button>
            <p>العدد: <span id="counter-subhan">0</span></p>

            <!-- تسبيحة الحمد لله -->
            <p>الحمد لله</p>
            <button onclick="incrementCounter('الحمد لله')">زيادة</button>
            <p>العدد: <span id="counter-alhamd">0</span></p>

            <!-- تسبيحة لا إله إلا الله -->
            <p>لا إله إلا الله</p>
            <button onclick="incrementCounter('لا إله إلا الله')">زيادة</button>
            <p>العدد: <span id="counter-la-ilaha">0</span></p>

            <!-- تسبيحة الله أكبر -->
            <p>الله أكبر</p>
            <button onclick="incrementCounter('الله أكبر')">زيادة</button>
            <p>العدد: <span id="counter-allah-akbar">0</span></p>

            <button onclick="resetCounters()">تصفير العداد</button>
        </div>

        <div class="footer">
            <p>صمم الموقع بواسطة محبك في الله: باسم حمادة</p>
        </div>
    </div>

    <script>
        // العدادات لكل ذكر
        let counters = {
            'سبحان الله': 0,
            'الحمد لله': 0,
            'لا إله إلا الله': 0,
            'الله أكبر': 0
        };

        function incrementCounter(dhikr) {
            // زيادة العداد إذا لم يصل إلى 33
            if (counters[dhikr] < 33) {
                counters[dhikr]++;
                document.getElementById('counter-' + dhikr.replace(' ', '-').toLowerCase()).innerText = counters[dhikr];
            }
        }

        function resetCounters() {
            // تصفير جميع العدادات
            counters = {
                'سبحان الله': 0,
                'الحمد لله': 0,
                'لا إله إلا الله': 0,
                'الله أكبر': 0
            };
            document.getElementById('counter-subhan').innerText = counters['سبحان الله'];
            document.getElementById('counter-alhamd').innerText = counters['الحمد لله'];
            document.getElementById('counter-la-ilaha').innerText = counters['لا إله إلا الله'];
            document.getElementById('counter-allah-akbar').innerText = counters['الله أكبر'];
        }
    </script>
</body>
</html>
