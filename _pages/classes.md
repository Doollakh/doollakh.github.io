---
layout: page
permalink: /classes/
title: My Classes
description: Four courses, from your first line of Python to modern deep learning.
nav: true
nav_order: 4

# ---------------------------------------------------------------------------
# Everything below drives the page. Adding a course is a YAML edit.
#
#   level     1-4, fills that many segments of the little meter
#   facts     omit any you don't have yet — nothing renders for a missing one
#   ready     false marks a course as still being written
# ---------------------------------------------------------------------------
hero:
  image: /assets/img/teaching-collage.webp
  alt: "Grid of video-call screenshots from live teaching sessions, showing dozens of students."
  stats:
    - value: "150+"
      label: "students taught"
    - value: "1,000+"
      label: "sessions delivered"
    - value: "5"
      label: "courses"

courses:
  - num: 1
    slug: python-fundamentals
    icon: "🐍"
    title: "Python Fundamentals"
    level: 1
    level_label: "Beginner"
    summary: "Start here if you have never written code. Variables, types, control flow,
      functions, collections and error handling, built up from nothing."
    facts:
      - "12 sessions"
      - "1.5 h each"
    tags: ["Variables", "Loops", "Functions", "Collections", "Exceptions"]

  - num: 2
    slug: python-intermediate
    icon: "🚀"
    title: "Python Intermediate"
    level: 2
    level_label: "Intermediate"
    summary: "Turn code that works into code you can live with: object-oriented design,
      modules, file handling, testing, and projects you finish."
    facts:
      - "15 sessions"
      - "1.5 h each"
      - "10 assignments"
    prereq: "Python Fundamentals"
    tags: ["OOP", "Modules", "File Handling", "Testing"]

  - num: 3
    slug: machine-learning
    icon: "🤖"
    title: "Machine Learning"
    level: 3
    level_label: "Applied"
    summary: "The classical toolkit that comes before neural networks: preparing data,
      supervised learning, and evaluating a model honestly."
    tags: ["Data Preparation", "Supervised Learning", "Evaluation"]

  - num: 4
    slug: deep-learning
    icon: "🧠"
    title: "Deep Learning"
    level: 4
    level_label: "Advanced"
    summary: "Neural networks from a single neuron through convolutional and sequence
      models to transformers, multi-modal systems and generative methods."
    facts:
      - "20 lectures"
      - "slides online"
    tags: ["CNNs", "Transformers", "LLMs", "Generative Models"]

# Runs alongside the ladder rather than on it — no number, no level meter,
# because it isn't a step after Deep Learning. Add more entries here if you
# ever teach another course that doesn't belong in the sequence.
alongside:
  heading: "Alongside the path"
  blurb: "Not a step on the ladder — worth taking at any point along it."
  courses:
    - slug: soft-skills
      icon: "🎤"
      title: "Soft Skills"
      level_label: "Any level"
      summary: "The parts of a technical career that aren't code: presenting your work so
        people follow it, writing a CV that actually gets read, and handling interviews."
      tags: ["Presentations", "CV & Résumé", "Interviews", "Communication"]
---

<style>
/* ===== Class hub =========================================================
   Shares its visual language with the course pages: al-folio theme tokens for
   colour, a monospace utility face for numbers and labels, the same card and
   rail treatment. The two pages should read as one system.
   ========================================================================= */
.hub {
  --hub-mono: ui-monospace, SFMono-Regular, "SF Mono", Menlo, Consolas, "Liberation Mono", monospace;
  --hub-rail: rgba(128, 128, 128, 0.25);
  --hub-rail: color-mix(in srgb, var(--global-theme-color) 25%, transparent);
  --hub-tint: rgba(128, 128, 128, 0.08);
  --hub-tint: color-mix(in srgb, var(--global-theme-color) 9%, transparent);
  --hub-tint-strong: rgba(128, 128, 128, 0.2);
  --hub-tint-strong: color-mix(in srgb, var(--global-theme-color) 22%, transparent);
  margin-top: 1.5rem;
}

