---
layout: page
title: 자율주행 신호등 인식 프로젝트
description: YOLOv8을 활용한 실시간 객체 탐지 모델 개발
img: assets/img/1.jpg
importance: 1
category: work
---

이 프로젝트는 자율주행 상황에서 신호등과 표지판을 실시간으로 인식하기 위해 진행했습니다.

### 📌 프로젝트 개요
* **기간**: 2024.01 ~ 2024.03 (3개월)
* **역할**: 데이터 전처리 및 YOLO 모델 학습 담당
* **사용 기술**: Python, PyTorch, YOLOv8, OpenCV

### 💡 해결 과제
야간이나 비가 오는 환경에서 인식률이 떨어지는 문제가 있었습니다. 이를 해결하기 위해 다음과 같은 기법을 적용했습니다.
1. **Data Augmentation**: 밝기 조절 및 노이즈 추가로 데이터 3배 증강
2. **Transfer Learning**: 사전 학습된 모델을 사용하여 학습 속도 20% 향상

### 🚀 결과
기존 모델 대비 **정확도(mAP)를 15% 향상**시켰으며, 초당 30프레임(FPS)의 실시간 탐지 속도를 달성했습니다.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
    </div>
</div>
<div class="caption">
    실제 구동 화면 캡처
</div>
