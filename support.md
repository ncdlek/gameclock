<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game Clock Pro Support</title>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            line-height: 1.6;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            color: #333;
        }
        h1, h2 {
            color: #2c3e50;
        }
        .section {
            margin-bottom: 30px;
        }
        .question {
            margin-bottom: 20px;
        }
        .contact {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 8px;
            margin-top: 40px;
        }
        .language-selector {
            position: sticky;
            top: 0;
            background: white;
            padding: 10px 0;
            border-bottom: 1px solid #eee;
            margin-bottom: 20px;
        }
        .language-selector button {
            padding: 5px 10px;
            margin: 0 5px;
            border: 1px solid #ddd;
            border-radius: 4px;
            background: white;
            cursor: pointer;
        }
        .language-selector button.active {
            background: #2c3e50;
            color: white;
        }
        [lang] {
            display: none;
        }
        [lang].active {
            display: block;
        }
    </style>
</head>
<body>
    <div class="language-selector">
        <button onclick="setLanguage('en')" data-lang="en">English</button>
        <button onclick="setLanguage('zh')" data-lang="zh">中文</button>
        <button onclick="setLanguage('ja')" data-lang="ja">日本語</button>
        <button onclick="setLanguage('ko')" data-lang="ko">한국어</button>
        <button onclick="setLanguage('ru')" data-lang="ru">Русский</button>
        <button onclick="setLanguage('tr')" data-lang="tr">Türkçe</button>
    </div>

    <!-- English Content -->
    <div lang="en" class="active">
        <h1>Game Clock Pro Support</h1>
        <!-- English content here -->
    </div>

    <!-- Chinese Content -->
    <div lang="zh">
        <h1>Game Clock Pro 支持</h1>
        <!-- Chinese content here -->
    </div>

    <!-- Japanese Content -->
    <div lang="ja">
        <h1>Game Clock Pro サポート</h1>
        <!-- Japanese content here -->
    </div>

    <!-- Korean Content -->
    <div lang="ko">
        <h1>Game Clock Pro 지원</h1>
        <!-- Korean content here -->
    </div>

    <!-- Russian Content -->
    <div lang="ru">
        <h1>Поддержка Game Clock Pro</h1>
        <!-- Russian content here -->
    </div>

    <!-- Turkish Content -->
    <div lang="tr">
        <h1>Game Clock Pro Destek</h1>
        <!-- Turkish content here -->
    </div>

    <script>
        function setLanguage(lang) {
            // Hide all language sections
            document.querySelectorAll('[lang]').forEach(el => {
                el.classList.remove('active');
            });
            // Show selected language section
            document.querySelector(`[lang="${lang}"]`).classList.add('active');
            // Update buttons
            document.querySelectorAll('.language-selector button').forEach(btn => {
                btn.classList.remove('active');
            });
            document.querySelector(`button[data-lang="${lang}"]`).classList.add('active');
            // Save preference
            localStorage.setItem('preferred-language', lang);
        }

        // Load preferred language or default to English
        document.addEventListener('DOMContentLoaded', () => {
            const preferredLang = localStorage.getItem('preferred-language') || 
                                navigator.language.split('-')[0] || 'en';
            setLanguage(preferredLang);
        });
    </script>
</body>
</html>
