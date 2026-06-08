<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>내신 성적 조회 - 나의 대학 찾기</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            overflow: hidden;
        }

        /* 헤더 */
        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 40px 20px;
            text-align: center;
        }

        .header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .header p {
            font-size: 1.1em;
            opacity: 0.9;
        }

        /* 메인 컨텐츠 */
        .main-content {
            padding: 40px;
        }

        section {
            margin-bottom: 40px;
        }

        section h2 {
            font-size: 1.8em;
            margin-bottom: 20px;
            color: #333;
            border-bottom: 3px solid #667eea;
            padding-bottom: 10px;
        }

        /* 입력 섹션 */
        .input-section {
            background: #f8f9fa;
            padding: 30px;
            border-radius: 10px;
        }

        .grade-system {
            display: flex;
            gap: 30px;
            margin-bottom: 30px;
        }

        .grade-system label {
            display: flex;
            align-items: center;
            cursor: pointer;
            font-size: 1.1em;
        }

        .grade-system input {
            margin-right: 10px;
            cursor: pointer;
            width: 18px;
            height: 18px;
        }

        /* 학년별 성적 입력 */
        .year-section {
            background: white;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 20px;
            border-left: 5px solid #667eea;
        }

        .year-section h3 {
            font-size: 1.3em;
            margin-bottom: 15px;
            color: #333;
        }

        .semester-group {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-bottom: 15px;
        }

        .semester-input {
            display: flex;
            flex-direction: column;
        }

        .semester-input label {
            margin-bottom: 8px;
            font-weight: bold;
            color: #333;
            font-size: 0.95em;
        }

        .semester-input select {
            padding: 10px;
            border: 2px solid #ddd;
            border-radius: 5px;
            font-size: 0.95em;
            cursor: pointer;
            transition: border-color 0.3s;
        }

        .semester-input select:hover,
        .semester-input select:focus {
            border-color: #667eea;
            outline: none;
        }

        .average-display {
            background: #f0f0f0;
            padding: 10px 15px;
            border-radius: 5px;
            font-weight: bold;
            color: #667eea;
            margin-top: 10px;
        }

        /* 지원 방식 선택 */
        .application-type {
            background: white;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 20px;
        }

        .application-type h3 {
            margin-bottom: 15px;
            color: #333;
        }

        .application-type-options {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }

        .application-type label {
            display: flex;
            align-items: center;
            cursor: pointer;
            font-size: 1em;
        }

        .application-type input {
            margin-right: 8px;
            cursor: pointer;
            width: 18px;
            height: 18px;
        }

        /* 버튼 */
        .search-btn {
            width: 100%;
            padding: 15px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 1.1em;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .search-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(102, 126, 234, 0.4);
        }

        .search-btn:active {
            transform: translateY(0);
        }

        /* 결과 섹션 */
        .results-section {
            background: #f8f9fa;
            padding: 30px;
            border-radius: 10px;
        }

        .grade-summary {
            background: white;
            padding: 20px;
            border-radius: 5px;
            margin-bottom: 20px;
            border-left: 5px solid #667eea;
        }

        .grade-summary-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
        }

        .summary-item {
            background: #f0f0f0;
            padding: 15px;
            border-radius: 5px;
            text-align: center;
        }

        .summary-item label {
            display: block;
            font-size: 0.9em;
            color: #666;
            margin-bottom: 5px;
        }

        .summary-item .value {
            font-size: 1.5em;
            font-weight: bold;
            color: #667eea;
        }

        .result-tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .tab-button {
            padding: 12px 20px;
            background: white;
            border: 2px solid #ddd;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1em;
            transition: all 0.3s;
        }

        .tab-button.active {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-color: transparent;
        }

        .tab-button:hover {
            border-color: #667eea;
        }

        .results-container {
            background: white;
            border-radius: 5px;
            padding: 20px;
        }

        .result-tab-content {
            display: none;
        }

        .result-tab-content.active {
            display: block;
        }

        .university-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 15px;
        }

        .university-card {
            background: #f8f9fa;
            border: 2px solid #ddd;
            border-radius: 8px;
            padding: 15px;
            transition: all 0.3s;
            cursor: pointer;
        }

        .university-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            border-color: #667eea;
        }

        .university-name {
            font-size: 1.2em;
            font-weight: bold;
            color: #333;
            margin-bottom: 8px;
        }

        .university-info {
            font-size: 0.9em;
            color: #666;
            margin-bottom: 5px;
        }

        .university-info strong {
            color: #667eea;
        }

        .empty-message {
            text-align: center;
            padding: 40px 20px;
            color: #999;
            font-size: 1.1em;
        }

        /* 정보 섹션 */
        .info-section {
            background: #f8f9fa;
            padding: 30px;
            border-radius: 10px;
        }

        /* 푸터 */
        .footer {
            background: #f8f9fa;
            padding: 20px;
            text-align: center;
            color: #666;
            font-size: 0.9em;
            border-top: 1px solid #ddd;
        }

        /* 반응형 디자인 */
        @media (max-width: 768px) {
            .main-content {
                padding: 20px;
            }

            .header h1 {
                font-size: 1.8em;
            }

            .semester-group {
                grid-template-columns: 1fr;
            }

            .university-list {
                grid-template-columns: 1fr;
            }

            .result-tabs {
                flex-direction: column;
            }

            .tab-button {
                width: 100%;
            }

            .grade-system {
                flex-direction: column;
                gap: 15px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- 헤더 -->
        <header class="header">
            <h1>🎓 내신 기반 대학 찾기</h1>
            <p>3년 내신 성적으로 지원 가능한 대학교를 찾아보세요</p>
        </header>

        <!-- 메인 컨텐츠 -->
        <main class="main-content">
            <!-- 성적 입력 섹션 -->
            <section class="input-section">
                <h2>내신 성적 입력</h2>
                
                <!-- 등급제 선택 -->
                <div class="grade-system">
                    <label>
                        <input type="radio" name="gradeSystem" value="9" checked> 9등급제
                    </label>
                    <label>
                        <input type="radio" name="gradeSystem" value="5"> 5등급제
                    </label>
                </div>

                <!-- 1학년 -->
                <div class="year-section">
                    <h3>1학년</h3>
                    <div class="semester-group">
                        <div class="semester-input">
                            <label for="grade1_mid">1학년 중간고사</label>
                            <select id="grade1_mid">
                                <option value="">선택하세요</option>
                            </select>
                        </div>
                        <div class="semester-input">
                            <label for="grade1_final">1학년 기말고사</label>
                            <select id="grade1_final">
                                <option value="">선택하세요</option>
                            </select>
                        </div>
                    </div>
                    <div class="average-display" id="avg1">1학년 평균: -</div>
                </div>

                <!-- 2학년 -->
                <div class="year-section">
                    <h3>2학년</h3>
                    <div class="semester-group">
                        <div class="semester-input">
                            <label for="grade2_mid">2학년 중간고사</label>
                            <select id="grade2_mid">
                                <option value="">선택하세요</option>
                            </select>
                        </div>
                        <div class="semester-input">
                            <label for="grade2_final">2학년 기말고사</label>
                            <select id="grade2_final">
                                <option value="">선택하세요</option>
                            </select>
                        </div>
                    </div>
                    <div class="average-display" id="avg2">2학년 평균: -</div>
                </div>

                <!-- 3학년 -->
                <div class="year-section">
                    <h3>3학년</h3>
                    <div class="semester-group">
                        <div class="semester-input">
                            <label for="grade3_mid">3학년 중간고사</label>
                            <select id="grade3_mid">
                                <option value="">선택하세요</option>
                            </select>
                        </div>
                        <div class="semester-input">
                            <label for="grade3_final">3학년 기말고사</label>
                            <select id="grade3_final">
                                <option value="">선택하세요</option>
                            </select>
                        </div>
                    </div>
                    <div class="average-display" id="avg3">3학년 평균: -</div>
                </div>

                <!-- 지원 방식 선택 -->
                <div class="application-type">
                    <h3>지원 방식 선택</h3>
                    <div class="application-type-options">
                        <label>
                            <input type="checkbox" name="applicationMethod" value="regular" checked> 정시
                        </label>
                        <label>
                            <input type="checkbox" name="applicationMethod" value="early"> 수시
                        </label>
                    </div>
                </div>

                <!-- 검색 버튼 -->
                <button id="searchBtn" class="search-btn">🔍 지원 가능 대학 검색</button>
            </section>

            <!-- 결과 섹션 -->
            <section class="results-section" id="resultsSection" style="display: none;">
                <h2>검색 결과</h2>
                
                <!-- 성적 정보 요약 -->
                <div class="grade-summary">
                    <div class="grade-summary-grid">
                        <div class="summary-item">
                            <label>1학년 평균</label>
                            <div class="value" id="summaryGrade1">-</div>
                        </div>
                        <div class="summary-item">
                            <label>2학년 평균</label>
                            <div class="value" id="summaryGrade2">-</div>
                        </div>
                        <div class="summary-item">
                            <label>3학년 평균</label>
                            <div class="value" id="summaryGrade3">-</div>
                        </div>
                        <div class="summary-item">
                            <label style="color: #667eea; font-weight: bold;">전체 평균</label>
                            <div class="value" id="summaryGradeTotal">-</div>
                        </div>
                    </div>
                </div>

                <!-- 결과 탭 -->
                <div class="result-tabs">
                    <button class="tab-button active" data-tab="suitable">
                        지원 가능 (상)
                    </button>
                    <button class="tab-button" data-tab="moderate">
                        지원 가능 (중)
                    </button>
                    <button class="tab-button" data-tab="risky">
                        도전 가능 (하)
                    </button>
                </div>

                <!-- 결과 카드 -->
                <div class="results-container">
                    <div class="result-tab-content active" id="suitable-tab">
                        <div class="university-list" id="suitableList"></div>
                    </div>
                    <div class="result-tab-content" id="moderate-tab">
                        <div class="university-list" id="moderateList"></div>
                    </div>
                    <div class="result-tab-content" id="risky-tab">
                        <div class="university-list" id="riskyList"></div>
                    </div>
                </div>
            </section>

            <!-- 정보 섹션 -->
            <section class="info-section">
                <h2>📊 등급제 정보</h2>
                <p style="margin-bottom: 20px; color: #666;">
                    내신 성적은 중학교 내신 등급 결과를 기반으로 계산됩니다.<br>
                    더 높은 정확도를 위해 최근 3년간의 평가 결과를 입력해주세요.
                </p>
                <div style="background: white; padding: 20px; border-radius: 8px;">
                    <h3 style="margin-bottom: 10px; color: #333;">계산 방식</h3>
                    <p style="color: #666; line-height: 1.6;">
                        ✓ 1학년 평균 = (중간고사 + 기말고사) ÷ 2<br>
                        ✓ 2학년 평균 = (중간고사 + 기말고사) ÷ 2<br>
                        ✓ 3학년 평균 = (중간고사 + 기말고사) ÷ 2<br>
                        ✓ 전체 평균 = (1학년 + 2학년 + 3학년) ÷ 3
                    </p>
                </div>
            </section>
        </main>

        <!-- 푸터 -->
        <footer class="footer">
            <p>참고: 대입정보포털 어디가, 진학사, 대학입결검색기 등의 데이터를 기반으로 합니다.</p>
            <p>최종 지원은 각 대학교 공식 홈페이지에서 확인하시기 바랍니다.</p>
        </footer>
    </div>

    <script>
        // 샘플 대학 데이터
        const universitiesData = {
            top: [
                { name: '서울대학교', average: 1.2, type: ['정시', '수시'], link: 'https://www.snu.ac.kr' },
                { name: '고려대학교', average: 1.5, type: ['정시', '수시'], link: 'https://www.korea.ac.kr' },
                { name: '연세대학교', average: 1.5, type: ['정시', '수시'], link: 'https://www.yonsei.ac.kr' },
                { name: 'KAIST', average: 1.3, type: ['정시', '수시'], link: 'https://www.kaist.ac.kr' },
                { name: 'POSTECH', average: 1.4, type: ['정시', '수시'], link: 'https://www.postech.ac.kr' },
            ],
            upper: [
                { name: '서강대학교', average: 2.0, type: ['정시', '수시'], link: 'https://www.sogang.ac.kr' },
                { name: '성균관대학교', average: 2.0, type: ['정시', '수시'], link: 'https://www.skku.edu' },
                { name: '한양대학교', average: 2.0, type: ['정시', '수시'], link: 'https://www.hanyang.ac.kr' },
                { name: '중앙대학교', average: 2.5, type: ['정시', '수시'], link: 'https://www.cau.ac.kr' },
                { name: '경희대학교', average: 2.5, type: ['정시', '수시'], link: 'https://www.khu.ac.kr' },
            ],
            middle: [
                { name: '이화여자대학교', average: 2.8, type: ['정시', '수시'], link: 'https://www.ewha.ac.kr' },
                { name: '숙명여자대학교', average: 3.0, type: ['정시', '수시'], link: 'https://www.sookmyung.ac.kr' },
                { name: '시립대학교', average: 3.2, type: ['정시'], link: 'https://www.uos.ac.kr' },
                { name: '부산대학교', average: 3.5, type: ['정시', '수시'], link: 'https://www.pusan.ac.kr' },
                { name: '광주과학기술원', average: 3.3, type: ['정시'], link: 'https://www.gist.ac.kr' },
            ],
            lower: [
                { name: '홍익대학교', average: 3.8, type: ['정시', '수시'], link: 'https://www.hongik.ac.kr' },
                { name: '건국대학교', average: 3.8, type: ['정시', '수시'], link: 'https://www.konkuk.ac.kr' },
                { name: '동국대학교', average: 3.9, type: ['정시', '수시'], link: 'https://www.dongguk.edu' },
                { name: '세종대학교', average: 4.0, type: ['정시', '수시'], link: 'https://www.sejong.ac.kr' },
                { name: '인천대학교', average: 4.2, type: ['정시'], link: 'https://www.inu.ac.kr' },
            ],
        };

        // 등급제 데이터
        const gradeSystemData = {
            9: { grades: 9 },
            5: { grades: 5 },
        };

        // 초기화
        document.addEventListener('DOMContentLoaded', function() {
            initializeGradeSelects();
            setupEventListeners();
        });

        // 등급 선택지 초기화
        function initializeGradeSelects() {
            const gradeSystem = document.querySelector('input[name="gradeSystem"]:checked').value;
            updateGradeOptions(gradeSystem);
        }

        // 등급 선택지 업데이트
        function updateGradeOptions(system) {
            const maxGrade = parseInt(system);
            const selects = [
                'grade1_mid', 'grade1_final',
                'grade2_mid', 'grade2_final',
                'grade3_mid', 'grade3_final'
            ];
            
            selects.forEach(id => {
                const select = document.getElementById(id);
                if (!select) return;
                
                const currentValue = select.value;
                select.innerHTML = '<option value="">선택하세요</option>';
                
                for (let i = 1; i <= maxGrade; i++) {
                    const option = document.createElement('option');
                    option.value = i.toString();
                    option.textContent = `${i}등급`;
                    select.appendChild(option);
                }
                
                if (currentValue && currentValue <= maxGrade) {
                    select.value = currentValue;
                }
            });
        }

        // 이벤트 리스너 설정
        function setupEventListeners() {
            // 등급제 변경
            document.querySelectorAll('input[name="gradeSystem"]').forEach(radio => {
                radio.addEventListener('change', function() {
                    updateGradeOptions(this.value);
                    updateAllAverages();
                });
            });

            // 성적 입력 시 평균 업데이트
            const gradeInputs = [
                'grade1_mid', 'grade1_final',
                'grade2_mid', 'grade2_final',
                'grade3_mid', 'grade3_final'
            ];

            gradeInputs.forEach(id => {
                const element = document.getElementById(id);
                if (element) {
                    element.addEventListener('change', updateAllAverages);
                }
            });

            // 검색 버튼
            document.getElementById('searchBtn').addEventListener('click', performSearch);

            // 탭 버튼
            document.querySelectorAll('.tab-button').forEach(button => {
                button.addEventListener('click', function() {
                    switchTab(this.dataset.tab);
                });
            });
        }

        // 모든 평균 업데이트
        function updateAllAverages() {
            updateYearAverage(1);
            updateYearAverage(2);
            updateYearAverage(3);
        }

        // 학년별 평균 계산 및 표시
        function updateYearAverage(year) {
            const midValue = document.getElementById(`grade${year}_mid`).value;
            const finalValue = document.getElementById(`grade${year}_final`).value;

            if (midValue && finalValue) {
                const average = (parseInt(midValue) + parseInt(finalValue)) / 2;
                document.getElementById(`avg${year}`).innerHTML = `${year}학년 평균: <strong>${average.toFixed(2)}</strong>`;
            } else {
                document.getElementById(`avg${year}`).innerHTML = `${year}학년 평균: -`;
            }
        }

        // 지원 가능 대학 검색
        function performSearch() {
            const grade1_mid = document.getElementById('grade1_mid').value;
            const grade1_final = document.getElementById('grade1_final').value;
            const grade2_mid = document.getElementById('grade2_mid').value;
            const grade2_final = document.getElementById('grade2_final').value;
            const grade3_mid = document.getElementById('grade3_mid').value;
            const grade3_final = document.getElementById('grade3_final').value;
            const applicationMethods = Array.from(document.querySelectorAll('input[name="applicationMethod"]:checked'))
                .map(cb => cb.value);

            if (!grade1_mid || !grade1_final || !grade2_mid || !grade2_final || !grade3_mid || !grade3_final || applicationMethods.length === 0) {
                alert('모든 성적을 입력해주세요.\n- 1~3학년 중간/기말고사 등급\n- 지원 방식 선택');
                return;
            }

            // 연도별 평균
            const avg1 = (parseInt(grade1_mid) + parseInt(grade1_final)) / 2;
            const avg2 = (parseInt(grade2_mid) + parseInt(grade2_final)) / 2;
            const avg3 = (parseInt(grade3_mid) + parseInt(grade3_final)) / 2;

            // 전체 평균 (3학년을 좀 더 가중치 있게)
            const totalAverage = (avg1 + avg2 + avg3 * 1.5) / 3.5;

            // 결과 분류
            const results = classifyUniversities(totalAverage, applicationMethods);

            // 결과 표시
            displayResults(results, avg1, avg2, avg3, totalAverage);
        }

        // 대학 분류
        function classifyUniversities(totalAverage, applicationMethods) {
            const suitable = [];
            const moderate = [];
            const risky = [];

            const allUniversities = [
                ...universitiesData.top,
                ...universitiesData.upper,
                ...universitiesData.middle,
                ...universitiesData.lower,
            ];

            allUniversities.forEach(uni => {
                const hasMatchingMethod = uni.type.some(t => 
                    (t === '정시' && applicationMethods.includes('regular')) ||
                    (t === '수시' && applicationMethods.includes('early'))
                );

                if (!hasMatchingMethod) return;

                const gradeDifference = Math.abs(uni.average - totalAverage);

                if (gradeDifference <= 0.5) {
                    suitable.push(uni);
                } else if (gradeDifference <= 1.0) {
                    moderate.push(uni);
                } else if (gradeDifference <= 1.5) {
                    risky.push(uni);
                }
            });

            return { suitable, moderate, risky };
        }

        // 결과 표시
        function displayResults(results, avg1, avg2, avg3, totalAverage) {
            document.getElementById('resultsSection').style.display = 'block';

            // 요약 정보 표시
            document.getElementById('summaryGrade1').textContent = avg1.toFixed(2);
            document.getElementById('summaryGrade2').textContent = avg2.toFixed(2);
            document.getElementById('summaryGrade3').textContent = avg3.toFixed(2);
            document.getElementById('summaryGradeTotal').textContent = totalAverage.toFixed(2);

            // 결과 카드 표시
            displayUniversityCards('suitableList', results.suitable);
            displayUniversityCards('moderateList', results.moderate);
            displayUniversityCards('riskyList', results.risky);

            switchTab('suitable');
            
            setTimeout(() => {
                document.getElementById('resultsSection').scrollIntoView({ behavior: 'smooth' });
            }, 100);
        }

        // 대학 카드 표시
        function displayUniversityCards(containerId, universities) {
            const container = document.getElementById(containerId);
            
            if (universities.length === 0) {
                container.innerHTML = '<div class="empty-message">해당하는 대학이 없습니다.</div>';
                return;
            }

            container.innerHTML = universities.map(uni => `
                <div class="university-card" onclick="window.open('${uni.link}', '_blank')">
                    <div class="university-name">${uni.name}</div>
                    <div class="university-info">
                        <strong>평균 등급:</strong> ${uni.average.toFixed(2)}등급
                    </div>
                    <div class="university-info">
                        <strong>지원 방식:</strong> ${uni.type.join(', ')}
                    </div>
                </div>
            `).join('');
        }

        // 탭 전환
        function switchTab(tab) {
            document.querySelectorAll('.tab-button').forEach(btn => btn.classList.remove('active'));
            document.querySelectorAll('.result-tab-content').forEach(content => content.classList.remove('active'));

            document.querySelector(`[data-tab="${tab}"]`).classList.add('active');
            document.getElementById(`${tab}-tab`).classList.add('active');
        }
    </script>
</body>
</html>
