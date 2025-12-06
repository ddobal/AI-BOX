---
layout: post
title: "Diffusion 모델 구조 정리"
date: 2025-12-01
category: "Generative AI"
tags: [diffusion, unet, attention]
---

Diffusion 모델의 핵심 구성 요소를 학습하며 정리한 문서입니다.

- U-Net 인코더/디코더 구조 파악
- Cross-Attention 동작 방식 복습
- Scheduler(DPM++, Euler 등) 비교
- 이미지 생성 과정의 흐름 시각화

실험 과정에서 느낀 점을 기준으로,  
모델이 어떻게 “노이즈 제거”를 단계적으로 수행하는지를 중심으로 정리했습니다.
