---
layout: page
permalink: /classes/deep-learning/
title: Deep Learning
description: Neural networks and modern deep learning methods.
nav: false
flat: true
pdf_dir: /assets/pdf/classes/deep-learning
img_dir: /assets/img/classes/deep-learning
collage:
  src: /assets/img/teaching-collage.webp
  heading: Taught live
  caption: These decks were built for real sessions, not for reading cold. The room above is every course
    together — Python, machine learning and this one.
  alt: Grid of video-call screenshots from live teaching sessions, showing dozens of students.
  link: /classes/
  link_text: See all four courses
# ---------------------------------------------------------------------------
# FLAT ARRANGEMENT, ADVANCED TOPICS AT THE END.
#
#   no `name:`        -> bare cards, no heading
#   `name:`           -> heading (and a rail node, if the section is on the rail)
#   `detached: true`  -> comes off the rail, fenced off with a rule above it
#
# To put Advanced Topics back in sequence, move its block between lecture 13
# and lecture 18 and delete `detached: true`.
# ---------------------------------------------------------------------------

parts:
- id: lectures
  lectures:
  - num: 1
    slug: 01-neural-network-basics
    title: Neural Network Basics
    summary: Perceptrons and multilayer networks, activation functions, loss design, backpropagation,
      and gradient-based optimisation.
    tags:
    - MLP
    - Backpropagation
    - SGD
    - Activations
  - num: 2
    slug: 02-cnn-basics
    title: CNN Basics
    summary: Convolution, stride and padding, pooling, receptive fields, and why weight sharing is the
      right prior for images.
    tags:
    - Convolution
    - Pooling
    - Receptive Field
  - num: 3
    slug: 03-popular-cnns
    title: Popular CNNs
    summary: LeNet through AlexNet, VGG, Inception, ResNet and DenseNet — what each architecture changed
      and why it stuck.
    tags:
    - ResNet
    - VGG
    - Inception
    - DenseNet
  - num: 4
    slug: 04-transfer-learning
    title: Transfer Learning
    summary: Pre-training and fine-tuning, frozen features versus full adaptation, domain shift, and when
      transfer stops helping.
    tags:
    - Fine-tuning
    - Pre-training
    - Domain Shift
  - num: 5
    slug: 05-object-detection
    title: Object Detection
    summary: Two-stage detectors of the R-CNN family, single-stage detectors like YOLO and SSD, anchors,
      NMS, and the mAP metric.
    tags:
    - R-CNN
    - Fast R-CNN
    - Faster R-CNN
    - YOLO
    - NMS
  - num: 6
    slug: 06-sequence-modeling
    title: Sequence Modeling
    summary: Recurrent networks, LSTM and GRU gating, vanishing gradients, encoder–decoder models, and
      the arrival of attention.
    tags:
    - RNN
    - LSTM
    - GRU
  - num: 7
    slug: 07-transformer-and-llm
    title: Transformer & LLM
    summary: Self-attention and multi-head attention, positional encoding, the full Transformer block,
      and what scaling it up produced.
    tags:
    - Self-Attention
    - Positional Encoding
    - Scaling
  - num: 8
    slug: 08-peft
    title: PEFT
    summary: 'Parameter-efficient fine-tuning: adapters, prefix and prompt tuning, and the low-rank family
      of LoRA and QLoRA.'
    tags:
    - prefix tuning
    - LoRA
    - Adapters
  - num: 9
    slug: 09-post-training
    title: Post-Training
    summary: Supervised instruction tuning, reward modelling and RLHF, and direct preference optimisation
      as a simpler alternative.
    tags:
    - Calibration
    - RLHF
    - DPO
  - num: 10
    slug: 10-reasoning
    title: Reasoning
    summary: Chain-of-thought prompting, self-consistency, spending compute at test time, and training
      models to reason rather than recall.
    tags:
    - Chain-of-Thought
    - Test-Time Compute
  - num: 11
    slug: 11-hallucination
    title: Hallucination
    summary: Why language and vision-language models assert things that aren't grounded, how it gets measured,
      and what actually reduces it.
    tags:
    - Knowledge neuron
    - Retrieval
    - Evaluation
  - num: 12
    slug: 12-multimodal-foundation-models
    title: Multi-modal Foundation Models
    summary: Contrastive image–text pre-training, connecting a vision encoder to a language model, and
      multi-modal instruction tuning.
    tags:
    - CLIP
    - VLM
    - Cross-Modal
  - num: 13
    slug: 13-agentic-ai
    title: Agentic AI
    summary: Planning, tool calling, memory, and multi-agent workflows — plus the hard problem of evaluating
      an agent's behaviour.
    tags:
    - Planning
    - Tool Use
    - Memory
  - num: 18
    slug: 18-self-supervised-learning
    title: Self-Supervised Learning
    summary: Pretext tasks, contrastive methods such as SimCLR and MoCo, non-contrastive BYOL and DINO,
      and masked modelling with MAE.
    tags:
    - Contrastive
    - BYOL
    - DINO
    - MAE
  - num: 19
    slug: 19-gans
    title: GANs
    summary: The generator–discriminator game, why training destabilises, mode collapse, Wasserstein and
      conditional variants, and StyleGAN.
    tags:
    - Adversarial
    - WGAN
    - StyleGAN
  - num: 20
    slug: 20-diffusion-models
    title: Diffusion Models
    summary: Forward and reverse diffusion, DDPM and DDIM sampling, score matching, classifier-free guidance,
      and latent diffusion.
    tags:
    - DDPM
    - Score Matching
    - Latent Diffusion
    soon: true
