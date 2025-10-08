---
title: "Research"
permalink: /research/
---

My work explores state-space models, information-theoretic cues, and vision–language alignment for detecting and localizing AI-generated local forgeries (copy-move, splicing, removal).

### Current themes
- **Information-theoretic fingerprints** for generative edits (diffusion/GAN).
- **State-space models (Mamba/SSM)** for long-range spatial reasoning in biomedical images.
- **Vision–language fusion** for modality-aware detection.

{% capture cardgrid %}
- title: InForcer
  text: Information-theoretic gradient fingerprints for generative local edits.
  link: /projects/inforcer/
- title: ForenSim
  text: Attention-based state-space model for copy-move & splicing.
  link: /projects/forensim/
- title: IntegScan
  text: VLM-guided biomedical forgery localization with SSM fusion.
  link: /projects/integscan/
- title: Rescind Dataset
  text: VLM-guided biomedical forgery datasets (EDD, IDD, CSTD).
  link: /projects/rescind/
{% endcapture %}

{% include feature_row id="research-cards" type="left" %}

{% assign items = cardgrid | split: "\n" %}
<ul>
{% for line in items %}
  {% if line contains "title:" %}
    {% assign t = line | remove: "- title: " %}
    {% assign next = forloop.index0 | plus: 1 %}
    {% assign text = items[next] | remove: "  text: " %}
    {% assign next2 = next | plus: 1 %}
    {% assign link = items[next2] | remove: "  link: " %}
    <li><strong><a href="{{ link }}">{{ t }}</a></strong> — {{ text }}</li>
  {% endif %}
{% endfor %}
</ul>
