
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>انتهاء الامتياز</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            text-align: center;
            background: linear-gradient(to bottom, #a8d5f2, #fef7e8);
            color: #333;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }
        #countdown {
            font-size: 2rem;
            font-weight: bold;
            color: #555;
            margin-bottom: 20px;
        }
        .footer {
            font-size: 1.8rem;
            font-weight: bold;
            color: #333;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>انتهاء الامتياز</h1>
    <div id="countdown">جاري التحميل...</div>
    <div class="footer">سبحان الله</div>

    <script>
        // تاريخ النهاية
        const endDate = new Date('May 2, 2025 00:00:00').getTime();

        // تحديث العد التنازلي كل ثانية
        const countdownInterval = setInterval(() => {
            const now = new Date().getTime();
            const timeLeft = endDate - now;

            // حساب الأيام والساعات والدقائق والثواني
            const days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);

            // عرض الوقت المتبقي
            document.getElementById("countdown").innerHTML = 
                `${days} يوم ${hours} ساعة ${minutes} دقيقة ${seconds} ثانية`;

            // إذا انتهى العد التنازلي
            if (timeLeft < 0) {
                clearInterval(countdownInterval);
                document.getElementById("countdown").innerHTML = "انتهت الفترة!";
            }
        }, 1000);
    </script>
</body>
</html>
