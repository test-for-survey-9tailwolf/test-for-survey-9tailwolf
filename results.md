---
layout: page
title: 📝 설문조사 결과
permalink: /results/
---



<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>체질 분석 최종 결과</title>
    <style>
        body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif; background-color: #f8f9fa; color: #212529; margin: 0;}
        .container { max-width: 800px; margin: 0 auto; background-color: #ffffff; padding: 20px 30px; border-radius: 12px; box-shadow: 0 4px 25px rgba(0,0,0,0.1); }
        h1, h2 { color: #0d6efd; border-bottom: 2px solid #dee2e6; padding-bottom: 10px; margin-top: 30px; margin-bottom: 20px; }
        .final-result-box { text-align: center; padding: 30px 20px; }
        .final-result-box p { margin: 0; font-size: 1.2em; color: #495057; }
        .final-result-box .result-type { font-size: 2.8em; font-weight: bold; color: #0d6efd; margin: 10px 0; }
        .info-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; }
        .info-grid p { background-color: #e9ecef; padding: 15px; border-radius: 8px; margin: 0; font-size: 1.1em; }
        .info-grid p strong { color: #0d6efd; margin-right: 8px; }
    </style>
</head>
<body>
    <div class="container">
        <div class="section final-result-box">
            <p>당신의 체질 분석 결과는</p>
            <h1 id="final-result-type" class="result-type">분석 중...</h1>
            <p>입니다.</p>
        </div>
        
        <div class="section">
            <h2>체질 확률 분포</h2>
            <div class="info-grid">
                <p><strong>태음인 확률:</strong> <span id="tae-eum-prob"></span></p>
                <p><strong>소음인 확률:</strong> <span id="so-eum-prob"></span></p>
                <p><strong>소양인 확률:</strong> <span id="so-yang-prob"></span></p>
            </div>
        </div>

        <div class="section">
            <h2>진단 기본 정보</h2>
            <div class="info-grid">
                <p><strong>나이:</strong> <span id="age"></span></p>
                <p><strong>성별:</strong> <span id="gender"></span></p>
                <p><strong>신장:</strong> <span id="height"></span></p>
                <p><strong>체중:</strong> <span id="weight"></span></p>
            </div>
        </div>
    </div>

    <script>
        window.onload = () => {
            try {
                // 1. URL에서 쿼리 파라미터 읽기
                const params = new URLSearchParams(window.location.search);
                const probabilities = {
                    tae_eum: parseFloat(params.get('p_te')),
                    so_eum: parseFloat(params.get('p_se')),
                    so_yang: parseFloat(params.get('p_sy'))
                };

                // 데이터가 하나라도 없으면 에러 처리
                if (!probabilities.tae_eum && probabilities.tae_eum !== 0) {
                    throw new Error('분석 데이터가 URL에 포함되지 않았습니다.');
                }

                // 2. 기본 정보 표시
                document.getElementById('age').textContent = `${params.get('age')} 세`;
                document.getElementById('gender').textContent = decodeURIComponent(params.get('gender'));
                document.getElementById('height').textContent = `${params.get('height')} cm`;
                document.getElementById('weight').textContent = `${params.get('weight')} kg`;

                // 3. 확률 분포 표시 (백분율)
                document.getElementById('tae-eum-prob').textContent = `${(probabilities.tae_eum * 100).toFixed(2)} %`;
                document.getElementById('so-eum-prob').textContent = `${(probabilities.so_eum * 100).toFixed(2)} %`;
                document.getElementById('so-yang-prob').textContent = `${(probabilities.so_yang * 100).toFixed(2)} %`;

                // 4. 가장 높은 확률의 체질 찾기
                let maxProb = -1;
                let finalType = '알 수 없음';
                const typeNames = { tae_eum: '태음인 (太陰人)', so_eum: '소음인 (少陰人)', so_yang: '소양인 (少陽人)' };

                for (const type in probabilities) {
                    if (probabilities[type] > maxProb) {
                        maxProb = probabilities[type];
                        finalType = typeNames[type];
                    }
                }

                // 5. 최종 결과 출력
                document.getElementById('final-result-type').textContent = finalType;

            } catch (error) {
                console.error("결과 페이지 오류:", error);
                document.querySelector('.container').innerHTML = `<h1>오류</h1><p>${error.message}</p>`;
            }
        };
    </script>
</body>
</html>