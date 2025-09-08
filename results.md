---
layout: page
title: 📝 설문조사 결과
permalink: /results/
---

<html lang="ko">
<head>
    <meta charset="UTF-8">
    <style>
        body {
            font-family: 'Malgun Gothic', sans-serif;
            margin: 20px;
        }
        h1 {
            border-bottom: 2px solid #007bff;
            padding-bottom: 10px;
        }
        #results-container {
            background-color: #f8f9fa;
            border: 1px solid #dee2e6;
            padding: 20px;
            border-radius: 5px;
            white-space: pre-wrap; /* JSON 코드가 예쁘게 보이도록 설정 */
            line-height: 1.8;
        }
    </style>
</head>
<body>

    <div id="results-container">
        결과를 불러오는 중입니다...
    </div>

    <script>
        // 페이지가 로드되면 바로 실행
        window.onload = () => {
            const resultsContainer = document.getElementById('results-container');
            
            // 1. LocalStorage에서 'surveyResults' 데이터 가져오기
            const savedDataJSON = localStorage.getItem('surveyResults');

            if (savedDataJSON) {
                // 2. 데이터가 있다면, JSON 문자열을 다시 객체로 변환
                const savedData = JSON.parse(savedDataJSON);
                
                // 3. 보기 좋게 포맷팅하여 화면에 출력
                // JSON.stringify의 세 번째 인자는 들여쓰기 칸 수
                // resultsContainer.textContent = JSON.stringify(savedData, null, 2);

                // (선택) 사용 후 저장된 데이터 삭제하기
                // localStorage.removeItem('surveyResults'); 
            } else {
                // 4. 저장된 데이터가 없다면 메시지 출력
                resultsContainer.textContent = '저장된 설문 결과가 없습니다. 설문 페이지에서 먼저 응답을 제출해주세요.';
            }
        };
    </script>

</body>
</html>