- id: advanced-topics
  name: Advanced Topics
  blurb: Four open research threads, each pointing at something we still don't fully understand about
    these models.
  detached: true
  lectures:
  - num: 14
    slug: 14-causality-for-llms
    title: Causality for LLMs
    summary: Interventions and counterfactuals, structural causal models, and what causal structure a
      language model does or doesn't learn.
    tags:
    - Interventions
    - Counterfactuals
    - SCM
  - num: 15
    slug: 15-superposition
    title: Superposition
    summary: How a network stores more features than it has neurons, why that makes single units polysemantic,
      and how sparse autoencoders pull them apart.
    tags:
    - Polysemanticity
    - Sparse Autoencoders
    - Interpretability
  - num: 16
    slug: 16-prompt-repetition
    title: Prompt Repetition
    summary: What repeating content in the context window does to attention and to model behaviour, and
      where it helps or hurts.
    tags:
    - Prompting
    - Context
    - Attention
  - num: 17
    slug: 17-world-model
    title: World Model
    summary: Learned latent dynamics, prediction in representation space rather than pixel space, and
      using a learned model to plan.
    tags:
    - JEPA
    - Latent Dynamics
    - Planning
---

{%- assign lectures = "" | split: "" -%}
{%- for part in page.parts -%}{%- assign lectures = lectures | concat: part.lectures -%}{%- endfor -%}
{%- assign total = lectures | size -%}
{%- assign ready = 0 -%}
{%- for lec in lectures -%}{%- unless lec.soon -%}{%- assign ready = ready | plus: 1 -%}{%- endunless -%}{%- endfor -%}
{%- assign named_parts = 0 -%}
{%- for part in page.parts -%}{%- if part.name -%}{%- assign named_parts = named_parts | plus: 1 -%}{%- endif -%}{%- endfor -%}


<style>
/* ===== Deep Learning course page ==========================================
   Colours come entirely from al-folio's theme tokens, so light/dark mode
   and any accent change you make in _sass/_themes.scss are picked up free.
   ========================================================================= */
.dl {
  --dl-mono: ui-monospace, SFMono-Regular, "SF Mono", Menlo, Consolas, "Liberation Mono", monospace;
  --dl-rail: var(--global-divider-color);
  --dl-rail: color-mix(in srgb, var(--global-theme-color) 25%, transparent);
  --dl-tint: rgba(128, 128, 128, 0.08);
  --dl-tint: color-mix(in srgb, var(--global-theme-color) 9%, transparent);
  --dl-tint-strong: rgba(128, 128, 128, 0.16);
  --dl-tint-strong: color-mix(in srgb, var(--global-theme-color) 16%, transparent);
  margin-top: 1.5rem;
}

