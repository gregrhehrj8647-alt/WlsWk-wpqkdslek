<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>대학 입시 성적 조회 - 나의 대학 찾기</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <!-- 헤더 -->
        <header class="header">
            <h1>🎓 나의 대학 찾기</h1>
            <p>성적 등급으로 지원 가능한 대학교를 찾아보세요</p>
        </header>

        <!-- 메인 컨텐츠 -->
        <main class="main-content">
            <!-- 성적 입력 섹션 -->
            <section class="input-section">
                <h2>성적 입력</h2>
                
                <!-- 등급제 선택 -->
                <div class="grade-system">
                    <label>
                        <input type="radio" name="gradeSystem" value="9" checked> 9등급제
                    </label>
                    <label>
                        <input type="radio" name="gradeSystem" value="5"> 5등급제
                    </label>
                </div>

                <!-- 성적 입력 폼 -->
                <div class="score-input-group">
                    <div class="score-input">
                        <label for="koreanGrade">국어 등급</label>
                        <select id="koreanGrade">
                            <option value="">선택하세요</option>
                        </select>
                    </div>
                    
                    <div class="score-input">
                        <label for="mathGrade">수학 등급</label>
                        <select id="mathGrade">
                            <option value="">선택하세요</option>
                        </select>
                    </div>
                    
                    <div class="score-input">
                        <label for="englishGrade">영어 등급</label>
                        <select id="englishGrade">
                            <option value="">선택하세요</option>
                        </select>
                    </div>

                    <div class="score-input">
                        <label for="elective1">선택과목 1</label>
                        <select id="elective1">
                            <option value="">선택하세요</option>
                        </select>
                    </div>

                    <div class="score-input">
                        <label for="elective2">선택과목 2</label>
                        <select id="elective2">
                            <option value="">선택하세요</option>
                        </select>
                    </div>
                </div>

                <!-- 지원 방식 선택 -->
                <div class="application-type">
                    <label>
                        <input type="checkbox" name="applicationMethod" value="regular" checked> 정시
                    </label>
                    <label>
                        <input type="checkbox" name="applicationMethod" value="early"> 수시
                    </label>
                </div>

                <!-- 검색 버튼 -->
                <button id="searchBtn" class="search-btn">🔍 지원 가능 대학 검색</button>
            </section>

            <!-- 결과 섹션 -->
            <section class="results-section" id="resultsSection" style="display: none;">
                <h2>검색 결과</h2>
                
                <!-- 성적 정보 요약 -->
                <div class="grade-summary">
                    <p id="gradeSummary"></p>
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
                <div class="grade-info">
                    <div class="grade-chart">
                        <h3>9등급제 비율</h3>
                        <table class="grade-table">
                            <tr>
                                <td>1등급</td><td>2등급</td><td>3등급</td><td>4등급</td><td>5등급</td>
                                <td>6등급</td><td>7등급</td><td>8등급</td><td>9등급</td>
                            </tr>
                            <tr>
                                <td>4%</td><td>7%</td><td>12%</td><td>17%</td><td>20%</td>
                                <td>17%</td><td>12%</td><td>7%</td><td>4%</td>
                            </tr>
                        </table>
                    </div>
                    <div class="grade-chart">
                        <h3>5등급제 비율</h3>
                        <table class="grade-table">
                            <tr>
                                <td>1등급</td><td>2등급</td><td>3등급</td><td>4등급</td><td>5등급</td>
                            </tr>
                            <tr>
                                <td>10%</td><td>24%</td><td>32%</td><td>24%</td><td>10%</td>
                            </tr>
                        </table>
                    </div>
                </div>
            </section>
        </main>

        <!-- 푸터 -->
        <footer class="footer">
            <p>참고: 대입정보포털 어디가, 진학사, 대학입결검색기 등의 데이터를 기반으로 합니다.</p>
            <p>최종 지원은 각 대학교 공식 홈페이지에서 확인하시기 바랍니다.</p>
        </footer>
    </div>

    <script src="script.js"></script>
