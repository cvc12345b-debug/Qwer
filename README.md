# Qwer
Qwer
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>درصدگیر دیپ سیک</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #2563eb;
            --secondary: #1e40af;
            --accent: #60a5fa;
            --correct: #10b981;
            --wrong: #ef4444;
            --unanswered: #6b7280;
            --neutral: #f8fafc;
        }
        
        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            line-height: 1.6;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(10px);
        }
        
        .header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .logo {
            font-size: 2.5rem;
            font-weight: bold;
            background: linear-gradient(45deg, #2563eb, #7c3aed);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
        }
        
        .subtitle {
            color: #6b7280;
            font-size: 1.1rem;
        }
        
        .test-image {
            width: 100%;
            max-width: 400px;
            height: 200px;
            background: linear-gradient(45deg, #2563eb, #7c3aed);
            border-radius: 15px;
            margin: 20px auto;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }
        
        .input-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .input-group {
            display: flex;
            flex-direction: column;
        }
        
        .input-group label {
            margin-bottom: 8px;
            font-weight: 600;
            color: #374151;
        }
        
        .input-group input {
            padding: 12px 15px;
            border: 2px solid #e5e7eb;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s;
        }
        
        .input-group input:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 15px;
            margin-bottom: 30px;
        }
        
        .stat-card {
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            color: white;
            font-weight: bold;
            transition: transform 0.3s;
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
        }
        
        .total { background: white; color: #333; border: 2px solid #e5e7eb; }
        .correct { background: var(--correct); }
        .unanswered { background: var(--unanswered); }
        .wrong { background: var(--wrong); }
        
        .stat-number {
            font-size: 2rem;
            margin-bottom: 5px;
        }
        
        .stat-label {
            font-size: 0.9rem;
            opacity: 0.9;
        }
        
        .calculate-btn {
            width: 100%;
            padding: 15px;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            border-radius: 12px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            margin-bottom: 20px;
        }
        
        .calculate-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(37, 99, 235, 0.3);
        }
        
        .result-section {
            display: none;
            text-align: center;
            padding: 30px;
            border-radius: 15px;
            margin-top: 20px;
            animation: fadeIn 0.5s ease;
        }
        
        .result-percentage {
            font-size: 4rem;
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        .result-message {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 20px;
        }
        
        .success { background: linear-gradient(135deg, #10b981, #059669); color: white; }
        .warning { background: linear-gradient(135deg, #f59e0b, #d97706); color: white; }
        .danger { background: linear-gradient(135deg, #ef4444, #dc2626); color: white; }
        
        .contact {
            text-align: center;
            margin-top: 30px;
            padding: 20px;
            background: #f8fafc;
            border-radius: 12px;
        }
        
        .contact a {
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes celebrate {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        .celebrate {
            animation: celebrate 0.5s ease infinite;
        }
        
        @media (max-width: 768px) {
            .input-section, .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .logo {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="logo">درصدگیر دیپ سیک</div>
            <div class="subtitle">محاسبه دقیق درصد آزمون‌های شما</div>
        </div>
        
        <div class="test-image">
            <i class="fas fa-edit"></i>
        </div>
        
        <div class="input-section">
            <div class="input-group">
                <label for="totalQuestions">تعداد کل سوالات</label>
                <input type="number" id="totalQuestions" placeholder="مثلاً: 100" min="1">
            </div>
            <div class="input-group">
                <label for="correctAnswers">تعداد سوالات درست</label>
                <input type="number" id="correctAnswers" placeholder="مثلاً: 75" min="0">
            </div>
            <div class="input-group">
                <label for="wrongAnswers">تعداد سوالات غلط</label>
                <input type="number" id="wrongAnswers" placeholder="مثلاً: 15" min="0">
            </div>
            <div class="input-group">
                <label for="unanswered">تعداد سوالات نزده</label>
                <input type="number" id="unanswered" placeholder="مثلاً: 10" min="0">
            </div>
        </div>
        
        <div class="stats-grid">
            <div class="stat-card total">
                <div class="stat-number" id="totalDisplay">0</div>
                <div class="stat-label">کل سوالات</div>
            </div>
            <div class="stat-card correct">
                <div class="stat-number" id="correctDisplay">0</div>
                <div class="stat-label">سوالات درست</div>
            </div>
            <div class="stat-card unanswered">
                <div class="stat-number" id="unansweredDisplay">0</div>
                <div class="stat-label">سوالات نزده</div>
            </div>
            <div class="stat-card wrong">
                <div class="stat-number" id="wrongDisplay">0</div>
                <div class="stat-label">سوالات غلط</div>
            </div>
        </div>
        
        <button class="calculate-btn" onclick="calculatePercentage()">
            <i class="fas fa-calculator"></i>
            محاسبه درصد
        </button>
        
        <div id="resultSection" class="result-section">
            <div class="result-percentage" id="percentage">0%</div>
            <div class="result-message" id="message">نتیجه آزمون شما</div>
        </div>
        
        <div class="contact">
            <p>برای ارتباط با ما:</p>
            <a href="https://t.me/Amir0qw" target="_blank">
                <i class="fab fa-telegram"></i>
                @Amir0qw
            </a>
        </div>
    </div>

    <script>
        // آپدیت خودکار آمار
        document.getElementById('totalQuestions').addEventListener('input', updateStats);
        document.getElementById('correctAnswers').addEventListener('input', updateStats);
        document.getElementById('wrongAnswers').addEventListener('input', updateStats);
        document.getElementById('unanswered').addEventListener('input', updateStats);
        
        function updateStats() {
            const total = parseInt(document.getElementById('totalQuestions').value) || 0;
            const correct = parseInt(document.getElementById('correctAnswers').value) || 0;
            const wrong = parseInt(document.getElementById('wrongAnswers').value) || 0;
            const unanswered = parseInt(document.getElementById('unanswered').value) || 0;
            
            document.getElementById('totalDisplay').textContent = total;
            document.getElementById('correctDisplay').textContent = correct;
            document.getElementById('wrongDisplay').textContent = wrong;
            document.getElementById('unansweredDisplay').textContent = unanswered;
        }
        
        function calculatePercentage() {
            const total = parseInt(document.getElementById('totalQuestions').value) || 0;
            const correct = parseInt(document.getElementById('correctAnswers').value) || 0;
            const wrong = parseInt(document.getElementById('wrongAnswers').value) || 0;
            const unanswered = parseInt(document.getElementById('unanswered').value) || 0;
            
            // اعتبارسنجی
            if (total === 0) {
                alert('لطفاً تعداد کل سوالات را وارد کنید');
                return;
            }
            
            if (correct + wrong + unanswered !== total) {
                alert('جمع سوالات درست، غلط و نزده باید برابر با کل سوالات باشد');
                return;
            }
            
            // محاسبه درصد
            const percentage = (correct / total) * 100;
            const roundedPercentage = Math.round(percentage * 100) / 100;
            
            // نمایش نتیجه
            const resultSection = document.getElementById('resultSection');
            const percentageElement = document.getElementById('percentage');
            const messageElement = document.getElementById('message');
            
            percentageElement.textContent = roundedPercentage + '%';
            
            // تعیین پیام و رنگ بر اساس درصد
            if (percentage >= 80) {
                resultSection.className = 'result-section success';
                messageElement.textContent = 'صدآفرین پسرم! 🎉';
                resultSection.classList.add('celebrate');
            } else if (percentage >= 20) {
                resultSection.className = 'result-section warning';
                messageElement.textContent = 'آفرین! بهتر میشی 💪';
                resultSection.classList.remove('celebrate');
            } else {
                resultSection.className = 'result-section danger';
                messageElement.textContent = 'نیاز به تلاش بیشتر 📚';
                resultSection.classList.remove('celebrate');
            }
            
            resultSection.style.display = 'block';
            resultSection.scrollIntoView({ behavior: 'smooth' });
        }
        
        // مقداردهی اولیه
        updateStats();
    </script>
</body>
</html>
