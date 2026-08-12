---
layout: page
permalink: /classes/python-intermediate/
title: Python Intermediate
description: The working toolkit — data, better Python, and getting a project out the door.
nav: false

# ---------------------------------------------------------------------------
# Course format. Delete any row you'd rather not publish; nothing renders for
# a missing one. Numbers here came from your existing course page.
# ---------------------------------------------------------------------------
format:
  - label: "Sessions"
    value: "15"
  - label: "Each"
    value: "1.5 hours"
  - label: "Assignments"
    value: "10"
  - label: "Prerequisite"
    value: "Python Fundamentals"
    link: /classes/python-fundamentals/

# ---------------------------------------------------------------------------
# Syllabus. Topics are in your original order — the group names just mark where
# the subject changes, they don't reorder anything.
#
# `note` is a one-line gloss. Delete every note line if you want the bare list.
# ---------------------------------------------------------------------------
groups:
  - name: "Working with data"
    topics:
      - num: 1
        title: "NumPy"
        note: "Arrays and vectorised computation — the layer the rest of the data stack sits on."
      - num: 2
        title: "Pandas"
        note: "DataFrames: loading, cleaning, filtering, grouping and joining tabular data."
      - num: 3
        title: "Matplotlib / Seaborn / Plotly"
        note: "Three plotting libraries — the general one, the statistical one, and the interactive one."
      - num: 4
        title: "os / glob"
        note: "Finding, walking and pattern-matching files so a script can work through a whole folder."

  - name: "Writing Python well"
    topics:
      - num: 5
        title: "Lambda functions"
        note: "Small anonymous functions, and treating a function as a value you can pass around."
      - num: 6
        title: "filter / map / reduce"
        note: "Applying a function across a collection instead of writing the loop yourself."
      - num: 7
        title: "List and dictionary comprehension"
        note: "Building lists and dictionaries in a single readable expression."
      - num: 8
        title: "Object-oriented programming"
        note: "Classes, inheritance and access modifiers — organising code around what it models."

  - name: "From the web to an app"
    topics:
      - num: 9
        title: "Selenium"
        note: "Driving a real browser to reach pages that only exist once the JavaScript has run."
      - num: 10
        title: "Beautiful Soup"
        note: "Parsing HTML and pulling out just the parts you need."
      - num: 11
        title: "Streamlit"
        note: "Turning a script into a shareable web app without writing any front-end code."
      - num: 12
        title: "Regular expressions"
        note: "Matching and extracting patterns in text — what finishes most scraping jobs."
---

{%- assign all_topics = "" | split: "" -%}
{%- for group in page.groups -%}{%- assign all_topics = all_topics | concat: group.topics -%}{%- endfor -%}

<style>
/* ===== Syllabus page =====================================================
   No slides for this course, so no cards and no thumbnails — a syllabus reads
   better as a dense list. Same theme tokens and monospace utility face as the
   rest of the site so it still belongs to the set.
   ========================================================================= */
.syl {
  --syl-mono: ui-monospace, SFMono-Regular, "SF Mono", Menlo, Consolas, "Liberation Mono", monospace;
  --syl-rail: rgba(128, 128, 128, 0.25);
  --syl-rail: color-mix(in srgb, var(--global-theme-color) 25%, transparent);
  --syl-tint: rgba(128, 128, 128, 0.08);
  --syl-tint: color-mix(in srgb, var(--global-theme-color) 9%, transparent);
  margin-top: 1.5rem;
}

.syl-back {
  display: inline-flex; align-items: center; gap: 0.35rem;
  font-family: var(--syl-mono); font-size: 0.72rem; font-weight: 600;
  letter-spacing: 0.04em; margin-bottom: 1.75rem;
}
.syl-back svg { width: 0.85em; height: 0.85em; }

/* --- course format ------------------------------------------------------- */
.syl-format {
  display: flex; flex-wrap: wrap; gap: 0.5rem;
  margin: 0 0 2rem; padding: 0; list-style: none;
}
.syl-format li {
  flex: 1 1 8rem;
  padding: 0.7rem 0.85rem; border-radius: 9px; background: var(--syl-tint);
}
.syl-format b {
  display: block; font-family: var(--syl-mono);
  font-size: 0.95rem; font-weight: 700; line-height: 1.3;
  color: var(--global-theme-color);
}
.syl-format span {
  font-size: 0.72rem; letter-spacing: 0.03em; text-transform: uppercase;
  color: var(--global-text-color-light);
}

