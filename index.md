---
layout: home
title:
---

# 🚀 단축형 사상체질 설문(KS-15)

자신에게 더 가깝다고 생각하는 버튼을 눌러주세요.

---


<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body { font-family: 'Malgun Gothic', sans-serif; line-height: 1.6; margin: 20px; }
        table { width: 100%; border-collapse: collapse; margin-bottom: 20px; }
        th, td { border: 1px solid #ccc; padding: 10px; text-align: center; }
        th.category { width: 80px; background-color: #f2f2f2; }
        td.question, td.personal-info { text-align: left; }
        .input-group { display: inline-block; margin-right: 5px; }
        .input-group input { width: 50px; text-align: right; }
        .radio-group label { margin-right: 15px; cursor: pointer; }

        /* 👇 버튼 스타일 (업데이트됨) */
        #submitBtn {
            display: block;
            width: 50%;
            max-width: 400px;
            margin: 40px auto;
            padding: 20px;
            font-size: 1.5em;
            font-weight: bold;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 123, 255, 0.3);
            transition: all 0.2s ease-in-out;
        }

        #submitBtn:hover {
            background-color: #0056b3;
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(0, 123, 255, 0.4);
        }
    </style>
</head>
<body>


    <table>
        <tr>
            <td class="personal-info" style="width: 50%;">
                <strong>신장</strong>
                <div class="input-group">
                    <input type="text" id="height"> cm
                </div>
            </td>
            <td class="personal-info" style="width: 50%;">
                <strong>체중</strong>
                <div class="input-group">
                    <input type="text" id="weight"> kg
                </div>
            </td>
        </tr>
        <tr>
            <td class="personal-info" colspan="2">
                <strong>성별</strong>
                <div class="radio-group" style="display: inline-block; margin-left: 10px;">
                    <label><input type="radio" name="gender" value="male"> 남성</label>
                    <label><input type="radio" name="gender" value="female"> 여성</label>
                </div>
            </td>
        </tr>
    </table>

    <p>⇨ 평소 성격에 대한 질문입니다. 해당되는 곳에 기입(✔)해 주세요.</p>
    <p>[예시] 포기(성격)가 빠른가요? 느린가요? <u>포기가 빠르다면</u> ①포기 빠름 <strong>✔②중간</strong> ③포기 느림</p>

<table>
        <tr>
            <th rowspan="6" class="category">성격</th>
            <td class="question">1. 성격이 대범하신가요? 섬세하신가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q1" value="1"> ①대범</label>
                <label><input type="radio" name="q1" value="2"> ②중간</label>
                <label><input type="radio" name="q1" value="3"> ③섬세</label>
            </td>
        </tr>
        <tr>
            <td class="question">2. 행동이 빠른 편인가요? 느린 편인가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q2" value="1"> ①빠르다</label>
                <label><input type="radio" name="q2" value="2"> ②중간</label>
                <label><input type="radio" name="q2" value="3"> ③느리다</label>
            </td>
        </tr>
        <tr>
            <td class="question">3. 모든 일에 적극적인가요? 소극적인가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q3" value="1"> ①적극적</label>
                <label><input type="radio" name="q3" value="2"> ②중간</label>
                <label><input type="radio" name="q3" value="3"> ③소극적</label>
            </td>
        </tr>
        <tr>
            <td class="question">4. 성격이 외향적인가요? 내성적인가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q4" value="1"> ①외향</label>
                <label><input type="radio" name="q4" value="2"> ②중간</label>
                <label><input type="radio" name="q4" value="3"> ③내성</label>
            </td>
        </tr>
        <tr>
            <td class="question">5. 남성적인 편인가요? 여성적인 편인가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q5" value="1"> ①남성적</label>
                <label><input type="radio" name="q5" value="2"> ②중간</label>
                <label><input type="radio" name="q5" value="3"> ③여성적</label>
            </td>
        </tr>
        <tr>
            <td class="question">6. 가끔 흥분하는 편인가요? 이성적인 편인가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q6" value="1"> ①흥분</label>
                <label><input type="radio" name="q6" value="2"> ②중간</label>
                <label><input type="radio" name="q6" value="3"> ③이성</label>
            </td>
        </tr>
    </table>

    <p>⇨ <strong>최근 6개월 내</strong> 본인의 생활 증상에 대한 질문입니다. 해당되는 곳에 기입(✔)해 주세요.</p>

    <table>
        <tr>
            <th rowspan="2" class="category">소화</th>
            <td class="question">7. 평소 소화는 어떠한가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q7" value="1"> ①소화가 잘 된다</label>
                <label><input type="radio" name="q7" value="2"> ②소화가 잘 안되지만 불편하지 않다</label>
                <label><input type="radio" name="q7" value="3"> ③소화가 안되고 불편함도 느낀다</label>
            </td>
        </tr>
        <tr>
            <td class="question">8. 평소 입맛은 어떠한가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q8" value="1"> ①좋은 편이다</label>
                <label><input type="radio" name="q8" value="2"> ②중간이다</label>
                <label><input type="radio" name="q8" value="3"> ③안 좋은 편이다</label>
            </td>
        </tr>
        <tr>
            <th rowspan="2" class="category">땀</th>
            <td class="question">9. 평소 땀을 어느 정도 흘리는 편인가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q9" value="1"> ①많다</label>
                <label><input type="radio" name="q9" value="2"> ②중간</label>
                <label><input type="radio" name="q9" value="3"> ③적다</label>
            </td>
        </tr>
        <tr>
            <td class="question">10. 땀을 흘리고 난 뒤 기분이 어떠한가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q10" value="1"> ①상쾌하다</label>
                <label><input type="radio" name="q10" value="2"> ②피곤하다</label>
                <label><input type="radio" name="q10" value="3"> ③아무느낌 없다</label>
            </td>
        </tr>
        <tr>
            <th class="category">대변</th>
            <td class="question">11. 대변이 마려운 신호가 왔을 때 참기 어려운가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q11" value="1"> ①자주 그렇다</label>
                <label><input type="radio" name="q11" value="2"> ②가끔 그렇다</label>
                <label><input type="radio" name="q11" value="3"> ③없다(어렵지 않다)</label>
            </td>
        </tr>
        <tr>
            <th class="category">소변</th>
            <td class="question">12. 밤(잠을 잘 때)에 소변을 몇 회 보나요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q12" value="1"> ①0회</label>
                <label><input type="radio" name="q12" value="2"> ②1회</label>
                <label><input type="radio" name="q12" value="3"> ③2회이상</label>
            </td>
        </tr>
        <tr>
            <th rowspan="2" class="category">한열<br>음수</th>
            <td class="question">13. 평소 추위, 더위 어느 것이 더 싫은가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q13" value="1"> ①추위</label>
                <label><input type="radio" name="q13" value="2"> ②더위</label>
                <label><input type="radio" name="q13" value="3"> ③모두 싫거나 모두 괜찮다</label>
            </td>
        </tr>
        <tr>
            <td class="question">14. 평소 마시는 물의 온도는 어떠한 가요?</td>
            <td class="radio-group">
                <label><input type="radio" name="q14" value="1"> ①주로 따뜻한 물</label>
                <label><input type="radio" name="q14" value="2"> ②주로 찬물</label>
                <label><input type="radio" name="q14" value="3"> ③가리지 않고 마신다</label>
            </td>
        </tr>
    </table>



    <button id="submitBtn">결과 저장 및 보기 🚀</button>

