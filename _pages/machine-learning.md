---
layout: page
permalink: /classes/machine-learning/
title: Machine Learning
description: The three families of models — supervised, unsupervised and ensemble — and how to tell whether one is working.
nav: false

# ---------------------------------------------------------------------------
# Course format. These show first in the bar at the top, ahead of the counts
# derived from the syllabus below.
#
# To add the prerequisite when you want it, append:
#   - label: "Prerequisite"
#     value: "Python Intermediate"
#     link: /classes/python-intermediate/
# ---------------------------------------------------------------------------
format:
  - label: "Sessions"
    value: "30"
  - label: "Total"
    value: "40+ hours"

# ---------------------------------------------------------------------------
# Syllabus. `sub` holds the indented items from your slide.
# Numbering restarts in each area, because the areas are parallel families
# rather than one running order.
# ---------------------------------------------------------------------------
areas:
  - name: "Supervised Learning"
    blurb: "Learning from labelled examples — the regression and classification models,
      together with the ideas that decide whether any of them is actually working."
    topics:
      - { num: 1,  title: "Linear regression" }
      - { num: 2,  title: "Polynomial regression" }
      - { num: 3,  title: "Logistic regression" }
      - { num: 4,  title: "Feature engineering" }
      - { num: 5,  title: "Gradient descent" }
      - { num: 6,  title: "Overfitting and underfitting" }
      - { num: 7,  title: "Bias–variance tradeoff" }
      - { num: 8,  title: "Normalization" }
      - { num: 9,  title: "Parameters and hyperparameters" }
      - { num: 10, title: "Cost and loss functions" }
      - { num: 11, title: "Evaluation metrics" }
      - { num: 12, title: "Decision trees" }
      - { num: 13, title: "Artificial neural networks" }
      - { num: 14, title: "Support vector machines" }
      - { num: 15, title: "K-nearest neighbours" }
      - { num: 16, title: "Naïve Bayes" }

  - name: "Unsupervised Learning"
    blurb: "Finding structure with no labels at all: grouping points that belong together,
      spotting the ones that don't, and squeezing high-dimensional data down to something
      you can actually look at."
    topics:
      - { num: 1, title: "K-means", sub: ["Silhouette analysis", "Limitations"] }
      - { num: 2, title: "Spectral clustering" }
      - { num: 3, title: "DBSCAN" }
      - { num: 4, title: "Agglomerative clustering" }
      - { num: 5, title: "Gaussian mixture models" }
      - { num: 6, title: "Anomaly detection algorithms" }
      - { num: 7, title: "Dimensionality reduction", sub: ["Curse of dimensionality", "PCA", "t-SNE"] }

  - name: "Ensemble Learning"
    blurb: "Combining many ordinary models into one good one — usually a better use of
      effort than tuning a single model harder."
    topics:
      - { num: 1, title: "Voting classifiers", sub: ["Hard and soft voting"] }
      - { num: 2, title: "Bagging and pasting" }
      - { num: 3, title: "Random forests", sub: ["Random patch", "Random subspace", "Feature importance"] }
      - { num: 4, title: "Extra-trees" }
      - { num: 5, title: "Boosting", sub: ["AdaBoost", "Gradient boosting", "Recent methods — XGBoost, CatBoost"] }
      - { num: 6, title: "Stacking" }

  # An area with no `topics:` renders as heading and blurb only — right when the
  # area name *is* the subject. It still counts as one topic in the totals.
  - name: "AutoML"
    blurb: "Handing model choice and hyperparameter tuning to a search process — what it
      buys you, and where you still need to look at the result yourself."
---

{%- assign topic_count = 0 -%}
{%- for area in page.areas -%}
{%- if area.topics -%}{%- assign topic_count = topic_count | plus: area.topics.size -%}
{%- else -%}{%- assign topic_count = topic_count | plus: 1 -%}{%- endif -%}
{%- endfor -%}
{%- assign area_count = page.areas | size -%}

<style>
/* ===== Syllabus page =====================================================
   Same language as the two Python course pages. Two differences this syllabus
   forced: topics can carry sub-topics, and the list runs in columns — thirty
   items in a single file would be a very long scroll for very short lines.
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

/* --- areas --------------------------------------------------------------- */
.syl-area {
  border-left: 1px solid var(--syl-rail);
  padding-left: 1.75rem; padding-bottom: 2.5rem;
}
.syl-area:last-of-type { padding-bottom: 0.5rem; }

