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
