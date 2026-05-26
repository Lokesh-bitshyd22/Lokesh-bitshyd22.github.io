---
layout: default
---

<section class="home-intro">
  <h1>Lokesh<br><em>Student & Developer.</em></h1>
  <p class="tagline">
    I build things with code — from web apps to systems that solve real problems.
    Currently studying at <!-- Your College -->, exploring the edge between
    software engineering and everything else.
  </p>
</section>

<section class="home-section">
  <h2>Now</h2>
  <p>
    <!-- What you're currently working on, learning, or thinking about.
         Update this regularly — it keeps your site alive. -->
    Currently working on <!-- Project Name -->, learning <!-- Skill/Topic -->,
    and looking for opportunities in <!-- domain e.g. backend / full-stack -->.
  </p>
</section>

<section class="home-section">
  <h2>Selected Projects</h2>

  <!-- Repeat this block for each project (max 3 here) -->
  <div class="projects-list">
    <div class="project-item">
      <div class="project-main">
        <h2>Project Name</h2>
        <p>A short one-liner describing what it does and why it matters.</p>
        <div class="project-tags">
          <span class="tag">Python</span>
          <span class="tag">React</span>
        </div>
      </div>
      <div class="project-meta">
        <span class="project-year">2024</span>
        <a class="project-link" href="https://github.com/lokesh2005/project" target="_blank">↗ view</a>
      </div>
    </div>
  </div>

  <a class="view-all" href="{{ '/projects' | relative_url }}">all projects →</a>
</section>

<section class="home-section">
  <h2>Recent Writing</h2>

  <div class="blog-list">
    {% for post in site.posts limit:4 %}
    <div class="recent-post">
      <span class="recent-post-date">{{ post.date | date: "%b %d, %Y" }}</span>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </div>
    {% else %}
    <p style="color: var(--gray-mid); font-size: 0.9rem;">No posts yet. Coming soon.</p>
    {% endfor %}
  </div>

  <a class="view-all" href="{{ '/blog' | relative_url }}">all writing →</a>
</section>
