---
layout: home
title:
---


<html lang="ko">
<head>
    <style>
        body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif; background-color: #f8f9fa; color: #212529; margin: 0;}
        .wrapper { max-width: 900px; margin: auto; padding: 20px; } /* 콘텐츠 너비 및 중앙 정렬 */

        /* 기본 정보 테이블 스타일 */
        .info-table { width: 100%; border-collapse: collapse; margin-bottom: 30px; }
        .info-table td { border: 1px solid #dee2e6; padding: 15px; }
        .info-table td:nth-child(odd) { background-color: #f8f9fa; font-weight: 500; width: 20%; }
        .input-group input { width: 60px; text-align: right; padding: 5px; border: 1px solid #ccc; border-radius: 4px; }

        input[type="number"]::-webkit-outer-spin-button,
        input[type="number"]::-webkit-inner-spin-button {
            -webkit-appearance: none;
            margin: 0;
        }
        input[type="number"] {
            -moz-appearance: textfield;
        }
        .info-table td:nth-child(2) {
        text-align: center;         
        }

        #submitBtn {
            display: block; width: 50%; max-width: 400px; margin: 40px auto; padding: 20px;
            font-size: 1.5em; font-weight: bold; background-color: #007bff; color: white;
            border: none; border-radius: 12px; cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 123, 255, 0.3);
            transition: all 0.2s ease-in-out;
        }
        #submitBtn:hover {
            background-color: #0056b3; transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(0, 123, 255, 0.4);
        }

        
        /* 목록 형태 질문 스타일 */
        .question-list-intro { font-weight: bold; margin-top: 30px; }
        .question-item {
            margin-bottom: 20px;
            padding: 20px;
            background-color: #f8f9fa;
            border: 1px solid #dee2e6;
            border-radius: 8px;
        }
        .question-text {
            font-weight: 500;
            margin: 0 0 15px 0;
            font-size: 1.1em;
        }
        .options-group label {
            display: block; /* 선택지를 세로로 나열 */
            margin-bottom: 8px;
            cursor: pointer;
            padding: 10px;
            border-radius: 5px;
            transition: background-color 0.2s;
            background-color: #fff;
            border: 1px solid #e0e0e0;
        }
        .options-group label:hover {
            background-color: #e9ecef;
        }
        /* 라디오 버튼을 선택했을 때 라벨 스타일 변경 (선택사항) */
        .options-group input[type="radio"]:checked + span {
            font-weight: bold;
            color: #0d6efd;
        }
        /* 실제 라디오 버튼은 숨김 (선택사항) */
        .options-group input[type="radio"] {
             display: none;
        }
    </style>
</head>

