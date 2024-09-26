# 국방 AI 경진대회 대비 연습문제1

위 연습문제는 학습데이터, 테스트데이터, 각 문항에 대한 IPYNB 형태의 파일로 이루어져 있습니다. 세 문항 모두 동일한 데이터를 활용하며, 각 문항에 알맞게 코드를 작성하여야 합니다.

# 1. 모델 학습 문제
위 문제에서 활용되는 데이터는 아래 항목과 같이 구성되어 있다.
- id, anaemia, creatinine_phosphokinase, diabetes, ejection_fraction, high_blood_pressure, platelets, serum_creatinine, serum_sodium, sex, smoking, time, DEATH_EVENT

데이터의 각 항목들을 활용하여 DEATH_EVENT에 해당하는 생사여부에 대해서 이진분류하는 모델을 구현하시오.

제한사항

- None 이외의 미리 주어진 코드를 임의로 수정하는 경우, 정상적인 채점이 어려울 수 있습니다.
- 함수가 지시사항대로 값을 계산하지 않고 특정 값을 반환하도록 하드코딩된 경우 오답으로 처리합니다.
- 주어진 학습데이터 이외의 데이터를 통해 모델을 학습시키면 안됩니다.
- 학습과정에서 테스트 데이터를 통한 학습이 이루어지지 않아야 합니다.

지시사항

1. train : 학습용데이터
  
   - 모델이 학습하는 데 사용하는 데이터입니다.
   - 해당 데이터를 자유롭게 사용하여 DEATH_EVENT를 예측하는 모델을 만드시오.

2. test : 검증용데이터
  
   - 모델의 성능을 검증하는데 사용하는 데이터입니다.
   - train 데이터에서 DEATH_EVENT 열이 제거된 구조입니다.
   - 해당 데이터를 사용해, DEATH_EVENT를 예측하시오.
   - 위에서 예측한 DEATH_EVENT를 test의 DEATH_EVENT 열에 채워넣어 제출하시오.

3. 제출한 test와 실제 정답을 비교한 정확도에 따라 점수가 부여됩니다.
  
   - 50%의 정확도가 나오면 0점을 받게 됩니다.
   - 점수 : max((정확도 - 0.5), 0) *2 * 30



# 2. 데이터 시각화

지시사항

1. 데이터 추출하기
  
   - get_high_blood 함수를 활용하여 데이터를 추출하시오.
   - 고혈압이지만, 당뇨는 없는 사람들의 데이터를 구하는 함수입니다.
   - df에서 high_blood_pressure는 1이지만, diabetes은 0인 데이터를 추출하여 반환하시오.

2. 산점도 그래프 그리기
  
   - make_scatter 함수를 활용하여 나이와 혈소판 수치의 산점도 그래프를 그리시오.
   - matplotlib.pyplot 라이브러리의 함수를 이용해 df에서 age와 platelets의 산점도 그래프를 그리시오.
   - x는 df의 나이를 저장합니다.
   - y는 df의 혈소판수치를 저장합니다.
   - x와 y를 이용하여 산점도 그래프를 그립니다.


# 3. 데이터 전처리

지시사항

1. 결측치 제거
   - remove_nan 함수를 작성하시오.
   - 결측치가 존재하는 행을 삭제하고 반환하시오.

2. 이상치 제거
   - replace_outlier 함수를 작성하시오.
   - 나이의 값이 60.667인 행을 제거합니다.
   - 이 외에도 이상치가 있다면 제거합니다.


3. 데이터 나누기
  
   - divide_data 함수를 작성하시오.
   - 데이터프레임을 전달받아 학습용 데이터와 검증용 데이터로 나눠 반환하는 함수를 작성하시오.
   - 해당 함수가 반환하는 데이터는 다음과 같습니다.
   - features는 DEATH_EVENT를 제외한 칼럼 이름들입니다.
   - 순서는 고려하지 않습니다.
   - y에 해당하는 값은 DEATH_EVENT입니다.
   - 학습용 데이터와 검증용 데이터의 비율은 8:2입니다.
   - 반환값은 x_train, x_valid, y_train, y_valid로 정의하시오.