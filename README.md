# web-ai

이 레포지토리는 뇌 MRI 데이터와 임상 정보를 활용하여 MMSE(Mini-Mental State Examination) 점수를 예측하는 인공지능 모델 연구를 위한 Jupyter Notebook 모음입니다.  
본 프로젝트는 논문 연구를 위해 진행되었으며, 다양한 딥러닝 접근법을 실험합니다.

## 주요 노트북 및 기능

### 1. MMSE Prediction  
- **파일:** `oasis2_slice_10mm_serial.ipynb`  
- **설명:**  
  - 본 노트북은 알츠하이머병(AD) 환자의 MMSE 점수를 예측하기 위해 CNN-LSTM 모델을 구현합니다.
  - OASIS-2 데이터셋의 MRI 슬라이스(central, ±10mm, ±15mm)와 메타데이터를 활용합니다.
  - 두 가지 데이터셋(central+±10mm 슬라이스(10mm dataset), central+±10mm+±15mm 슬라이스(combined dataset))을 생성하여 실험합니다.
  - VGG16을 이용해 MRI 이미지에서 특징을 추출하고, 이를 메타데이터와 결합하여 MMSE 점수를 예측합니다.
  - 10mm 모델이 combined 모델보다 더 우수한 성능(MSE 0.527, MAE 0.509)을 보였습니다.
  - 본 연구는 MRI와 메타데이터를 활용한 MMSE 점수 예측이 AD의 조기 진단에 유용함을 시사합니다.

### 2. Multi-slice & Metadata  
- **파일:** `oasis2_slice_metadata_combined.ipynb`  
- **설명:**  
  - 본 노트북은 다중 슬라이스 MRI 이미지와 환자의 임상 메타데이터(나이, 성별, MMSE, 교육 수준, SES)를 통합 분석하여 알츠하이머병(AD) 진단 정확도를 높이는 딥러닝 모델을 구현합니다.
  - OASIS 데이터셋을 활용하여 Non-Demented, Demented, Converted 세 가지로 분류하며, ±10mm, ±15mm, 그리고 결합 데이터셋을 사용합니다.
  - VGG16(Pretrained ImageNet) 기반의 모델에 추가적인 fully connected layer를 쌓아 학습하며, Adam optimizer로 최적화합니다.
  - 모델 성능은 accuracy, loss, precision, recall, F1-score 등 다양한 지표로 평가합니다.
  - 다중 슬라이스와 메타데이터(특히 Age, Sex, MMSE)를 결합한 모델이 95% accuracy, 95% precision, 92% recall, 94% F1-score로 가장 우수한 성능을 보였습니다.
  - 슬라이스 범위 확장과 메타데이터 결합이 성능 향상에 크게 기여하였으며, 모든 클래스에서 균형 잡힌 결과를 확인하였습니다.
  - 본 연구는 뇌 영상의 공간적 변화와 임상 정보를 함께 고려하는 것이 미세한 신경퇴행성 변화를 감지하는 데 중요함을 시사합니다.
  - 향후 연구에서는 데이터셋 확장 및 모델 고도화를 통해 임상 적용 가능성을 높일 예정입니다.

## 데이터셋

- **OASIS2**: 공개 뇌 MRI 및 임상 데이터셋  
  - [OASIS 브레인 프로젝트](https://www.oasis-brains.org/)
  - 데이터 다운로드 및 사용 방법은 각 노트북의 안내를 참고하세요.

## 실행 환경

- Python 3.8 이상 권장
- 주요 라이브러리:  
  - numpy, pandas, scikit-learn, matplotlib, seaborn  
  - tensorflow 또는 pytorch (노트북별로 상이)
  - jupyter notebook

## 참고 및 인용

- 본 레포지토리의 실험 및 결과는 논문 연구의 일부로 활용되었습니다.
- 논문, 데이터셋, 코드 인용 시 반드시 원 저작자를 명시해 주세요.