<body>
    <h2><strong>기본 인적 사항</strong></h2>
    <table class="info-table">
        <tr>
            <td><strong>생년월일</strong></td>
            <td colspan="3">
                <input type="text" id="birthdate" inputmode="numeric" maxlength="6" placeholder="예) 950909" style="width: 160px; padding: 5px;">
            </td>
        </tr>
        <tr>
            <td><strong>성별</strong></td>
            <td colspan="3">
                <div class="radio-group">
                    <label><input type="radio" name="gender" value="male"> 남성</label>
                    <label><input type="radio" name="gender" value="female"> 여성</label>
                </div>
            </td>
        </tr>
        <tr>
            <td><strong>신장</strong></td>
            <td>
                <div class="input-group"><input type="number" id="height"> cm</div>
            </td>
            <td><strong>체중</strong></td>
            <td>
                <div class="input-group"><input type="number" id="weight"> kg</div>
            </td>
        </tr>
    </table>

    <br>
    <h2><strong>성격</strong></h2>
    <p class="question-list-intro">⇨ <strong>평소 성격</strong>에 대한 질문입니다. 자신에게 더 가깝다고 생각하는 답변을 선택(✔)해 주세요.</p> 
    
    <div class="question-item">
        <p class="question-text">1. 성격이 대범하신가요? 섬세하신가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q1" value="1"><span> ① 대범</span></label>
            <label><input type="radio" name="q1" value="2"><span> ② 중간</span></label>
            <label><input type="radio" name="q1" value="3"><span> ③ 섬세</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">2. 행동이 빠른 편인가요? 느린 편인가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q2" value="1"><span> ① 빠르다</span></label>
            <label><input type="radio" name="q2" value="2"><span> ② 중간</span></label>
            <label><input type="radio" name="q2" value="3"><span> ③ 느리다</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">3. 모든 일에 적극적인가요? 소극적인가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q3" value="1"><span> ① 적극적</span></label>
            <label><input type="radio" name="q3" value="2"><span> ② 중간</span></label>
            <label><input type="radio" name="q3" value="3"><span> ③ 소극적</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">4. 성격이 외향적인가요? 내성적인가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q4" value="1"><span> ① 외향</span></label>
            <label><input type="radio" name="q4" value="2"><span> ② 중간</span></label>
            <label><input type="radio" name="q4" value="3"><span> ③ 내성</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">5. 남성적인 편인가요? 여성적인 편인가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q5" value="1"><span> ① 남성적</span></label>
            <label><input type="radio" name="q5" value="2"><span> ② 중간</span></label>
            <label><input type="radio" name="q5" value="3"><span> ③ 여성적</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">6. 가끔 흥분하는 편인가요? 이성적인 편인가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q6" value="1"><span> ① 흥분</span></label>
            <label><input type="radio" name="q6" value="2"><span> ② 중간</span></label>
            <label><input type="radio" name="q6" value="3"><span> ③ 이성</span></label>
        </div>
    </div>


    <br><br>
    <h2><strong>생활</strong></h2>
    <p class="question-list-intro">⇨ <strong>최근 6개월 내</strong> 본인의 생활 증상에 대한 질문입니다. 해당되는 답변을 선택(✔)해 주세요.</p>
    
    <div class="question-item">
        <p class="question-text">7. 평소 소화는 어떠한가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q7" value="1"><span> ① 소화가 잘 된다</span></label>
            <label><input type="radio" name="q7" value="2"><span> ② 소화가 잘 안되지만 불편하지 않다</span></label>
            <label><input type="radio" name="q7" value="3"><span> ③ 소화가 안되고 불편함도 느낀다</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">8. 평소 입맛은 어떠한가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q8" value="1"><span> ① 좋은 편이다</span></label>
            <label><input type="radio" name="q8" value="2"><span> ② 중간이다</span></label>
            <label><input type="radio" name="q8" value="3"><span> ③ 안 좋은 편이다</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">9. 평소 땀을 어느 정도 흘리는 편인가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q9" value="1"><span> ① 많다</span></label>
            <label><input type="radio" name="q9" value="2"><span> ② 중간</span></label>
            <label><input type="radio" name="q9" value="3"><span> ③ 적다</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">10. 땀을 흘리고 난 뒤 기분이 어떠한가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q10" value="1"><span> ① 상쾌하다</span></label>
            <label><input type="radio" name="q10" value="2"><span> ② 피곤하다</span></label>
            <label><input type="radio" name="q10" value="3"><span> ③ 아무느낌 없다</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">11. 대변이 마려운 신호가 왔을 때 참기 어려운가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q11" value="1"><span> ① 자주 그렇다</span></label>
            <label><input type="radio" name="q11" value="2"><span> ② 가끔 그렇다</span></label>
            <label><input type="radio" name="q11" value="3"><span> ③ 없다(어렵지 않다)</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">12. 밤(잠을 잘 때)에 소변을 몇 회 보나요?</p>
        <div class="options-group">
            <label><input type="radio" name="q12" value="1"><span> ① 0회</span></label>
            <label><input type="radio" name="q12" value="2"><span> ② 1회</span></label>
            <label><input type="radio" name="q12" value="3"><span> ③ 2회이상</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">13. 평소 추위, 더위 어느 것이 더 싫은가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q13" value="1"><span> ① 추위</span></label>
            <label><input type="radio" name="q13" value="2"><span> ② 더위</span></label>
            <label><input type="radio" name="q13" value="3"><span> ③ 모두 싫거나 모두 괜찮다</span></label>
        </div>
    </div>
    <div class="question-item">
        <p class="question-text">14. 평소 마시는 물의 온도는 어떠한 가요?</p>
        <div class="options-group">
            <label><input type="radio" name="q14" value="1"><span> ① 주로 따뜻한 물</span></label>
            <label><input type="radio" name="q14" value="2"><span> ② 주로 찬물</span></label>
            <label><input type="radio" name="q14" value="3"><span> ③ 가리지 않고 마신다</span></label>
        </div>
    </div>



    <button id="submitBtn">결과 보기 🚀</button>

