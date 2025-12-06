---
layout: default
title: About
permalink: /about/
---

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 사람 아이콘 -->
    <svg viewBox="0 0 24 24" width="36" height="36" aria-hidden="true">
      <path d="M12 2a5 5 0 1 1 0 10 5 5 0 0 1 0-10zm0 12c4.4 0 8 2 8 4.5V22H4v-3.5C4 16 7.6 14 12 14z"
            fill="url(#aboutGrad)"/>
      <defs>
        <linearGradient id="aboutGrad" x1="0" y1="0" x2="1" y2="1">
          <stop offset="0%" stop-color="#4facfe"/>
          <stop offset="100%" stop-color="#38f9d7"/>
        </linearGradient>
      </defs>
    </svg>
  </div>

  <h1>About Me</h1>
  <p class="mini-hero-sub">
    AI·컴퓨터비전·딥러닝 실습을 중심으로 공부한 내용을 정리하는 개인 포트폴리오
  </p>
</div>

<style>
  /* About 페이지 전용 컨테이너: 카드 가로폭 통일 */
  .about-container {
    max-width: 920px;   /* Projects 카드 폭이랑 비슷하게 */
    margin: 0 auto 48px;
  }

  /* About 페이지 전용: 카드 간 세로 간격 / 내부 여백 조정 */
  .about-container .section-card {
    margin-bottom: 48px !important;   /* 카드 사이 간격 넉넉하게 */
    padding: 28px 28px 30px;          /* 기본보다 살짝 넓게 */
  }

  .about-section-title {
    display:flex;
    align-items:center;
    gap:10px;
    margin-bottom:12px;
  }
  .about-section-title svg {
    width:20px;
    height:20px;
  }

  /* 프로필 카드 레이아웃 */
  .about-profile-wrapper {
    display:flex;
    gap:24px;
    align-items:center;
    flex-wrap:wrap;
  }
  .about-profile-photo {
    flex:0 0 120px;
    width:120px;
    height:120px;
    border-radius:999px;
    overflow:hidden;
    border:1px solid rgba(255,255,255,0.1);
    box-shadow:0 10px 30px rgba(0,0,0,0.6);
    background:radial-gradient(circle at 30% 0%, #1f2937, #020617);
  }
  .about-profile-photo img {
    width:100%;
    height:100%;
    object-fit:cover;
    display:block;
  }
  .about-profile-text {
    flex:1;
    min-width:220px;
  }
  .about-profile-name {
    font-size:1.1rem;
    font-weight:600;
    margin-bottom:4px;
  }
  .about-profile-meta {
    font-size:0.9rem;
    color:rgba(226,232,240,0.8);
    margin-bottom:8px;
  }

  /* 스킬 태그 */
  .skill-tag-list {
    display:flex;
    flex-wrap:wrap;
    gap:8px;
    margin-top:8px;
  }
  .skill-tag {
    font-size:0.82rem;
    padding:4px 10px;
    border-radius:999px;
    border:1px solid rgba(148,163,184,0.5);
    background:radial-gradient(circle at top, rgba(148,163,184,0.22), rgba(15,23,42,0.9));
    box-shadow:0 6px 18px rgba(15,23,42,0.8);
    white-space:nowrap;
  }

  @media (max-width:768px) {
    .about-container {
      margin: 0 16px 32px;
    }
    .about-container .section-card {
      margin-bottom: 32px !important; /* 모바일에서는 조금만 줄이기 */
      padding: 22px 20px 24px;
    }
    .about-profile-wrapper {
      justify-content:flex-start;
    }
    .about-profile-photo {
      margin-bottom:8px;
    }
  }
</style>

<!-- 여기부터 본문 전체를 about-container로 감싸기 -->
<div class="about-container">

  <!-- 프로필 + 바이오 + 스킬 태그 -->
  <div class="section-card">
    <div class="about-profile-wrapper">
      <div class="about-profile-photo">
        <!-- TODO: 여기에 실제 프로필 이미지 경로 넣기 -->
        <!-- 예시: assets/img/profile.jpg -->
        <img src="/assets/img/profile.jpg" alt="Profile photo">
      </div>

      <div class="about-profile-text">
        <div class="about-section-title" style="margin-bottom:6px;">
          <svg viewBox="0 0 24 24" fill="none">
            <circle cx="12" cy="12" r="10" stroke="#7dd3fc" stroke-width="1.4"/>
            <path d="M12 8.5v.01" stroke="#7dd3fc" stroke-width="2" stroke-linecap="round"/>
            <path d="M12 11v5" stroke="#7dd3fc" stroke-width="2" stroke-linecap="round"/>
          </svg>
          <h2 style="margin:0;">Introduction</h2>
        </div>

        <div class="about-profile-name">
          정현석 · AI 전공 재학생
        </div>
        <div class="about-profile-meta">
          딥러닝·컴퓨터비전 실습을 꾸준히 해 보면서, 실험 과정을 기록하는 습관을 만들고 있는 중이다.
        </div>
        <p>
          모델이 왜 그 결과를 내는지 궁금해서, 직접 코드를 수정해 보고 그래프를 그려보는 걸 좋아한다.
          이 포트폴리오는 그런 실험과 과제를 하나씩 모아두는 “개인 연구 노트”에 가깝다.
        </p>

        <div class="skill-tag-list">
          <span class="skill-tag">Python · NumPy · Pandas</span>
          <span class="skill-tag">PyTorch 기초</span>
          <span class="skill-tag">scikit-learn</span>
          <span class="skill-tag">CNN · 이미지 분류</span>
          <span class="skill-tag">Computer Vision 입문</span>
          <span class="skill-tag">Git · GitHub</span>
          <span class="skill-tag">Jekyll · GitHub Pages</span>
        </div>
      </div>
    </div>
  </div>

  <!-- 포트폴리오 소개 -->
  <div class="section-card">
    <div class="about-section-title">
      <svg viewBox="0 0 24 24" fill="none">
        <circle cx="12" cy="12" r="10" stroke="#7dd3fc" stroke-width="1.4"/>
        <path d="M12 8.5v.01" stroke="#7dd3fc" stroke-width="2" stroke-linecap="round"/>
        <path d="M12 11v5" stroke="#7dd3fc" stroke-width="2" stroke-linecap="round"/>
      </svg>
      <h2>포트폴리오 소개</h2>
    </div>

    <p>
      수업 과제로 시작했지만 인공지능 전공을 공부하면서 자연스럽게 다양한 실습과 프로젝트를 접하게 됐고,
      그 과정에서 “배운 내용을 기록으로 남기는 일”의 필요성을 느끼게 됐다.
      이 포트폴리오(AI-BOX)는 그 기록을 정리하고, 나중에 다시 참고할 수 있는 개인 공간을 만들고자 시작한 프로젝트다.
    </p>

    <p>
      지금은 주로 딥러닝과 컴퓨터비전 실습을 중심으로 학습하고 있고,
      간단한 모델 실험부터 데이터 전처리, 증강, 최적화 과정까지
      실제로 손으로 다뤄봐야 이해가 깊어지는 부분을 꾸준히 정리하고 있다.
      특히 모델이 어떻게 동작하는지 “직접 관찰하고 비교하는 과정”을 중요하게 생각한다.
    </p>
  </div>

  <!-- 관심 분야 -->
  <div class="section-card">
    <div class="about-section-title">
      <svg viewBox="0 0 24 24" fill="none">
        <circle cx="12" cy="12" r="9" stroke="#a78bfa" stroke-width="1.4"/>
        <circle cx="12" cy="12" r="5" stroke="#a78bfa" stroke-width="1.4"/>
      </svg>
      <h2>관심 분야</h2>
    </div>

    <p>
      아직 배우는 단계이지만, 아래 분야들을 중점적으로 공부하고 있다.
      수업뿐 아니라 실제 데이터를 다뤄보며 흥미가 더 커지는 중이다.
    </p>

    <ul>
      <li><b>Computer Vision</b> — Object Detection, Pose Tracking 등 실시간 분석 분야</li>
      <li><b>Generative AI</b> — Diffusion 기반 이미지 생성, 스타일 변환 실험</li>
      <li><b>Deep Learning Optimization</b> — 학습률, 배치 크기, 정규화 등 하이퍼파라미터 실험</li>
      <li><b>Reinforcement Learning</b> — 간단한 환경을 직접 만들어 보는 수준의 RL 실험</li>
      <li><b>AI Automation</b> — Vision + 간단한 로직을 결합한 자동화 시나리오 구상</li>
    </ul>

    <p>
      모든 내용이 완전히 정리된 건 아니지만,
      실험과 실패를 반복하면서 이해가 조금씩 깊어지는 과정 자체를 즐기고 있다.
    </p>
  </div>

  <!-- 포트폴리오를 만든 이유 -->
  <div class="section-card">
    <div class="about-section-title">
      <svg viewBox="0 0 24 24" fill="none">
        <path d="M12 3l8 4-8 4-8-4 8-4z" stroke="#f9a8d4" stroke-width="1.4" />
        <path d="M4 12l8 4 8-4" stroke="#f9a8d4" stroke-width="1.4" />
        <path d="M4 16l8 4 8-4" stroke="#f9a8d4" stroke-width="1.4" />
      </svg>
      <h2>포트폴리오를 만든 이유</h2>
    </div>

    <p>
      학기마다 배우는 내용이 계속 쌓이는데, 시간이 지나면 정작 어떤 실험을 했는지 기억이 잘 나지 않는다.
      그래서 단순히 결과만 모아두는 대신,
      <b>배경 → 진행 과정 → 시행착오 → 개선점</b> 순서로 정리해두면
      나중에 다시 보고 활용하기 좋겠다는 생각이 들었다.
    </p>

    <p>
      Projects 페이지는 각 실습·프로젝트를 카드 형태로 정리한 공간이고,
      Blog는 실험 로그와 공부 중 떠오른 생각을 자유롭게 적는 공간이다.
      두 페이지 모두 “완성된 성과”보다 “성장 과정의 기록”에 더 초점을 맞추고 있다.
    </p>
  </div>

  <!-- 향후 계획 -->
  <div class="section-card">
    <div class="about-section-title">
      <svg viewBox="0 0 24 24" fill="none">
        <path d="M5 3h14v4H5z" stroke="#c084fc" stroke-width="1.4"/>
        <circle cx="7" cy="14" r="2" stroke="#c084fc" stroke-width="1.4"/>
        <circle cx="17" cy="18" r="2" stroke="#c084fc" stroke-width="1.4"/>
        <path d="M7 14v-7h10v11" stroke="#c084fc" stroke-width="1.4" />
      </svg>
      <h2>향후 계획</h2>
    </div>

    <p>
      앞으로 배우는 과목이나 진행하는 프로젝트가 늘어날수록,
      이 공간도 함께 확장될 예정이다. 특히 아래 작업들을 천천히 추가해보고 싶다.
    </p>

    <ul>
      <li>실습을 진행할 때마다 Blog에 단계별 기록 추가</li>
      <li>작은 개인 프로젝트도 Projects에 모두 아카이빙</li>
      <li>비전·생성 모델 실험을 더 체계적으로 문서화</li>
      <li>태그, 검색 등 탐색 기능 강화</li>
      <li>학기별 정리 페이지(“Semester Notes”) 추가</li>
    </ul>

    <p>
      아직은 공부 중인 학생이지만,
      차근차근 기록을 쌓아가면 나중에는 성장 과정을 한눈에 볼 수 있는
      나만의 연구 노트가 될 거라고 생각한다.
    </p>
  </div>

</div> <!-- /.about-container -->
