---
layout: default
---

<section class="home-intro">
  <h1>Lokesh<br><em>Mathematician & Computer Scientist.</em></h1>
  <p class="tagline">
    Final-year undergraduate in Mathematics and Computer Science at BITS Pilani, Hyderabad.
    Interested in theoretical computer science, algebraic complexity, and combinatorics.
    Incoming Visiting Student at The Institute of Mathematical Sciences.
  </p>
</section>

<section class="home-section">
  <h2>Now</h2>
  <p>
    Wrapping up my dual degree (M.Sc. Mathematics & B.E. CS) at BITS Pilani.
    Starting a year-long thesis at IMSc Chennai on algebraic methods in computational complexity.
    Currently studying field theory and extremal combinatorics.
  </p>
</section>

<section class="home-section">
  <h2>Selected Projects</h2>

  <div class="projects-list">
    <div class="project-item">
      <div class="project-main">
        <h2>Galerkin Neural Networks for PDEs</h2>
        <p>Neural-network-based Galerkin framework in JAX for solving partial differential equations. Explored adaptive basis construction, domain decomposition, and time discretization. Resulted in a joint publication.</p>
        <div class="project-tags">
          <span class="tag">JAX</span>
          <span class="tag">Python</span>
          <span class="tag">NumPy</span>
          <span class="tag">Computational Mathematics</span>
        </div>
      </div>
      <div class="project-meta">
        <span class="project-year">2025</span>
      </div>
    </div>

    <div class="project-item">
      <div class="project-main">
        <h2>Tiger Language Compiler</h2>
        <p>Compiler front-end for a subset of the Tiger programming language using Lex and Bison. Implemented parsing, syntax-directed translation, and three-address code generation.</p>
        <div class="project-tags">
          <span class="tag">C</span>
          <span class="tag">Lex</span>
          <span class="tag">Bison</span>
        </div>
      </div>
      <div class="project-meta">
        <span class="project-year">2026</span>
        <a class="project-link" href="https://github.com/Lokesh-bitshyd22/Tiger-Compiler" target="_blank">↗ github</a>
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
