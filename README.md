<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>한국철도공사 노조 부전지구 - 건의사항</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }

        .header {
            background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%);
            color: white;
            padding: 30px;
            text-align: center;
            position: relative;
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="20" cy="20" r="2" fill="rgba(255,255,255,0.1)"/><circle cx="80" cy="20" r="1.5" fill="rgba(255,255,255,0.1)"/><circle cx="40" cy="40" r="1" fill="rgba(255,255,255,0.1)"/><circle cx="60" cy="70" r="2" fill="rgba(255,255,255,0.1)"/><circle cx="10" cy="80" r="1.5" fill="rgba(255,255,255,0.1)"/></svg>') repeat;
        }

        .header-content {
            position: relative;
            z-index: 1;
        }

        .logo {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .title {
            font-size: 1.8em;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .subtitle {
            font-size: 1.1em;
            opacity: 0.9;
        }

        .main-content {
            padding: 40px 30px;
        }

        .tab-buttons {
            display: flex;
            margin-bottom: 30px;
            background: #f7fafc;
            border-radius: 15px;
            padding: 5px;
        }

        .tab-btn {
            flex: 1;
            padding: 15px;
            border: none;
            background: transparent;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .tab-btn.active {
            background: #4299e1;
            color: white;
            box-shadow: 0 4px 15px rgba(66, 153, 225, 0.3);
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        .form-group {
            margin-bottom: 25px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #2d3748;
        }

        .form-group input, 
        .form-group select, 
        .form-group textarea {
            width: 100%;
            padding: 15px;
            border: 2px solid #e2e8f0;
            border-radius: 10px;
            font-size: 16px;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus, 
        .form-group select:focus, 
        .form-group textarea:focus {
            outline: none;
            border-color: #4299e1;
            box-shadow: 0 0 0 3px rgba(66, 153, 225, 0.1);
        }

        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }

        .checkbox-group {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 10px;
        }

        .checkbox-group input[type="checkbox"] {
            width: auto;
            margin: 0;
        }

        .submit-btn {
            width: 100%;
            padding: 18px;
            background: linear-gradient(135deg, #48bb78 0%, #38a169 100%);
            color: white;
            border: none;
            border-radius: 15px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(72, 187, 120, 0.3);
        }

        .suggestions-list {
            margin-top: 30px;
        }

        .suggestion-item {
            background: #f7fafc;
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 15px;
            border-left: 5px solid #4299e1;
            transition: all 0.3s ease;
        }

        .suggestion-item:hover {
            transform: translateX(5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .suggestion-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .suggestion-category {
            background: #4299e1;
            color: white;
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 0.9em;
            font-weight: bold;
        }

        .suggestion-date {
            color: #666;
            font-size: 0.9em;
        }

        .suggestion-title {
            font-weight: bold;
            color: #2d3748;
            margin-bottom: 8px;
        }

        .suggestion-content {
            color: #4a5568;
            line-height: 1.6;
        }

        .status-badge {
            display: inline-block;
            padding: 4px 10px;
            border-radius: 10px;
            font-size: 0.8em;
            font-weight: bold;
            margin-left: 10px;
        }

        .status-pending {
            background: #fed7d7;
            color: #c53030;
        }

        .status-reviewing {
            background: #feebc8;
            color: #c05621;
        }

        .status-completed {
            background: #c6f6d5;
            color: #2f855a;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
        }

        .stat-number {
            font-size: 2.5em;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .stat-label {
            font-size: 0.9em;
            opacity: 0.9;
        }

        .qr-info {
            background: #e6fffa;
            border: 2px solid #38b2ac;
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            margin-bottom: 30px;
        }

        .qr-placeholder {
            width: 150px;
            height: 150px;
            background: white;
            border: 2px solid #38b2ac;
            border-radius: 10px;
            margin: 0 auto 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .qr-code {
            width: 140px;
            height: 140px;
        }

        .admin-login {
            position: fixed;
            top: 20px;
            right: 20px;
            background: rgba(45, 55, 72, 0.9);
            color: white;
            padding: 10px 15px;
            border-radius: 20px;
            cursor: pointer;
            font-size: 0.9em;
            border: none;
            transition: all 0.3s ease;
        }

        .admin-login:hover {
            background: rgba(45, 55, 72, 1);
            transform: scale(1.05);
        }

        .admin-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 1000;
        }

        .admin-modal-content {
            background: white;
            border-radius: 20px;
            padding: 30px;
            width: 90%;
            max-width: 400px;
            text-align: center;
        }

        .admin-input {
            width: 100%;
            padding: 15px;
            margin: 10px 0;
            border: 2px solid #e2e8f0;
            border-radius: 10px;
            font-size: 16px;
        }

        .admin-btn {
            width: 100%;
            padding: 15px;
            background: #4299e1;
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 16px;
            cursor: pointer;
            margin: 10px 0;
        }

        .admin-panel {
            display: none;
            background: #f7fafc;
            border-radius: 15px;
            padding: 20px;
            margin-top: 20px;
        }

        .admin-panel.active {
            display: block;
        }

        .suggestion-admin-item {
            background: white;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 15px;
            border-left: 5px solid #4299e1;
        }

        .admin-actions {
            margin-top: 15px;
            display: flex;
            gap: 10px;
        }

        .action-btn {
            padding: 8px 15px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 0.9em;
            font-weight: bold;
        }

        .btn-review {
            background: #fbb6ce;
            color: #b83280;
        }

        .btn-complete {
            background: #c6f6d5;
            color: #2f855a;
        }

        .btn-delete {
            background: #fed7d7;
            color: #c53030;
        }

        .export-btn {
            background: #4299e1;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            margin: 10px 5px;
            font-weight: bold;
        }

        @media (max-width: 768px) {
            .container {
                margin: 10px;
                border-radius: 15px;
            }

            .header {
                padding: 20px;
            }

            .title {
                font-size: 1.5em;
            }

            .main-content {
                padding: 20px;
            }

            .tab-buttons {
                flex-direction: column;
                gap: 5px;
            }
        }
    </style>
</head>
<body>
    <button class="admin-login" onclick="showAdminLogin()">🔧 관리자</button>
    
    <!-- 관리자 로그인 모달 -->
    <div id="adminModal" class="admin-modal">
        <div class="admin-modal-content">
            <h3>관리자 로그인</h3>
            <input type="password" id="adminPassword" class="admin-input" placeholder="비밀번호를 입력하세요" onkeypress="handleAdminKeyPress(event)">
            <button class="admin-btn" onclick="adminLogin()">로그인</button>
            <button class="admin-btn" style="background: #e53e3e;" onclick="closeAdminModal()">취소</button>
        </div>
    </div>

    <div class="container">
        <div class="header">
            <div class="header-content">
                <div class="logo">🚆</div>
                <div class="title">한국철도공사 노동조합</div>
                <div class="subtitle">부전지구 건의사항 수집센터</div>
            </div>
        </div>

        <div class="main-content">
            <div class="qr-info">
                <div class="qr-placeholder">
                    <canvas id="qrcode" class="qr-code"></canvas>
                </div>
                <p><strong>조합원 여러분!</strong><br>위 QR코드를 스캔하시면 바로 이 페이지로 접속할 수 있습니다.</p>
            </div>

            <div class="tab-buttons">
                <button class="tab-btn active" onclick="showTab('submit')">건의사항 제출</button>
                <button class="tab-btn" onclick="showTab('view')">건의사항 보기</button>
                <button class="tab-btn" onclick="showTab('stats')">현황</button>
                <button class="tab-btn" id="adminTabBtn" onclick="showTab('admin')" style="display: none;">관리자</button>
            </div>

            <!-- 건의사항 제출 탭 -->
            <div id="submit-tab" class="tab-content active">
                <form id="suggestionForm">
                    <div class="form-group">
                        <label for="category">건의 분야 *</label>
                        <select id="category" required>
                            <option value="">분야를 선택하세요</option>
                            <option value="임금">임금 및 수당</option>
                            <option value="근무환경">근무환경 개선</option>
                            <option value="복리후생">복리후생</option>
                            <option value="안전">안전 관련</option>
                            <option value="교육">교육 및 훈련</option>
                            <option value="인사">인사 제도</option>
                            <option value="시설">시설 개선</option>
                            <option value="기타">기타</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="title">제목 *</label>
                        <input type="text" id="title" placeholder="건의사항 제목을 입력하세요" required>
                    </div>

                    <div class="form-group">
                        <label for="content">내용 *</label>
                        <textarea id="content" placeholder="구체적인 건의내용을 작성해주세요.&#10;현황, 문제점, 개선방안 등을 포함해주시면 더욱 도움이 됩니다." required></textarea>
                    </div>

                    <div class="form-group">
                        <label for="workplace">근무지</label>
                        <input type="text" id="workplace" placeholder="예: 부전역, 태화강역 등">
                    </div>

                    <div class="form-group">
                        <label for="contact">연락처 (선택)</label>
                        <input type="text" id="contact" placeholder="답변을 받고 싶으시면 연락처를 남겨주세요">
                    </div>

                    <div class="form-group">
                        <div class="checkbox-group">
                            <input type="checkbox" id="anonymous">
                            <label for="anonymous">익명으로 제출</label>
                        </div>
                    </div>

                    <button type="submit" class="submit-btn">건의사항 제출하기</button>
                </form>
            </div>

            <!-- 건의사항 보기 탭 -->
            <div id="view-tab" class="tab-content">
                <div class="suggestions-list">
                    <div class="suggestion-item">
                        <div class="suggestion-header">
                            <span class="suggestion-category">근무환경</span>
                            <span class="suggestion-date">2024.08.12</span>
                        </div>
                        <div class="suggestion-title">부전역사 휴게실 에어컨 교체 요청 <span class="status-badge status-reviewing">검토중</span></div>
                        <div class="suggestion-content">휴게실 에어컨이 노후되어 냉방 효과가 떨어집니다. 여름철 휴식시간에 제대로 쉴 수 없어 업무 효율성에 영향을 미치고 있습니다...</div>
                    </div>

                    <div class="suggestion-item">
                        <div class="suggestion-header">
                            <span class="suggestion-category">안전</span>
                            <span class="suggestion-date">2024.08.10</span>
                        </div>
                        <div class="suggestion-title">승강장 미끄럼 방지 시설 설치 <span class="status-badge status-pending">접수</span></div>
                        <div class="suggestion-content">우천시 승강장이 미끄러워 안전사고 위험이 있습니다. 미끄럼 방지 매트나 논슬립 코팅 등의 안전시설 설치를 건의드립니다...</div>
                    </div>

                    <div class="suggestion-item">
                        <div class="suggestion-header">
                            <span class="suggestion-category">복리후생</span>
                            <span class="suggestion-date">2024.08.08</span>
                        </div>
                        <div class="suggestion-title">직원식당 메뉴 개선 요청 <span class="status-badge status-completed">완료</span></div>
                        <div class="suggestion-content">직원식당 메뉴가 단조롭고 영양 균형이 부족합니다. 다양한 메뉴와 건강식 옵션 추가를 요청드립니다...</div>
                    </div>
                </div>
            </div>

            <!-- 현황 탭 -->
            <div id="stats-tab" class="tab-content">
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="stat-number" id="totalSuggestions">23</div>
                        <div class="stat-label">총 건의사항</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number" id="pendingSuggestions">8</div>
                        <div class="stat-label">접수 대기</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number" id="reviewingSuggestions">10</div>
                        <div class="stat-label">검토 중</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number" id="completedSuggestions">5</div>
                        <div class="stat-label">처리 완료</div>
                    </div>
                </div>

                <div style="background: #f7fafc; border-radius: 15px; padding: 20px; margin-top: 20px;">
                    <h3 style="color: #2d3748; margin-bottom: 15px;">📊 분야별 건의 현황</h3>
                    <div style="display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px;">
                        <div>근무환경: 8건</div>
                        <div>안전관련: 6건</div>
                        <div>복리후생: 4건</div>
                        <div>임금수당: 3건</div>
                        <div>시설개선: 2건</div>
                    </div>
                </div>
            </div>

            <!-- 관리자 탭 -->
            <div id="admin-tab" class="tab-content">
                <div class="admin-panel">
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px;">
                        <h3>🔧 관리자 패널</h3>
                        <div>
                            <button class="export-btn" onclick="exportToExcel()">📊 엑셀 다운로드</button>
                            <button class="export-btn" onclick="adminLogout()" style="background: #e53e3e;">로그아웃</button>
                        </div>
                    </div>
                    
                    <div id="adminSuggestionsList">
                        <!-- 관리자용 건의사항 목록이 여기에 동적으로 추가됩니다 -->
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- QR Code Library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcode/1.5.3/qrcode.min.js"></script>

    <script>
        let suggestions = JSON.parse(localStorage.getItem('suggestions') || '[]');
        let isAdminLoggedIn = sessionStorage.getItem('adminLoggedIn') === 'true';
        
        // QR 코드 생성
        window.addEventListener('load', function() {
            const canvas = document.getElementById('qrcode');
            const currentUrl = window.location.href;
            
            QRCode.toCanvas(canvas, currentUrl, {
                width: 140,
                margin: 1,
                color: {
                    dark: '#2c7a7b',
                    light: '#ffffff'
                }
            }, function (error) {
                if (error) {
                    console.error('QR 코드 생성 실패:', error);
                    canvas.parentElement.innerHTML = '<div style="color: #2c7a7b; font-size: 0.9em;">QR 코드<br>생성 중...</div>';
                }
            });
        });

        // 관리자 로그인 관련
        function showAdminLogin() {
            document.getElementById('adminModal').style.display = 'flex';
            document.getElementById('adminPassword').focus();
        }

        function closeAdminModal() {
            document.getElementById('adminModal').style.display = 'none';
            document.getElementById('adminPassword').value = '';
        }

        function handleAdminKeyPress(event) {
            if (event.key === 'Enter') {
                adminLogin();
            }
        }

        function adminLogin() {
            const password = document.getElementById('adminPassword').value;
            // 실제로는 서버에서 인증해야 하지만, 데모용으로 간단한 비밀번호 사용
            if (password === 'korail2024' || password === '부전총무') {
                isAdminLoggedIn = true;
                sessionStorage.setItem('adminLoggedIn', 'true');
                document.getElementById('adminTabBtn').style.display = 'block';
                closeAdminModal();
                showTab('admin');
                alert('관리자 로그인 성공!');
            } else {
                alert('비밀번호가 틀렸습니다.');
            }
        }

        function adminLogout() {
            isAdminLoggedIn = false;
            sessionStorage.removeItem('adminLoggedIn');
            document.getElementById('adminTabBtn').style.display = 'none';
            showTab('submit');
            alert('로그아웃 되었습니다.');
        }

        // 페이지 로드시 관리자 상태 확인
        if (isAdminLoggedIn) {
            document.getElementById('adminTabBtn').style.display = 'block';
        }
        
        function showTab(tabName) {
            // 모든 탭 숨기기
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // 모든 버튼 비활성화
            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            
            // 선택된 탭 보이기
            document.getElementById(tabName + '-tab').classList.add('active');
            
            // 해당하는 버튼 활성화
            const buttons = document.querySelectorAll('.tab-btn');
            const buttonTexts = ['submit', 'view', 'stats', 'admin'];
            const index = buttonTexts.indexOf(tabName);
            if (index !== -1 && buttons[index]) {
                buttons[index].classList.add('active');
            }
            
            // 특정 탭 업데이트
            if (tabName === 'view') {
                updateSuggestionsList();
            } else if (tabName === 'admin') {
                updateAdminSuggestionsList();
            }
        }

        // 폼 제출 처리
        document.getElementById('suggestionForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const formData = {
                id: Date.now(),
                category: document.getElementById('category').value,
                title: document.getElementById('title').value,
                content: document.getElementById('content').value,
                workplace: document.getElementById('workplace').value,
                contact: document.getElementById('contact').value,
                anonymous: document.getElementById('anonymous').checked,
                date: new Date().toLocaleDateString('ko-KR'),
                status: 'pending',
                submittedAt: new Date().toISOString()
            };
            
            // 메모리에 저장
            suggestions.unshift(formData);
            localStorage.setItem('suggestions', JSON.stringify(suggestions));
            
            alert('건의사항이 성공적으로 제출되었습니다!\n검토 후 답변드리겠습니다.');
            
            // 폼 초기화
            this.reset();
            
            // 통계 업데이트
            updateStats();
        });

        function updateSuggestionsList() {
            const suggestionsList = document.querySelector('.suggestions-list');
            suggestionsList.innerHTML = '';
            
            if (suggestions.length === 0) {
                suggestionsList.innerHTML = '<p style="text-align: center; color: #666; padding: 40px;">아직 등록된 건의사항이 없습니다.</p>';
                return;
            }
            
            suggestions.forEach(suggestion => {
                const statusClass = {
                    'pending': 'status-pending',
                    'reviewing': 'status-reviewing', 
                    'completed': 'status-completed'
                }[suggestion.status] || 'status-pending';
                
                const statusText = {
                    'pending': '접수',
                    'reviewing': '검토중',
                    'completed': '완료'
                }[suggestion.status] || '접수';
                
                const item = document.createElement('div');
                item.className = 'suggestion-item';
                item.innerHTML = `
                    <div class="suggestion-header">
                        <span class="suggestion-category">${suggestion.category}</span>
                        <span class="suggestion-date">${suggestion.date}</span>
                    </div>
                    <div class="suggestion-title">${suggestion.title} <span class="status-badge ${statusClass}">${statusText}</span></div>
                    <div class="suggestion-content">${suggestion.content.substring(0, 100)}${suggestion.content.length > 100 ? '...' : ''}</div>
                `;
                
                suggestionsList.appendChild(item);
            });
        }

        function updateAdminSuggestionsList() {
            const adminList = document.getElementById('adminSuggestionsList');
            adminList.innerHTML = '';
            
            if (suggestions.length === 0) {
                adminList.innerHTML = '<p style="text-align: center; color: #666; padding: 40px;">등록된 건의사항이 없습니다.</p>';
                return;
            }
            
            suggestions.forEach((suggestion, index) => {
                const statusClass = {
                    'pending': 'status-pending',
                    'reviewing': 'status-reviewing', 
                    'completed': 'status-completed'
                }[suggestion.status] || 'status-pending';
                
                const statusText = {
                    'pending': '접수',
                    'reviewing': '검토중',
                    'completed': '완료'
                }[suggestion.status] || '접수';
                
                const item = document.createElement('div');
                item.className = 'suggestion-admin-item';
                item.innerHTML = `
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px;">
                        <span class="suggestion-category">${suggestion.category}</span>
                        <span class="suggestion-date">${suggestion.date}</span>
                    </div>
                    <div class="