/* --- intro ------------------------------------------------------------- */
.dl-lede { font-size: 1.05rem; line-height: 1.65; margin-bottom: 1rem; }
.dl-meta {
  font-family: var(--dl-mono); font-size: 0.78rem; letter-spacing: 0.02em;
  color: var(--global-text-color-light); margin-bottom: 2rem;
}
.dl-meta b { color: var(--global-theme-color); font-weight: 600; }

/* --- toolbar: search + jump links -------------------------------------- */
.dl-toolbar {
  display: flex; flex-wrap: wrap; align-items: center; gap: 0.5rem;
  padding-bottom: 1.75rem;
}
.dl-search {
  flex: 1 1 13rem; min-width: 0;
  font-family: inherit; font-size: 0.9rem;
  padding: 0.5rem 0.75rem;
  color: var(--global-text-color);
  background: var(--global-bg-color);
  border: 1px solid var(--global-divider-color);
  border-radius: 7px;
  transition: border-color 0.15s ease;
}
.dl-search::placeholder { color: var(--global-text-color-light); }
.dl-search:focus { outline: none; border-color: var(--global-theme-color); }
.dl-search:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: 1px; }
.dl .dl-jump {
  font-family: var(--dl-mono); font-size: 0.72rem; letter-spacing: 0.03em;
  padding: 0.4rem 0.6rem; border-radius: 6px;
  color: var(--global-text-color-light);
  background: var(--dl-tint);
  border: 1px solid transparent;
  text-decoration: none; white-space: nowrap;
  transition: color 0.15s ease, border-color 0.15s ease;
}
.dl .dl-jump:hover, .dl .dl-jump:focus-visible {
  color: var(--global-theme-color); border-color: var(--dl-rail); text-decoration: none;
}

/* --- the syllabus rail -------------------------------------------------- */
.dl-part {
  position: relative;
  border-left: 1px solid var(--dl-rail);
  padding-left: 1.75rem;
  padding-top: 0.35rem;
  padding-bottom: 2.5rem;
  scroll-margin-top: 5rem;
}
.dl-part:last-of-type { padding-bottom: 0.5rem; }

/* A section with no heading is just a run of the sequence: no node, tighter. */
.dl-part--plain { padding-top: 0; padding-bottom: 1.5rem; }

/* Flat mode: one named group among plain runs, so give it enough weight to
   read as a deliberate block on the rail rather than an accident. */
.dl--flat .dl-part--marked {
  background: var(--dl-tint);
  border-left-color: var(--global-theme-color);
  border-radius: 0 10px 10px 0;
  padding-top: 1.5rem; padding-right: 1.25rem; padding-bottom: 1.75rem;
}
/* Breathing room after the block. Padding, not margin — a margin here would
   cut a gap in the rail, since the rail is the section's own left border. */
.dl--flat .dl-part--marked + .dl-part--plain { padding-top: 1.75rem; }

/* In flat mode the plain runs carry no headings, so there are no nodes for the
   rail to hold. A bare line with nothing on it is decoration, not structure —
   drop it and let the cards use the full width. */
.dl--flat .dl-part--plain { border-left: 0; padding-left: 0; }

/* A named group sitting outside the numbered run comes off the rail entirely
   and is fenced off with a rule, so it reads as an appendix rather than as the
   next step in the sequence. */
.dl .dl-part.dl-part--detached {
  border-left: 0; padding-left: 0; padding-right: 0;
  background: none; border-radius: 0;
  margin-top: 2.5rem; padding-top: 2.25rem;
  border-top: 1px solid var(--global-divider-color);
}
.dl .dl-part.dl-part--detached .dl-part-head::before { display: none; }
.dl .dl-part.dl-part--detached .dl-part-name { font-size: 1.5rem; }
.dl--flat .dl-part--marked .dl-part-head::before { width: 11px; height: 11px; top: 0.45rem; }