/* --- hero ---------------------------------------------------------------- */
.hub-hero img {
  display: block; width: 100%; height: auto;
  border-radius: 12px; border: 1px solid var(--global-divider-color);
}
/* The collage has a white background, which glares against the dark theme.
   A light dim settles it without washing out anyone's face. */
html[data-theme="dark"] .hub-hero img { filter: brightness(0.86); }

/* The numbers are baked into the image, where a screen reader can't reach them
   and a phone renders them at about eight pixels. Restate them in real text. */
.hub-stats {
  display: flex; flex-wrap: wrap; gap: 0.5rem;
  margin: 0.9rem 0 0; padding: 0; list-style: none;
}
.hub-stat {
  flex: 1 1 8rem;
  padding: 0.7rem 0.85rem; border-radius: 9px;
  background: var(--hub-tint);
}
.hub-stat b {
  display: block; font-family: var(--hub-mono);
  font-size: 1.15rem; font-weight: 700; letter-spacing: -0.01em;
  color: var(--global-theme-color); line-height: 1.2;
}
.hub-stat span {
  font-size: 0.76rem; letter-spacing: 0.02em;
  color: var(--global-text-color-light);
}

.hub-lede { font-size: 1.05rem; line-height: 1.65; margin: 2rem 0 0.5rem; }
.hub-hint {
  font-size: 0.88rem; line-height: 1.6;
  color: var(--global-text-color-light); margin: 0 0 2rem; max-width: 62ch;
}

/* --- the ladder ---------------------------------------------------------- */
.hub-path { border-left: 1px solid var(--hub-rail); padding-left: 1.75rem; }

.hub-card {
  position: relative;
  display: grid; grid-template-columns: 4.25rem 1fr; gap: 1.15rem;
  padding: 1.15rem 1.25rem;
  margin-bottom: 1rem;
  background: var(--global-card-bg-color);
  border: 1px solid var(--global-divider-color);
  border-radius: 11px;
  transition: transform 0.18s ease, border-color 0.18s ease, box-shadow 0.18s ease;
}
.hub-card:last-child { margin-bottom: 0; }
.hub a.hub-card { color: var(--global-text-color); text-decoration: none; }
.hub a.hub-card:hover, .hub a.hub-card:focus-visible {
  transform: translateY(-3px);
  border-color: var(--global-theme-color);
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.09);
  text-decoration: none; color: var(--global-text-color);
}
.hub a.hub-card:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: 2px; }

/* node on the rail, one per course */
.hub-card::before {
  content: ""; position: absolute;
  left: calc(-1.75rem - 6px); top: 1.6rem;
  width: 9px; height: 9px; border-radius: 50%;
  background: var(--global-bg-color);
  border: 2px solid var(--global-theme-color);
}

.hub-badge { display: flex; flex-direction: column; align-items: center; gap: 0.5rem; }
.hub-icon {
  display: grid; place-items: center;
  width: 3.5rem; height: 3.5rem; border-radius: 12px;
  background: var(--hub-tint); font-size: 1.75rem; line-height: 1;
}
.hub-num {
  font-family: var(--hub-mono); font-size: 0.72rem; font-weight: 700;
  letter-spacing: 0.08em; color: var(--global-text-color-light);
}

.hub-eyebrow {
  display: flex; align-items: center; flex-wrap: wrap; gap: 0.55rem;
  margin-bottom: 0.3rem;
}
.hub-level {
  font-family: var(--hub-mono); font-size: 0.66rem; font-weight: 600;
  letter-spacing: 0.11em; text-transform: uppercase;
  color: var(--global-theme-color);
}
/* four segments, filled to the course's level — the ladder at a glance */
.hub-meter { display: flex; gap: 3px; }
.hub-meter i { width: 13px; height: 4px; border-radius: 2px; background: var(--hub-tint-strong); }
.hub-meter i.on { background: var(--global-theme-color); }

.hub-title { font-size: 1.12rem; font-weight: 600; line-height: 1.3; margin: 0 0 0.35rem; }
.hub-summary {
  font-size: 0.885rem; line-height: 1.6;
  color: var(--global-text-color-light); margin: 0 0 0.7rem; max-width: 58ch;
}