.syl-lede { font-size: 1.02rem; line-height: 1.65; margin: 0 0 2rem; max-width: 62ch; }

/* --- the syllabus -------------------------------------------------------- */
.syl-group {
  border-left: 1px solid var(--syl-rail);
  padding-left: 1.75rem; padding-bottom: 2.25rem;
}
.syl-group:last-of-type { padding-bottom: 0.5rem; }

.syl-group-head { position: relative; margin-bottom: 0.5rem; }
.syl-group-head::before {
  content: ""; position: absolute;
  left: calc(-1.75rem - 5px); top: 0.4rem;
  width: 9px; height: 9px; border-radius: 50%;
  background: var(--global-bg-color); border: 2px solid var(--global-theme-color);
}
.syl-group-name {
  font-family: var(--syl-mono); font-size: 0.7rem; font-weight: 600;
  letter-spacing: 0.12em; text-transform: uppercase;
  color: var(--global-theme-color); margin: 0;
}

.syl-list { margin: 0; padding: 0; list-style: none; }
.syl-item {
  display: grid; grid-template-columns: 2.4rem 1fr; gap: 0.6rem;
  padding: 0.85rem 0;
  border-bottom: 1px solid var(--global-divider-color);
}
.syl-item:last-child { border-bottom: 0; padding-bottom: 0; }
.syl-num {
  font-family: var(--syl-mono); font-size: 0.78rem; font-weight: 600;
  color: var(--global-text-color-light); padding-top: 0.15rem;
}
.syl-title { font-size: 1rem; font-weight: 600; line-height: 1.4; }
.syl-note {
  font-size: 0.855rem; line-height: 1.55;
  color: var(--global-text-color-light); margin: 0.15rem 0 0; max-width: 56ch;
}

.syl-foot {
  margin-top: 2.5rem; padding-top: 1.25rem;
  border-top: 1px solid var(--global-divider-color);
  font-size: 0.86rem; line-height: 1.6; color: var(--global-text-color-light);
}

@media (max-width: 576px) {
  .syl-group { padding-left: 1.15rem; padding-bottom: 1.75rem; }
  .syl-group-head::before { left: calc(-1.15rem - 5px); }
  .syl-format li { flex-basis: 100%; }
}
</style>

<div class="syl">

<a class="syl-back" href="{{ '/classes/' | relative_url }}"><svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M13.5 8h-11M6.5 4l-4 4 4 4"/></svg> All classes</a>

{%- if page.format %}
<ul class="syl-format">
{%- for row in page.format %}
<li><b>{% if row.link %}<a href="{{ row.link | relative_url }}">{{ row.value }}</a>{% else %}{{ row.value }}{% endif %}</b><span>{{ row.label }}</span></li>
{%- endfor %}
</ul>
{%- endif %}

<p class="syl-lede">The second course picks up where the fundamentals stop. You already know how to write a function and a loop; this one is about the libraries and habits that turn that into real work — handling data, writing Python that reads well, pulling information off the web, and putting a project somewhere other people can use it.</p>

{%- for group in page.groups %}
<section class="syl-group">
{%- if group.name %}
<header class="syl-group-head">
<h2 class="syl-group-name">{{ group.name }}</h2>
</header>
{%- endif %}
<ul class="syl-list">
{%- for topic in group.topics %}
{%- assign padded = topic.num | prepend: '0' | slice: -2, 2 -%}
<li class="syl-item">
<span class="syl-num">{{ padded }}</span>
<div>
<span class="syl-title">{{ topic.title }}</span>
{%- if topic.note %}
<p class="syl-note">{{ topic.note }}</p>
{%- endif %}
</div>
</li>
{%- endfor %}
</ul>
</section>
{%- endfor %}

<p class="syl-foot">{{ all_topics | size }} topics across {{ page.format[0].value }} live sessions, with assignments reviewed and discussed in class.{% if site.email %} Questions are welcome — <a href="mailto:{{ site.email }}">get in touch</a>.{% endif %}</p>

</div>