.dl-part-head { position: relative; margin-bottom: 1.4rem; }
.dl-part-head::before {           /* node sitting on the rail */
  content: ""; position: absolute;
  left: calc(-1.75rem - 5px); top: 0.5rem;
  width: 9px; height: 9px; border-radius: 50%;
  background: var(--global-bg-color);
  border: 2px solid var(--global-theme-color);
}
.dl-part-label {
  display: block; font-family: var(--dl-mono);
  font-size: 0.7rem; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase;
  color: var(--global-theme-color); margin-bottom: 0.3rem;
}
.dl-part-name { font-size: 1.3rem; font-weight: 600; line-height: 1.3; margin: 0 0 0.35rem; }
.dl-part-blurb { font-size: 0.9rem; line-height: 1.55; color: var(--global-text-color-light); margin: 0; max-width: 46ch; }

/* --- lecture grid ------------------------------------------------------- */
.dl-grid { display: grid; gap: 1.1rem; grid-template-columns: repeat(auto-fill, minmax(15rem, 1fr)); }

.dl a.dl-card, .dl .dl-card {
  display: flex; flex-direction: column;
  background: var(--global-card-bg-color);
  border: 1px solid var(--global-divider-color);
  border-radius: 10px; overflow: hidden;
  color: var(--global-text-color); text-decoration: none;
  transition: transform 0.18s ease, border-color 0.18s ease, box-shadow 0.18s ease;
}
.dl a.dl-card:hover, .dl a.dl-card:focus-visible {
  transform: translateY(-3px);
  border-color: var(--global-theme-color);
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.09);
  text-decoration: none; color: var(--global-text-color);
}
.dl a.dl-card:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: 2px; }
.dl .dl-card--soon { border-style: dashed; }

/* --- thumbnail (first slide of the deck) -------------------------------- */
.dl-thumb {
  position: relative; aspect-ratio: 16 / 9;
  background: var(--dl-tint);
  /* Deliberately stronger than the card border: a white title slide sitting on a
     white card needs the panel edge to read, or the thumbnail looks like a gap. */
  border-bottom: 1px solid rgba(128, 128, 128, 0.35);
  border-bottom-color: color-mix(in srgb, var(--global-text-color) 18%, transparent);
  overflow: hidden;
}
.dl-thumb img { width: 100%; height: 100%; object-fit: cover; display: block; transition: transform 0.35s ease; }
.dl a.dl-card:hover .dl-thumb img { transform: scale(1.035); }

/* shown when no thumbnail file exists yet — keeps the grid looking intentional */
.dl-thumb.is-blank { display: grid; place-items: center; }
.dl-thumb.is-blank::after {
  content: attr(data-num);
  font-family: var(--dl-mono); font-size: 2.4rem; font-weight: 600;
  color: var(--dl-tint-strong);
}

.dl-num {
  position: absolute; top: 0.5rem; left: 0.5rem; z-index: 1;
  font-family: var(--dl-mono); font-size: 0.68rem; font-weight: 600; letter-spacing: 0.05em;
  padding: 0.2rem 0.4rem; border-radius: 5px;
  color: #fff; background: rgba(0, 0, 0, 0.62);
  -webkit-backdrop-filter: blur(3px); backdrop-filter: blur(3px);
}

/* --- card body ---------------------------------------------------------- */
.dl-body { display: flex; flex-direction: column; flex: 1; padding: 0.9rem 1rem 1rem; }
.dl-title { font-size: 1rem; font-weight: 600; line-height: 1.35; margin: 0 0 0.4rem; }
.dl-summary { font-size: 0.845rem; line-height: 1.55; color: var(--global-text-color-light); margin: 0 0 0.85rem; }

.dl-tags { display: flex; flex-wrap: wrap; gap: 0.3rem; margin-bottom: 0.9rem; }
.dl-tag {
  font-family: var(--dl-mono); font-size: 0.66rem; letter-spacing: 0.02em;
  padding: 0.15rem 0.4rem; border-radius: 4px;
  background: var(--dl-tint); color: var(--global-text-color-light);
}

.dl-action {
  margin-top: auto; display: flex; align-items: center; gap: 0.35rem;
  font-family: var(--dl-mono); font-size: 0.72rem; font-weight: 600; letter-spacing: 0.04em;
  color: var(--global-theme-color);
}
.dl-action svg { width: 0.85em; height: 0.85em; flex: none; }
.dl-action--soon { color: var(--global-text-color-light); font-weight: 500; }