<script>
        document.getElementById('submitBtn').addEventListener('click', () => {
            
            // ======================================================
            // 👇 [추가된 부분] 유효성 검사 (Validation)
            // ======================================================

            // 1. 신장, 체중, 성별 검사
            const height = document.getElementById('height').value;
            const weight = document.getElementById('weight').value;
            const gender = document.querySelector('input[name="gender"]:checked');

            if (!height || !weight) {
                alert('신장과 체중을 입력해주세요.');
                return; // 함수 종료
            }
            if (!gender) {
                alert('성별을 선택해주세요.');
                return; // 함수 종료
            }

            // 2. 총 14개의 설문 항목을 순서대로 검사
            const totalQuestions = 14;
            for (let i = 1; i <= totalQuestions; i++) {
                const questionName = 'q' + i;
                const isAnswered = document.querySelector(`input[name="${questionName}"]:checked`);

                // 답변이 안 된 항목을 찾으면 즉시 경고창을 띄우고 함수를 종료
                if (!isAnswered) {
                    // 경고창에 표시할 질문 텍스트 찾기
                    const questionInput = document.querySelector(`input[name="${questionName}"]`);
                    const questionText = questionInput.closest('.radio-group').previousElementSibling.innerText.trim();
                    
                    alert(`'${questionText}' 항목에 답변해주세요.`);
                    return; // 함수 종료
                }
            }

            // ======================================================
            // 👇 [기존 부분] 모든 검사를 통과했을 때만 아래 코드가 실행됨
            // ======================================================
            
            const surveyData = {};

            // 개인 정보 수집
            surveyData.height = height;
            surveyData.weight = weight;
            surveyData.gender = {
                value: gender.value,
                text: gender.parentElement.innerText.trim()
            };

            // 질문과 답변을 상세히 저장할 배열 생성
            surveyData.responses = [];
            const checkedQuestions = document.querySelectorAll('input[type="radio"]:checked:not([name="gender"])');

            checkedQuestions.forEach(radio => {
                const selectedValue = radio.value;
                const selectedText = radio.parentElement.innerText.trim();
                const questionCell = radio.closest('.radio-group').previousElementSibling;
                const questionText = questionCell ? questionCell.innerText.trim() : '질문을 찾을 수 없음';

                surveyData.responses.push({
                    name: radio.name,
                    question: questionText,
                    answer: {
                        value: selectedValue,
                        text: selectedText
                    }
                });
            });

            // LocalStorage에 데이터 저장 및 페이지 이동
            localStorage.setItem('surveyResults', JSON.stringify(surveyData));
            alert('응답이 저장되었습니다. 결과 페이지로 이동합니다.');
            window.location.href = './results';
        });
    </script>
</body>
</html>