</body>
</html>
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
    max-width: 1000px;
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
    margin-bottom: 20px;
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

.score-input-group {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 15px;
    margin-bottom: 20px;
}

.score-input {
    display: flex;
    flex-direction: column;
}

.score-input label {
    margin-bottom: 8px;
    font-weight: bold;
    color: #333;
}

.score-input select {
    padding: 12px;
    border: 2px solid #ddd;
    border-radius: 5px;
    font-size: 1em;
    cursor: pointer;
    transition: border-color 0.3s;
}

.score-input select:hover,
.score-input select:focus {
    border-color: #667eea;
    outline: none;
}

.application-type {
    display: flex;
    gap: 20px;
    margin-bottom: 20px;
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

.grade-summary p {
    font-size: 1.1em;
    color: #333;
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

.grade-info {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
}

.grade-chart {
    background: white;
    padding: 20px;
    border-radius: 8px;
    border-left: 5px solid #667eea;
}

.grade-chart h3 {
    margin-bottom: 15px;
    color: #333;
}

.grade-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.9em;
}

.grade-table tr:first-child {
    background: #f0f0f0;
    font-weight: bold;
}

.grade-table td {
    padding: 10px;
    text-align: center;
    border: 1px solid #ddd;
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

    .score-input-group {
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
}
// 샘플 대학 데이터 (실제로는 API나 데이터베이스에서 가져와야 함)
const universitiesData = {
    // 상위권 대학 (1~2등급)
    top: [
        { name: '서울대학교', average: 1.2, type: ['정시', '수시'], link: 'https://www.snu.ac.kr' },
        { name: '고려대학교', average: 1.5, type: ['정시', '수시'], link: 'https://www.korea.ac.kr' },
        { name: '연세대학교', average: 1.5, type: ['정시', '수시'], link: 'https://www.yonsei.ac.kr' },
        { name: 'KAIST', average: 1.3, type: ['정시', '수시'], link: 'https://www.kaist.ac.kr' },
        { name: 'POSTECH', average: 1.4, type: ['정시', '수시'], link: 'https://www.postech.ac.kr' },
    ],
    // 중상위권 대학 (2~3등급)
    upper: [
        { name: '서강대학교', average: 2.0, type: ['정시', '수시'], link: 'https://www.sogang.ac.kr' },
        { name: '성균관대학교', average: 2.0, type: ['정시', '수시'], link: 'https://www.skku.edu' },
        { name: '한양대학교', average: 2.0, type: ['정시', '수시'], link: 'https://www.hanyang.ac.kr' },
        { name: '중앙대학교', average: 2.5, type: ['정시', '수시'], link: 'https://www.cau.ac.kr' },
        { name: '경희대학교', average: 2.5, type: ['정시', '수시'], link: 'https://www.khu.ac.kr' },
    ],
    // 중위권 대학 (3~4등급)
    middle: [
        { name: '이화여자대학교', average: 2.8, type: ['정시', '수시'], link: 'https://www.ewha.ac.kr' },
        { name: '숙명여자대학교', average: 3.0, type: ['정시', '수시'], link: 'https://www.sookmyung.ac.kr' },
        { name: '시립대학교', average: 3.2, type: ['정시'], link: 'https://www.uos.ac.kr' },
        { name: '부산대학교', average: 3.5, type: ['정시', '수시'], link: 'https://www.pusan.ac.kr' },
        { name: '광주과학기술원', average: 3.3, type: ['정시'], link: 'https://www.gist.ac.kr' },
    ],
    // 중하위권 대학 (4~5등급)
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
    9: {
        grades: 9,
        percentages: [4, 7, 12, 17, 20, 17, 12, 7, 4],
    },
    5: {
        grades: 5,
        percentages: [10, 24, 32, 24, 10],
    },
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
    const maxGrade = gradeSystemData[system].grades;
    const selects = ['koreanGrade', 'mathGrade', 'englishGrade', 'elective1', 'elective2'];
    
    selects.forEach(id => {
        const select = document.getElementById(id);
        const currentValue = select.value;
        select.innerHTML = '<option value="">선택하세요</option>';
        
        for (let i = 1; i <= maxGrade; i++) {
            const option = document.createElement('option');
            option.value = i;
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
        });
    });

    // 검색 버튼
    document.getElementById('searchBtn').addEventListener('click', performSearch);

    // 탭 버튼
    document.querySelectorAll('.tab-button').forEach(button => {
        button.addEventListener('click', function() {
            const tab = this.dataset.tab;
            switchTab(tab);
        });
    });
}

// 지원 가능 대학 검색
function performSearch() {
    const koreanGrade = parseInt(document.getElementById('koreanGrade').value);
    const mathGrade = parseInt(document.getElementById('mathGrade').value);
    const englishGrade = parseInt(document.getElementById('englishGrade').value);
    const gradeSystem = document.querySelector('input[name="gradeSystem"]:checked').value;
    const applicationMethods = Array.from(document.querySelectorAll('input[name="applicationMethod"]:checked'))
        .map(cb => cb.value);

    // 입력 검증
    if (!koreanGrade || !mathGrade || !englishGrade || applicationMethods.length === 0) {
        alert('모든 필수 정보를 입력해주세요.');
        return;
    }

    // 평균 등급 계산
    const averageGrade = (koreanGrade + mathGrade + englishGrade) / 3;

    // 결과 분류
    const results = classifyUniversities(averageGrade, applicationMethods);

    // 결과 표시
    displayResults(results, averageGrade, gradeSystem);
}

// 대학 분류
function classifyUniversities(averageGrade, applicationMethods) {
    const suitable = [];
    const moderate = [];
    const risky = [];

    // 모든 대학 데이터 통합
    const allUniversities = [
        ...universitiesData.top,
        ...universitiesData.upper,
        ...universitiesData.middle,
        ...universitiesData.lower,
    ];

    allUniversities.forEach(uni => {
        // 지원 방식 필터링
        const hasMatchingMethod = uni.type.some(t => 
            (t === '정시' && applicationMethods.includes('regular')) ||
            (t === '수시' && applicationMethods.includes('early'))
        );

        if (!hasMatchingMethod) return;

        const gradeDifference = Math.abs(uni.average - averageGrade);

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
function displayResults(results, averageGrade, gradeSystem) {
    // 결과 섹션 보이기
    document.getElementById('resultsSection').style.display = 'block';

    // 성적 요약
    const gradeSummaryText = `
        평균 등급: <strong>${averageGrade.toFixed(2)}등급</strong> 
        (${gradeSystem}등급제)
    `;
    document.getElementById('gradeSummary').innerHTML = gradeSummaryText;

    // 결과 카드 표시
    displayUniversityCards('suitableList', results.suitable, '지원 가능 대학');
    displayUniversityCards('moderateList', results.moderate, '중위험 대학');
    displayUniversityCards('riskyList', results.risky, '고위험 대학');

    // 첫 탭 활성화
    switchTab('suitable');

    // 페이지 스크롤
    document.getElementById('resultsSection').scrollIntoView({ behavior: 'smooth' });
}

// 대학 카드 표시
function displayUniversityCards(containerId, universities, title) {
    const container = document.getElementById(containerId);
    
    if (universities.length === 0) {
        container.innerHTML = `<div class="empty-message">해당하는 ${title}이 없습니다.</div>`;
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
            <div class="university-info" style="color: #999; font-size: 0.8em;">
                클릭하면 대학 홈페이지로 이동합니다
            </div>
        </div>
    `).join('');
}

// 탭 전환
function switchTab(tab) {
    // 모든 탭 버튼 비활성화
    document.querySelectorAll('.tab-button').forEach(btn => {
        btn.classList.remove('active');
    });

    // 모든 탭 컨텐츠 숨기기
    document.querySelectorAll('.result-tab-content').forEach(content => {
        content.classList.remove('active');
    });

    // 선택한 탭 활성화
    document.querySelector(`[data-tab="${tab}"]`).classList.add('active');
    document.getElementById(`${tab}-tab`).classList.add('active');
}