.syl-area-head { position: relative; margin-bottom: 1rem; }
.syl-area-head::before {
  content: ""; position: absolute;
  left: calc(-1.75rem - 5px); top: 0.4rem;
  width: 9px; height: 9px; border-radius: 50%;
  background: var(--global-bg-color); border: 2px solid var(--global-theme-color);
}
.syl-area-name {
  font-family: var(--syl-mono); font-size: 0.7rem; font-weight: 600;
  letter-spacing: 0.12em; text-transform: uppercase;
  color: var(--global-theme-color); margin: 0 0 0.4rem;
}
.syl-area-count { opacity: 0.6; }
.syl-area-blurb {
  font-size: 0.885rem; line-height: 1.6;
  color: var(--global-text-color-light); margin: 0; max-width: 60ch;
}

/* Multi-column so the flow runs down one column then the next, which is how a
   numbered list wants to be read. Collapses to one column on its own. */
.syl-cols { columns: 17rem 2; column-gap: 2.25rem; margin: 0; padding: 0; list-style: none; }
.syl-item {
  break-inside: avoid; -webkit-column-break-inside: avoid;
  display: grid; grid-template-columns: 2.1rem 1fr; gap: 0.5rem;
  padding: 0.42rem 0;
}
.syl-num {
  font-family: var(--syl-mono); font-size: 0.75rem; font-weight: 600;
  color: var(--global-text-color-light); padding-top: 0.16rem;
}
.syl-title { font-size: 0.95rem; font-weight: 600; line-height: 1.45; }
.syl-sub {
  font-size: 0.8rem; line-height: 1.5;
  color: var(--global-text-color-light); margin: 0.1rem 0 0;
}
.syl-sub .sep { opacity: 0.45; padding: 0 0.15rem; }

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
  display: block; font-size: 0.83rem; line-height: 1.5;
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
  .syl-area { padding-left: 1.15rem; padding-bottom: 2rem; }
  .syl-area-head::before { left: calc(-1.15rem - 5px); }
  .syl-cols { columns: 1; }
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

<ul class="syl-format">
{%- for row in page.format %}
<li><b>{% if row.link %}<a href="{{ row.link | relative_url }}">{{ row.value }}</a>{% else %}{{ row.value }}{% endif %}</b><span>{{ row.label }}</span></li>
{%- endfor %}
<li><b>{{ topic_count }}</b><span>Topics</span></li>
<li><b>{{ area_count }}</b><span>Areas</span></li>
</ul>

<p class="syl-lede">Machine learning as it is actually practised: the three families of models, and — just as much of the course — the habits that tell you whether the thing you built works or only looks like it does. Overfitting, the bias–variance tradeoff and evaluation metrics sit early on purpose, because every model after them depends on getting those right.</p>

{%- for area in page.areas %}
<section class="syl-area">
<header class="syl-area-head">
<h2 class="syl-area-name">{{ area.name }}{% if area.topics %} <span class="syl-area-count">· {{ area.topics | size }} topics</span>{% endif %}</h2>
{%- if area.blurb %}
<p class="syl-area-blurb">{{ area.blurb }}</p>
{%- endif %}
</header>
{%- if area.topics %}
<ul class="syl-cols">
{%- for topic in area.topics %}
{%- assign padded = topic.num | prepend: '0' | slice: -2, 2 -%}
<li class="syl-item">
<span class="syl-num">{{ padded }}</span>
<div>
<span class="syl-title">{{ topic.title }}</span>
{%- if topic.sub %}
<p class="syl-sub">{% for s in topic.sub %}{% unless forloop.first %}<span class="sep">·</span>{% endunless %}{{ s }}{% endfor %}</p>
{%- endif %}
</div>
</li>
{%- endfor %}
</ul>
{%- endif %}
</section>
{%- endfor %}

<a class="syl-next" href="{{ '/classes/deep-learning/' | relative_url }}">
<span class="syl-next-icon" aria-hidden="true">🧠</span>
<span>
<span class="syl-next-label">Next course</span>
<span class="syl-next-title">Deep Learning</span>
<span class="syl-next-blurb">Neural networks from a single neuron through to transformers and generative models.</span>
</span>
<span class="syl-next-arrow"><svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M2.5 8h11M9.5 4l4 4-4 4"/></svg></span>
</a>

<p class="syl-foot">{{ topic_count }} topics across {{ area_count }} areas, over 30 live sessions and more than 40 hours, with exercises worked through in class.{% if site.email %} Questions are welcome, <a href="mailto:{{ site.email }}">get in touch</a>.{% endif %}</p>

</div>