.hub-facts {
  display: flex; flex-wrap: wrap; align-items: center; gap: 0.4rem;
  font-family: var(--hub-mono); font-size: 0.72rem;
  color: var(--global-text-color-light); margin-bottom: 0.6rem;
}
.hub-facts .sep { opacity: 0.45; }
.hub-prereq { color: var(--global-theme-color); }

.hub-tags { display: flex; flex-wrap: wrap; gap: 0.3rem; margin-bottom: 0.75rem; }
.hub-tag {
  font-family: var(--hub-mono); font-size: 0.66rem;
  padding: 0.15rem 0.42rem; border-radius: 4px;
  background: var(--hub-tint); color: var(--global-text-color-light);
}

.hub-go {
  display: inline-flex; align-items: center; gap: 0.35rem;
  font-family: var(--hub-mono); font-size: 0.72rem; font-weight: 600;
  letter-spacing: 0.04em; color: var(--global-theme-color);
}
.hub-go svg { width: 0.85em; height: 0.85em; flex: none; transition: transform 0.18s ease; }
.hub a.hub-card:hover .hub-go svg { transform: translateX(3px); }
.hub-go--soon { color: var(--global-text-color-light); font-weight: 500; }
.hub-card--soon { border-style: dashed; }

/* Parallel track. Off the rail and behind a rule, because it isn't the next
   rung — the numbering and the meter would both be lying if it sat in line. */
.hub-aside {
  margin-top: 2.5rem; padding-top: 2.25rem;
  border-top: 1px solid var(--global-divider-color);
}
.hub-aside-head {
  font-family: var(--hub-mono); font-size: 0.7rem; font-weight: 600;
  letter-spacing: 0.12em; text-transform: uppercase;
  color: var(--global-theme-color); margin: 0 0 0.4rem;
}
.hub-aside-blurb {
  font-size: 0.88rem; line-height: 1.6;
  color: var(--global-text-color-light); margin: 0 0 1.15rem; max-width: 58ch;
}
.hub-aside .hub-card { margin-bottom: 0.85rem; }
.hub-aside .hub-card:last-child { margin-bottom: 0; }
.hub-aside .hub-card::before { display: none; }   /* no rail, so no node */

.hub-foot {
  margin-top: 2.5rem; padding-top: 1.25rem;
  border-top: 1px solid var(--global-divider-color);
  font-size: 0.87rem; line-height: 1.6; color: var(--global-text-color-light);
}

@media (max-width: 576px) {
  .hub-path { padding-left: 1.15rem; }
  .hub-card { grid-template-columns: 1fr; gap: 0.85rem; padding: 1rem; }
  .hub-card::before { left: calc(-1.15rem - 6px); top: 1.4rem; }
  .hub-badge { flex-direction: row; align-items: center; gap: 0.65rem; }
  .hub-icon { width: 2.5rem; height: 2.5rem; font-size: 1.3rem; border-radius: 9px; }
  .hub-stat { flex-basis: 100%; }
}

@media (prefers-reduced-motion: reduce) {
  .hub a.hub-card, .hub-go svg { transition: none; }
  .hub a.hub-card:hover { transform: none; }
  .hub a.hub-card:hover .hub-go svg { transform: none; }
}
</style>

<div class="hub">

{%- if page.hero %}
<div class="hub-hero">
<img src="{{ page.hero.image | relative_url }}" alt="{{ page.hero.alt }}" loading="eager" decoding="async">
{%- if page.hero.stats %}
<ul class="hub-stats">
{%- for stat in page.hero.stats %}
<li class="hub-stat"><b>{{ stat.value }}</b><span>{{ stat.label }}</span></li>
{%- endfor %}
</ul>
{%- endif %}
</div>
{%- endif %}

<p class="hub-lede">Four courses that run as one path, from your first line of Python through to the models behind today's AI systems — and one that runs alongside all of them.</p>

<p class="hub-hint">New to programming? Begin at 01 and work down — each course assumes the one above it. If you already have the background, any of them stands on its own.</p>

