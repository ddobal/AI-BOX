---
layout: project
title: 간단한 객체 탐지 실습
permalink: /projects/simple-object-detection/
order: 7
---

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 카메라/박스 아이콘 -->
    <svg viewBox="0 0 24 24" width="32" height="32">
      <rect x="4" y="5" width="16" height="12" rx="2" stroke="#22c55e" stroke-width="1.6" fill="none"/>
      <rect x="9" y="9" width="6" height="4" stroke="#22c55e" stroke-width="1.4" fill="none"/>
    </svg>
  </div>

  <h1>간단한 객체 탐지 실습</h1>
  <p class="mini-hero-sub">
    OpenCV와 기존 모델을 활용해 얼굴·사물 검출을 직접 테스트해 본 컴퓨터비전 입문 프로젝트
  </p>
</div>

<!-- Overview -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Overview</h2>
  <p>
    이 프로젝트는 복잡한 딥러닝 모델을 직접 학습시키기보다는,
    이미 공개된 객체 탐지 모델을 활용해 간단한 검출 실험을 해보는 것이 목적이다.
    웹캠 혹은 이미지 파일에서 얼굴이나 특정 사물을 찾아 박스로 표시하는 흐름을 직접 구현했다.
  </p>
  <p>
    아래 도형은 카메라 입력부터 탐지 결과가 화면에 그려지기까지의 과정을
    한눈에 볼 수 있도록 정리한 파이프라인이다.
  </p>
</div>

<!-- Diagram 1 : Object Detection Flow -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">Object Detection Flow</h3>

  <svg width="100%" height="260" viewBox="0 0 840 260">
    <!-- Camera / Image -->
    <rect x="40" y="90" width="160" height="80" rx="12" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="120" y="120" font-size="14" fill="#e5e7eb" text-anchor="middle">카메라 / 이미지</text>
    <text x="120" y="140" font-size="11" fill="#bbf7d0" text-anchor="middle">웹캠 프레임 또는 파일</text>

    <!-- Arrow 1 -->
    <line x1="200" y1="130" x2="270" y2="130" stroke="#64748b" stroke-width="2"/>
    <polygon points="270,130 260,125 260,135" fill="#64748b"/>

    <!-- Preprocessing -->
    <rect x="270" y="80" width="180" height="100" rx="12" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="360" y="115" font-size="14" fill="#e5e7eb" text-anchor="middle">전처리</text>
    <text x="360" y="135" font-size="11" fill="#bae6fd" text-anchor="middle">리사이즈 · 그레이스케일 · 정규화</text>

    <!-- Arrow 2 -->
    <line x1="450" y1="130" x2="520" y2="130" stroke="#64748b" stroke-width="2"/>
    <polygon points="520,130 510,125 510,135" fill="#64748b"/>

    <!-- Detection Model -->
    <rect x="520" y="70" width="190" height="120" rx="12" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="615" y="110" font-size="14" fill="#e5e7eb" text-anchor="middle">탐지 모델</text>
    <text x="615" y="130" font-size="11" fill="#c7d2fe" text-anchor="middle">Haar Cascade / YOLO</text>

    <!-- Arrow 3 -->
    <line x1="710" y1="130" x2="780" y2="130" stroke="#64748b" stroke-width="2"/>
    <polygon points="780,130 770,125 770,135" fill="#64748b"/>

    <!-- Output / Draw Boxes -->
    <rect x="780" y="90" width="40" height="80" rx="8" fill="#020617" stroke="#f97316" stroke-width="2"/>
    <text x="760" y="180" font-size="11" fill="#fed7aa" text-anchor="middle">Bounding Box 그리기</text>
  </svg>
</div>

<!-- Tools & Methods -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Tools & Methods</h2>
  <p>
    OpenCV에서 제공하는 Haar Cascade 기반 얼굴 검출기를 먼저 사용해 보았고,
    이후에는 사전에 학습된 YOLO 계열 가중치를 불러와 간단히 테스트했다.
  </p>
  <p>
    Haar Cascade는 비교적 오래된 방식이지만 속도가 빠르고 구현이 단순하고,
    YOLO는 딥러닝 기반으로 더 다양한 객체에 대해 높은 정확도를 기대할 수 있다는 차이가 있다.
  </p>
  <p>
    아래 도식은 두 방법이 어떤 형태로 프레임을 입력받고, 어떤 출력 박스를 생성하는지
    개념적으로 비교한 그림이다.
  </p>
</div>

