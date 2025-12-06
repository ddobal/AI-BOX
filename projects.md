---
layout: default
title: Projects
permalink: /projects/
---

<style>
  .section-heading {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 1.1rem;
    margin-bottom: 8px;
  }

  .section-heading-icon {
    width: 24px;
    height: 24px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
  }

  .section-heading-icon svg {
    width: 20px;
    height: 20px;
    display: block;
  }

  .section-card-grid--columns {
    max-width: 900px;
    margin: 0 auto 60px;
  }
</style>

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <svg width="38" height="38" viewBox="0 0 24 24" fill="none">
      <path d="M12 2c2.4 0 4.8.8 6.4 2.4l-4.8 4.8H8L12 2zM4 20l2.4-6.4h4.8l4.8 4.8A10 10 0 0 1 12 22c-2.4 0-4.8-.8-6.4-2.4z"
            fill="url(#rocketGrad)"/>
      <defs>
        <linearGradient id="rocketGrad">
          <stop offset="0%" stop-color="#ff6b6b"/>
          <stop offset="100%" stop-color="#f9d423"/>
        </linearGradient>
      </defs>
    </svg>
  </div>

  <h1>Projects</h1>
  <p class="mini-hero-sub">
    인공지능학과 재학생 수준에서 수행할 수 있는 실습 기반 프로젝트들을 정리해두었습니다.  
    머신러닝·딥러닝·데이터 분석·컴퓨터비전 기초 수업 중심으로 구성했습니다.
  </p>
</div>

<div class="section-card-grid--columns">

  {% capture project_icon_svg %}
  <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
    <rect x="4" y="4" width="6" height="6" rx="1.2" stroke="white" stroke-width="1.4" />
    <rect x="14" y="4" width="6" height="6" rx="1.2" stroke="white" stroke-width="1.4" />
    <rect x="4" y="14" width="6" height="6" rx="1.2" stroke="white" stroke-width="1.4" />
    <rect x="14" y="14" width="6" height="6" rx="1.2" stroke="white" stroke-width="1.4" />
  </svg>
  {% endcapture %}

  <!-- 1: MNIST 숫자 손글씨 분류 -->
  <a class="section-card section-card-link" href="{{ '/projects/mnist-digit-classification/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">{{ project_icon_svg }}</span>
      MNIST 손글씨 숫자 분류
    </h2>
    <p class="section-card-meta">Machine Learning · 딥러닝 기초</p>
    <p>
      CNN 기반 모델로 MNIST 숫자 이미지를 분류하는 기본 딥러닝 실습.  
      초기 모델과 개선 모델을 비교하며 학습률·에폭에 따른 성능 변화를 분석함.
    </p>
  </a>

  <!-- 2: 영화 리뷰 감성 분석 -->
  <a class="section-card section-card-link" href="{{ '/projects/movie-review-sentiment/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">{{ project_icon_svg }}</span>
      영화 리뷰 감성 분석
    </h2>
    <p class="section-card-meta">NLP · 텍스트 분류</p>
    <p>
      IMDB 리뷰 데이터를 이용해 긍정/부정 분류 모델을 구축.  
      TF-IDF 및 간단한 RNN 모델을 사용해 텍스트 처리 흐름을 실습함.
    </p>
  </a>

  <!-- 3: 식물 잎 병해 이미지 분류 -->
  <a class="section-card section-card-link" href="{{ '/projects/leaf-disease-classification/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">{{ project_icon_svg }}</span>
      식물 잎 병해 이미지 분류
    </h2>
    <p class="section-card-meta">Computer Vision</p>
    <p>
      Kaggle PlantVillage 데이터셋을 활용해  
      건강한 잎과 병충해 잎을 구분하는 이미지 분류 모델 개발.
    </p>
  </a>

  <!-- 4: 대중교통 승객 수 예측 -->
  <a class="section-card section-card-link" href="{{ '/projects/bus-passenger-forecast/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">{{ project_icon_svg }}</span>
      대중교통 승객 수 예측
    </h2>
    <p class="section-card-meta">Time Series · Forecasting</p>
    <p>
      특정 노선의 시간대별 승객 데이터를 기반으로  
      단순 LSTM 모델을 사용해 미래 승객 수를 예측한 프로젝트.
    </p>
  </a>

  <!-- 5: 간단한 챗봇 만들기 -->
  <a class="section-card section-card-link" href="{{ '/projects/basic-chatbot/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">{{ project_icon_svg }}</span>
      간단한 규칙 기반 챗봇
    </h2>
    <p class="section-card-meta">NLP 기초 · Rule-based AI</p>
    <p>
      패턴 매칭과 간단한 의도 분류를 이용하여  
      FAQ 응답이 가능한 기본 챗봇을 구현한 실습 프로젝트.
    </p>
  </a>

  <!-- 6: 온라인 쇼핑몰 고객 데이터 분석 -->
  <a class="section-card section-card-link" href="{{ '/projects/ecommerce-data-analysis/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">{{ project_icon_svg }}</span>
      온라인 쇼핑몰 고객 데이터 분석
    </h2>
    <p class="section-card-meta">Data Analysis</p>
    <p>
      구매 이력 데이터에서 고객 유형을 분류하고  
      RFM 분석을 통해 소비 패턴을 시각화하는 데이터 분석 프로젝트.
    </p>
  </a>

  <!-- 7: 간단한 객체 탐지 실습 -->
  <a class="section-card section-card-link" href="{{ '/projects/simple-object-detection/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">{{ project_icon_svg }}</span>
      간단한 객체 탐지 실습
    </h2>
    <p class="section-card-meta">Computer Vision · OpenCV</p>
    <p>
      OpenCV의 Haar Cascade를 활용해 얼굴·사물 검출을 실습하는 기초 CV 프로젝트.  
      실제 딥러닝 기반 탐지 모델(YOLO 등)과의 차이를 비교해보는 것이 목표.
    </p>
  </a>

</div>
