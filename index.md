---
layout: default
title: Home
---

<div class="wrapper">
  <div class="main">

    <!-- HERO -->
    <div class="header" style="text-align: center; margin-bottom: 1rem;">
      <img src="assets/images/image.png" alt="Image" width="172" />
      <h1>Isaiah Butler</h1>
      <div class="divider"></div>
      <p class="job-title">Software Engineer &amp; Programming Educator</p>
      <p style="max-width: 30rem; margin: 0.5rem auto 0; font-size: 0.95rem; color: #3d3d3d;">
        5+ years shipping mobile software at scale, now building EdTech tools and teaching the next generation of programmers.
      </p>
      {% include socials.html %}
    </div>

    <!-- FEATURED -->
    <section id="featured" class="section">
      <div class="section-header">
        <a href="#featured" class="arrow-button"><i class="fas fa-chevron-down"></i></a>
        <h2 class="section-title">Featured Projects</h2>
        <div class="divider"></div>
      </div>
      {% assign featured_projects = site.projects | where: "featured", true | sort: "priority" %}
      <div class="projects-grid featured-grid">
        {% for project in featured_projects %}
          {% include project-card.html project=project %}
        {% endfor %}
      </div>
    </section>

    <!-- ALL PROJECTS -->
    <section id="projects" class="section">
      <div class="section-header">
        <a href="#projects" class="arrow-button"><i class="fas fa-chevron-down"></i></a>
        <h2 class="section-title">All Projects</h2>
        <div class="divider"></div>
      </div>

      <input type="text" id="project-search" class="project-search" placeholder="Search projects...">

      <div class="tag-filters" id="tag-filters">
        <button class="tag-filter active" data-track="all">All</button>
        <button class="tag-filter" data-track="swe">Software Engineering</button>
        <button class="tag-filter" data-track="teaching">Teaching</button>
        <button class="tag-filter" data-track="personal">Personal</button>
      </div>

      <div class="projects-grid" id="all-projects-grid">
        {% assign all_projects = site.projects | sort: "priority" %}
        {% for project in all_projects %}
          {% include project-card.html project=project %}
        {% endfor %}
      </div>
      <p class="no-results" id="no-results" hidden>No projects match your search.</p>
    </section>

    <!-- ABOUT -->
    <section id="about" class="section">
      <div class="section-header">
        <a href="#about" class="arrow-button"><i class="fas fa-chevron-down"></i></a>
        <h2 class="section-title">About Me</h2>
        <div class="divider"></div>
      </div>
      <div class="about-text">
        <p>Hi! 👋 I'm Isaiah Butler — a Software Engineer with a background in mobile development and a Master's in Computer Science. 🤖</p>
        <p>I've shipped Android apps used by millions, and I'm now focused on EdTech, developer tooling, and small product teams where engineers own meaningful slices of work.</p>
        <p>Alongside engineering, I teach programming part-time and I'm building toward a longer-term goal of teaching computer science at the college level.</p>
        <p>From mobile apps to internal tools to AI-driven projects, I love building things that matter — and I'm always excited to learn more. 🤓</p>
      </div>
    </section>

    <!-- SKILLS (unchanged from current site) -->
    <section id="skills" class="section">
      <div class="section-header">
        <a href="#skills" class="arrow-button"><i class="fas fa-chevron-down"></i></a>
        <h2 class="section-title">Skills</h2>
        <div class="divider"></div>
      </div>
      <h3 class="section-subtitle">Software Development</h3>
      <div class="skills-columns">
        <div class="skills-col">
          <h4>Development</h4>
          <ul>
            <li><i class="fas fa-mug-hot"></i> Java</li>
            <li><i class="devicon-python-plain"></i> Python</li>
            <li><i class="devicon-c-plain"></i> C</li>
            <li><i class="devicon-cplusplus-plain"></i> C++</li>
            <li><i class="devicon-csharp-plain"></i> C#</li>
          </ul>
        </div>
        <div class="skills-col">
          <h4>AI/ML</h4>
          <ul>
            <li><i class="devicon-tensorflow-original"></i> TensorFlow</li>
            <li><i class="fas fa-k"></i> Keras</li>
            <li><i class="devicon-jupyter-plain"></i> Jupyter</li>
            <li><i class="devicon-pandas-plain"></i> Pandas</li>
            <li><i class="devicon-pytorch-original"></i> PyTorch</li>
            <li><i class="fas fa-brain"></i> NLP</li>
            <li><i class="fas fa-robot"></i> LLMs</li>
          </ul>
        </div>
        <div class="skills-col">
          <h4>Tools &amp; Infrastructure</h4>
          <ul>
            <li><i class="fab fa-git-alt"></i> Git</li>
            <li><i class="fas fa-fire"></i> Firebase</li>
            <li><i class="fas fa-cloud"></i> Amazon S3</li>
            <li><i class="fas fa-credit-card"></i> Payments</li>
            <li><i class="fas fa-fingerprint"></i> Biometrics</li>
            <li><i class="devicon-embeddedc-plain"></i> Embedded Systems</li>
          </ul>
        </div>
        <div class="skills-col">
          <h4>Mobile Apps</h4>
          <ul>
            <li><i class="fab fa-android"></i> Android (Java/Kotlin)</li>
            <li><i class="fab fa-apple"></i> iOS (Objective-C)</li>
          </ul>
        </div>
        <div class="skills-col">
          <h4>Frontend</h4>
          <ul>
            <li><i class="fab fa-html5"></i> HTML</li>
            <li><i class="fab fa-css3-alt"></i> CSS</li>
            <li><i class="fab fa-js-square"></i> JavaScript</li>
          </ul>
        </div>
        <div class="skills-col">
          <h4>Backend</h4>
          <ul>
            <li><i class="fas fa-database"></i> MySQL</li>
            <li><i class="fas fa-cloud"></i> AWS</li>
          </ul>
        </div>
      </div>
      <h3 class="section-subtitle">Project Management</h3>
      <div class="skills-columns">
        <div class="skills-col">
          <ul>
            <li><i class="fas fa-project-diagram"></i> Agile</li>
            <li><i class="fas fa-network-wired"></i> Scrum</li>
            <li><i class="fas fa-stream"></i> Waterfall</li>
            <li><i class="fab fa-jira"></i> Jira</li>
            <li><i class="fab fa-confluence"></i> Confluence</li>
            <li><i class="fab fa-trello"></i> Trello</li>
            <li><i class="devicon-azure-plain"></i> Azure</li>
          </ul>
        </div>
        <div class="skills-col">
          <ul>
            <li><i class="fas fa-users"></i> Team Leadership</li>
            <li><i class="fas fa-handshake"></i> Stakeholder Management</li>
            <li><i class="fas fa-shield-alt"></i> Risk Management</li>
            <li><i class="fas fa-user-check"></i> Client Communication</li>
          </ul>
        </div>
        <div class="skills-col">
          <ul>
            <li><i class="fas fa-chart-line"></i> Reports &amp; Analytics</li>
            <li><i class="fas fa-gears"></i> Resource Planning</li>
            <li><i class="fas fa-lightbulb"></i> Decision-Making</li>
            <li><i class="fas fa-users-gear"></i> Cross-functional Collaboration</li>
            <li><i class="fas fa-tools"></i> Problem Solving</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" class="section">
      <div class="section-header">
        <a href="#contact" class="arrow-button"><i class="fas fa-chevron-down"></i></a>
        <h2 class="section-title">Contact Me</h2>
        <div class="divider"></div>
      </div>
      <form class="contact-form" id="contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
        <div>
          <label for="name">Name</label>
          <input type="text" id="name" name="name" required>
        </div>
        <div>
          <label for="email">Email</label>
          <input type="email" id="email" name="email" required>
        </div>
        <div>
          <label for="message">Message</label>
          <textarea id="message" name="message" required></textarea>
        </div>
        <button type="submit" class="button-primary">Send Message</button>
        <p class="contact-status" id="contact-status" hidden></p>
      </form>
    </section>

    <section id="end" class="section">
      <div class="section-header">
        <a href="#end" class="arrow-button"><i class="fas fa-chevron-down"></i></a>
        <h2 class="section-title">Thanks!</h2>
        <div class="divider"></div>
      </div>
    </section>

    <footer class="footer">
      {% include socials.html %}
      <p>&copy; Isaiah Butler. 2026. All rights reserved.</p>
    </footer>
  </div>
