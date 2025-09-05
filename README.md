# ramonmlbbclub
Ramon Mobile Legends Club official website
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub - ramcomm@bchab</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        }
        
        body {
            background-color: #0d1117;
            color: #c9d1d9;
            line-height: 1.5;
        }
        
        .container {
            display: flex;
            max-width: 1280px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .sidebar {
            width: 220px;
            flex-shrink: 0;
            margin-right: 24px;
        }
        
        .main-content {
            flex-grow: 1;
            max-width: 896px;
        }
        
        .repo-header {
            display: flex;
            align-items: center;
            margin-bottom: 16px;
            padding-bottom: 16px;
            border-bottom: 1px solid #21262d;
        }
        
        .repo-owner {
            color: #58a6ff;
            font-weight: 500;
        }
        
        .repo-name {
            font-weight: 600;
            color: #c9d1d9;
        }
        
        .repo-divider {
            margin: 0 4px;
            color: #6e7681;
        }
        
        .nav-list {
            list-style: none;
            margin-bottom: 16px;
        }
        
        .nav-item {
            padding: 8px 0;
            padding-left: 16px;
            margin-bottom: 4px;
            border-radius: 6px;
            cursor: pointer;
            display: flex;
            align-items: center;
        }
        
        .nav-item i {
            margin-right: 8px;
            width: 16px;
        }
        
        .nav-item:hover {
            background-color: #161b22;
        }
        
        .nav-item.active {
            background-color: #161b22;
            font-weight: 500;
            position: relative;
        }
        
        .nav-item.active::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            height: 100%;
            width: 2px;
            background-color: #f78166;
        }
        
        .file-browser {
            background-color: #161b22;
            border: 1px solid #21262d;
            border-radius: 6px;
            margin-bottom: 16px;
        }
        
        .file-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 8px 16px;
            background-color: #0d1117;
            border-bottom: 1px solid #21262d;
            border-top-left-radius: 6px;
            border-top-right-radius: 6px;
        }
        
        .file-path {
            font-family: 'Monaco', 'Menlo', 'Ubuntu Mono', monospace;
            font-size: 14px;
        }
        
        .file-actions {
            display: flex;
        }
        
        .btn {
            padding: 5px 16px;
            background-color: #21262d;
            color: #c9d1d9;
            border: 1px solid #363b42;
            border-radius: 6px;
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
            margin-left: 8px;
            display: flex;
            align-items: center;
        }
        
        .btn i {
            margin-right: 4px;
        }
        
        .btn-primary {
            background-color: #238636;
            color: white;
            border: 1px solid #2ea043;
        }
        
        .btn-primary:hover {
            background-color: #2ea043;
        }
        
        .editor {
            padding: 16px;
        }
        
        .editor-text {
            font-family: 'Monaco', 'Menlo', 'Ubuntu Mono', monospace;
            font-size: 14px;
            line-height: 1.6;
            white-space: pre-wrap;
            background-color: #161b22;
            padding: 16px;
            border-radius: 6px;
            border: 1px solid #21262d;
            margin-bottom: 16px;
        }
        
        .editor-text .comment {
            color: #8b949e;
        }
        
        .editor-text .command {
            color: #7ee787;
        }
        
        .editor-text .path {
            color: #79c0ff;
        }
        
        .commit-section {
            background-color: #0d1117;
            border: 1px solid #21262d;
            border-radius: 6px;
            padding: 16px;
            margin-bottom: 16px;
        }
        
        .commit-title {
            font-weight: 600;
            margin-bottom: 8px;
        }
        
        .commit-form {
            display: flex;
            flex-direction: column;
        }
        
        .commit-input {
            background-color: #0d1117;
            border: 1px solid #21262d;
            border-radius: 6px;
            padding: 8px;
            color: #c9d1d9;
            font-family: inherit;
            margin-bottom: 8px;
            resize: vertical;
            min-height: 80px;
        }
        
        .commit-button {
            align-self: flex-end;
            padding: 7px 16px;
            background-color: #238636;
            color: white;
            border: 1px solid #2ea043;
            border-radius: 6px;
            font-weight: 500;
            cursor: pointer;
        }
        
        .commit-button:disabled {
            background-color: #133d1e;
            border-color: #1b4e29;
            color: #8b949e;
            cursor: not-allowed;
        }
        
        .keyboard-help {
            color: #8b949e;
            font-size: 12px;
            margin-top: 16px;
            padding: 8px;
            border-top: 1px solid #21262d;
        }
        
        .branch-selector {
            display: flex;
            align-items: center;
            margin-left: 8px;
            color: #58a6ff;
            cursor: pointer;
            font-size: 14px;
        }
        
        .branch-selector i {
            margin-left: 4px;
        }
        
        .tab {
            display: inline-block;
            padding: 8px 16px;
            border-bottom: 2px solid transparent;
            cursor: pointer;
            margin-right: 8px;
        }
        
        .tab.active {
            border-bottom-color: #f78166;
            font-weight: 500;
        }
        
        .language-selector {
            position: absolute;
            top: 20px;
            right: 20px;
        }
        
        .language-btn {
            background-color: #21262d;
            color: #c9d1d9;
            border: 1px solid #363b42;
            border-radius: 6px;
            padding: 8px 16px;
            cursor: pointer;
            display: flex;
            align-items: center;
        }
        
        .language-btn i {
            margin-right: 8px;
        }
        
        @media (max-width: 768px) {
            .container {
                flex-direction: column;
            }
            
            .sidebar {
                width: 100%;
                margin-right: 0;
                margin-bottom: 20px;
            }
            
            .language-selector {
                position: relative;
                top: 0;
                right: 0;
                margin-bottom: 20px;
                text-align: center;
            }
        }
        
        h2 {
            font-size: 16px;
            margin-bottom: 8px;
            color: #f0f6fc;
            padding-left: 16px;
        }
        
        .status-message {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: #238636;
            color: white;
            padding: 12px 20px;
            border-radius: 6px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
            display: none;
        }
    </style>
