---
layout: page
title: Blog
permalink: /blog/
---

<style>
.post-list-custom li {
  margin-bottom: 8px;
}
.post-list-custom a {
  text-decoration: none;
}
.post-list-custom a:hover {
  text-decoration: underline;
}
</style>

# 📝 Blog

공부하면서 정리한 내용, 실험 로그, 삽질 기록 등을  
가볍게 옮겨두는 공간입니다.

아직 게시된 글은 없지만,  
나중에 `_posts` 폴더에 글을 추가하면 이 페이지에 자동으로 목록이 표시됩니다.

---

{% if site.posts and site.posts != empty %}
<ul class="post-list-custom">
  {% for post in site.posts %}
  <li>
    <a href="{{ post.url | relative_url }}">
      {{ post.date | date: "%Y-%m-%d" }} – {{ post.title }}
    </a>
  </li>
  {% endfor %}
</ul>
{% else %}
> 아직 포스트가 없습니다.  
> 첫 번째 글은 “최근에 해본 실험/프로젝트 회고” 정도로 시작해도 좋아요.
{% endif %}
