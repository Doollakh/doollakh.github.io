---
layout: page
permalink: /classes/python-fundamentals/
title: Python Fundamentals
description: The starting course — from no code at all to writing programs that work.
nav: false

# ---------------------------------------------------------------------------
# Course format. Numbers came from your existing page. Delete any row you'd
# rather not publish; nothing renders for a missing one.
# ---------------------------------------------------------------------------
format:
  - label: "Sessions"
    value: "12"
  - label: "Each"
    value: "1.5 hours"
  - label: "Prerequisite"
    value: "None"

# ---------------------------------------------------------------------------
# Syllabus, in your original order. Group names only mark where the subject
# changes — they don't reorder anything.
#
# `note` is a one-line gloss. Delete every note line for the bare list.
# ---------------------------------------------------------------------------
groups:
  - name: "Values and expressions"
    topics:
      - num: 1
        title: "Variables"
        note: "Naming a value so you can use it again, and what assignment actually does."
      - num: 2
        title: "Data types and type conversion"
        note: "Numbers, text and booleans — and moving between them deliberately rather than by accident."
      - num: 3
        title: "Operators"
        note: "Arithmetic, comparison and logical operators, and the order Python applies them in."
      - num: 4
        title: "Strings"
        note: "Working with text: indexing, slicing, formatting, and the methods you reach for daily."

  - name: "Control flow"
    topics:
      - num: 5
        title: "Conditional statements"
        note: "if, elif and else — letting a program take different paths."
      - num: 6
        title: "Loops"
        note: "while and for, and recognising which one a problem is asking for."

  - name: "Building real programs"
    topics:
      - num: 7
        title: "Functions"
        note: "Packaging a piece of work under a name, with arguments and a return value."
      - num: 8
        title: "Exception handling"
        note: "try and except — dealing with what goes wrong instead of crashing."
      - num: 9
        title: "Collections"
        note: "Lists, tuples, sets and dictionaries, and picking the right one for the job."

# Forward pointer to the next rung of the ladder. Delete to remove.
next:
  icon: "🚀"
  title: "Python Intermediate"
  blurb: "NumPy and Pandas, object-oriented Python, scraping the web, and Streamlit."
  link: /classes/python-intermediate/
---

{%- assign all_topics = "" | split: "" -%}
{%- for group in page.groups -%}{%- assign all_topics = all_topics | concat: group.topics -%}{%- endfor -%}

<style>
/* ===== Syllabus page =====================================================
   Same structure and class names as the Python Intermediate page, so the two
   stay a matched pair. Colours are al-folio's theme tokens throughout.
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

.syl-lede { font-size: 1.02rem; line-height: 1.65; margin: 0 0 0.75rem; max-width: 62ch; }
.syl-sub {
  font-size: 0.88rem; line-height: 1.6; margin: 0 0 2rem; max-width: 62ch;
  color: var(--global-text-color-light);
}

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

/* --- next course --------------------------------------------------------- */
.syl a.syl-next {
  display: flex; align-items: center; gap: 0.9rem;
  margin-top: 2.5rem; padding: 0.95rem 1.1rem;
  background: var(--global-card-bg-color);
  border: 1px solid var(--global-divider-color); border-radius: 11px;
  color: var(--global-text-color); text-decoration: none;
  transition: transform 0.18s ease, border-color 0.18s ease, box-shadow 0.18s ease;
}
.syl a.syl-next:hover, .syl a.syl-next:focus-visible {
  transform: translateY(-3px); border-color: var(--global-theme-color);
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.09);
  text-decoration: none; color: var(--global-text-color);
}
.syl a.syl-next:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: 2px; }
.syl-next-icon {
  display: grid; place-items: center; flex: none;
  width: 2.75rem; height: 2.75rem; border-radius: 10px;
  background: var(--syl-tint); font-size: 1.4rem; line-height: 1;
}
.syl-next-label {
  display: block; font-family: var(--syl-mono); font-size: 0.66rem; font-weight: 600;
  letter-spacing: 0.11em; text-transform: uppercase;
  color: var(--global-theme-color); margin-bottom: 0.15rem;
}
.syl-next-title { display: block; font-size: 1rem; font-weight: 600; line-height: 1.35; }
.syl-next-blurb {
  display: block;                      /* spans are inline — without this the
                                          blurb runs on from the title */
  font-size: 0.83rem; line-height: 1.5;
  color: var(--global-text-color-light); margin: 0.1rem 0 0;
}
.syl-next-arrow { margin-left: auto; flex: none; color: var(--global-theme-color); }
.syl-next-arrow svg { width: 1rem; height: 1rem; transition: transform 0.18s ease; }
.syl a.syl-next:hover .syl-next-arrow svg { transform: translateX(3px); }

.syl-foot {
  margin-top: 2.5rem; padding-top: 1.25rem;
  border-top: 1px solid var(--global-divider-color);
  font-size: 0.86rem; line-height: 1.6; color: var(--global-text-color-light);
}

@media (max-width: 576px) {
  .syl-group { padding-left: 1.15rem; padding-bottom: 1.75rem; }
  .syl-group-head::before { left: calc(-1.15rem - 5px); }
  .syl-format li { flex-basis: 100%; }
  .syl-next-arrow { display: none; }
}

@media (prefers-reduced-motion: reduce) {
  .syl a.syl-next, .syl-next-arrow svg { transition: none; }
  .syl a.syl-next:hover { transform: none; }
  .syl a.syl-next:hover .syl-next-arrow svg { transform: none; }
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

<p class="syl-lede">The course to start with if you have never written a line of code. Twelve sessions build Python up from nothing — values, control flow, functions and data structures — with extra sessions for exercises and problem-solving on top of those twelve.</p>

<p class="syl-sub">Almost every session comes with a practice assignment. You hand it in, you get feedback on it, and the exercises are worked through and discussed in class rather than just marked and returned.</p>

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

{%- if page.next %}
<a class="syl-next" href="{{ page.next.link | relative_url }}">
<span class="syl-next-icon" aria-hidden="true">{{ page.next.icon }}</span>
<span>
<span class="syl-next-label">Next course</span>
<span class="syl-next-title">{{ page.next.title }}</span>
{%- if page.next.blurb %}
<span class="syl-next-blurb">{{ page.next.blurb }}</span>
{%- endif %}
</span>
<span class="syl-next-arrow"><svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M2.5 8h11M9.5 4l4 4-4 4"/></svg></span>
</a>
{%- endif %}

<p class="syl-foot">These are the main {{ all_topics | size }} topics, not the whole of it — the exercise sessions go wherever the group needs them.{% if site.email %} Questions are welcome, <a href="mailto:{{ site.email }}">get in touch</a>.{% endif %}</p>

</div>