<!-- Diagram 2 : Haar vs YOLO -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">Haar Cascade vs YOLO (개념도)</h3>

  <svg width="100%" height="260" viewBox="0 0 840 260">
    <!-- Input frame -->
    <rect x="60" y="100" width="160" height="80" rx="12" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="140" y="135" font-size="13" fill="#e5e7eb" text-anchor="middle">입력 프레임</text>
    <text x="140" y="153" font-size="11" fill="#bbf7d0" text-anchor="middle">웹캠 / 이미지</text>

    <!-- Split arrows -->
    <line x1="220" y1="120" x2="310" y2="80" stroke="#64748b" stroke-width="2"/>
    <polygon points="310,80 300,77 303,87" fill="#64748b"/>

    <line x1="220" y1="160" x2="310" y2="200" stroke="#64748b" stroke-width="2"/>
    <polygon points="310,200 303,192 300,202" fill="#64748b"/>

    <!-- Haar block -->
    <rect x="310" y="50" width="200" height="80" rx="12" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="410" y="82" font-size="13" fill="#e5e7eb" text-anchor="middle">Haar Cascade</text>
    <text x="410" y="100" font-size="11" fill="#bae6fd" text-anchor="middle">정해진 특징 + 슬라이딩 윈도우</text>

    <!-- YOLO block -->
    <rect x="310" y="170" width="200" height="80" rx="12" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="410" y="202" font-size="13" fill="#e5e7eb" text-anchor="middle">YOLO (사전 학습)</text>
    <text x="410" y="220" font-size="11" fill="#c7d2fe" text-anchor="middle">end-to-end 딥러닝 모델</text>

    <!-- Arrows to outputs -->
    <line x1="510" y1="90" x2="600" y2="90" stroke="#64748b" stroke-width="2"/>
    <polygon points="600,90 590,85 590,95" fill="#64748b"/>

    <line x1="510" y1="210" x2="600" y2="210" stroke="#64748b" stroke-width="2"/>
    <polygon points="600,210 590,205 590,215" fill="#64748b"/>

    <!-- Output boxes -->
    <rect x="600" y="60" width="180" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="690" y="88" font-size="12" fill="#e5e7eb" text-anchor="middle">얼굴 영역 Bounding Box</text>

    <rect x="600" y="180" width="180" height="60" rx="10" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="690" y="208" font-size="12" fill="#e5e7eb" text-anchor="middle">사람 / 물체 등 여러 클래스 박스</text>
  </svg>
</div>

<!-- What I Learned -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>What I Learned</h2>
  <p>
    코드 몇 줄만으로도 꽤 강력한 객체 탐지 결과를 얻을 수 있다는 점이 인상적이었다.
    동시에, 실제 서비스에 적용하려면 데이터셋 구성, 성능 튜닝, 지연 시간 등
    고려할 요소가 훨씬 많다는 것도 느끼게 되었다.
  </p>
  <p>
    특히 “어떤 모델이 더 좋은가?”라는 질문에 단순 정답은 없고,
    속도와 정확도, 사용할 환경(PC, 모바일, 웹캠 등)에 따라 선택이 달라진다는 점을
    간단한 실습만으로도 체감할 수 있었다.
  </p>
  <p>
    아래 그래프는 Haar 방식과 YOLO 방식의 속도·정확도 차이를 개념적으로 표현한 것이다.
  </p>
</div>

<!-- Diagram 3 : Speed vs Accuracy -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">Speed vs Accuracy (개념도)</h3>

  <svg width="100%" height="230" viewBox="0 0 840 230">
    <!-- Axes -->
    <line x1="140" y1="180" x2="720" y2="180" stroke="#475569" stroke-width="1.5"/>
    <line x1="140" y1="60" x2="140" y2="180" stroke="#475569" stroke-width="1.5"/>

    <text x="130" y="60" font-size="11" fill="#9ca3af" text-anchor="end">정확도</text>
    <text x="720" y="195" font-size="11" fill="#9ca3af" text-anchor="end">처리 속도(프레임)</text>

    <!-- Haar point -->
    <circle cx="260" cy="120" r="7" fill="#38bdf8"/>
    <text x="260" y="110" font-size="11" fill="#e0f2fe" text-anchor="middle">Haar</text>
    <text x="260" y="190" font-size="11" fill="#e5e7eb" text-anchor="middle">속도 ↑ / 정확도 보통</text>

    <!-- YOLO point -->
    <circle cx="500" cy="90" r="7" fill="#6366f1"/>
    <text x="500" y="80" font-size="11" fill="#c7d2fe" text-anchor="middle">YOLO</text>
    <text x="500" y="190" font-size="11" fill="#e5e7eb" text-anchor="middle">정확도 ↑ / 속도는 환경 의존</text>

    <!-- Legend -->
    <rect x="160" y="70" width="14" height="14" fill="#38bdf8"/>
    <text x="180" y="82" font-size="11" fill="#e0f2fe">Haar Cascade (전통 방식)</text>

    <rect x="160" y="95" width="14" height="14" fill="#6366f1"/>
    <text x="180" y="107" font-size="11" fill="#c7d2fe">YOLO 계열 (딥러닝)</text>
  </svg>
</div>
