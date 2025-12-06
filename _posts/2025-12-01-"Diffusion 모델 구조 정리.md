---
layout: post
title: "Diffusion 모델 구조 정리"
date: 2025-12-01
category: "Generative AI"
tags: [diffusion, unet, attention, scheduler]
---

이 글은 Diffusion 기반 이미지 생성 모델을 이해하기 위해  
구조를 단계별로 정리한 **학습용 기록**이다.  
특히 *“이미지를 어떻게 노이즈에서 복원하는가?”* 라는 관점에서 정리했다.

---

## 1. Diffusion의 큰 흐름

Diffusion 모델은 거칠게 말하면 다음 두 과정을 왔다 갔다 한다.

1. **Forward Process (추가 노이즈 단계)**  
   - 깨끗한 이미지에 점점 노이즈를 추가해서  
     최종적으로는 `정규분포에 가까운 노이즈`로 만든다.
   - 수식적으로는 `q(x_t | x_{t-1})` 와 같은 형태로 표현된다.

2. **Reverse Process (노이즈 제거 단계)**  
   - 완전히 노이즈화된 상태에서 시작해서  
     서서히 노이즈를 제거하며 이미지를 복원한다.
   - 이때의 핵심이 `ε(노이즈)`를 얼마나 정확하게 예측하느냐이다.

실제로 우리가 “학습시키는 모델”은  
**노이즈를 예측하는 U-Net 형태의 네트워크**라고 보면 된다.

---

## 2. U-Net 인코더/디코더 구조

Diffusion에서 사용하는 U-Net은 보통 다음과 같은 단계로 나뉜다.

- **Encoder**  
  - Conv + Downsampling 블록을 반복하며  
    점점 해상도를 줄이고, 채널 수를 늘려 정보를 압축한다.
- **Bottleneck**  
  - 가장 낮은 해상도에서 여러 Residual Block + Attention Block을 쌓는다.
- **Decoder**  
  - Upsampling을 하며 다시 해상도를 키우고,  
    Encoder에서 넘어온 Skip Connection과 결합해 세부 정보를 복원한다.

이 구조 덕분에  
“전체적인 윤곽 + 세부 텍스처”를 동시에 잘 다룰 수 있다.

---

## 3. Time Embedding과 조건 정보

Diffusion에서 **시간(step) 정보**는 굉장히 중요하다.

- 각 step마다 노이즈 양이 다르기 때문에  
  `t` 정보를 네트워크에 알려줘야 한다.
- 보통 `sin/cos positional embedding` 방식으로 `t`를 임베딩하고  
  이를 각 블록에 더하거나, 별도 MLP를 거쳐 feature에 주입한다.

또한 Text-to-Image의 경우

- **텍스트 인코더(CLIP, T5, etc.)**로 문장을 임베딩하고  
- Cross-Attention을 통해 U-Net 내부 feature와 결합한다.

---

## 4. Cross-Attention 동작 방식

Cross-Attention은 간단히 말하면,

> “이미지 피처가 텍스트 피처를 참고해서,  
> 어떤 부분을 어떻게 그릴지 결정하는 메커니즘”

이라고 볼 수 있다.

- Query: 이미지 feature map에서 뽑음  
- Key / Value: 텍스트 인코더에서 나온 토큰 임베딩  
- 결과: 이미지 feature가 텍스트 의미를 반영해 업데이트됨

이 덕분에 `"a cat sitting on a chair"` 같은 문장을  
이미지 구조와 내용에 잘 반영할 수 있다.

---

## 5. Scheduler(DPM++, Euler 등)의 역할

Scheduler는 **“t를 어떤 간격으로, 어떤 방식으로 줄여 나갈지”** 를 결정한다.

- DDPM, DDIM, Euler, DPM++ 등 다양한 종류가 있고  
- 각 방법은  
  - 샘플링 속도  
  - 품질  
  - 안정성  
  사이에서 서로 다른 트레이드오프를 가진다.

실습 시 느낀 점:

- 고정 step(예: 50~100)에서 Scheduler만 바꿔도  
  결과 품질이 꽤 눈에 띄게 달라진다.
- 특정 프롬프트에서 “붓 터치 느낌”, “디테일 수준”이  
  Scheduler에 따라 다르게 표현되는 것을 체감했다.

---

## 6. 정리 및 개인적인 메모

- Diffusion은 “노이즈 제거 문제”로 이해하면 머릿속이 훨씬 정리된다.
- U-Net + Time Embedding + Cross-Attention + Scheduler 조합이  
  **현재 이미지 생성 모델의 기본 골격**이라고 느꼈다.
- 다음 학습 목표:
  - Latent 공간 설명 더 깊게 보기  
  - LoRA / ControlNet 구조까지 같이 정리해보기