/* --- filtering ---------------------------------------------------------- */
.dl [hidden] { display: none !important; }
.dl-noresults {
  font-size: 0.9rem; color: var(--global-text-color-light);
  padding: 1.5rem 0 0.5rem; border-top: 1px solid var(--global-divider-color);
}

/* Closing band. The image carries baked-in text that gets small on a phone and
   is invisible to a screen reader, so the caption below restates the point in
   real text rather than leaving the picture to say it alone. */
.dl-collage { margin-top: 3rem; padding-top: 2.25rem; border-top: 1px solid var(--global-divider-color); }
.dl-collage-head {
  font-family: var(--dl-mono); font-size: 0.7rem; font-weight: 600;
  letter-spacing: 0.12em; text-transform: uppercase;
  color: var(--global-theme-color); margin: 0 0 0.85rem;
}
.dl-collage img {
  display: block; width: 100%; height: auto;
  border-radius: 10px; border: 1px solid var(--global-divider-color);
}
.dl-collage-cap {
  font-size: 0.88rem; line-height: 1.6; color: var(--global-text-color-light);
  margin: 0.85rem 0 0; max-width: 68ch;
}
/* The collage has a white background, which reads as a glaring slab against the
   dark theme. A light dim settles it without washing out anyone's face. */
html[data-theme="dark"] .dl-collage img { filter: brightness(0.86); }

.dl-foot {
  margin-top: 2.5rem; padding-top: 1.25rem;
  border-top: 1px solid var(--global-divider-color);
  font-size: 0.85rem; line-height: 1.6; color: var(--global-text-color-light);
}

@media (max-width: 576px) {
  .dl-search { flex-basis: 100%; }   /* chips get their own row instead of orphaning one */
  .dl-part { padding-left: 1.15rem; padding-bottom: 2rem; }
  .dl-part-head::before { left: calc(-1.15rem - 5px); }
  .dl-grid { grid-template-columns: 1fr; }
  .dl-part-name { font-size: 1.15rem; }
}

@media (prefers-reduced-motion: reduce) {
  .dl a.dl-card, .dl .dl-thumb img, .dl .dl-jump, .dl-search { transition: none; }
  .dl a.dl-card:hover { transform: none; }
  .dl a.dl-card:hover .dl-thumb img { transform: none; }
}

@media print {
  .dl-toolbar { display: none; }
  .dl a.dl-card { break-inside: avoid; }
}
</style>

<div class="dl{% if page.flat %} dl--flat{% endif %}">

<p class="dl-lede">{{ total }} lectures that start from a single artificial neuron and end at the systems behind today's language, vision and generative models. Each card links straight to that lecture's slide deck as a PDF, and the picture on it is the deck's own title slide.</p>

<p class="dl-meta"><b>{{ total }}</b> lectures &nbsp;·&nbsp; {% if named_parts > 1 %}<b>{{ named_parts }}</b> parts &nbsp;·&nbsp; {% endif %}<b>{{ ready }}</b> decks online</p>

<div class="dl-toolbar">
<input class="dl-search" id="dl-search" type="search" aria-label="Filter lectures by topic" placeholder="Filter by topic — try “attention”, “LoRA”, “diffusion”" autocomplete="off">
{%- for part in page.parts %}{% if part.name %}
<a class="dl-jump" href="#{{ part.id }}">{{ part.label | default: part.name }}</a>
{%- endif %}{%- endfor %}
</div>