</head>
<body>
    <div class="language-selector">
        <button class="language-btn" onclick="toggleLanguage()">
            <i class="fas fa-language"></i> Tilni o'zgartirish
        </button>
    </div>

    <div class="container">
        <div class="sidebar">
            <h2>Cache</h2>
            <ul class="nav-list">
                <li class="nav-item active"><i class="fas fa-exclamation-circle"></i> Muammolar</li>
                <li class="nav-item"><i class="fas fa-code-branch"></i> To'liq so'rovlar</li>
            </ul>
            
            <h2>Harakatlar</h2>
            <ul class="nav-list">
                <li class="nav-item"><i class="fas fa-project-diagram"></i> Loyihalar</li>
                <li class="nav-item"><i class="fas fa-globe"></i> Veb</li>
                <li class="nav-item"><i class="fas fa-shield-alt"></i> Xavfsizlik</li>
                <li class="nav-item"><i class="fas fa-chart-line"></i> Tahlillar</li>
                <li class="nav-item"><i class="fas fa-cog"></i> Sozlamalar</li>
            </ul>
        </div>
        
        <div class="main-content">
            <div class="repo-header">
                <span class="repo-owner">ramcomm@bchab</span>
                <span class="repo-divider">/</span>
                <span class="repo-name">README.md</span>
                <div class="branch-selector">
                    <span>main</span>
                    <i class="fas fa-caret-down"></i>
                </div>
            </div>
            
            <div class="file-browser">
                <div class="file-header">
                    <div class="file-path">ramcomm@bchab / README.md</div>
                    <div class="file-actions">
                        <button class="btn"><i class="fas fa-history"></i> Tarix</button>
                        <button class="btn btn-primary" id="editButton"><i class="fas fa-pencil-alt"></i> Tahrirlash</button>
                    </div>
                </div>
                
                <div class="editor">
                    <div class="tabs">
                        <div class="tab active">Tahrirlash</div>
                        <div class="tab">Ko'rib chiqish</div>
                    </div>
                    
                    <div class="editor-text" id="editorContent">
