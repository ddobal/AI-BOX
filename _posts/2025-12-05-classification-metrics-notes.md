---
layout: post
title: "분류 모델 성능 지표 정리: Accuracy만으로는 부족한 이유"
date: 2025-04-15
tags: [metrics, classification, theory-note]
excerpt: "불균형 데이터에서 Accuracy만 보는 게 왜 위험한지, Precision·Recall·F1-score를 예시와 함께 정리한 이론 메모."
---

<style>
  .post-section-title {
    display: flex;
    align-items: center;
    gap: 8px;
    margin: 20px 0 10px;
  }
  .post-section-title svg {
    width: 20px;
    height: 20px;
  }
</style>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <rect x="4" y="4" width="16" height="16" rx="2" stroke="#38bdf8" stroke-width="1.5"/>
    <path d="M8 10h8M8 14h6" stroke="#38bdf8" stroke-width="1.5" stroke-linecap="round"/>
  </svg>
  <h2>글을 쓰게 된 계기</h2>
</div>

<p>
  과제용 데이터셋을 돌려보면 대부분 정확도(Accuracy)만 보고 결과를 평가하는 경우가 많다.
  나 역시 처음에는 “정확도가 높으면 좋은 모델”이라고 단순하게 생각했는데,
  불균형 데이터 문제를 접하면서 생각이 많이 바뀌었다.
  그래서 이번에는 분류 문제에서 자주 쓰는 성능 지표들을 간단히 정리해보고 싶었다.
</p>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <circle cx="12" cy="12" r="9" stroke="#a855f7" stroke-width="1.5"/>
    <path d="M8 10h8M10 8v8" stroke="#a855f7" stroke-width="1.5" stroke-linecap="round"/>
  </svg>
  <h2>기본 지표 정리</h2>
</div>

<ul>
  <li>Accuracy: 전체 샘플 중에서 정답을 맞춘 비율</li>
  <li>Precision: 모델이 양성이라고 예측한 것 중 실제로 양성인 비율</li>
  <li>Recall: 실제 양성 중에서 모델이 양성이라고 잘 찾아낸 비율</li>
  <li>F1-score: Precision과 Recall의 조화 평균</li>
</ul>

<p>
  특히 질병 진단처럼 양성 클래스를 놓치면 안 되는 문제에서는
  Accuracy 하나만 보는 것이 위험할 수 있다는 점을 다시 확인했다.
</p>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <path d="M4 19V5h16v9a5 5 0 0 1-5 5H9" stroke="#22c55e" stroke-width="1.5" fill="none"/>
  </svg>
  <h2>간단한 예시</h2>
</div>

<p>
  전체 데이터의 95%가 음성(정상)이고 5%만 양성(이상)이라고 가정해보면,
  모델이 모든 샘플을 그냥 “정상”이라고만 예측해도 Accuracy는 95%가 나온다.
  하지만 이 모델은 실제로는 이상 케이스를 하나도 잡아내지 못한다.
</p>
<p>
  이런 상황에서는 Confusion Matrix와 Precision, Recall, F1-score를 같이 보지 않으면
  모델이 얼마나 엉터리인지 알아차리기 어렵다.
</p>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <rect x="5" y="4" width="14" height="16" rx="2" stroke="#e5e7eb" stroke-width="1.4"/>
    <path d="M8 9h8M8 13h6" stroke="#e5e7eb" stroke-width="1.4" stroke-linecap="round"/>
  </svg>
  <h2>정리</h2>
</div>

<p>
  앞으로 분류 모델을 평가할 때는 Accuracy만 확인하고 끝내지 않고,
  최소한 Confusion Matrix와 Precision, Recall, F1-score 정도는 함께 보는 습관을 들일 필요가 있다.
  실제 문제에서는 어떤 지표를 우선순위에 둘지부터 정하는 게
  모델링만큼이나 중요한 단계라는 것도 점점 느껴지는 중이다.
</p>