{%- for part in page.parts %}
<section class="dl-part {% if part.name %}dl-part--marked{% else %}dl-part--plain{% endif %}{% if part.detached %} dl-part--detached{% endif %}" id="{{ part.id }}">
{%- if part.name %}
<header class="dl-part-head">
<span class="dl-part-label">{% if part.label %}{{ part.label }} &nbsp;·&nbsp; {% endif %}Lectures {{ part.lectures | map: 'num' | first }}–{{ part.lectures | map: 'num' | last }}</span>
<h2 class="dl-part-name">{{ part.name }}</h2>
{%- if part.blurb %}
<p class="dl-part-blurb">{{ part.blurb }}</p>
{%- endif %}
</header>
{%- endif %}
<div class="dl-grid">
{%- for lec in part.lectures %}
{%- assign padded = lec.num | prepend: '0' | slice: -2, 2 -%}
{%- capture haystack %}{{ lec.title }} {{ lec.summary }} {{ lec.tags | join: ' ' }} {{ part.name }}{% endcapture -%}
{%- if lec.soon %}
<div class="dl-card dl-card--soon" data-q="{{ haystack | strip_newlines | downcase | escape }}">
<div class="dl-thumb is-blank" data-num="{{ padded }}"><span class="dl-num">{{ padded }}</span></div>
<div class="dl-body">
<h3 class="dl-title">{{ lec.title }}</h3>
<p class="dl-summary">{{ lec.summary }}</p>
<div class="dl-tags">{% for tag in lec.tags %}<span class="dl-tag">{{ tag }}</span>{% endfor %}</div>
<span class="dl-action dl-action--soon">In preparation</span>
</div>
</div>
{%- else %}
<a class="dl-card" href="{{ page.pdf_dir | append: '/' | append: lec.slug | append: '.pdf' | relative_url }}" data-q="{{ haystack | strip_newlines | downcase | escape }}">
<div class="dl-thumb" data-num="{{ padded }}">
<span class="dl-num">{{ padded }}</span>
<img src="{{ page.img_dir | append: '/' | append: lec.slug | append: '.webp' | relative_url }}" alt="Title slide of the {{ lec.title }} lecture" loading="lazy" decoding="async" width="1000" height="562" onerror="this.parentNode.classList.add('is-blank');this.remove();">
</div>
<div class="dl-body">
<h3 class="dl-title">{{ lec.title }}</h3>
<p class="dl-summary">{{ lec.summary }}</p>
<div class="dl-tags">{% for tag in lec.tags %}<span class="dl-tag">{{ tag }}</span>{% endfor %}</div>
<span class="dl-action">Slides, PDF <svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M8 2v9M4.5 7.5 8 11l3.5-3.5M2.5 13.5h11"/></svg></span>
</div>
</a>
{%- endif %}
{%- endfor %}
</div>
</section>
{%- endfor %}

<p class="dl-noresults" id="dl-noresults" hidden>No lecture matches that. <button type="button" id="dl-clear" style="background:none;border:0;padding:0;color:var(--global-theme-color);cursor:pointer;font:inherit;text-decoration:underline;">Clear the filter</button></p>

{%- if page.collage %}
<section class="dl-collage">
{%- if page.collage.heading %}
<h2 class="dl-collage-head">{{ page.collage.heading }}</h2>
{%- endif %}
<img src="{{ page.collage.src | relative_url }}" alt="{{ page.collage.alt }}" loading="lazy" decoding="async">
{%- if page.collage.caption %}
<p class="dl-collage-cap">{{ page.collage.caption }}{% if page.collage.link %} <a href="{{ page.collage.link | relative_url }}">{{ page.collage.link_text | default: 'More' }}</a>.{% endif %}</p>
{%- endif %}
</section>
{%- endif %}

<p class="dl-foot">Slides are shared for the students of this course and anyone else who finds them useful. If you spot a mistake or would like the source files, {% if site.email %}please <a href="mailto:{{ site.email }}">get in touch</a>{% else %}please get in touch{% endif %}.</p>

</div>

<script>
(function () {
  var input = document.getElementById('dl-search');
  if (!input) return;
  var cards = Array.prototype.slice.call(document.querySelectorAll('.dl .dl-card'));
  var parts = Array.prototype.slice.call(document.querySelectorAll('.dl .dl-part'));
  var empty = document.getElementById('dl-noresults');
  var clear = document.getElementById('dl-clear');

  function apply() {
    var q = input.value.trim().toLowerCase();
    var hits = 0;
    cards.forEach(function (card) {
      var match = !q || card.getAttribute('data-q').indexOf(q) !== -1;
      card.hidden = !match;
      if (match) hits++;
    });
    parts.forEach(function (part) {
      part.hidden = !part.querySelector('.dl-card:not([hidden])');
    });
    empty.hidden = hits !== 0;
  }

  input.addEventListener('input', apply);
  input.addEventListener('keydown', function (e) {
    if (e.key === 'Escape') { input.value = ''; apply(); }
  });
  if (clear) clear.addEventListener('click', function () { input.value = ''; apply(); input.focus(); });
})();
</script>