<script>
    // =======================================================================
    // 데이터 영역: 모든 계산에 필요한 가중치 및 계수 데이터
    // =======================================================================

    // 1. 연령별 BMI 가중치 데이터
    const weightsByAge = {
        '8': { male: 6.51, female: 5.34 }, '9': { male: 5.90, female: 5.78 }, '10': { male: 5.26, female: 4.04 },
        '11': { male: 4.55, female: 6.11 }, '12': { male: 3.44, female: 4.57 }, '13': { male: 4.77, female: 6.22 },
        '14': { male: 2.86, female: 2.77 }, '15': { male: 3.93, female: 2.72 }, '16-20': { male: 2.12, female: 1.29 },
        '21-25': { male: 0.75, female: 1.93 }, '26-30': { male: -0.12, female: 1.83 }, '31-35': { male: -0.32, female: 1.18 },
        '36-40': { male: -0.59, female: 0.52 }, '41-45': { male: -0.68, female: -0.19 }, '46-50': { male: -0.69, female: -0.27 },
        '51-55': { male: -0.50, female: -0.70 }, '56-60': { male: -0.36, female: -0.95 }, '61-65': { male: -0.21, female: -1.06 },
        '66-70': { male: 0.12, female: -1.30 }, '71+': { male: 0.78, female: -1.00 }
    };

    // 2. 체질 분석 점수(A) 가중치 데이터
    const scoresData = {
        male: {
            q1: { '1': { tae_eum: 1.621, so_eum: -5.496, so_yang: 1.444 }, '3': { tae_eum: -3.507 } },
            q2: { '1': { tae_eum: -6.467, so_eum: 7.432 }, '2': { tae_eum: 2.521, so_eum: -2.97 }, '3': { tae_eum: 2.829, so_eum: -3.087 } },
            q3: { '1': { so_eum: -5.655, so_yang: 3.969 }, '2': { tae_eum: 1.991, so_eum: -1.521 }, '3': { tae_eum: 3.04, so_eum: -2.04 } },
            q4: { '1': { tae_eum: -3.274, so_eum: 3.923 }, '3': { tae_eum: 2.829, so_eum: -3.087 } },
            q5: { '1': { so_eum: -6.669, so_yang: 1.419 }, '2': { tae_eum: 2.113, so_eum: -3.157 }, '3': { tae_eum: 2.282 } },
            q6: { '1': { tae_eum: -1.77, so_eum: 1.444 }, '3': { so_eum: -1.869 } },
            q7: { '1': { tae_eum: 1.721, so_eum: -4.952, so_yang: -1.596 }, '3': { tae_eum: -3.565, so_eum: 8.435, so_yang: -1.596 } },
            q8: { '1': { tae_eum: -1.721, so_eum: 6.943, so_yang: -1.596 }, '2': { tae_eum: 6.335, so_eum: -8.747 }, '3': { tae_eum: -4.975, so_eum: 6.309 } },
            q9: { '1': { so_eum: -1.342, so_yang: 1.342 }, '3': { tae_eum: 4.861, so_eum: -4.587 } },
            q10: { '1': { tae_eum: -2.895, so_eum: 4.493 }, '2': { tae_eum: 2.186, so_eum: -3.669 }, '3': { tae_eum: -4.997, so_eum: 6.039 } },
            q12: { '1': { so_eum: 1.894 } },
            q13: { '1': { tae_eum: -6.129, so_eum: 6.422 }, '2': { tae_eum: 9.239, so_eum: -7.655 } },
            q14: { '1': { tae_eum: -1.967, so_eum: 3.134 }, '3': { so_eum: -1.368 } }
        },
        female: {
            q1: { '1': { so_eum: 4.496, so_yang: -8.484 }, '2': { tae_eum: -3.576, so_eum: 7.991 }, '3': { so_eum: -2.687, so_yang: 3.946 } },
            q2: { '1': { so_yang: -1.844 }, '2': { tae_eum: 1.342, so_eum: -1.495 }, '3': { tae_eum: -7.163, so_eum: 2.089, so_yang: 2.829 } },
            q3: { '1': { so_eum: 2.711, so_yang: -1.746 }, '2': { so_eum: -7.185, so_yang: 4.404 } },
            q4: { '1': { tae_eum: 5.881, so_eum: -5.836 }, '2': { tae_eum: 4.793, so_eum: -7.32 }, '3': { so_eum: -1.918, so_yang: 1.419 } },
            q5: { '1': { tae_eum: -3.437, so_eum: 12, so_yang: -2.426 }, '2': { tae_eum: -5.61, so_eum: 2.758 }, '3': { so_yang: 3.04 } },
            q6: { '1': { tae_eum: 1.495, so_eum: -1.795 }, '2': { tae_eum: 2.497, so_eum: -5.474 }, '3': { tae_eum: -2.497, so_eum: 7.339 } },
            q7: { '1': { so_eum: -3.839, so_yang: 9.004 }, '2': { tae_eum: 5.656, so_eum: -8.423 }, '3': { tae_eum: -4.838, so_eum: 4.747 } },
            q8: { '1': { tae_eum: 1.991, so_eum: -1.342 }, '2': { tae_eum: 8.259, so_eum: -5.474 } },
            q9: { '1': { tae_eum: -3.772, so_eum: 5.043 }, '2': { tae_eum: 6.714, so_eum: -7.723 }, '3': { tae_eum: -2.592, so_eum: 5.971 } },
            q10: { '1': { tae_eum: -1.596, so_eum: -1.47 }, '2': { so_yang: 2.354 } },
            q11: { '1': { tae_eum: 2.426, so_eum: -1.546 }, '2': { tae_eum: -1.546, so_eum: 2.64 } },
            q12: { '3': { tae_eum: -2.48 } }
        }
    };

    // 3. 성별 회귀계수 데이터
    const logitCoefficients = {
        male: {
            tae_eum: { intercept: -6.467, bmi: 0.281, tae_eum_a: 0.03, so_eum_a: -0.006, so_yang_a: -0.066 },
            so_eum: { intercept: 4.919, bmi: -0.215, tae_eum_a: 0.001, so_eum_a: 0.017, so_yang_a: -0.059 }
        },
        female: {
            tae_eum: { intercept: -8.067, bmi: 0.349, tae_eum_a: 0.014, so_eum_a: -0.004, so_yang_a: -0.066 },
            so_eum: { intercept: 6.107, bmi: -0.294, tae_eum_a: 0.008, so_eum_a: 0.025, so_yang_a: -0.015 }
        }
    };

    // =======================================================================
    // 함수 영역: 계산에 사용될 헬퍼 함수
    // =======================================================================

    // BMI 가중치 계산 함수
    function getWeight(age, gender) {
        for (const ageRange in weightsByAge) {
            if (ageRange.includes('-')) {
                const [start, end] = ageRange.split('-').map(Number);
                if (age >= start && age <= end) return weightsByAge[ageRange][gender];
            } else if (ageRange.includes('+')) {
                if (age >= Number(ageRange.replace('+', ''))) return weightsByAge[ageRange][gender];
            } else {
                if (age == Number(ageRange)) return weightsByAge[ageRange][gender];
            }
        }
        return 0;
    }
    
    // Softmax 함수
    function softmax(logits) {
        const exps = {
            tae_eum: Math.exp(logits.tae_eum),
            so_eum: Math.exp(logits.so_eum),
            so_yang: Math.exp(logits.so_yang)
        };
        const sumExps = exps.tae_eum + exps.so_eum + exps.so_yang;
        return {
            tae_eum: exps.tae_eum / sumExps,
            so_eum: exps.so_eum / sumExps,
            so_yang: exps.so_yang / sumExps
        };
    }

    // =======================================================================
    // 메인 로직: 버튼 클릭 시 모든 검사와 계산을 수행
    // =======================================================================
    document.getElementById('submitBtn').addEventListener('click', () => {
        try {
            // ======================================================
            // 1. 입력값 가져오기
            // ======================================================
            const birthdateInput = document.getElementById('birthdate').value;
            const heightInput = document.getElementById('height').value;
            const weightInput = document.getElementById('weight').value;
            const genderRadio = document.querySelector('input[name="gender"]:checked');

            // ======================================================
            // 2. 유효성 검사
            // ======================================================
            // 기본 정보 입력 여부 확인
            if (!birthdateInput || !heightInput || !weightInput || !genderRadio) {
                throw new Error('생년월일, 성별, 신장, 체중을 모두 입력해주세요.');
            }
            // 생년월일 형식(6자리 숫자) 확인
            if (!/^\d{6}$/.test(birthdateInput)) {
                throw new Error('생년월일을 6자리 숫자로 입력해주세요. (예: 950909)');
            }

            let year = parseInt(birthdateInput.substring(0, 2), 10);
            const month = parseInt(birthdateInput.substring(2, 4), 10) - 1; // JS 월은 0-11
            const day = parseInt(birthdateInput.substring(4, 6), 10);

            // 2000년생 구분
            const currentYearLastTwoDigits = new Date().getFullYear() % 100;
            year += (year > currentYearLastTwoDigits) ? 1900 : 2000;

            // Date 객체 생성
            const birthDate = new Date(year, month, day);

            // 👇 [추가] 유효한 날짜인지 확인
            // 생성된 날짜의 월/일이 입력한 월/일과 다르면 존재하지 않는 날짜임
            if (birthDate.getFullYear() !== year || birthDate.getMonth() !== month || birthDate.getDate() !== day) {
                throw new Error('유효하지 않은 생년월일입니다. 날짜를 다시 확인해주세요.');
            }

            // 만 나이 계산
            const today = new Date();
            let age = today.getFullYear() - birthDate.getFullYear();
            const m = today.getMonth() - birthDate.getMonth();
            if (m < 0 || (m === 0 && today.getDate() < birthDate.getDate())) {
                age--;
            }
            // 신장, 체중이 양수인지 확인
            const height = parseFloat(heightInput);
            const weight = parseFloat(weightInput);
            if (isNaN(height) || height <= 0) throw new Error('신장은 0보다 큰 숫자로 입력해주세요.');
            if (isNaN(weight) || weight <= 0) throw new Error('체중은 0보다 큰 숫자로 입력해주세요.');
            
            // 모든 설문 항목이 체크되었는지 확인
            const totalQuestions = 14;
            for (let i = 1; i <= totalQuestions; i++) {
                // 오타 수정: `q$ {i}` -> `q${i}`
                if (!document.querySelector(`input[name="q${i}"]:checked`)) {
                    const qElement = document.querySelector(`input[name="q${i}"]`);
                    const qText = qElement.closest('.question-item').querySelector('.question-text').innerText.trim();
                    throw new Error(`'${qText}' 항목에 답변해주세요.`);
                }
            }


            // 2. 기본 데이터 수집
            const basicInfo = {
                age,
                height,
                weight,
                // ▼ [수정 2] span 태그 없이 성별 텍스트를 찾는 로직
                gender: { value: genderRadio.value, text: genderRadio.parentElement.textContent.trim() }
            };
            const responses = [];
            document.querySelectorAll('input[type="radio"]:checked:not([name="gender"])').forEach(radio => {
                responses.push({
                    name: radio.name,
                    answer: { value: radio.value }
                });
            });

            // 3. 최종 BMI 계산 (이전과 동일)
            const heightInMeters = basicInfo.height / 100;
            const actualBmi = basicInfo.weight / (heightInMeters * heightInMeters);
            const bmiWeight = getWeight(basicInfo.age, basicInfo.gender.value);
            const weightedBmi = actualBmi + bmiWeight;

            // 4. 체질 분석 점수(A) 계산 (이전과 동일)
            const finalScores = { tae_eum: 0, so_eum: 0, so_yang: 0, tae_yang: 0 };
            const weightsTable = scoresData[basicInfo.gender.value];
            if (weightsTable) {
                responses.forEach(response => {
                    const scores = weightsTable[response.name]?.[response.answer.value];
                    if (scores) {
                        finalScores.tae_eum += scores.tae_eum || 0;
                        finalScores.so_eum += scores.so_eum || 0;
                        finalScores.so_yang += scores.so_yang || 0;
                        finalScores.tae_yang += scores.tae_yang || 0;
                    }
                });
            }

            // 5. Logit 값 계산 (이전과 동일)
            const coeffs = logitCoefficients[basicInfo.gender.value];
            let taeEumLogit = 0, soEumLogit = 0;
            const soYangLogit = 0;
            if (coeffs) {
                const teCoeff = coeffs.tae_eum;
                taeEumLogit = teCoeff.intercept + (teCoeff.bmi * weightedBmi) + (teCoeff.tae_eum_a * finalScores.tae_eum) + (teCoeff.so_eum_a * finalScores.so_eum) + (teCoeff.so_yang_a * finalScores.so_yang);
                const seCoeff = coeffs.so_eum;
                soEumLogit = seCoeff.intercept + (seCoeff.bmi * weightedBmi) + (seCoeff.tae_eum_a * finalScores.tae_eum) + (seCoeff.so_eum_a * finalScores.so_eum) + (seCoeff.so_yang_a * finalScores.so_yang);
            }
            
            // 6. Softmax로 최종 확률 계산 (이전과 동일)
            const logits = { tae_eum: taeEumLogit, so_eum: soEumLogit, so_yang: soYangLogit };
            const probabilities = softmax(logits);

            // 7. URL 쿼리 파라미터 생성 및 페이지 이동 (이전과 동일)
            const params = new URLSearchParams();
            params.append('age', basicInfo.age);
            params.append('gender', encodeURIComponent(basicInfo.gender.text));
            params.append('height', basicInfo.height);
            params.append('weight', basicInfo.weight);
            params.append('p_te', probabilities.tae_eum.toFixed(4));
            params.append('p_se', probabilities.so_eum.toFixed(4));
            params.append('p_sy', probabilities.so_yang.toFixed(4));

            window.location.href = `./results?${params.toString()}`;

        } catch (error) {
            // 오류 발생 시 사용자에게 알림
            alert(error.message);
        }
    });
</script>   
</body>
</html>


