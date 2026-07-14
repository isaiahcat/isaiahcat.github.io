---
layout: default
title: Home
---

<div class="wrapper">
  <div class="main">

    <!-- HERO -->
    <div class="header" style="text-align: center; margin-bottom: 1rem;">
      <div class="hero-avatar">IB</div>
      <h1 style="font-size: 24px; font-weight: 500; margin: 0;">Isaiah Butler</h1>
      <p class="job-title">Software Engineer &amp; Programming Educator</p>
      <p style="max-width: 28rem; margin: 0.6rem auto 0; font-size: 13px; color: #888; line-height: 1.6;">
        5+ years shipping mobile software at scale, now building EdTech tools and teaching the next generation of programmers.
      </p>
      {% include socials.html %}
    </div>

    <!-- FEATURED -->
    <section id="featured" class="section">
      <p class="eyebrow">Featured projects</p>
      {% assign featured_projects = site.projects | where: "featured", true | sort: "priority" %}
      <div class="projects-grid featured-grid">
        {% for project in featured_projects %}
          {% include project-card.html project=project %}
        {% endfor %}
      </div>
    </section>

    <!-- ALL PROJECTS -->
    <section id="projects" class="section">
      <p class="eyebrow">All projects</p>

      <div class="project-search-wrap">
        <i class="fas fa-search"></i>
        <input type="text" id="project-search" class="project-search" placeholder="Search projects...">
      </div>

      <div class="tag-filters" id="tag-filters">
        <button class="tag-filter active" data-track="all">All</button>
        <button class="tag-filter" data-track="swe">Software Engineering</button>
        <button class="tag-filter" data-track="teaching">Teaching</button>
        <button class="tag-filter" data-track="personal">Personal</button>
      </div>

      <div class="projects-grid" id="all-projects-grid">
        {% assign all_projects = site.projects | sort: "date" | reverse %}
        {% for project in all_projects %}
          {% include project-card.html project=project %}
        {% endfor %}
      </div>
      <p class="no-results" id="no-results" hidden>No projects match your search.</p>
    </section>

    <!-- ABOUT -->
    <section id="about" class="section">
      <p class="eyebrow">About me</p>
      <div class="about-text">
        <p>Hi! 👋 I'm Isaiah Butler — a Software Engineer with a background in mobile development and a Master's in Computer Science. 🤖</p>
        <p>I've shipped Android apps used by millions, and I'm now focused on EdTech, developer tooling, and small product teams where engineers own meaningful slices of work.</p>
        <p>Alongside engineering, I teach programming part-time and I'm building toward a longer-term goal of teaching computer science at the college level.</p>
        <p>From mobile apps to internal tools to AI-driven projects, I love building things that matter — and I'm always excited to learn more. 🤓</p>
      </div>
    </section>

    <!-- SKILLS -->
    <section id="skills" class="section">
      <p class="eyebrow">Skills</p>
      <div class="skills-grid">
        <div class="skill-card">
          <h4>Engineering &amp; Systems</h4>
          <div class="skill-pills">
            <span>Java</span>
            <span>Python</span>
            <span>C</span>
            <span>C++</span>
            <span>C#</span>
            <span>JavaScript</span>
            <span>HTML</span>
            <span>CSS</span>
            <span>Android (Kotlin/Java)</span>
            <span>iOS (Objective-C)</span>
            <span>Embedded Systems</span>
            <span>MySQL</span>
            <span>AWS</span>
            <span>Firebase</span>
            <span>Amazon S3</span>
            <span>Git</span>
          </div>
        </div>

        <div class="skill-card">
          <h4>AI / ML</h4>
          <div class="skill-pills">
            <span>TensorFlow</span>
            <span>PyTorch</span>
            <span>Keras</span>
            <span>Jupyter</span>
            <span>Pandas</span>
            <span>NLP</span>
            <span>LLMs</span>
          </div>
        </div>

        <div class="skill-card">
          <h4>Leadership &amp; Delivery</h4>
          <div class="skill-pills">
            <span>Agile</span>
            <span>Scrum</span>
            <span>Waterfall</span>
            <span>Jira</span>
            <span>Confluence</span>
            <span>Trello</span>
            <span>Azure</span>
            <span>Team Leadership</span>
            <span>Stakeholder Management</span>
            <span>Risk Management</span>
            <span>Client Communication</span>
            <span>Resource Planning</span>
            <span>Cross-functional Collaboration</span>
            <span>Problem Solving</span>
            <span>Reports &amp; Analytics</span>
            <span>Decision-Making</span>
          </div>
        </div>
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" class="section">
      <p class="eyebrow">Contact me</p>
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

    <footer class="footer">
      {% include socials.html %}
      <p>&copy; Isaiah Butler. 2026. All rights reserved.</p>
    </footer>
  </div>
</div>

<div class="modal-overlay" id="project-modal-overlay">
  {% for project in site.projects %}
    {% include project-modal.html project=project %}
  {% endfor %}
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

  // ---- Project modal ----
  const overlay = document.getElementById('project-modal-overlay');
  const modalBoxes = document.querySelectorAll('.modal-box');

  function closeModal() {
    modalBoxes.forEach(m => m.style.display = 'none');
    overlay.classList.remove('active');
    document.body.classList.remove('modal-open');
  }

  function openModalBySlug(slug) {
    const modal = document.getElementById('modal-' + slug);
    if (!modal) return false;
    modalBoxes.forEach(m => m.style.display = 'none');
    modal.style.display = 'block';
    overlay.classList.add('active');
    document.body.classList.add('modal-open');
    return true;
  }

  document.querySelectorAll('.project-card-trigger').forEach(trigger => {
    trigger.addEventListener('click', function(e) {
      const card = trigger.closest('.project-card');
      const slug = card.getAttribute('data-slug');
      if (openModalBySlug(slug)) {
        e.preventDefault();
        history.pushState({ modal: slug }, '', trigger.getAttribute('href'));
      }
    });
  });

  overlay.addEventListener('click', function(e) {
    if (e.target === overlay) {
      closeModal();
      history.pushState({}, '', '/#projects');
    }
  });

  document.querySelectorAll('.modal-close').forEach(btn => {
    btn.addEventListener('click', function() {
      closeModal();
      history.pushState({}, '', '/#projects');
    });
  });

  document.addEventListener('keydown', function(e) {
    if (e.key === 'Escape' && overlay.classList.contains('active')) {
      closeModal();
      history.pushState({}, '', '/#projects');
    }
  });

  window.addEventListener('popstate', function() {
    const match = window.location.pathname.match(/^\/projects\/([^\/]+)\/?$/);
    if (match) {
      openModalBySlug(match[1]);
    } else {
      closeModal();
    }
  });
})();
</script>