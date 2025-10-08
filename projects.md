---
layout: default
title: Projects
---
<!-- Include custom CSS -->
<link rel="stylesheet" href="{{ '/assets/css/projects.css' | relative_url }}">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<header class="page-header">
  <h1>🚀 My Projects</h1>
  <p>A collection of experiments, tools, and AI-powered creations.</p>
</header>

<div class="projects-container">
  {% for project in site.data.projects %}
    <section class="project-card">
      <h2>{{ project.title }}</h2>
      <p><strong>Technologies:</strong> {{ project.technologies }}</p>
      <p>{{ project.description }}</p>

      {% if project.video %}
        <div class="video-container">
          <iframe src="{{ project.video }}" frameborder="0" allowfullscreen></iframe>
        </div>
      {% endif %}

      {% if project.github %}
        <a href="{{ project.github }}" class="github-link" target="_blank">
          <i class="fab fa-github"></i> View on GitHub
        </a>
      {% endif %}
    </section>
  {% endfor %}
</div>

<script>
document.addEventListener("scroll", () => {
  document.querySelectorAll(".project-card").forEach(card => {
    const rect = card.getBoundingClientRect();
    if (rect.top < window.innerHeight - 100) {
      card.style.opacity = 1;
      card.style.transform = "translateY(0)";
    }
  });
});

document.querySelectorAll(".project-card").forEach(card => {
  card.style.opacity = 0;
  card.style.transform = "translateY(40px)";
  card.style.transition = "opacity 0.6s ease, transform 0.6s ease";
});
</script>
