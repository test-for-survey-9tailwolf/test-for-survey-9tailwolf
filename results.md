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
        body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif; background-color: #f8f9fa; color: #212529; margin: 0; padding: 20px; }
        .container { max-width: 800px; margin: 0 auto; background-color: #ffffff; padding: 20px 30px; border-radius: 12px; box-shadow: 0 4px 25px rgba(0,0,0,0.1); }
        h1, h2 { color: #0d6efd; border-bottom: 2px solid #dee2e6; padding-bottom: 10px; margin-top: 30px; margin-bottom: 20px; }
        .final-result-box { text-align: center; padding: 30px 20px; }
        .final-result-box p { margin: 0; font-size: 1.2em; color: #495057; }
        .final-result-box .result-type { font-size: 2.8em; font-weight: bold; color: #0d6efd; margin: 10px 0; }
        .info-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; }
        .info-grid p { background-color: #e9ecef; padding: 15px; border-radius: 8px; margin: 0; font-size: 1.1em; }
        .info-grid p strong { color: #0d6efd; margin-right: 8px; }
        #saveBtn {
            display: block; width: 100%; max-width: 500px; margin: 40px auto 20px; padding: 15px;
            font-size: 1.2em; font-weight: bold; background-color: #198754; color: white;
            border: none; border-radius: 8px; cursor: pointer; transition: background-color 0.2s;
        }
        #saveBtn:hover { background-color: #157347; }
        #saveBtn:disabled { background-color: #6c757d; cursor: not-allowed; }
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
            <button id="saveBtn">분석 결과 데이터 수집에 동의 및 제출</button>
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

                // 필수 데이터가 없는 경우 오류 처리
                if (isNaN(probabilities.tae_eum)) {
                    throw new Error('분석 데이터가 URL에 포함되지 않았습니다.');
                }

                // 2. 기본 정보 표시
                document.getElementById('age').textContent = `${params.get('age')} 세`;
                document.getElementById('gender').textContent = params.get('gender');
                document.getElementById('height').textContent = `${params.get('height')} cm`;
                document.getElementById('weight').textContent = `${params.get('weight')} kg`;

                // 3. 확률 분포 표시
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
                
                // 6. "결과 수집" 버튼 이벤트 리스너 추가
                const saveBtn = document.getElementById('saveBtn');
                saveBtn.addEventListener('click', () => {
                    // Google Sheets에 저장할 데이터 객체 생성
                    const dataToSend = {
                        gender: params.get('gender'),
                        birthdate: params.get('birthdate'),
                        height: params.get('height'),
                        weight: params.get('weight')
                    };
                    for (let i = 1; i <= 14; i++) {
                        dataToSend[`q${i}`] = params.get(`q${i}`);
                    }

                    const GOOGLE_SCRIPT_URL = "https://script.google.com/macros/s/AKfycbzNkvAPAMzxnXAsG3hG-_9eooR-Dj4TiKxkXxPEcxlEAzNNvaYTvjAWPBUsF06uRXUx4w/exec";
                    
                    saveBtn.disabled = true;
                    saveBtn.textContent = "저장 중...";

                    fetch(GOOGLE_SCRIPT_URL, {
                        method: 'POST',
                        body: JSON.stringify(dataToSend),
                        headers: { 'Content-Type': 'application/json' }
                    })
                    .then(response => response.json())
                    .then(data => {
                        if(data.result === 'success') {
                            alert("소중한 데이터 감사드립니다. 설문 데이터가 성공적으로 제출되었습니다.");
                            saveBtn.textContent = "제출 완료";
                        } else {
                            throw new Error('데이터 저장에 실패했습니다.');
                        }
                    })
                    .catch(error => {
                        console.error("전송 오류:", error);
                        alert(`오류가 발생하여 데이터가 제출되지 않았습니다: ${error.message}`);
                        saveBtn.disabled = false;
                        saveBtn.textContent = "분석 결과 데이터 수집에 동의 및 제출";
                    });
                });

            } catch (error) {
                console.error("결과 페이지 오류:", error);
                document.querySelector('.container').innerHTML = `<h1>오류</h1><p>${error.message}</p>`;
            }
        };
    </script>
</body>
</html>