<div class="hub-path">
{%- for course in page.courses %}
{%- assign padded = course.num | prepend: '0' | slice: -2, 2 -%}
{%- if course.ready == false %}
<div class="hub-card hub-card--soon">
{%- else %}
<a class="hub-card" href="{{ '/classes/' | append: course.slug | append: '/' | relative_url }}">
{%- endif %}

<div class="hub-badge">
<span class="hub-icon" aria-hidden="true">{{ course.icon }}</span>
<span class="hub-num">{{ padded }}</span>
</div>

<div class="hub-body">
<div class="hub-eyebrow">
<span class="hub-level">{{ course.level_label }}</span>
<span class="hub-meter" role="img" aria-label="Level {{ course.level }} of 4">{% for i in (1..4) %}<i class="{% if i <= course.level %}on{% endif %}"></i>{% endfor %}</span>
</div>
<h2 class="hub-title">{{ course.title }}</h2>
<p class="hub-summary">{{ course.summary }}</p>

{%- if course.facts or course.prereq %}
<div class="hub-facts">
{%- for fact in course.facts %}{% unless forloop.first %}<span class="sep">·</span>{% endunless %}<span>{{ fact }}</span>{% endfor %}
{%- if course.prereq %}{% if course.facts %}<span class="sep">·</span>{% endif %}<span class="hub-prereq">after {{ course.prereq }}</span>{% endif %}
</div>
{%- endif %}

{%- if course.tags %}
<div class="hub-tags">{% for tag in course.tags %}<span class="hub-tag">{{ tag }}</span>{% endfor %}</div>
{%- endif %}

{%- if course.ready == false %}
<span class="hub-go hub-go--soon">In preparation</span>
{%- else %}
<span class="hub-go">Syllabus and materials <svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M2.5 8h11M9.5 4l4 4-4 4"/></svg></span>
{%- endif %}
</div>

{%- if course.ready == false %}
</div>
{%- else %}
</a>
{%- endif %}
{%- endfor %}
</div>

{%- if page.alongside %}
<section class="hub-aside">
{%- if page.alongside.heading %}
<h2 class="hub-aside-head">{{ page.alongside.heading }}</h2>
{%- endif %}
{%- if page.alongside.blurb %}
<p class="hub-aside-blurb">{{ page.alongside.blurb }}</p>
{%- endif %}
{%- for course in page.alongside.courses %}
{%- if course.ready == false %}
<div class="hub-card hub-card--soon">
{%- else %}
<a class="hub-card" href="{{ '/classes/' | append: course.slug | append: '/' | relative_url }}">
{%- endif %}

<div class="hub-badge">
<span class="hub-icon" aria-hidden="true">{{ course.icon }}</span>
</div>

<div class="hub-body">
{%- if course.level_label %}
<div class="hub-eyebrow"><span class="hub-level">{{ course.level_label }}</span></div>
{%- endif %}
<h3 class="hub-title">{{ course.title }}</h3>
<p class="hub-summary">{{ course.summary }}</p>
{%- if course.facts %}
<div class="hub-facts">{% for fact in course.facts %}{% unless forloop.first %}<span class="sep">·</span>{% endunless %}<span>{{ fact }}</span>{% endfor %}</div>
{%- endif %}
{%- if course.tags %}
<div class="hub-tags">{% for tag in course.tags %}<span class="hub-tag">{{ tag }}</span>{% endfor %}</div>
{%- endif %}
{%- if course.ready == false %}
<span class="hub-go hub-go--soon">In preparation</span>
{%- else %}
<span class="hub-go">Syllabus and materials <svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M2.5 8h11M9.5 4l4 4-4 4"/></svg></span>
{%- endif %}
</div>

{%- if course.ready == false %}
</div>
{%- else %}
</a>
{%- endif %}
{%- endfor %}
</section>
{%- endif %}

<p class="hub-foot">Every course runs live, in small groups, with assignments reviewed and discussed in class rather than just marked. {% if site.email %}Questions about any of them are welcome — <a href="mailto:{{ site.email }}">get in touch</a>.{% endif %}</p>

</div>
