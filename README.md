
 ##hogwarts-house-cnn
해리 포터 시리즈의 4개 기숙사 인물 이미지를 학습해 기숙사를 분류하는 CNN 모델입니다.
딥러닝 수업 2인 팀 프로젝트이며, 이미지 데이터 수집·정리, 결과 분석, 발표를 담당했습니다.

## 사용 기술
Python, TensorFlow/Keras, OpenCV, PIL, matplotlib

## 데이터
- 기숙사당 64장, 총 256장 (학습 208 / 검증 48)
- 이미지는 저작권상 저장소에 포함하지 않았습니다.
- 출처: Harry Potter Fandom 위키, Ranker (수업 과제용 수집)

## 모델
- Conv2D(32) → MaxPooling → Conv2D(16) → MaxPooling → Flatten → Dense(64) → Dropout(0.5) → Dense(4, softmax)
- 데이터 증강, EarlyStopping(patience 7) 적용

## 결과와 한계
- 검증 정확도는 대부분 25~44%(최고 43.75%)로, 무작위 수준(25%)보다 조금 높은 정도였습니다.
- 원인: 데이터 부족(256장), 분류 기준의 모호함(얼굴 외 의상·배경 영향), 얕은 모델 구조

## 개선 방향
- 사전학습 모델(MobileNet, ResNet 등) 전이학습
- 얼굴 영역 크롭 전처리와 더 다양한 데이터 수집
- 혼동행렬로 오분류 패턴 분석