<span class="comment"># ramcomm@bchab</span>
<span class="comment">## Loyiha haqida</span>
Bu loyiha GitHub interfeysini o'zbek tilida namoyish etadi.

<span class="comment">## O'rnatish</span>
<span class="command">git clone</span> <span class="path">https://github.com/abstract-library-memory/ramcomm@bchab.git</span>
<span class="command">cd ramcomm@bchab</span>

<span class="comment">## Ishlatish</span>
Dasturni ishga tushirish uchun quyidagi buyruqni ishlating:
<span class="command">npm start</span>

<span class="comment">## Hissa qo'shish</span>
Hisoa qo'shish uchus quyidagi qadamlarni bajaring:
1. Repositoryni fork qiling
2. Yangi branch yarating
3. O'zgarishlaringizni commit qiling
4. Pull Request yuboring
                    </div>
                    
                    <div class="commit-section">
                        <div class="commit-title">O'zgarishlarni commit qilish</div>
                        <form class="commit-form" id="commitForm">
                            <input type="text" class="commit-input" id="commitMessage" placeholder="Commit xabari...">
                            <textarea class="commit-input" id="commitDescription" placeholder="Qo'shimcha tavsif (ixtiyoriy)"></textarea>
                            <button type="submit" class="commit-button" id="commitButton" disabled>Commit o'zgarishlar</button>
                        </form>
                    </div>
                    
                    <div class="keyboard-help">
                        Interaktiv elementlar orasida harakatlanish uchun Ctrl + M yoki S ni bosing.
                        Fayllarni qo'shish uchun ularni sudrab olib keling, tanlang yoki joylashtiring.
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="status-message" id="statusMessage"></div>

    <script>
        function toggleLanguage() {
            showMessage("Til o'zgartirish funksiyasi bu yerda ishlaydi. Haqiqiy ilova bu funksionallikni qo'shadi.");
        }
        
        function showMessage(message) {
            const messageElement = document.getElementById('statusMessage');
            messageElement.textContent = message;
            messageElement.style.display = 'block';
            
            setTimeout(() => {
                messageElement.style.display = 'none';
            }, 3000);
        }
        
        // Commit form validation
        const commitForm = document.getElementById('commitForm');
        const commitMessage = document.getElementById('commitMessage');
        const commitDescription = document.getElementById('commitDescription');
        const commitButton = document.getElementById('commitButton');
        
        commitMessage.addEventListener('input', () => {
            commitButton.disabled = !commitMessage.value.trim();
        });
        
        commitForm.addEventListener('submit', (e) => {
            e.preventDefault();
            showMessage("Commit muvaffaqiyatli amalga oshirildi: " + commitMessage.value);
            commitMessage.value = '';
            commitDescription.value = '';
            commitButton.disabled = true;
        });
        
        // Tab functionality
        const tabs = document.querySelectorAll('.tab');
        tabs.forEach(tab => {
            tab.addEventListener('click', () => {
                tabs.forEach(t => t.classList.remove('active'));
                tab.classList.add('active');
                
                if (tab.textContent === "Ko'rib chiqish") {
                    showMessage("Ko'rib chiqish rejimi faollashtirildi");
                } else {
                    showMessage("Tahrirlash rejimi faollashtirildi");
                }
            });
        });
        
        // Edit button functionality
        const editButton = document.getElementById('editButton');
        editButton.addEventListener('click', () => {
            showMessage("Tahrirlash rejimi faollashtirildi. Endi fayl mazmunini o'zgartirishingiz mumkin.");
        });
        
        // Navigation items functionality
        const navItems = document.querySelectorAll('.nav-item');
        navItems.forEach(item => {
            item.addEventListener('click', () => {
                navItems.forEach(i => i.classList.remove('active'));
                item.classList.add('active');
                showMessage(item.textContent + " bo'limi ochildi");
            });
        });
        
        // Branch selector functionality
        const branchSelector = document.querySelector('.branch-selector');
        branchSelector.addEventListener('click', () => {
            showMessage("Branch tanlash menyusi ochildi");
        });
    </script>
</body>
</html>
