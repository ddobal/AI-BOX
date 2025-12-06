---
layout: page
title: Projects
permalink: /projects/
---

<style>
.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 20px;
  margin-top: 20px;
}

.card {
  background: rgba(255,255,255,0.06);
  padding: 18px 18px 16px 18px;
  border-radius: 18px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255,255,255,0.12);
  transition: 0.18s ease;
  font-size: 14px;
}

.card:hover {
  transform: translateY(-4px);
  background: rgba(255,255,255,0.09);
  box-shadow: 0 14px 30px rgba(0,0,0,0.45);
}

.card h3 {
  margin-top: 0;
  font-size: 19px;
  margin-bottom: 6px;
}

.card .tag {
  display: inline-block;
  font-size: 11px;
  padding: 2px 8px;
  border-radius: 999px;
  border: 1px solid rgba(255,255,255,0.18);
  margin-right: 4px;
  opacity: 0.9;
}
</style>

# 🚀 Projects

> 실제로 만들어본 프로젝트/프로토타입들을 정리해 두는 공간입니다.  
> 아래 내용은 예시이니, 진행하면서 하나씩 바꿔 넣으면 됩니다.

<div class="project-grid">

<div class="card">
  <h3>AI-BOX Automation</h3>
  <div class="tag">Computer Vision</div>
  <div class="tag">Backend</div>
  <p>
    딥러닝 기반 분석 파이프라인을 실험하기 위한 개인용 샌드박스.  
    데이터 수집 → 전처리 → 모델 학습/평가 → 결과 리포트까지  
    한 번에 돌려볼 수 있는 워크플로우를 구성했습니다.
  </p>
</div>

<div class="card">
  <h3>Vision Detector</h3>
  <div class="tag">Object Detection</div>
  <div class="tag">Real-time</div>
  <p>
    YOLO 계열 모델을 활용한 객체 탐지/트래킹 시스템.  
    GPU 최적화, 비디오 스트림 입력, 결과 오버레이 UI 등을 포함해  
    실시간 데모 환경을 구성했습니다.
  </p>
</div>

<div class="card">
  <h3>Generative Transformer</h3>
  <div class="tag">Generative AI</div>
  <div class="tag">Diffusion</div>
  <p>
    Diffusion/Transformer 기반 이미지 생성 실험.  
    텍스트 프롬프트에 따라 스타일이 달라지는  
    여러 버전의 모델을 비교·분석했습니다.
  </p>
</div>

</div>
