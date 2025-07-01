# 🧠 web-ai

뇌 MRI 영상과 임상 정보를 통합하여 **MMSE (Mini-Mental State Examination)** 점수를 예측하는 딥러닝 기반 인공지능 모델 연구 프로젝트입니다.  
본 프로젝트는 **알츠하이머병(AD)** 조기 진단을 목표로 하며, 다양한 슬라이스 범위와 메타데이터 조합을 실험하였습니다.

📌 해당 연구는 다음과 같은 **학술적 성과**를 이루었습니다:

- 🧾 **대한의료정보학회 춘계학술대회 (2024)** 포스터 발표  
  - 논문: *A Deep Learning Model for Early Diagnosis of Alzheimer's Disease Using Multi-Slice MRI and Metadata Integration*
- 🥉 **ACK 한국정보처리학회 학술발표대회 (2024)** 논문 **동상 수상**  
  - 논문: *Prognosis Prediction of Alzheimer's Disease: Multi-Horizon MMSE Prediction from MRI and Metadata*

> 본 프로젝트의 모든 저자는 **공동 제1저자(Co-first authors)**로서 연구에 동등하게 기여하였습니다.

---

## 📒 주요 노트북 및 기능

### 1. MMSE 점수 예측 (Regression)
- **파일:** `oasis2_slice_10mm_serial.ipynb`
- **내용 요약:**
  - CNN + LSTM 구조로 MMSE 점수 회귀 예측
  - MRI 중앙 슬라이스와 ±10mm, ±15mm 슬라이스 활용
  - VGG16 기반 CNN으로 영상 특징 추출 + LSTM으로 시계열 맥락 반영
  - 10mm 모델이 combined 모델보다 우수한 성능 달성  
    - `MSE: 0.527`, `MAE: 0.509`
  - **의의:** 영상 기반 MMSE 예측이 AD 조기 진단에 유효함을 시사

### 2. 다중 슬라이스 + 메타데이터 기반 AD 분류 (Classification)
- **파일:** `oasis2_slice_metadata_combined.ipynb`
- **내용 요약:**
  - MRI 슬라이스와 임상 메타데이터(age, sex, MMSE, education, SES) 통합
  - VGG16 + fully connected layer 구조
  - AD 3-class 분류 (Non-Demented / Demented / Converted)
  - 최종 모델 성능:
    - `Accuracy: 95%`, `Precision: 95%`, `Recall: 92%`, `F1-score: 94%`
  - **의의:** 공간적 영상 변화 + 메타데이터 결합이 진단 정확도에 큰 기여

---

## 📊 데이터셋

- **OASIS-2**: 공개 뇌 MRI 및 임상 데이터셋  
  - MRI 3D T1-weighted 영상 → 중앙 슬라이스 + ±10mm, ±15mm 슬라이스 추출  
  - 메타데이터: Age, Sex, MMSE, Education, SES  
  - 데이터 출처: [OASIS 홈페이지](https://www.oasis-brains.org/)

---

## ⚙️ 실행 환경

- **Python:** 3.8 이상
- **사용 라이브러리:**
  - `numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`
  - `tensorflow` 또는 `torch` (노트북에 따라 상이)
  - `jupyter notebook`

---

## 📝 참고 및 인용

이 프로젝트는 아래 두 논문에 기반한 연구입니다:

### 📌 대한의료정보학회 춘계학술대회 2024
> Cho C., Moon S., Song Y., Jang J. (2024).  
> *A Deep Learning Model for Early Diagnosis of Alzheimer's Disease Using Multi-Slice MRI and Metadata Integration*.  
> 대한의료정보학회 춘계학술대회 포스터 발표

### 📌 ACK 한국정보처리학회 2024
> Cho C., Moon S., Song Y., Jang J. (2024).  
> *Prognosis Prediction of Alzheimer's Disease: Multi-Horizon MMSE Prediction from MRI and Metadata*.  
> ACK 2024 논문집 제31권 제2호, 동상 수상작

논문 또는 코드를 인용하실 경우, 반드시 해당 저자를 명시해 주세요.

---

## 📎 논문 PDF

- [📄 대한의료정보학회 2024 발표 논문 (2024)](https://drive.google.com/file/d/1dbiCpb2bz-N80J7KH8Wulh0q4p1TyCka/view?usp=drive_link)  
  *A Deep Learning Model for Early Diagnosis of Alzheimer's Disease Using Multi-Slice MRI and Metadata Integration*

- [🥉 ACK 한국정보처리학회 2024 수상 논문 (동상)](https://drive.google.com/file/d/1TAbvF0PwFMSDRorrUg6_eCjNLEYiTP4O/view?usp=drive_link)  
  *Prognosis Prediction of Alzheimer's Disease: Multi-Horizon MMSE Prediction from MRI and Metadata*