</div>

<script>
(function() {
  const searchInput = document.getElementById('project-search');
  const tagButtons = document.querySelectorAll('.tag-filter');
  const cards = document.querySelectorAll('#all-projects-grid .project-card');
  const noResults = document.getElementById('no-results');
  let activeTrack = 'all';

  function applyFilters() {
    const query = searchInput.value.trim().toLowerCase();
    let visibleCount = 0;

    cards.forEach(card => {
      const track = card.getAttribute('data-track');
      const tech = card.getAttribute('data-tech') || '';
      const title = card.getAttribute('data-title') || '';

      const matchesTrack = activeTrack === 'all' || track === activeTrack;
      const matchesQuery = query === '' || title.includes(query) || tech.includes(query);

      const visible = matchesTrack && matchesQuery;
      card.hidden = !visible;
      if (visible) visibleCount++;
    });

    noResults.hidden = visibleCount !== 0;
  }

  searchInput.addEventListener('input', applyFilters);

  tagButtons.forEach(btn => {
    btn.addEventListener('click', () => {
      tagButtons.forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
      activeTrack = btn.getAttribute('data-track');
      applyFilters();
    });
  });

  // Contact form submission (Formspree-compatible, no page reload)
  const contactForm = document.getElementById('contact-form');
  const contactStatus = document.getElementById('contact-status');

  if (contactForm) {
    contactForm.addEventListener('submit', async function(e) {
      e.preventDefault();
      const formData = new FormData(contactForm);
      contactStatus.hidden = false;
      contactStatus.textContent = 'Sending...';
      try {
        const response = await fetch(contactForm.action, {
          method: 'POST',
          body: formData,
          headers: { 'Accept': 'application/json' }
        });
        if (response.ok) {
          contactStatus.textContent = "Thanks! I'll get back to you soon.";
          contactForm.reset();
        } else {
          contactStatus.textContent = 'Something went wrong. Please email me directly instead.';
        }
      } catch (err) {
        contactStatus.textContent = 'Something went wrong. Please email me directly instead.';
      }
    });
  }
})();
</script>